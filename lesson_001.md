# Lesson 1: Data Types and Operators

## Contents
1. Data Types
    1. Introduction
        1. [What is a type](#what-is-a-type)
        1. [Why are types important](#why-are-types-important)
        1. [What is a primitive type](#what-is-a-primitive-type)
    1. JavaScript Primitive Types
        1. [number](#number)
        1. [string](#string)
        1. [boolean](#boolean)
        1. [undefined and null](#undefined-and-null)
1. Operators
    1. Numbers
        1. [Basic arithmetic](#basic-arithmetic)
        1. [Mod, aka %](#mod-aka-)
    1. Strings
        1. [Concatenation, aka +](#concatenation-aka-)
        1. [length](#length)
        1. [Character-at-index, aka [n]](#character-at-index-aka-n)
    1. Booleans
        1. [not, aka !](#not-aka-)
        1. [and, aka &&](#and-aka-)
        1. [or, aka ||](#or-aka-)
        1. [Combining boolean operators](#combining-boolean-operators)

## Data Types

### Introduction

#### What is a type

Programmming can be boiled down to one concept: Doing things with data. Data
can be categorized by how it looks and how it behaves. For instance, a
combination of digits would be categorized as a number, or an arbitrary day,
month and year would be categorized as a date. A category of data that looks and
behaves in a common way is referred to as a **type**.

#### Why are types important

Different forms of data behave in different ways. For example, several numbers
can be added together resulting in yet another number, or two dates can be
compared to determine which comes first. The things you can do with a piece of
data are determined by the type of that data. There are very clear ways for one
number to interact with another number, because those two pieces of data are of
the same type. By contrast, if you are given a number and a date, there's not
much you can do to make them interact with each other because they are different
types of data.

#### What is a primitive type

The term data usually refers to large groupings of things, such as a spreadsheet
or a list of tweets. While these groupings may be data types in and of
themselves, they're really composed of several different smaller datatypes. A
calendar is made up of dates, a bank statement is made up of charges, each of
which is a date and a number. The smallest units of data (dates, numbers, etc.)
are referred to as **primitive types**.

### JavaScript Primitive Types

#### number

A number is represented plainly as the value itself.
```
13;
```

A `-` sign directly in front of a number denotes a negative number.
```
-13;
```

In JavaScript, whole numbers and decimals are of the same number type. In other
languages, decimals (sometimes called _floats_ or _floating point numbers_) are
explicitly different types. In JavaScript, decimals are crazy and inaccurate.
You should avoid working with decimals if at all possible. If not, it is
recommended you use a [library](https://github.com/MikeMcl/big.js/).
```
1.3;
```

JavaScript can also recognize with bases other than decimal: binary, octal, and
hexadecimal. A non-decimal number should start with a zero, followed by a letter
denoting the base, (b for binary, o for octal, x for hexadecimal), followed by
the number itself. If a number starts with 0 and no letter is provided to denote
its base, JavaScript will assume the number is in octal.
```
0b1101;
0o15;
015;
0xd;
```

[Read more about numbers at MDN.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

#### string

A grouping of one or more letters, surrounded by quotes, is referred to in
programming as a **string**. A string can be made up of any combination of
letters, spaces, and punctuation marks.
```
"Hello, 日本!";
```

A single letter, space, or punctuation mark is commonly referred to as a
**character**. Some programming languages treat characters as a different type
than strings, but in JavaScript, all characters are strings.
```
"a";
```

Some characters have special meanings to computers, and can only be represented
by what is called an **escape sequence**. In JavaScript, this usually means
placing a frontslash in front of the character. Note that the frontslash itself
is one such special character, thus the JavaScript string representation of
a frontslash is actually two frontslashes!
```
"\\\"\t";
```

In some JavaScript code, you may see a string represented with single-quotes.
Elsewhere, it may use double-quotes. Either type of quote will still represent
the same kind of string. Which type of quote is used is entirely up to the
person or people writing the code, but a string must end with the same type of
quotation mark that it began with. One thing of note is that within a string,
you cannot use the type of quote that defined the string unless it is preceded
by a frontslash.
```
"this string is the same as the other string";
'this string is the same as the other string';
'What\'s going on in here?';
'I said, "Hey!"';
"And then I was all \"Pay attention to me!\"";
```

In JavaScript, strings must begin and end on the same line. If the string
contains a line break, you can use the special new line character `\n`.
```
'Hey, there.\nLook at you, on your fancy second line!';
```

[Read more about strings at MDN.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

#### boolean

On the surface, booleans are very simple. There are only two possible boolean
values: `true` and `false`. They are represented in JavaScript as their names,
all lower-case and unaccompanied by quotation marks.
```
true;
false;
```

While programming, boolean values come in handy when we are comparing things.
They can be thought of as 'yes' and 'no'. When you ask a computer if two numbers
are equal, or if one string is longer than another, the computer will output
either `true` or `false`. You can then take the answer and act one way if it's
`true` and another for `false`. While you may not see these two explicit values
very often, the concepts of truth and falsehood are the bread and butter of
programming.

#### undefined and null

JavaScript has two different ways to represent the absence of data. These two
types will be further explained later.
```
undefined;
null;
```

## Operators

### Numbers

#### Basic Arithmetic

Math in JavaScript is very similar to what you were taught in elementary school.
The four most basic mathematical operations look as you might expect.
```
10 + 3;
16 - 3;
13 * 2;
26 / 2;
```

Multiple arithmetic operators can be used in one line for more complicated
mathematical expressions, and operators can be mixed and matched at will.
```
10 + 2 + 1;
16 - 4 + 1;
3 * 5 - 4 + 2;
36 / 2 - 11 + 2 * 3;
```

Parenthesis can be used when managed the order of operations. Just like in the
real world, JavaScript follows PEMDAS: Parentheses, Multiply and Divide, Add and
Subtract, from left to right... But without the E, because there is no exponent
operator.
```
36 / (2 * 3 - 3) + 1;
(24 + 2) / (5 - 3);
```

The `-` symbol can be used to denote either negativity or subtraction.
```
( -(1 + 2) * 12 + 10) / -2;
```

As mentioned previously, decimals in JavaScript are crazy and inaccurate. This
will become quickly apparent when attempting arithmetic with decimals.
```
1.1 + .1;
```

#### Mod, aka %

When performing division, sometimes you may only be interested in the remainder.
Most programming languages offer an operator that will give you the remainder of
division, called **modulo** or mod for short. This operation is usually
represented by the `%` symbol.
```
13 % 3;
```

One common operation in programming is to determine whether a number is odd or
even. The modulo operator makes this easy.
```
9 % 2;
4 % 2;
```

### Strings

#### Concatenation, aka +

While you can't perform arithmetic with strings, adding two strings together,
also known as **concatenation** or concat, is easy.
```
'Hello,' + " " + 'world!';
```

#### length

When working with a string whose contents are unknown, one of the most useful
pieces of information you can obtain about that string is how long it is, i.e.
the number of characters that make up the string.
```
'Dudeladmanguy'.length;
```

When a string contains a character that requires an escape sequence, it is
important to note that the preceding `\` character that you must use when
defining the string is not counted towards the string's length.
```
'length is \'14\''.length;
```

If you are concatenating two strings and want to get the length of the resulting
string, simply wrap the concatenation in parentheses, and place the `.length`
portion of the statement after the ending parenthesis.
```
('yo' + ' ' + 'dawg!').length;
```

#### Character-at-Index, aka [n]

When given a user-generated string, it is common to want more information about
the string. For instance, you may want your program to behave differently based
on the first letter of the user input. It is very east to inspect the first, or
any item, in the string. To get a letter at a position, place the number of the
position within square brackets after the string. A position number is commonly
referred to as an index.
```
'Hello, world!'[2];
```

If you try to evaluate the above statement in a JavaScript console, you might be
surprised to see that the result is `l` and not `e`! This is because JavaScript
is *zero-indexed*. When a language is zero-indexed, counting positions in
strings will start with the first character at index 0. So, the second character
would be at index 1 and the third character will be at index 2, as above.
This is common across many programming languages, not just JavaScript.
```
'Zero is first!'[0];
```

Because JavaScript is zero-indexed, you must take care when trying to get the
last character in a string. Although the `length` operator will return the
number of characters in a string, the last character is actually at
`length - 1`.
```
'My string'.length;
'My string'[8];
```

JavaScript and many other programming languages will not behave well if you try
to find the character at an index that does not exist in the string. For
instance, your program will return `undefined` if you use a negative index, and
will also return `undefined` if the index is outside the length of the string.
```
'Nope!'[-1];
'Fail.'[13];
```

### Booleans

#### Not, aka !

The 'not' operator, represented by `!` and sometimes referred to as 'bang', will
return the opposite of the boolean it is used on. The opposite of `true` is
`false`, and the opposite of `false` is `true`.
```
!true;
!false;
```

#### And, aka &&

The 'and' operator, represented as `&&`, is a way to combine booleans, and if
they all individually evaluate to `true` the final result will be true.
```
true && true;
```

If any of the individual boolean portions evaluates to `false`, then the entire
statement will evaluate to `false`. In JavaScript and some other programming
languages, as soon as a `false` value is encountered, the program will not look
at any of the values to the right of the `false` value. This is commonly
referred to as **short circuiting**.
```
true && false;
false && true;
```

The `!` operator can be applied to any individual part of an '&&' combination.
It can also be applied to the combination itself by wrapping the combination in
parentheses and placing the `!` operator in front, in which case the result will
be the opposite of what the combination evaluated to.
```
true && !false;
!(true && !false);
!(false && true);
```

Like arithmetic operators, you can combine as many booleans as you want with
`&&`.
```
true && !false && true;
!false && (false && true) && !true;
```

#### Or, aka ||

While the `&&` operator will evaluate to `true` if _all_ of the individual parts
are true, the or operator, represented by `||`, will evaluate to `true` if _any
one_ of the individual parts evaluates to `true`.
```
true || !false;
false || true;
```

For the `||` operator to evaluate to `false`, _all_ of the individual boolean
components must each evaluate to `false`.
```
!true || false;
false || !true;
```

Similar to how `&&` will 'short circuit' as soon as a `false` value is
encountered, when the `||` operator encounters a `true` value, it will not
evaluate anything to the right of that value.
```
true || !true;
```

Also like `&&` operator, you can combine as many parts as you want with `||`.
```
true || !false || true;
```

#### Combining boolean operators

It is common to combine the `&&` and `||` operators in a single statement. If no
parentheses are used, the operators will start by evaluating all && statements
first, from left to right, followed by || statements again from left to right.
For example:
```
true || false && true && false;
```
We start by evaluating the left-most && statement, `false && true`, which
evaluates to `false` resulting in the following simplified expression:
```
true || false && false;
```
The next && statement is `false && false`, which evaluates to false, resulting
in the following simplified expression:
```
true || false;
```
Because the final combination, `true || false`, evaluates to `true`, the entire
set of operations will evaluate to `true`. The original statement could also be
rewritten with parentheses to make it more obvious how evaluation will occur:
```
true || ((false && true) && false);
```

Like with arithmetic, when a boolean combination is wrapped in parentheses, the
combination within parentheses will be evaluated before other combinations.
```
(!true || true) && (false || !false);
(false && true) || false || ((!true && true) || true);
```
