# Quad names

## Overview
There is a [vendor-agnostic](https://aplwiki.com/wiki/List_of_language_developers) article about [quad-names on the APL Wiki](https://aplwiki.com/wiki/Quad_name). This page is an overview focusing on application development with Dyalog.

See the Dyalog online documentation for:

- [a complete list of categorised system functions](http://help.dyalog.com/18.0/#Language/System%20Functions/Summary%20Tables/System%20Functions%20Categorised.htm)
- [a complete list of system variables](http://help.dyalog.com/18.0/#Language/System%20Functions/Summary%20Tables/System%20Variables.htm)

## System variables

System variables describe the state of the system.  
Some variables are <span class="svstc">static</span> and cannot change.  
Some variables are <span class="svdyn">dynamic</span> and can change without user intervention.  
The others can be <span class="svset">changed by the user</span>.

<style>
	.svstc{color: red;}
	.svdyn{color: orange;}
	.svset{color: blue;}
</style>

<table>
	<tr>
		<td class="svstc">⎕A</td>
		<td class="svdyn">⎕DM</td>
		<td class="svdyn">⎕DMX</td>
		<td class="svset">⎕PATH</td>
		<td class="svset">⎕SM</td>
	</tr>
	<tr>
		<td class="svset">⎕TRAP</td>
		<td class="svstc">⎕AN</td>
		<td class="svdyn">⎕EN</td>
		<td class="svset">⎕PP</td>
		<td class="svdyn">⎕STACK</td>
	</tr>
	<tr>
		<td class="svdyn">⎕TS</td>
		<td class="svdyn">⎕AV</td>
		<td class="svset">⎕FR</td>
		<td class="svset">⎕PW</td>
		<td class="svstc">⎕TC</td>
	</tr>
	<tr>
		<td class="svset">⎕USING</td>
		<td class="svset">⎕AVU</td>
		<td class="svset">⎕IO</td>
		<td class="svset">⎕RL</td>
		<td class="svdyn">⎕THIS</td>
	</tr>
	<tr>
		<td class="svdyn">⎕WA</td>
		<td class="svset">⎕CT</td>
		<td class="svdyn">⎕LC</td>
		<td class="svdyn">⎕RSI</td>
		<td class="svdyn">⎕TID</td>
	</tr>
	<tr>
		<td class="svset">⎕WSID</td>
		<td class="svstc">⎕D</td>
		<td class="svset">⎕LX</td>
		<td class="svdyn">⎕RTL</td>
		<td class="svdyn">⎕TNAME</td>
	</tr>
	<tr>
		<td class="svset">⎕WX</td>
		<td class="svset">⎕DCT</td>
		<td class="svset">⎕ML</td>
		<td class="svdyn">⎕SE</td>
		<td class="svdyn">⎕TNUMS</td>
	</tr>
	<tr>
		<td class="svdyn">⎕XSI</td>
		<td class="svset">⎕DIV</td>
		<td class="svstc">⎕NULL</td>
		<td class="svdyn">⎕SI</td>
		<td class="svdyn">⎕TPOOL</td>
	</tr>
</table>

Of course, the majority of the time you can refer to the [help system](../Help) to remind yourself exactly how each of these works. There are many system variables built up over the decades, many of which are kept mostly for backwards compatibility.

In the following table, the <span class="svimp">quad-names</span> you are <span class="svimp">most likely to come across</span> in existing code are highlighted in <span class="svimp">red</span>.

<style>
	.sv{color: black;}
	.svimp{color: red;}
</style>

<table id="sysvars">
	<tr>
		<td class="svimp">⎕A</td>
		<td class="sv">⎕DM</td>
		<td class="sv">⎕DMX</td>
		<td class="svimp">⎕PATH</td>
		<td class="sv">⎕SM</td>
	</tr>
	<tr>
		<td class="svimp">⎕TRAP</td>
		<td class="sv">⎕AN</td>
		<td class="sv">⎕EN</td>
		<td class="sv">⎕PP</td>
		<td class="sv">⎕STACK</td>
	</tr>
	<tr>
		<td class="svimp">⎕TS</td>
		<td class="sv">⎕AV</td>
		<td class="sv">⎕FR</td>
		<td class="sv">⎕PW</td>
		<td class="sv">⎕TC</td>
	</tr>
	<tr>
		<td class="sv">⎕USING</td>
		<td class="sv">⎕AVU</td>
		<td class="svimp">⎕IO</td>
		<td class="svimp">⎕RL</td>
		<td class="sv">⎕THIS</td>
	</tr>
	<tr>
		<td class="sv">⎕WA</td>
		<td class="svimp">⎕CT</td>
		<td class="svimp">⎕LC</td>
		<td class="sv">⎕RSI</td>
		<td class="sv">⎕TID</td>
	</tr>
	<tr>
		<td class="sv">⎕WSID</td>
		<td class="svimp">⎕D</td>
		<td class="svimp">⎕LX</td>
		<td class="sv">⎕RTL</td>
		<td class="sv">⎕TNAME</td>
	</tr>
	<tr>
		<td class="sv">⎕WX</td>
		<td class="sv">⎕DCT</td>
		<td class="svimp">⎕ML</td>
		<td class="svimp">⎕SE</td>
		<td class="sv">⎕TNUMS</td>
	</tr>
	<tr>
		<td class="sv">⎕XSI</td>
		<td class="svimp">⎕DIV</td>
		<td class="svimp">⎕NULL</td>
		<td class="sv">⎕SI</td>
		<td class="sv">⎕TPOOL</td>
	</tr>
</table>

### Constant
```APL
      ⎕A        ⍝ Upper-case alphabet
ABCDEFGHIJKLMNOPQRSTUVWXYZ
      ⎕D        ⍝ Digits 0-9
0123456789
      ⎕AN       ⍝ User's ID
dyalog
      ⎕NULL     ⍝ NULL constant
[Null]
      ⎕TC       ⍝ BackSpace, LineFeed, CarriageReturn 



      ⎕UCS⎕TC   ⍝ BackSpace, LineFeed, CarriageReturn 
8 10 13
```

### Dynamic
```APL
⎕AV     ⍝ List of APL characters
⎕DM     ⍝ Last error message
⎕DMX    ⍝ ⎕DM+⎕EN in a thread safe form
⎕EN     ⍝ Last error number
⎕RTL    ⍝ Response time limit
⎕SE     ⍝ The session object
⎕TS     ⍝ Current date/time
⎕THIS   ⍝ Current object
```

### Settable
```APL
⎕AVU   characters to use in ⎕AV
⎕CT    Comparison Tolerance
⎕DCT   Decimal Comparison Tolerance
⎕DIV   how to handle division by 0
⎕FR    float decimal system in use
⎕IO    index origin
⎕ML    Migration Level 
⎕LX    Latent eXpression
⎕PATH  where to find functions 
```

### Comparison tolerance

!!! Warning
	This subsection is likely to move

`⎕CT` comparison tolerance

`⎕DCT` decimal comparison tolerance

Of course, floating point arithmetic voids certain mathematical properties:

${{3}\over{5}} = 3 \times {{5}\over{9}} \div 5$

```APL
      ⎕CT←1e¯14   ⍝ Default comparison tolerance
      (1÷3)=3×(5÷9)÷5
1
      ⎕CT←0       ⍝ No comparison tolerance
      (1÷3)=3×(5÷9)÷5
0
```

```APL
	⎕CT←1E¯14
	1=1 + 10 * -⎕←⍳16
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 
0 0 0 0 0 0 0 0 0  0  0  0  0  1  1  1 
```
For exact comparisons set ⎕CT to 0, but beware:
```APL
      10=+/100⍴0.1
1
      ⎕CT←0
      10=+/100⍴0.1
0
      10-+/100⍴0.1
1.953992523E¯14
```

### Division control
```APL
      ⎕DIV←0   ⍝ Default
      3÷0
DOMAIN ERROR: Divide by zero
      3÷0
       ∧
      0÷0
1
      ⎕DIV←1
      3÷0
0
      0÷0
0
```

## System functions

### Comparison Tolerance
APL systems prefer to act like traditional arithmetic where possible. However, the base-2 (binary) representation used by computers is unable to represent certain decimal numbers precisely.

In traditional mathematical notation:

$1={6\over10}\times10\times{1\over6}$

```APL
      ⎕CT   ⍝ Default is 10*¯14
1E¯14
      1=(6÷10)×10×÷6
1
      ⎕CT←0
      1=(6÷10)×10×÷6
0
```

### Print Precision
The number of significant digits in the display of numeric output.
```APL
      ⎕PP←3
      ÷812
0.00123
≢'123'
3
      ⎕PP←17
      ÷812
0.0012315270935960591
≢'12315270935960591'
17
```

### Print Width

### Trap control

