# Performance
This course is intended to teach not only the symbols, syntax and system interactions of Dyalog APL, but also to try and teach you *the APL way*. This is a combination of array-oriented problem solving and deft ability to combine primitives to solve all manner of problems using computers.

There are some inherent benefits to APL, such as the fact that exploring with APL can often lead you to optimal solutions to particular types of problems. Not only this, but the terseness makes it very easy to play with different approaches to the same problem, usually to improve readability or performance.

Besides APL itself, however, there are particular techniques, considerations, and special optimisations within the Dyalog interpreter that you should be aware of in case you find a performance bottleneck in your application and are wondering how to solve it.

## Flat array techniques

### Peppery code

## Loop sometimes

## Rank in general

## Reduction in general

## Scan in general

## Idioms
APL idioms are short expressions to perform certain tasks. [APLcart](https://aplcart.info) is a comprehensive, searchable list of idioms. Some of these include slightly obscure but performant versions of particular tasks, especially those related to [partitioned functions]().

In Dyalog APL, there are also "idioms" which are specially recognised phrases, or combinations of characters, which are treated as individual tokens and executed with special code, rather than parsed symbol-by-symbol and executed function-at-a-time. These offer significant performance improvements for particular tasks, and are all listed:

- [latest](https://docs.dyalog.com/latest/CheatSheet%20-%20Idioms.pdf)
- [17.1](https://docs.dyalog.com/17.1/CheatSheet%20-%20Idioms.pdf)
- [12.1](https://help.dyalog.com/12.1/index.html?page=html%2Fidiom%20list.htm)