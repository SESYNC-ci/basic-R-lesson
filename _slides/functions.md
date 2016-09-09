---
---

## Creating functions

Writing functions to use multiple times within a project can prevent you from duplicating code. If you see blocks of similar lines of code through your project, those are usually candidates for being moved into functions.

## Anatomy of a function

Writing functions is also a great way to understand the terminology and workings of R. Like all programming languages, R has keywords that are reserved for import activities, like creating functions. Keywords are usually very intuitive, the one we need is `function`.


~~~r
function(...) {
    ...
	return(...)
}
~~~
{:.text-document title="lesson-1.R"}

Three components:

* __arguments__: control how you can call the function
* __body__: the code inside the function
* __return value__: controls what output the function gives

<!--split-->

We'll make a function to extract the first row and column of its argument, for which we can choose an arbitrary name:


~~~r
function(data) {
    result <- data[1, 1]
    return(result)
}
~~~

~~~
function(data) {
    result <- data[1, 1]
    return(result)
}
~~~
{:.text-document title="lesson-1.R"}

Note that `x` doesn't exist until we call the function, which gives the recipe for how `df` will be handled.

<!--split-->

Finally, we need to give the function a name so we can use it like we used `c()` and `seq()` above.


~~~r
first <- function(data) {
    result <- data[1, 1]
    return(result)
}
~~~
{:.text-document title="lesson-1.R"}


~~~r
first(df)
~~~
{:.input}

~~~
[1] middle
Levels: college < highschool < middle
~~~
{:.output}

<!--split-->

Question
: Can you explain the result of entering `first(counts)` into the console?

Answer
: {:.fragment} The function caused an error, which prompted the interpreter to print a helpful error message. Never ignore an error message.