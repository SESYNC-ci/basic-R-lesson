---
---

## Creating functions

Writing functions to use multiple times within a project can prevent you from duplicating code. If you see blocks of similar lines of code through your project, those are usually candidates for being moved into functions.

===

## Anatomy of a function

Writing functions is also a great way to understand the terminology and workings of R. Like all programming languages, R has keywords that are reserved for import activities, like creating functions. Keywords are usually very intuitive, the one we need is `function`.


~~~r
function(...) {
    ...
    return(...)
}
~~~
{:.text-document title="lesson-2.R"}

Three components:

* __arguments__: control how you can call the function
* __body__: the code inside the function
* __return value__: controls what output the function gives

===

We'll make a function to extract the first row and column of its argument, for which we can choose an arbitrary name:


~~~r
function(x) {
    result <- x[1, 1]
    return(result)
}
~~~
{:.text-document title="lesson-2.R"}

Note that `x` doesn't exist until we call the function, which gives the recipe for how `x` will be handled.

===

Finally, we need to give the function a name so we can use it like we used `c()` and `seq()` above.


~~~r
first <- function(x) {
    result <- x[1, 1]
    return(result)
}
~~~
{:.text-document title="lesson-2.R"}


~~~r
first(df)
~~~
{:.input}
~~~
[1] college
Levels: middle < highschool < college
~~~
{:.output}

===

Question
: Can you explain the result of entering `first(counts)` into the console?

Answer
: {:.fragment} The function caused an error, which prompted the interpreter to print a helpful error message. Never ignore an error message.

===

## Exercise 3

Subset the data frame by column name and row position to obtain the following output.

~~~
[1] highschool college
Levels: middle < highschool < college
~~~
{:.output}