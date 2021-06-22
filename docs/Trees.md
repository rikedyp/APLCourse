# Trees
> [Algorithms + Data Structures = Programs](https://en.wikipedia.org/wiki/Algorithms_%2B_Data_Structures_%3D_Programs)

Computer science is rife with complex theory and practice about data structures and algorithms. There is a wealth of knowledge designed to allow people who know about computers to engineer solutions for various different fields, and it gets quite complicated quite quickly.

We are a little more pragmatic. For us, there are 2 data types: numbers and characters, and 2 types of data structures: rectangles and trees. The rectangles are like the arrays we have been working with, with a shape defined by the lengths of zero or more orthogonal axes:
```APL
      2 2 3 4⍴⎕A
ABCD
EFGH
IJKL
    
MNOP
QRST
UVWX
    
    
YZAB
CDEF
GHIJ
    
KLMN
OPQR
STUV
```

Many people will recognise something like a spreadsheet, and a high dimensional array is akin to something like a workbook; a collection of sheets.

The trees are more like JSON format data.

*[JSON]: JavaScript Object Notation

## When to use what?
Contemporary computer science advocates learning about all kinds of data structures and algorithms, with the caveat best expressed by one of the lines in [The Zen of Python](https://www.python.org/dev/peps/pep-0020/):
> There should be one-- and preferably only one --obvious way to do it.

However, we have flipped the script and provide a small set of primitives, 2 data types and 1 data structure, all of which can be combined in myriad ways to solve all kinds of problems.

Of course, the interpreter itself is written in [C](https://en.wikipedia.org/wiki/C_(programming_language)) and uses many different data types and algorithms to carry out computations. But as an APLer we try not to think too hard about these things unless we really have to, usually for performance reasons.

In some sense, the philosophy of APL is exemplified by one of its most famous (or *infamous*) examples: [Conway's Game of Life](https://dfns.dyalog.com/n_life.htm). In the Game of Life, a few simple rules lead to a complex set of behaviours. The Game of Life is, in fact, turing complete and can be used to [model a computer which itself then plays the Game of Life](https://youtu.be/xP5-iIeKXE8).

## To do
- Nested arrays
- Namespaces
- PV Trees (Hsu)