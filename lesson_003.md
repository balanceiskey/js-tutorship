# Lesson 1: Functions

## Contents
1. [Functions Are Mini Programs](#functions-are-mini-programs)
1. [Function Definition](#function-definition)
    1. [The Function Keyword](#the-function-keyword)
    1. [The Function Identifier](#the-function-identifier)
    1. [Function Parameters](#function-parameters)
    1. [The Function Body](#the-function-body)
    1. [The Return Statement](#the-return-statement)
1. [Function Invocation](#function-invocation)
    1. [Function Arguments](#function-arguments)
1. [Homework](#homework)

## Functions Are Mini Programs

Think of a cooking recipe - baking cookies, for instance - as a program. Each
step in the recipe is analogous to one statement in a program. For instance,
mixing ingredients together would be one statement in a program, pre-heating the
oven would be another statement.

One of the first steps in making cookies is to make cookie dough. You could have
each step of making the dough in your main "making cookies" recipe, but the
steps for making cookie dough might differ depending on what kind of cookies
you're making. However, the rest of the recipe - pre-heat the oven, put gobs of
dough on a sheet, and put the sheets in the oven for a certain amount of time -
are generally the same regardless of what kind of cookies you're making.

So, let's instead assume that we have one general recipe for baking cookies that
has "make the dough" as a step, instead of listing out all the individual steps
of making a specific type of dough. The process of making the dough is a
separate recipe. This "separate recipe" is analogous to a function.

If a program is a recipe, and a function is also a recipe, aren't functions just
programs? Yes, in fact, you can think of a function as a mini-program. A small
program just consists of one function that is executed immediately. Bigger
programs will consist of many functions that can be called at separate times,
sometimes executing a function more than once, and sometimes executing one
function instead of another depending on the circumstances.

## Function Definition

Before you can use a function in your program, you must first create the
function. The portion of code that creates a function is called the
**function definition**.

Consider this example function:

```javascript
function add (x, y) {
    return x + y;
}
```

### The Function Keyword

The `function` keyword tells the computer that we're going to be creating a new
function. Unlike the `var` keyword, you must always use the function keyword
once per function.

### The Function Identifier

`addOne` is the function's **identifier**. As mentioned in Lesson 2, an
identifier is a name we can use to refer to a piece of data.

Function identifiers follow all the same rules as [variable identifiers](https://github.com/mseman/js-tutorship/blob/master/lesson_002.md#identifier-rules).

### Function Parameters

`(x, y)` is referred to as the function's **parameters**. Rather, `x` is one
parameter and `y` is a different parameter. Defining parameters is a way of
telling the computer "These are the inputs this function will use, and the
identifiers that will be used to refer to those inputs."

Like variables and functions themselves, parameters have identifiers. You can
think of a parameter as a variable that has already been defined somewhere else
in your program. The value that a parameter holds depends on what value was
passed during function invocation, which is discussed later in this lesson.

Parameter identifiers follow all the same rules as [variable identifiers](https://github.com/mseman/js-tutorship/blob/master/lesson_002.md#identifier-rules).

A function can have as many parameters, few parameters, just one parameter, or
no parameters. A function with no parameters will simply be defined with an open
parenthesis followed by a close parenthesis, with nothing (except whitespace)
between them.

```javascript
function two () {
    return 1 + 1;
}
```

A function with just one parameter will have an open parenthesis, followed by
the parameter's identifier, followed by a close parenthesis.

```javascript
function addOne (x) {
    return x + 1;
}
```

When a function has multiple parameters, there should be a comma between
parameters, but not before the first parameter and not after the last parameter.

```javascript
function add (x, y) {
    return x + y;
}

### The Function Body

The curly brackets, aka braces, surround what we call the **body** of the
function. When the function is executed, each line in the body is executed
until no more statements are left, or...

### The Return Statement

The `return x + y;` statement denotes the end of the function. The result of the
expression after `return` will be sent back to where the function was
**[invoked](#function-invocation)**. Any statements that are placed after the
return statement will not be executed by the program.

A return statement is not a hard requirement. If a function does not have a
return statement, it will simply run all the statements inside the function
until no more statements are left to run. When a program doesn't have a return
statement, the value sent back to where the function was invoked is `undefined`.

A program can have multiple return statements. However, only one of them can get
executed each time the function is called (because, as noted above, as soon as a
return statement is executed no other statements inside a function will be
executed). This will be more useful later on. For now, all of your functions
should have 0 or 1 return statements.

## Function Invocation

When you want to use a function that you have defined, you perform what's called
a **function invocation**. A function invocation looks like this:

```javascript
var sum = add(1, 3);
```

The actual invocation is the `add(1, 3)` portion of the statement. In this case
we're assigning the result of the function to the variable `x`. An invocation
requires the function identifier, followed by parentheses containing the
**arguments** you would like to pass to the function.

### Function Arguments

Any data that you would like to send to the function is referred to as an
**argument**. When we invoke add as `add(1, 3)` the arguments to the add
function are `1` and `3`.

Arguments can be of any type, and you can also use variables as arguments. The
following code will produce the same result as the previous example.

```javascript
var x = 1;
var y = 3;
var sum = add(x, y);
```

You can supply arguments to a function that expects no arguments without causing
an error. This should generally be avoided, however.

It is also possible to supply fewer arguments to a function than it expects. Any
parameters which were not supplied with values will then have their values set
to `undefined`.

