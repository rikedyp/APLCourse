# The Stack

## What is a stack?
A stack is a structure with two principle operations. You can **push** something onto the top of the stack, or you can **pop** something off of the top of the stack.

A simple APL model might be:

Our stack is a vector
```APL
      stack←⍬
```
To Push onto the stack, concatenate scalars
```APL
      stack,←⊂'hello'
      stack,←⊂'world'
```
To Read the top of the stack, index the last element
```APL
      (≢⌷⊢)stack
```
- To Pop from the stack, delete the last element
- No other operations are allowed

Some [programming languages are stack-based](https://en.wikipedia.org/wiki/List_of_programming_languages_by_type#Stack-based_languages). Examples include PostScript, Forth, and the Forth-based APL-like language [CoSy](http://cosy.com/).

## How to build the stack
Functions can call other functions:
```APL
    ∇  r←Recurse level                           
[1]   ⍝ Arguably the worst way to count backwards
[2]    r←level                                   
[3]    :If level>1                               
[4]        r,←Recurse level-1                    
[5]    :Else                                     
[6]        r←1                                   
[7]    :EndIf                                    
    ∇  
```
When a function is called, it goes to the top of 

## Name scope
The scope of a name describes the circumstances under which it is visible to code.
When a program is called, names in the calling environment are visible, unless explicitly localised in the header.

## Locals vs Globals
!!! Note
	Likely to be moved to the section on user defined functions, we'll see

In a TradFn, names are localized by putting them in the header, separated by semicolons.
In a d	fn names are automatically localized when a new name is assigned. (We will see our first dfn in a moment).

### Dfns

### Tradfns

### Avoid globals
When possible, avoid using global variables.
Pass parameters to functions as arguments unless this becomes very awkward.
The use of global variables should be limited to state settings that affect the entire application, or tables containing databases that are shared globally.
If you need global constants, it is a good idea to create them in a function in order to be able to use source code management / change tracking

In recent years, a new reason is emerging to avoid globals:
A function which uses globals is difficult, if not impossible, to run in parallel.
If two copies of the function run in parallel and they update the global data, some kind of locking is required.
Locking often defeats the potential benefits of parallel execution.

When one program calls another, APL maintains a stack to it can find its way back and continue execution when a called function completes
Local names only exist while the function they are local to is on the stack.
Names should be localized unless they really really, really, really need to be global

### When to use globals
Example, a switch which affects the entire application:
```APL
    ∇  err←Log msg                                  
[1]    :If verbose                                  
[2]        ⎕←msg   ⍝ Display information to the user
[3]    :EndIf                                       
[4]    PrintFile msg                                
    ∇   
```

