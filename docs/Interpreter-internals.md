# Interpreter Internals
Just some of the nitty-gritty under the covers.

## Storage
Memory allocated to store an array needs space for:

- Each element of the array (which could be a reference to another array)
- `8×≢⍴array` bytes for the shape (`4×` in 32-bit)
- 4 bytes for the type/rank

For a reference, the object requires an 8-byte pointer, plus space for the contents of the object.

## Data types
Internally, Dyalog represents data with the following types. As a program runs, occasionally the interpreter will squeeze arrays into the smallest data type that can represent a particular figure, which helps keep memory usage low and may allow the interpreter to use vectorised instructions for certain operations on certain data types.

!!! Warning "Version Warning"
	Some data types are only available in Dyalog Unicode Edition.

### Character
```
      ⎕DR'APL'           ⍝ 1-byte
80
      ⎕DR'配列'           ⍝ 2-byte
160
      ⎕DR⎕←⎕UCS 128077   ⍝ 4-byte
👍
320
```

### Number
```
      ⎕DR 1 0 1 0 1 0   ⍝ 1 bit
11
      ⎕DR 42            ⍝ 1 byte
83
      ⎕DR 128           ⍝ 2 byte
163
      ⎕DR 2*15          ⍝ 4 byte
323
      ⎕DR 0J1           ⍝ Complex (2×8 byte double)
1289
```

#### Comparison tolerance
APL systems prefer to act like traditional arithmetic where possible. However, the base-2 (binary) representation used by computers is unable to represent certain decimal numbers precisely. Therefore, floating point arithmetic voids certain mathematical properties:

${{1}\over{3}} = 3 \times {{5}\over{9}} \div 5$

```APL
      ⎕CT←1e¯14   ⍝ Default comparison tolerance
      (1÷3)=3×(5÷9)÷5
```
```
1
```
---
```APL
      ⎕CT←0       ⍝ No comparison tolerance
      (1÷3)=3×(5÷9)÷5
```
```
0
```
---
```APL
      ⎕CT←1E¯14
      1=1 + 10 * -⎕←⍳16
```
```
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 
0 0 0 0 0 0 0 0 0  0  0  0  0  1  1  1 
```

For exact comparisons set `⎕CT` to `0`, but beware:

```APL
      10=+/100⍴0.1
```
```
1
```
---
```APL
      ⎕CT←0
      10=+/100⍴0.1
```
```
0
```
---
```APL
      10-+/100⍴0.1
```
```
1.953992523E¯14
```

`⎕DCT` decimal comparison tolerance

### Value types
If more than one name points to the same array value:
```
      a←b←1 2 3 4
```
then there is a reference count internally, and only one copy of the data is stored in memory.

If one of those arrays is modified:
```
      b[2]←99
```
then a copy of the data is taken at that point so that other arrays are unaffected:
```
      a b
┌───────┬────────┐
│1 2 3 4│1 99 3 4│
└───────┴────────┘
```

For a nested array, however, the elements are separate.
```
      a←b←(1 2 3)(4 5)
```
if one of the elements is modified
```
      b[⊂2 1]←99
```
then the other elements remain shared between names. In this example, the `1 2 3` array remains shared.

### Reference types
While APL arrays are pass-by-value, namespaces and other objects are pass-by-reference.

```
      nsref←⎕NS⍬
      jsonref←⎕JSON'{}'
      ⎕FIX':Class myclass' ':Endclass'
      ⎕DR¨nsref jsonref myclass
326 326 326
```

Although namespaces are pass-by-reference, the references themselves are still values:
```
      (ns1 ns2)←⎕NS¨2⍴⊂⍬
      (ns1 ns2).var←42 99
      a←ns1
      a.var
42
      a←ns2
      a.var
99
```

## APL item hierarchy
This useful chart shows what operations are valid for different kinds of items.

![APL item hierarchy](../img/APL_Citizens.png)

## Floating-point representation
There are also 16-byte decimal floating point numbers available, but you need to enable them with `⎕FR`.

```
      ⎕PP←34
      ○1
3.141592653589793
      ⎕FR←645    ⍝ 64-bit float (default)
      ○1
3.141592653589793
      ⎕FR←1287   ⍝ 128-bit decimal
      ○1
3.141592653589793238462643383279503
```

## Comparison tolerance

```
      ⎕FR←645 ⋄ ⎕CT
1E¯14
      1⍳⍨⎕←1=1+10*-⍳20
0 0 0 0 0 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1
14
      ⎕FR←1287 ⋄ ⎕DCT
1E¯28
      20+1⍳⍨⎕←1=1+10*-20+⍳10
0 0 0 0 0 0 0 1 1 1
28
```

## Configuration parameters
Many aspects of the interpreter environment can be modified before runtime using [**configuration parameters**](https://help.dyalog.com/latest/index.htm#UserGuide/Installation%20and%20Configuration/Configuration%20Parameters.htm). The values of configuration parameters are determined by a hierarchy of scope on the operating system. On Microsoft Windows, these are often registry settings at the base level. On Unix-like systems, they are environment variables.

For example, we can set parameters on the command line in a batch file before starting Dyalog. We can even create custom parameters.

*Save the following as a .bat file and run it on Windows*

```text
@SET FOO=bar
@START "Dyalog" "C:\Program Files\Dyalog\Dyalog APL-64 18.0 Unicode\dyalog.exe"
```

See the value of a configuration parameter with `⎕NQ`:

```APL
      ⎕←2⎕NQ'.' 'GetEnvironment' 'FOO'
```
```
bar
```

You might find it useful to read the [Dyalog for Microsoft Windows Installation and Configuration Guide](http://docs.dyalog.com/17.1/Dyalog%20for%20Microsoft%20Windows%20Installation%20and%20Configuration%20Guide.pdf#%5B%7B%22num%22%3A22%2C%22gen%22%3A0%7D%2C%7B%22name%22%3A%22XYZ%22%7D%2C63%2C679.5%2C0%5D) and the [Dyalog for UNIX Installation and Configuration Guide](http://docs.dyalog.com/17.1/Dyalog%20for%20UNIX%20Installation%20and%20Configuration%20Guide.pdf#%5B%7B%22num%22%3A21%2C%22gen%22%3A0%7D%2C%7B%22name%22%3A%22XYZ%22%7D%2C63%2C541.5%2C0%5D).

Recent versions of Dyalog support universal [configuration files](https://help.dyalog.com/latest/index.htm#UserGuide/Installation%20and%20Configuration/Configuration%20Files.htm) which work across all supported platforms.

## What am I running?
What version of Dyalog am I running?

```APL
'.'⎕WG'APLVersion'
```

For error reports, get the BuildID:

```APL
⎕←2⎕NQ'.' 'GetBuildID'
```

Am I a Unicode interpreter?

```APL
80=⎕DR' '
```

Am I big endian?

```APL
⍬⍴83 ⎕DR 256
```

What is my word width?

```APL
{z←⍵ ⋄ 2×⍬⍴⎕SIZE'z'} ⍬
```
