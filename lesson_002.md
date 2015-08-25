# Lesson 2 - Variable Assignment

## Recap

As a quick reminder you should have a pretty decent understanding of the following:

### Primitives
* These are our legos. They’re the most basic building block of a program.
* There are different types of primitives. So far we know about `number`, `string` and `boolean`.
* We can do things to primitives with `operators`. Different primitive types can be combined with specific operators.

## Variable Intro

A variable is a way to provide a name for primitive so it can be referenced later in your program. If the name 'variable' sounds familiar, it should. It looks and acts a lot like mathematical variables (but with gotchas, so pay attention).

Here’s an example:

```javascript
var x = 1;
```

Let’s break this down into bits.

### `var`

Remember, JavaScript has special words reserved by the language called [keywords]. `var` is one of those keywords and we use it to ‘declare’ a variable.

### `x`

The `x` here is called an identifier. It’s the name you give to your variable. But it has some rules. We’ll go over those after we’ve reviewed the rest of the statement.

### `=`

The equal sign is how we `assign` a value to `x`.

### `1`

This is our value. It’s the thing we’re trying to store for use later.

### `;`

Don’t forget the semicolon!

### Put it together.

What we get is `var x = 1;`. Somewhat confusingly, you’ll often hear developers say this as `1 is assigned to x`.

## Variable Use

Anything you can do with a primitive using operators, you can do with a variable. Here’s an example:

```javascript
var x = 3;
x + 2; // 5
x * 2; // 6
x / 2; // 1.5
x - 2; // 1
x % 2; // 1
```

What about if it’s a string or boolean?

```javascript
var a = 'A string.';
a + ' With some other stuff.';
a.length;

var b = true;
!b; // false
b && b; // true
```

You can even combine variables with other variables:

```javascript
var a = 3;
var b = 4;

a + b; // 7
a - b; // -1
a * b; // 12
a / b; // 0.75
```

### Variable Reassignment


#### Basics

Things can get a little scary when we start reassigning variables, but fret not adventurer, we're here to help. Let's start with this:

```
var a = 1;
a = 2;
```

You'll notice something interesting here. When `a` is initially declared we use the `var` keyword. When it's assigned a second time we no longer need `var` since the variable has already been declared.

What is `a` now? 2.

```
a; // 2
```

We can continue in this way:

```
a = 3;
a = 'hello';
a = true;
```

What's `a` now? `true`.

#### Hairier

Okay, let's make things a little more interesting. What happens when one variable is assigned to another variable that's in turn assigned to a primitive? (IMPORTANT: We're talking strictly about primitives at the moment.)

```
var a = 1;
var b = a;
```

In this case, `1` is assigned to `a` and `a` is assigned to `b`.

If we change `a`...

```
a = 5;
```

What's `b`? In this case `b` remains `1`.

You can think of modifying variables in this case as splitting from a tree. Both `a` and `b` begin life associated with the value `1`. But once `a` takes on a new value `5`, `b` remains associated with `1`.

Again, it's worth emphasizing. This is 1/2 of how assignment works and it only applies to primitives. We'll talk later about what happens when we're not dealing with primitives.

## Variable Gotchas

Declaring a variable is relatively simple but it comes packed with some gotchas.

### Identifier Rules

While you have a lot of freedom in what you can call a variable there are some rules:

* An identifier can be compose of letters, numbers, underscores or dollar-signs.
* An identifier must start with a letter, underscore or dollar-sign.

All of these are valid:

```javascript
var a = 1;
var $ = 2;
var superMan = 'some string';
var cat5 = true;
var $someOtherThing = 'okay, you’re probably getting the picture';
var _oBnOx1i0us$_ = "Don’t do this. Just don’t.";
```

These are not valid:

```javascript
var 1 = 2;
var 1abc = false;
var & = 'sorry, nope';
```

### Right-to-left

There’s also one other declaration not allowed. You can’t do the following:

```javascript
var 12 = theNumberTwelve;
```

Assignment always happens right-to-left, so we’ll always see the keyword `var`, the identifier, the equal sign, the value and the semicolon in the same order. Remember also, when speaking about assignment developers will say, “<insert value> was assigned to <insert identifier>”.

### Scope.

We’re not going to talk about what scope is right now, but know that this…

```javascript
x = 1;
```

…is possible. Note the `var` keyword is nowhere to be seen. Don’t ever do this when declaring a variable. We will explain why at another time.
