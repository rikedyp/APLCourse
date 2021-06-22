# Array-oriented data structures
I hope you have begun to feel the freedom of a very dynamically typed language. Occasionally it's important to know the difference between `'1'` and `1`, but mostly it's nice to be fairly sure that numbers and numbers and characters are characters (except for that pesky [floating point arithmetic](../implementation#comparison-tolerance)).

## There are two data structures
The programming world is rife with special . It is also said that "algorithms + data structures = programs" as a broad answer to the question "what is programming?" in a similar way that "grammar + vocabulary = language". There are also countless tutorials about things called arrays, structs, dicts, linked lists, strings and many more data structures with specific algorithms written to suit specific types of problems with both reasonable computational efficiency and efficacy of expression.

APLers like to believe that it is a bit easier to just have a few types of things and to have a useful set of composable.

It is with this that I would like to posit that as there are really only 2 data types, there are also only 2 data structures.

### Rectangles
APL loves rectangles. Computers love rectangles. The rectangular, homogeneous (same type) array is the most efficient data type for storing and accessing data both linearly (`⎕A[3+⍳10]`) and randomly (`⎕A[1 4 22 4 6`).

### Trees

#### Nested vector
#### JSON object
#### Parent-depth vector
- ASCII graph
- Insert
- Delete
- Update
- Index / traverse


## How do I represent X?
Any way which you think is appropriate. Firstly choose a representation which you find easy to understand and to describe and explain to other people. If you are quite unlucky you might have chosen a representation on which your necessary computations are slow. If this is the case, there will be alternative representations which offer performance improvements. However, it is always best to consider readability and maintainability above all else. How long will it take your future self to recognise and remember the functions and structures you chose to use?

### Graph
A small directed graph might be well represented as a list of edges from one node to another:

- Undirected graph
- Directed graph
- Graph with loops


- Fast search boggle board?

###

