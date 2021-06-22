# Getting Help
Following this course should give you at least an overview of all of the aspects of Dyalog which are needed to solve problems and build applications. By the end, hopefully you'll start to feel comfortable solving problems, reading and writing APL, and at least have an idea of where to look when you need to do some systems programming or interfacing with the outside world.

To that end, here we list some of the resources available to you if you ever get stuck.

## What does this thing do?
If you need help with a particular primitive or quad-name, the [Dyalog online help](https://help.dyalog.com/latest/) can answer *what does this do?*-style questions. Press `F1` in the session while highlighting a construct to go to its help page.

```APL
      ⍣              ⍝ Primitives
      ⎕THIS          ⍝ Quad-names
      HTMLRenderer   ⍝ Some keywords relate to specific objects
```
Many of the keywords which have documentation pages are the names of [GUI objects](http://help.dyalog.com/latest/#GUI/SummaryTables/GUIOverview.htm).

It is also possible to set a custom URL to use for queries when the interpreter doesn't recognise something.

In the IDE for Microsoft Windows, go to Options → Configure → Help/DMX. Tick "Use online help for non-Dyalog topics" and set the custom URL of your choice. For example, you can try using `https://aplcart.info/?q=%s`, so that <kbd>F1</kbd> behaves like an alias to the `]APLcart` user command.

In the RIDE, <kbd>F1</kbd> opens a browser window to the [Dyalog online documentation](https://help.dyalog.com/latest).

- The [Documentation Centre]() 

## How do I do this?
This is a much more difficult thing to overcome. Sometimes you have an idea of what you want to achieve, but you either aren't sure what constructs are available to help you achieve it, or you aren't sure that the solution you've come up with is the best way to go about it.

- If you need help with *how to do something*, try searching in [APLcart](https://aplcart.info/), the searchable idiom<sup><a href="#1">\*</a></sup> library

We strongly recommend that you spend some time on a regular basis (maybe at least a few hours each month) reading and exploring the existing APL media. As a language with a rich history, there have been a huge number of conferences, published papers and presentations where users and implementors discuss their activities and achievements. 


## Talk to humans
- If you cannot find a solution on APLcart, please [ask on Stack Overflow](https://stackoverflow.com/questions/ask). There are a number of keep APLers who monitor this site and will eagerly answer any questions asked there.

### Your Resources
There are some places you can go to get help.




- Introduce yourself in [the APL Orchard](https://chat.stackexchange.com/rooms/52405/the-apl-orchard) Stack Exchange chat room, where you can usually get same-day replies to your queries.
- As well as Stack Overflow, the [Dyalog forums](https://forums.dyalog.com/) are full of interesting discussions and are quite active.
- [The APL Wiki](https://aplwiki.com/) has hundreds of articles about both the history of APL, as well as specific language features and usage examples.

<a id="1"></a><br>  
> \***Idioms**  
> an *idiom* in APL is a short phrase to perform some specific task. For example, here is how to [remove leading, trailing and duplicate spaces from a text vector](https://aplcart.info/?q=remove%20leading%20trailing%20blanks#). In Dyalog specifically, [some idioms](http://docs.dyalog.com/latest/CheatSheet%20-%20Idioms.pdf) are recognised by the interpreter and cause special code to be executed which is faster and uses less memory than if the the whole expression was interpreted primitive-by-primitive. In contrast to [idioms](https://en.wikipedia.org/wiki/Idiom) in natural language, which have a literal meaning different to their actual meaning, APL idioms say exactly what they do. I find it interesting that the phrase commonly used to demonstrate idioms in English, *raining cats and dogs*, is not very commonly used in speech anymore.