---
title: "Js for Modern Web Development"
date: 2020-07-23T11:52:24+05:30
Description: "JS For modern web development Part-1"
Tags: ["web development","HTML","Zero To Hero","Crash Course"]
Categories: []
DisableComments: false
---

# Introduction
Here we are at the end of the modern web development course, At the right basics of the language which make the web interactive and functional. JS Is the back-born of the modern Internet, Why do I say so? Because we can do literally Anything you imagine. Without further explanation, Let's start with the course. Before getting here, Please follow [HTML](/post/html-for-modern-web-development/) [CSS](/post/css-for-modern-web-development/) and [SCSS](/post/scss-for-modern-web-development/) guides.

# Hello, world!
Javascript is fully functional with HTML and CSS, so first, Let's create our demo document with HTML CSS And JS. I'm creating 3 files in the root folder. index.html, style.css, style.scss and index.js And linking the css in the head, and the JS in the bottom of the body. pro tip Always link your js in the end of the body tag, so the JS would be load after the HTML elements and you won't face any DOM issues regarding load time or so, I'll explain later and also you can link JS in head but I don't recommend it. Let's do it in the ways of modern web development.

Now, Javascript files can be linked using script element and using a src attribute. Now that out to the way

![Root](/uploads/20200723_01.png)
![Root](/uploads/20200723_02.png)

Let's start with our first code. Remember we don't have a specific curve to learn JS so we burst in. Hold tight and let's explore.

I'm placing an empty h1 element in the HTML page with the id of hello

>       <!DOCTYPE html>
>       <html lang="en">
>       
>       <head>
>           <link rel="stylesheet" href="style.css">
>           <title>JS Document</title>
>       </head>
>       
>       <body>
>           <h1 id="hello"></h1>
>           <script src="index.js"></script>
>       </body>
>       
>       </html>

Using SCSS I'm giving the body a grid display and item alignment of center

>       body {
>           display: grid;
>           place-items: center;
>       }

Now for our JS file, I'm placing down a function which can find elements by ID and using that I'm changing the inner HTML of that element to Hello World

>       document.getElementById("hello").innerHTML = "Hello World";

Now you should get something like this as the output

![Root](/uploads/20200723_03.png)

That's All for the hello world! And Welcome to the Javascript community.

# Before coding
JS has some limitations and node.js makes those limitations go away, with that we're using JS as a full fledge programming language and we'll explore the possibilities in another tutorial.

# Code structure

The first thing we'll study is the building blocks of code.

## Statements

Statements are syntax constructs and commands that perform actions.

We've already seen a statement, `alert('Hello, world!')`, which shows the message "Hello, world!".

We can have as many statements in our code as we want. Statements can be separated with a semicolon.

For example, here we split "Hello World" into two alerts:

```js run no-beautify
alert('Hello'); alert('World');
```

Usually, statements are written on separate lines to make the code more readable:

```js run no-beautify
alert('Hello');
alert('World');
```

## Semicolons [#semicolon]

A semicolon may be omitted in most cases when a line break exists.

This would also work:

```js run no-beautify
alert('Hello')
alert('World')
```

Here, JavaScript interprets the line break as an "implicit" semicolon. This is called an [automatic semicolon insertion](https://tc39.github.io/ecma262/#sec-automatic-semicolon-insertion).

**In most cases, a newline implies a semicolon. But "in most cases" does not mean "always"!**

There are cases when a newline does not mean a semicolon. For example:

```js run no-beautify
alert(3 +
1
+ 2);
```

The code outputs `6` because JavaScript does not insert semicolons here. It is intuitively obvious that if the line ends with a plus `"+"`, then it is an "incomplete expression", so the semicolon is not required. And in this case that works as intended.

**But there are situations where JavaScript "fails" to assume a semicolon where it is really needed.**

Errors which occur in such cases are quite hard to find and fix.

If you're curious to see a concrete example of such an error, check this code out:

```js run
[1, 2].forEach(alert)
```

No need to think about the meaning of the brackets `[]` and `forEach` yet. We'll study them later. For now, just remember the result of the code: it shows `1` then `2`.

Now, let's add an `alert` before the code and *not* finish it with a semicolon:

```js run no-beautify
alert("There will be an error")

[1, 2].forEach(alert)
```

Now if we run the code, only the first `alert` is shown and then we have an error!

But everything is fine again if we add a semicolon after `alert`:
```js run
alert("All fine now");

[1, 2].forEach(alert)  
```

Now we have the "All fine now" message followed by `1` and `2`.


The error in the no-semicolon variant occurs because JavaScript does not assume a semicolon before square brackets `[...]`.

So, because the semicolon is not auto-inserted, the code in the first example is treated as a single statement. Here's how the engine sees it:

```js run no-beautify
alert("There will be an error")[1, 2].forEach(alert)
```

But it should be two separate statements, not one. Such a merging in this case is just wrong, hence the error. This can happen in other situations.


We recommend putting semicolons between statements even if they are separated by newlines. This rule is widely adopted by the community. Let's note once again -- *it is possible* to leave out semicolons most of the time. But it's safer -- especially for a beginner -- to use them.

## Comments [#code-comments]

As time goes on, programs become more and more complex. It becomes necessary to add *comments* which describe what the code does and why.

Comments can be put into any place of a script. They don't affect its execution because the engine simply ignores them.

**One-line comments start with two forward slash characters `//`.**

The rest of the line is a comment. It may occupy a full line of its own or follow a statement.

Like here:
```js run
// This comment occupies a line of its own
alert('Hello');

alert('World'); // This comment follows the statement
```

**Multiline comments start with a forward slash and an asterisk <code>/&#42;</code> and end with an asterisk and a forward slash <code>&#42;/</code>.**

Like this:

```js run
/* An example with two messages.
This is a multiline comment.
*/
alert('Hello');
alert('World');
```

The content of comments is ignored, so if we put code inside <code>/&#42; ... &#42;/</code>, it won't execute.

Sometimes it can be handy to temporarily disable a part of code:

```js run
/* Commenting out the code
alert('Hello');
*/
alert('World');
```

In most editors, a line of code can be commented out by pressing the `key:Ctrl+/` hotkey for a single-line comment and something like `key:Ctrl+Shift+/` -- for multiline comments (select a piece of code and press the hotkey). For Mac, try `key:Cmd` instead of `key:Ctrl` and `key:Option` instead of `key:Shift`.


There may not be `/*...*/` inside another `/*...*/`.

Such code will die with an error:

```js run no-beautify
/*
  /* nested comment ?!? */
*/
alert( 'World' );
```


Please, don't hesitate to comment your code.

Comments increase the overall code footprint, but that's not a problem at all. There are many tools which minify code before publishing to a production server. They remove comments, so they don't appear in the working scripts. Therefore, comments do not have negative effects on production at all.

Later in the tutorial there will be a chapter <info:code-quality> that also explains how to write better comments.

# The modern mode, "use strict"

For a long time, JavaScript evolved without compatibility issues. New features were added to the language while old functionality didn't change.

That had the benefit of never breaking existing code. But the downside was that any mistake or an imperfect decision made by JavaScript's creators got stuck in the language forever.

This was the case until 2009 when ECMAScript 5 (ES5) appeared. It added new features to the language and modified some of the existing ones. To keep the old code working, most such modifications are off by default. You need to explicitly enable them with a special directive: `"use strict"`.

## "use strict"

The directive looks like a string: `"use strict"` or `'use strict'`. When it is located at the top of a script, the whole script works the "modern" way.

For example:

```js
"use strict";

// this code works the modern way
...
```

Quite soon we're going to learn functions (a way to group commands), so let's note in advance that `"use strict"` can be put at the beginning of a function. Doing that enables strict mode in that function only. But usually people use it for the whole script.


Please make sure that `"use strict"` is at the top of your scripts, otherwise strict mode may not be enabled.

Strict mode isn't enabled here:

```js no-strict
alert("some code");
// "use strict" below is ignored--it must be at the top

"use strict";

// strict mode is not activated
```

Only comments may appear above `"use strict"`.


There is no directive like `"no use strict"` that reverts the engine to old behavior.

Once we enter strict mode, there's no going back.

## Browser console

When you use a [developer console](info:devtools) to run code, please note that it doesn't `use strict` by default.

Sometimes, when `use strict` makes a difference, you'll get incorrect results.

So, how to actually `use strict` in the console?

First, you can try to press `key:Shift+Enter` to input multiple lines, and put `use strict` on top, like this:

```js
'use strict'; <Shift+Enter for a newline>
//  ...your code
<Enter to run>
```

It works in most browsers, namely Firefox and Chrome.

If it doesn't, e.g. in an old browser, there's an ugly, but reliable way to ensure `use strict`. Put it inside this kind of wrapper:

```js
(function() {
  'use strict';

  // ...your code here...
})()
```

## Should we "use strict"?

The question may sound obvious, but it's not so.

One could recommend to start scripts with `"use strict"`... But you know what's cool?

Modern JavaScript supports "classes" and "modules" - advanced language structures (we'll surely get to them), that enable `use strict` automatically. So we don't need to add the `"use strict"` directive, if we use them.

**So, for now `"use strict";` is a welcome guest at the top of your scripts. Later, when your code is all in classes and modules, you may omit it.**

As of now, we've got to know about `use strict` in general.

In the next chapters, as we learn language features, we'll see the differences between the strict and old modes. Luckily, there aren't many and they actually make our lives better.

All examples in this tutorial assume strict mode unless (very rarely) specified otherwise.
# Variables

Most of the time, a JavaScript application needs to work with information. Here are two examples:
1. An online shop -- the information might include goods being sold and a shopping cart.
2. A chat application -- the information might include users, messages, and much more.

Variables are used to store this information.

## A variable

A [variable](https://en.wikipedia.org/wiki/Variable_(computer_science)) is a "named storage" for data. We can use variables to store goodies, visitors, and other data.

To create a variable in JavaScript, use the `let` keyword.

The statement below creates (in other words: *declares*) a variable with the name "message":

```js
let message;
```

Now, we can put some data into it by using the assignment operator `=`:

```js
let message;


message = 'Hello'; // store the string

```

The string is now saved into the memory area associated with the variable. We can access it using the variable name:

```js run
let message;
message = 'Hello!';


alert(message); // shows the variable content

```

To be concise, we can combine the variable declaration and assignment into a single line:

```js run
let message = 'Hello!'; // define the variable and assign the value

alert(message); // Hello!
```

We can also declare multiple variables in one line:

```js no-beautify
let user = 'John', age = 25, message = 'Hello';
```

That might seem shorter, but we don't recommend it. For the sake of better readability, please use a single line per variable.

The multiline variant is a bit longer, but easier to read:

```js
let user = 'John';
let age = 25;
let message = 'Hello';
```

Some people also define multiple variables in this multiline style:
```js no-beautify
let user = 'John',
  age = 25,
  message = 'Hello';
```

...Or even in the "comma-first" style:

```js no-beautify
let user = 'John'
  , age = 25
  , message = 'Hello';
```

Technically, all these variants do the same thing. So, it's a matter of personal taste and aesthetics.

In older scripts, you may also find another keyword: `var` instead of `let`:

```js
var message = 'Hello';
```

The `var` keyword is *almost* the same as `let`. It also declares a variable, but in a slightly different, "old-school" way.

There are subtle differences between `let` and `var`, but they do not matter for us yet. We'll cover them in detail in the chapter <info:var>.


## A real-life analogy

We can easily grasp the concept of a "variable" if we imagine it as a "box" for data, with a uniquely-named sticker on it.

For instance, the variable `message` can be imagined as a box labeled `"message"` with the value `"Hello!"` in it:

We can put any value in the box.

We can also change it as many times as we want:
```js run
let message;

message = 'Hello!';

message = 'World!'; // value changed

alert(message);
```

When the value is changed, the old data is removed from the variable:

We can also declare two variables and copy data from one into the other.

```js run
let hello = 'Hello world!';

let message;


// copy 'Hello world' from hello into message
message = hello;


// now two variables hold the same data
alert(hello); // Hello world!
alert(message); // Hello world!
```

A variable should be declared only once.

A repeated declaration of the same variable is an error:

```js run
let message = "This";

// repeated 'let' leads to an error
let message = "That"; // SyntaxError: 'message' has already been declared
```
So, we should declare a variable once and then refer to it without `let`.


It's interesting to note that there exist [functional](https://en.wikipedia.org/wiki/Functional_programming) programming languages, like [Scala](http://www.scala-lang.org/) or [Erlang](http://www.erlang.org/) that forbid changing variable values.

In such languages, once the value is stored "in the box", it's there forever. If we need to store something else, the language forces us to create a new box (declare a new variable). We can't reuse the old one.

Though it may seem a little odd at first sight, these languages are quite capable of serious development. More than that, there are areas like parallel computations where this limitation confers certain benefits. Studying such a language (even if you're not planning to use it soon) is recommended to broaden the mind.

## Variable naming [#variable-naming]

There are two limitations on variable names in JavaScript:

1. The name must contain only letters, digits, or the symbols `$` and `_`.
2. The first character must not be a digit.

Examples of valid names:

```js
let userName;
let test123;
```

When the name contains multiple words, [camelCase](https://en.wikipedia.org/wiki/CamelCase) is commonly used. That is: words go one after another, each word except first starting with a capital letter: `myVeryLongName`.

What's interesting -- the dollar sign `'$'` and the underscore `'_'` can also be used in names. They are regular symbols, just like letters, without any special meaning.

These names are valid:

```js run untrusted
let $ = 1; // declared a variable with the name "$"
let _ = 2; // and now a variable with the name "_"

alert($ + _); // 3
```

Examples of incorrect variable names:

```js no-beautify
let 1a; // cannot start with a digit

let my-name; // hyphens '-' aren't allowed in the name
```

Variables named `apple` and `AppLE` are two different variables.

It is possible to use any language, including cyrillic letters or even hieroglyphs, like this:

```js
let имя = '...';
let 我 = '...';
```

Technically, there is no error here. Such names are allowed, but there is an international convention to use English in variable names. Even if we're writing a small script, it may have a long life ahead. People from other countries may need to read it some time.

There is a [list of reserved words](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords), which cannot be used as variable names because they are used by the language itself.

For example: `let`, `class`, `return`, and `function` are reserved.

The code below gives a syntax error:

```js run no-beautify
let let = 5; // can't name a variable "let", error!
let return = 5; // also can't name it "return", error!
```



Normally, we need to define a variable before using it. But in the old times, it was technically possible to create a variable by a mere assignment of the value without using `let`. This still works now if we don't put `use strict` in our scripts to maintain compatibility with old scripts.

```js run no-strict
// note: no "use strict" in this example

num = 5; // the variable "num" is created if it didn't exist

alert(num); // 5
```

This is a bad practice and would cause an error in strict mode:

```js
"use strict";


num = 5; // error: num is not defined

```

## Constants

To declare a constant (unchanging) variable, use `const` instead of `let`:

```js
const myBirthday = '18.04.1982';
```

Variables declared using `const` are called "constants". They cannot be reassigned. An attempt to do so would cause an error:

```js run
const myBirthday = '18.04.1982';

myBirthday = '01.01.2001'; // error, can't reassign the constant!
```

When a programmer is sure that a variable will never change, they can declare it with `const` to guarantee and clearly communicate that fact to everyone.


### Uppercase constants

There is a widespread practice to use constants as aliases for difficult-to-remember values that are known prior to execution.

Such constants are named using capital letters and underscores.

For instance, let's make constants for colors in so-called "web" (hexadecimal) format:

```js run
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// ...when we need to pick a color
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```

Benefits:

- `COLOR_ORANGE` is much easier to remember than `"#FF7F00"`.
- It is much easier to mistype `"#FF7F00"` than `COLOR_ORANGE`.
- When reading the code, `COLOR_ORANGE` is much more meaningful than `#FF7F00`.

When should we use capitals for a constant and when should we name it normally? Let's make that clear.

Being a "constant" just means that a variable's value never changes. But there are constants that are known prior to execution (like a hexadecimal value for red) and there are constants that are *calculated* in run-time, during the execution, but do not change after their initial assignment.

For instance:
```js
const pageLoadTime = /* time taken by a webpage to load */;
```

The value of `pageLoadTime` is not known prior to the page load, so it's named normally. But it's still a constant because it doesn't change after assignment.

In other words, capital-named constants are only used as aliases for "hard-coded" values.  

## Name things right

Talking about variables, there's one more extremely important thing.

A variable name should have a clean, obvious meaning, describing the data that it stores.

Variable naming is one of the most important and complex skills in programming. A quick glance at variable names can reveal which code was written by a beginner versus an experienced developer.

In a real project, most of the time is spent modifying and extending an existing code base rather than writing something completely separate from scratch. When we return to some code after doing something else for a while, it's much easier to find information that is well-labeled. Or, in other words, when the variables have good names.

Please spend time thinking about the right name for a variable before declaring it. Doing so will repay you handsomely.

Some good-to-follow rules are:

- Use human-readable names like `userName` or `shoppingCart`.
- Stay away from abbreviations or short names like `a`, `b`, `c`, unless you really know what you're doing.
- Make names maximally descriptive and concise. Examples of bad names are `data` and `value`. Such names say nothing. It's only okay to use them if the context of the code makes it exceptionally obvious which data or value the variable is referencing.
- Agree on terms within your team and in your own mind. If a site visitor is called a "user" then we should name related variables `currentUser` or `newUser` instead of `currentVisitor` or `newManInTown`.

Sounds simple? Indeed it is, but creating descriptive and concise variable names in practice is not. Go for it.

And the last note. There are some lazy programmers who, instead of declaring new variables, tend to reuse existing ones.

As a result, their variables are like boxes into which people throw different things without changing their stickers. What's inside the box now? Who knows? We need to come closer and check.

Such programmers save a little bit on variable declaration but lose ten times more on debugging.

An extra variable is good, not evil.

Modern JavaScript minifiers and browsers optimize code well enough, so it won't create performance issues. Using different variables for different values can even help the engine optimize your code.

## Summary

We can declare variables to store data by using the `var`, `let`, or `const` keywords.

- `let` -- is a modern variable declaration.
- `var` -- is an old-school variable declaration. Normally we don't use it at all, but we'll cover subtle differences from `let` in the chapter <info:var>, just in case you need them.
- `const` -- is like `let`, but the value of the variable can't be changed.

Variables should be named in a way that allows us to easily understand what's inside them.
# Data types

A value in JavaScript is always of a certain type. For example, a string or a number.

There are eight basic data types in JavaScript. Here, we'll cover them in general and in the next chapters we'll talk about each of them in detail.

We can put any type in a variable. For example, a variable can at one moment be a string and then store a number:

```js
// no error
let message = "hello";
message = 123456;
```

Programming languages that allow such things, such as JavaScript, are called "dynamically typed", meaning that there exist data types, but variables are not bound to any of them.

## Number

```js
let n = 123;
n = 12.345;
```

The *number* type represents both integer and floating point numbers.

There are many operations for numbers, e.g. multiplication `*`, division `/`, addition `+`, subtraction `-`, and so on.

Besides regular numbers, there are so-called "special numeric values" which also belong to this data type: `Infinity`, `-Infinity` and `NaN`.

- `Infinity` represents the mathematical [Infinity](https://en.wikipedia.org/wiki/Infinity) ∞. It is a special value that's greater than any number.

    We can get it as a result of division by zero:

    ```js run
    alert( 1 / 0 ); // Infinity
    ```

    Or just reference it directly:

    ```js run
    alert( Infinity ); // Infinity
    ```
- `NaN` represents a computational error. It is a result of an incorrect or an undefined mathematical operation, for instance:

    ```js run
    alert( "not a number" / 2 ); // NaN, such division is erroneous
    ```

    `NaN` is sticky. Any further operation on `NaN` returns `NaN`:

    ```js run
    alert( "not a number" / 2 + 5 ); // NaN
    ```

    So, if there's a `NaN` somewhere in a mathematical expression, it propagates to the whole result.

Doing maths is "safe" in JavaScript. We can do anything: divide by zero, treat non-numeric strings as numbers, etc.

The script will never stop with a fatal error ("die"). At worst, we'll get `NaN` as the result.

Special numeric values formally belong to the "number" type. Of course they are not numbers in the common sense of this word.

We'll see more about working with numbers in the chapter <info:number>.

## BigInt

In JavaScript, the "number" type cannot represent integer values larger than <code>(2<sup>53</sup>-1)</code> (that's `9007199254740991`), or less than <code>-(2<sup>53</sup>-1)</code> for negatives. It's a technical limitation caused by their internal representation.

For most purposes that's quite enough, but sometimes we need really big numbers, e.g. for cryptography or microsecond-precision timestamps.

`BigInt` type was recently added to the language to represent integers of arbitrary length.

A `BigInt` value is created by appending `n` to the end of an integer:

```js
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```

As `BigInt` numbers are rarely needed, we don't cover them here, but devoted them a separate chapter <info:bigint>. Read it when you need such big numbers.

Right now `BigInt` is supported in Firefox/Chrome/Edge, but not in Safari/IE.

## String

A string in JavaScript must be surrounded by quotes.

```js
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

In JavaScript, there are 3 types of quotes.

1. Double quotes: `"Hello"`.
2. Single quotes: `'Hello'`.
3. Backticks: <code>&#96;Hello&#96;</code>.

Double and single quotes are "simple" quotes. There's practically no difference between them in JavaScript.

Backticks are "extended functionality" quotes. They allow us to embed variables and expressions into a string by wrapping them in `${…}`, for example:

```js run
let name = "John";

// embed a variable
alert( `Hello, ${name}!` ); // Hello, John!

// embed an expression
alert( `the result is ${1 + 2}` ); // the result is 3
```

The expression inside `${…}` is evaluated and the result becomes a part of the string. We can put anything in there: a variable like `name` or an arithmetical expression like `1 + 2` or something more complex.

Please note that this can only be done in backticks. Other quotes don't have this embedding functionality!
```js run
alert( "the result is ${1 + 2}" ); // the result is ${1 + 2} (double quotes do nothing)
```

We'll cover strings more thoroughly in the chapter <info:string>.

In some languages, there is a special "character" type for a single character. For example, in the C language and in Java it is called "char".

In JavaScript, there is no such type. There's only one type: `string`. A string may consist of only one character or many of them.

## Boolean (logical type)

The boolean type has only two values: `true` and `false`.

This type is commonly used to store yes/no values: `true` means "yes, correct", and `false` means "no, incorrect".

For instance:

```js
let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked
```

Boolean values also come as a result of comparisons:

```js run
let isGreater = 4 > 1;

alert( isGreater ); // true (the comparison result is "yes")
```

We'll cover booleans more deeply in the chapter <info:logical-operators>.

## The "null" value

The special `null` value does not belong to any of the types described above.

It forms a separate type of its own which contains only the `null` value:

```js
let age = null;
```

In JavaScript, `null` is not a "reference to a non-existing object" or a "null pointer" like in some other languages.

It's just a special value which represents "nothing", "empty" or "value unknown".

The code above states that `age` is unknown.

## The "undefined" value

The special value `undefined` also stands apart. It makes a type of its own, just like `null`.

The meaning of `undefined` is "value is not assigned".

If a variable is declared, but not assigned, then its value is `undefined`:

```js run
let age;

alert(age); // shows "undefined"
```

Technically, it is possible to explicitly assign `undefined` to a variable:

```js run
let age = 100;

// change the value to undefined
age = undefined;

alert(age); // "undefined"
```

...But we don't recommend doing that. Normally, one uses `null` to assign an "empty" or "unknown" value to a variable, while `undefined` is reserved as a default initial value for unassigned things.

## Objects and Symbols

The `object` type is special.

All other types are called "primitive" because their values can contain only a single thing (be it a string or a number or whatever). In contrast, objects are used to store collections of data and more complex entities.

Being that important, objects deserve a special treatment. We'll deal with them later in the chapter <info:object>, after we learn more about primitives.

The `symbol` type is used to create unique identifiers for objects. We have to mention it here for the sake of completeness, but also postpone the details till we know objects.

## The typeof operator [#type-typeof]

The `typeof` operator returns the type of the argument. It's useful when we want to process values of different types differently or just want to do a quick check.

It supports two forms of syntax:

1. As an operator: `typeof x`.
2. As a function: `typeof(x)`.

In other words, it works with parentheses or without them. The result is the same.

The call to `typeof x` returns a string with the type name:

```js
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"


typeof Math // "object"  (1)



typeof null // "object"  (2)



typeof alert // "function"  (3)

```

The last three lines may need additional explanation:

1. `Math` is a built-in object that provides mathematical operations. We will learn it in the chapter <info:number>. Here, it serves just as an example of an object.
2. The result of `typeof null` is `"object"`. That's an officially recognized error in `typeof` behavior, coming from the early days of JavaScript and kept for compatibility. Definitely, `null` is not an object. It is a special value with a separate type of its own.
3. The result of `typeof alert` is `"function"`, because `alert` is a function. We'll study functions in the next chapters where we'll also see that there's no special "function" type in JavaScript. Functions belong to the object type. But `typeof` treats them differently, returning `"function"`. That also comes from the early days of JavaScript. Technically, such behavior isn't correct, but can be convenient in practice.

## Summary

There are 8 basic data types in JavaScript.

- `number` for numbers of any kind: integer or floating-point, integers are limited by ±2<sup>53</sup>.
- `bigint` is for integer numbers of arbitrary length.
- `string` for strings. A string may have zero or more characters, there's no separate single-character type.
- `boolean` for `true`/`false`.
- `null` for unknown values -- a standalone type that has a single value `null`.
- `undefined` for unassigned values -- a standalone type that has a single value `undefined`.
- `object` for more complex data structures.
- `symbol` for unique identifiers.

The `typeof` operator allows us to see which type is stored in a variable.

- Two forms: `typeof x` or `typeof(x)`.
- Returns a string with the name of the type, like `"string"`.
- For `null` returns `"object"` -- this is an error in the language, it's not actually an object.

In the next chapters, we'll concentrate on primitive values and once we're familiar with them, we'll move on to objects.
# Interaction: alert, prompt, confirm

As we'll be using the browser as our demo environment, let's see a couple of functions to interact with the user: `alert`, `prompt` and `confirm`.

## alert

This one we've seen already. It shows a message and waits for the user to press "OK".

For example:

```js run
alert("Hello");
```

The mini-window with the message is called a *modal window*. The word "modal" means that the visitor can't interact with the rest of the page, press other buttons, etc, until they have dealt with the window. In this case -- until they press "OK".

## prompt

The function `prompt` accepts two arguments:

```js no-beautify
result = prompt(title, [default]);
```

It shows a modal window with a text message, an input field for the visitor, and the buttons OK/Cancel.

`title`
: The text to show the visitor.

`default`
: An optional second parameter, the initial value for the input field.

```
The square brackets around `default` in the syntax above denote that the parameter as optional, not required.
```

The visitor can type something in the prompt input field and press OK. Then we get that text in the `result`. Or they can cancel the input by pressing Cancel or hitting the `key:Esc` key, then we get `null` as the `result`.

The call to `prompt` returns the text from the input field or `null` if the input was canceled.

For instance:

```js run
let age = prompt('How old are you?', 100);

alert(`You are ${age} years old!`); // You are 100 years old!
```


The second parameter is optional, but if we don't supply it, Internet Explorer will insert the text `"undefined"` into the prompt.

Run this code in Internet Explorer to see:

```js run
let test = prompt("Test");
```

So, for prompts to look good in IE, we recommend always providing the second argument:

```js run
let test = prompt("Test", ''); // <-- for IE
```

## confirm

The syntax:

```js
result = confirm(question);
```

The function `confirm` shows a modal window with a `question` and two buttons: OK and Cancel.

The result is `true` if OK is pressed and `false` otherwise.

For example:

```js run
let isBoss = confirm("Are you the boss?");

alert( isBoss ); // true if OK is pressed
```

## Summary

We covered 3 browser-specific functions to interact with visitors:

`alert`
: shows a message.

`prompt`
: shows a message asking the user to input text. It returns the text or, if Cancel button or `key:Esc` is clicked, `null`.

`confirm`
: shows a message and waits for the user to press "OK" or "Cancel". It returns `true` for OK and `false` for Cancel/`key:Esc`.

All these methods are modal: they pause script execution and don't allow the visitor to interact with the rest of the page until the window has been dismissed.

There are two limitations shared by all the methods above:

1. The exact location of the modal window is determined by the browser. Usually, it's in the center.
2. The exact look of the window also depends on the browser. We can't modify it.

That is the price for simplicity. There are other ways to show nicer windows and richer interaction with the visitor, but if "bells and whistles" do not matter much, these methods work just fine.
# Type Conversions

Most of the time, operators and functions automatically convert the values given to them to the right type.

For example, `alert` automatically converts any value to a string to show it. Mathematical operations convert values to numbers.

There are also cases when we need to explicitly convert a value to the expected type.

In this chapter, we won't cover objects. For now we'll just be talking about primitives.

Later, after we learn about objects, in the chapter <info:object-toprimitive> we'll see how objects fit in.

## String Conversion

String conversion happens when we need the string form of a value.

For example, `alert(value)` does it to show the value.

We can also call the `String(value)` function to convert a value to a string:

```js run
let value = true;
alert(typeof value); // boolean


value = String(value); // now value is a string "true"
alert(typeof value); // string

```

String conversion is mostly obvious. A `false` becomes `"false"`, `null` becomes `"null"`, etc.

## Numeric Conversion

Numeric conversion happens in mathematical functions and expressions automatically.

For example, when division `/` is applied to non-numbers:

```js run
alert( "6" / "2" ); // 3, strings are converted to numbers
```

We can use the `Number(value)` function to explicitly convert a `value` to a number:

```js run
let str = "123";
alert(typeof str); // string

let num = Number(str); // becomes a number 123

alert(typeof num); // number
```

Explicit conversion is usually required when we read a value from a string-based source like a text form but expect a number to be entered.

If the string is not a valid number, the result of such a conversion is `NaN`. For instance:

```js run
let age = Number("an arbitrary string instead of a number");

alert(age); // NaN, conversion failed
```

Numeric conversion rules:

| Value                                 | Becomes...                                                                                                                                                                  |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `undefined`                           | `NaN`                                                                                                                                                                       |
| `null`                                | `0`                                                                                                                                                                         |
| <code>true&nbsp;and&nbsp;false</code> | `1` and `0`                                                                                                                                                                 |
| `string`                              | Whitespaces from the start and end are removed. If the remaining string is empty, the result is `0`. Otherwise, the number is "read" from the string. An error gives `NaN`. |

Examples:

```js run
alert( Number("   123   ") ); // 123
alert( Number("123z") );      // NaN (error reading a number at "z")
alert( Number(true) );        // 1
alert( Number(false) );       // 0
```

Please note that `null` and `undefined` behave differently here: `null` becomes zero while `undefined` becomes `NaN`.

Most mathematical operators also perform such conversion, we'll see that in the next chapter.

## Boolean Conversion

Boolean conversion is the simplest one.

It happens in logical operations (later we'll meet condition tests and other similar things) but can also be performed explicitly with a call to `Boolean(value)`.

The conversion rule:

- Values that are intuitively "empty", like `0`, an empty string, `null`, `undefined`, and `NaN`, become `false`.
- Other values become `true`.

For instance:

```js run
alert( Boolean(1) ); // true
alert( Boolean(0) ); // false

alert( Boolean("hello") ); // true
alert( Boolean("") ); // false
```


Some languages (namely PHP) treat `"0"` as `false`. But in JavaScript, a non-empty string is always `true`.

```js run
alert( Boolean("0") ); // true
alert( Boolean(" ") ); // spaces, also true (any non-empty string is true)
```

## Summary

The three most widely used type conversions are to string, to number, and to boolean.

**`String Conversion`** -- Occurs when we output something. Can be performed with `String(value)`. The conversion to string is usually obvious for primitive values.

**`Numeric Conversion`** -- Occurs in math operations. Can be performed with `Number(value)`.

The conversion follows the rules:

| Value                               | Becomes...                                                                                                              |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `undefined`                         | `NaN`                                                                                                                   |
| `null`                              | `0`                                                                                                                     |
| <code>true&nbsp;/&nbsp;false</code> | `1 / 0`                                                                                                                 |
| `string`                            | The string is read "as is", whitespaces from both sides are ignored. An empty string becomes `0`. An error gives `NaN`. |

**`Boolean Conversion`** -- Occurs in logical operations. Can be performed with `Boolean(value)`.

Follows the rules:

| Value                                 | Becomes... |
| ------------------------------------- | ---------- |
| `0`, `null`, `undefined`, `NaN`, `""` | `false`    |
| any other value                       | `true`     |


Most of these rules are easy to understand and memorize. The notable exceptions where people usually make mistakes are:

- `undefined` is `NaN` as a number, not `0`.
- `"0"` and space-only strings like `"   "` are true as a boolean.

Objects aren't covered here. We'll return to them later in the chapter <info:object-toprimitive> that is devoted exclusively to objects after we learn more basic things about JavaScript.
# Basic operators, maths

We know many operators from school. They are things like addition `+`, multiplication `*`, subtraction `-`, and so on.

In this chapter, we’ll start with simple operators, then concentrate on JavaScript-specific aspects, not covered by school arithmetic.

## Terms: "unary", "binary", "operand"

Before we move on, let's grasp some common terminology.

- *An operand* -- is what operators are applied to. For instance, in the multiplication of `5 * 2` there are two operands: the left operand is `5` and the right operand is `2`. Sometimes, people call these "arguments" instead of "operands".
- An operator is *unary* if it has a single operand. For example, the unary negation `-` reverses the sign of a number:

    ```js run
    let x = 1;

    
    x = -x;
    
    alert( x ); // -1, unary negation was applied
    ```
- An operator is *binary* if it has two operands. The same minus exists in binary form as well:

    ```js run no-beautify
    let x = 1, y = 3;
    alert( y - x ); // 2, binary minus subtracts values
    ```

    Formally, in the examples above we have two different operators that share the same symbol: the negation operator, a unary operator that reverses the sign, and the subtraction operator, a binary operator that subtracts one number from another.

## Maths

The following math operations are supported:

- Addition `+`,
- Subtraction `-`,
- Multiplication `*`,
- Division `/`,
- Remainder `%`,
- Exponentiation `**`.

The first four are straightforward, while `%` and `**` need a few words about them.

### Remainder %

The remainder operator `%`, despite its appearance, is not related to percents.

The result of `a % b` is the [remainder](https://en.wikipedia.org/wiki/Remainder) of the integer division of `a` by `b`.

For instance:

```js run
alert( 5 % 2 ); // 1, a remainder of 5 divided by 2
alert( 8 % 3 ); // 2, a remainder of 8 divided by 3
```

### Exponentiation **

The exponentiation operator `a ** b` multiplies `a` by itself `b` times.

For instance:

```js run
alert( 2 ** 2 ); // 4  (2 multiplied by itself 2 times)
alert( 2 ** 3 ); // 8  (2 * 2 * 2, 3 times)
alert( 2 ** 4 ); // 16 (2 * 2 * 2 * 2, 4 times)
```

Mathematically, the exponentiation is defined for non-integer numbers as well. For example, a square root is an exponentiation by `1/2`:

```js run
alert( 4 ** (1/2) ); // 2 (power of 1/2 is the same as a square root)
alert( 8 ** (1/3) ); // 2 (power of 1/3 is the same as a cubic root)
```


## String concatenation with binary +

Let's meet features of JavaScript operators that are beyond school arithmetics.

Usually, the plus operator `+` sums numbers.

But, if the binary `+` is applied to strings, it merges (concatenates) them:

```js
let s = "my" + "string";
alert(s); // mystring
```

Note that if any of the operands is a string, then the other one is converted to a string too.

For example:

```js run
alert( '1' + 2 ); // "12"
alert( 2 + '1' ); // "21"
```

See, it doesn't matter whether the first operand is a string or the second one.

Here's a more complex example:

```js run
alert(2 + 2 + '1' ); // "41" and not "221"
```

Here, operators work one after another. The first `+` sums two numbers, so it returns `4`, then the next `+` adds the string `1` to it, so it's like `4 + '1' = 41`.

The binary `+` is the only operator that supports strings in such a way. Other arithmetic operators work only with numbers and always convert their operands to numbers.

Here's the demo for subtraction and division:

```js run
alert( 6 - '2' ); // 4, converts '2' to a number
alert( '6' / '2' ); // 3, converts both operands to numbers
```

## Numeric conversion, unary +

The plus `+` exists in two forms: the binary form that we used above and the unary form.

The unary plus or, in other words, the plus operator `+` applied to a single value, doesn't do anything to numbers. But if the operand is not a number, the unary plus converts it into a number.

For example:

```js run
// No effect on numbers
let x = 1;
alert( +x ); // 1

let y = -2;
alert( +y ); // -2


// Converts non-numbers
alert( +true ); // 1
alert( +"" );   // 0

```

It actually does the same thing as `Number(...)`, but is shorter.

The need to convert strings to numbers arises very often. For example, if we are getting values from HTML form fields, they are usually strings. What if we want to sum them?

The binary plus would add them as strings:

```js run
let apples = "2";
let oranges = "3";

alert( apples + oranges ); // "23", the binary plus concatenates strings
```

If we want to treat them as numbers, we need to convert and then sum them:

```js run
let apples = "2";
let oranges = "3";


// both values converted to numbers before the binary plus
alert( +apples + +oranges ); // 5


// the longer variant
// alert( Number(apples) + Number(oranges) ); // 5
```

From a mathematician's standpoint, the abundance of pluses may seem strange. But from a programmer's standpoint, there's nothing special: unary pluses are applied first, they convert strings to numbers, and then the binary plus sums them up.

Why are unary pluses applied to values before the binary ones? As we're going to see, that's because of their *higher precedence*.

## Operator precedence

If an expression has more than one operator, the execution order is defined by their *precedence*, or, in other words, the default priority order of operators.

From school, we all know that the multiplication in the expression `1 + 2 * 2` should be calculated before the addition. That's exactly the precedence thing. The multiplication is said to have *a higher precedence* than the addition.

Parentheses override any precedence, so if we're not satisfied with the default order, we can use them to change it. For example, write `(1 + 2) * 2`.

There are many operators in JavaScript. Every operator has a corresponding precedence number. The one with the larger number executes first. If the precedence is the same, the execution order is from left to right.

Here's an extract from the [precedence table](https://developer.mozilla.org/en/JavaScript/Reference/operators/operator_precedence) (you don't need to remember this, but note that unary operators are higher than corresponding binary ones):

| Precedence | Name           | Sign |
| ---------- | -------------- | ---- |
| ...        | ...            | ...  |
| 17         | unary plus     | `+`  |
| 17         | unary negation | `-`  |
| 16         | exponentiation | `**` |
| 15         | multiplication | `*`  |
| 15         | division       | `/`  |
| 13         | addition       | `+`  |
| 13         | subtraction    | `-`  |
| ...        | ...            | ...  |
| 3          | assignment     | `=`  |
| ...        | ...            | ...  |

As we can see, the "unary plus" has a priority of `17` which is higher than the `13` of "addition" (binary plus). That's why, in the expression `"+apples + +oranges"`, unary pluses work before the addition.

## Assignment

Let's note that an assignment `=` is also an operator. It is listed in the precedence table with the very low priority of `3`.

That's why, when we assign a variable, like `x = 2 * 2 + 1`, the calculations are done first and then the `=` is evaluated, storing the result in `x`.

```js
let x = 2 * 2 + 1;

alert( x ); // 5
```

### Assignment = returns a value

The fact of `=` being an operator, not a "magical" language construct has an interesting implication.

Most operators in JavaScript return a value. That's obvious for `+` and `-`, but also true for `=`.

The call `x = value` writes the `value` into `x` *and then returns it*.

Here's a demo that uses an assignment as part of a more complex expression:

```js run
let a = 1;
let b = 2;


let c = 3 - (a = b + 1);


alert( a ); // 3
alert( c ); // 0
```

In the example above, the result of expression `(a = b + 1)` is the value which was assigned to `a` (that is `3`). It is then used for further evaluations.

Funny code, isn't it? We should understand how it works, because sometimes we see it in JavaScript libraries.

Although, please don't write the code like that. Such tricks definitely don't make code clearer or readable.

### Chaining assignments

Another interesting feature is the ability to chain assignments:

```js run
let a, b, c;


a = b = c = 2 + 2;


alert( a ); // 4
alert( b ); // 4
alert( c ); // 4
```

Chained assignments evaluate from right to left. First, the rightmost expression `2 + 2` is evaluated and then assigned to the variables on the left: `c`, `b` and `a`. At the end, all the variables share a single value.

Once again, for the purposes of readability it's better to split such code into few lines:

```js
c = 2 + 2;
b = c;
a = c;
```
That's easier to read, especially when eye-scanning the code fast.

## Modify-in-place

We often need to apply an operator to a variable and store the new result in that same variable.

For example:

```js
let n = 2;
n = n + 5;
n = n * 2;
```

This notation can be shortened using the operators `+=` and `*=`:

```js run
let n = 2;
n += 5; // now n = 7 (same as n = n + 5)
n *= 2; // now n = 14 (same as n = n * 2)

alert( n ); // 14
```

Short "modify-and-assign" operators exist for all arithmetical and bitwise operators: `/=`, `-=`, etc.

Such operators have the same precedence as a normal assignment, so they run after most other calculations:

```js run
let n = 2;

n *= 3 + 5;

alert( n ); // 16  (right part evaluated first, same as n *= 8)
```

## Increment/decrement

<!-- Can't use -- in title, because the built-in parser turns it into a 'long dash' – -->

Increasing or decreasing a number by one is among the most common numerical operations.

So, there are special operators for it:

- **Increment** `++` increases a variable by 1:

    ```js run no-beautify
    let counter = 2;
    counter++;        // works the same as counter = counter + 1, but is shorter
    alert( counter ); // 3
    ```
- **Decrement** `--` decreases a variable by 1:

    ```js run no-beautify
    let counter = 2;
    counter--;        // works the same as counter = counter - 1, but is shorter
    alert( counter ); // 1
    ```

```warn
Increment/decrement can only be applied to variables. Trying to use it on a value like `5++` will give an error.
```

The operators `++` and `--` can be placed either before or after a variable.

- When the operator goes after the variable, it is in "postfix form": `counter++`.
- The "prefix form" is when the operator goes before the variable: `++counter`.

Both of these statements do the same thing: increase `counter` by `1`.

Is there any difference? Yes, but we can only see it if we use the returned value of `++/--`.

Let's clarify. As we know, all operators return a value. Increment/decrement is no exception. The prefix form returns the new value while the postfix form returns the old value (prior to increment/decrement).

To see the difference, here's an example:

```js run
let counter = 1;
let a = ++counter; // (*)

alert(a); // 2
```

In the line `(*)`, the *prefix* form `++counter` increments `counter` and returns the new value, `2`. So, the `alert` shows `2`.

Now, let's use the postfix form:

```js run
let counter = 1;
let a = counter++; // (*) changed ++counter to counter++

alert(a); // 1
```

In the line `(*)`, the *postfix* form `counter++` also increments `counter` but returns the *old* value (prior to increment). So, the `alert` shows `1`.

To summarize:

- If the result of increment/decrement is not used, there is no difference in which form to use:

    ```js run
    let counter = 0;
    counter++;
    ++counter;
    alert( counter ); // 2, the lines above did the same
    ```
- If we'd like to increase a value *and* immediately use the result of the operator, we need the prefix form:

    ```js run
    let counter = 0;
    alert( ++counter ); // 1
    ```
- If we'd like to increment a value but use its previous value, we need the postfix form:

    ```js run
    let counter = 0;
    alert( counter++ ); // 0
    ```

The operators `++/--` can be used inside expressions as well. Their precedence is higher than most other arithmetical operations.

For instance:

```js run
let counter = 1;
alert( 2 * ++counter ); // 4
```

Compare with:

```js run
let counter = 1;
alert( 2 * counter++ ); // 2, because counter++ returns the "old" value
```

Though technically okay, such notation usually makes code less readable. One line does multiple things -- not good.

While reading code, a fast "vertical" eye-scan can easily miss something like `counter++` and it won't be obvious that the variable increased.

We advise a style of "one line -- one action":

```js run
let counter = 1;
alert( 2 * counter );
counter++;
```

## Bitwise operators

Bitwise operators treat arguments as 32-bit integer numbers and work on the level of their binary representation.

These operators are not JavaScript-specific. They are supported in most programming languages.

The list of operators:

- AND ( `&` )
- OR ( `|` )
- XOR ( `^` )
- NOT ( `~` )
- LEFT SHIFT ( `<<` )
- RIGHT SHIFT ( `>>` )
- ZERO-FILL RIGHT SHIFT ( `>>>` )

These operators are used very rarely, when we need to fiddle with numbers on the very lowest (bitwise) level. We won't need these operators any time soon, as web development has little use of them, but in some special areas, such as cryptography, they are useful. You can read the [Bitwise Operators](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators) article on MDN when a need arises.

## Comma

The comma operator `,` is one of the rarest and most unusual operators. Sometimes, it's used to write shorter code, so we need to know it in order to understand what's going on.

The comma operator allows us to evaluate several expressions, dividing them with a comma `,`. Each of them is evaluated but only the result of the last one is returned.

For example:

```js run

let a = (1 + 2, 3 + 4);


alert( a ); // 7 (the result of 3 + 4)
```

Here, the first expression `1 + 2` is evaluated and its result is thrown away. Then, `3 + 4` is evaluated and returned as the result.

Please note that the comma operator has very low precedence, lower than `=`, so parentheses are important in the example above.

Without them: `a = 1 + 2, 3 + 4` evaluates `+` first, summing the numbers into `a = 3, 7`, then the assignment operator `=` assigns `a = 3`, and the rest is ignored. It's like `(a = 1 + 2), 3 + 4`.

Why do we need an operator that throws away everything except the last expression?

Sometimes, people use it in more complex constructs to put several actions in one line.

For example:

```js
// three operations in one line
for (a = 1, b = 3, c = a * b; a < 10; a++) {
 ...
}
```

Such tricks are used in many JavaScript frameworks. That's why we're mentioning them. But usually they don't improve code readability so we should think well before using them.
# Comparisons

We know many comparison operators from maths.

In JavaScript they are written like this:

- Greater/less than: <code>a &gt; b</code>, <code>a &lt; b</code>.
- Greater/less than or equals: <code>a &gt;= b</code>, <code>a &lt;= b</code>.
- Equals: `a == b`, please note the double equality sign `==` means the equality test, while a single one `a = b` means an assignment.
- Not equals. In maths the notation is <code>&ne;</code>, but in JavaScript it's written as <code>a != b</code>.

In this article we'll learn more about different types of comparisons, how JavaScript makes them, including important peculiarities. 

At the end you'll find a good recipe to avoid "javascript quirks"-related issues.

## Boolean is the result

All comparison operators return a boolean value:

- `true` -- means "yes", "correct" or "the truth".
- `false` -- means "no", "wrong" or "not the truth".

For example:

```js run
alert( 2 > 1 );  // true (correct)
alert( 2 == 1 ); // false (wrong)
alert( 2 != 1 ); // true (correct)
```

A comparison result can be assigned to a variable, just like any value:

```js run
let result = 5 > 4; // assign the result of the comparison
alert( result ); // true
```

## String comparison

To see whether a string is greater than another, JavaScript uses the so-called "dictionary" or "lexicographical" order.

In other words, strings are compared letter-by-letter.

For example:

```js run
alert( 'Z' > 'A' ); // true
alert( 'Glow' > 'Glee' ); // true
alert( 'Bee' > 'Be' ); // true
```

The algorithm to compare two strings is simple:

1. Compare the first character of both strings.
2. If the first character from the first string is greater (or less) than the other string's, then the first string is greater (or less) than the second. We're done.
3. Otherwise, if both strings' first characters are the same, compare the second characters the same way.
4. Repeat until the end of either string.
5. If both strings end at the same length, then they are equal. Otherwise, the longer string is greater.

In the examples above, the comparison `'Z' > 'A'` gets to a result at the first step while the strings `"Glow"` and `"Glee"` are compared character-by-character:

1. `G` is the same as `G`.
2. `l` is the same as `l`.
3. `o` is greater than `e`. Stop here. The first string is greater.

The comparison algorithm given above is roughly equivalent to the one used in dictionaries or phone books, but it's not exactly the same.

For instance, case matters. A capital letter `"A"` is not equal to the lowercase `"a"`. Which one is greater? The lowercase `"a"`. Why? Because the lowercase character has a greater index in the internal encoding table JavaScript uses (Unicode). We'll get back to specific details and consequences of this in the chapter <info:string>.

## Comparison of different types

When comparing values of different types, JavaScript converts the values to numbers.

For example:

```js run
alert( '2' > 1 ); // true, string '2' becomes a number 2
alert( '01' == 1 ); // true, string '01' becomes a number 1
```

For boolean values, `true` becomes `1` and `false` becomes `0`.

For example:

```js run
alert( true == 1 ); // true
alert( false == 0 ); // true
```

It is possible that at the same time:

- Two values are equal.
- One of them is `true` as a boolean and the other one is `false` as a boolean.

For example:

```js run
let a = 0;
alert( Boolean(a) ); // false

let b = "0";
alert( Boolean(b) ); // true

alert(a == b); // true!
```

From JavaScript's standpoint, this result is quite normal. An equality check converts values using the numeric conversion (hence `"0"` becomes `0`), while the explicit `Boolean` conversion uses another set of rules.


## Strict equality

A regular equality check `==` has a problem. It cannot differentiate `0` from `false`:

```js run
alert( 0 == false ); // true
```

The same thing happens with an empty string:

```js run
alert( '' == false ); // true
```

This happens because operands of different types are converted to numbers by the equality operator `==`. An empty string, just like `false`, becomes a zero.

What to do if we'd like to differentiate `0` from `false`?

**A strict equality operator `===` checks the equality without type conversion.**

In other words, if `a` and `b` are of different types, then `a === b` immediately returns `false` without an attempt to convert them.

Let's try it:

```js run
alert( 0 === false ); // false, because the types are different
```

There is also a "strict non-equality" operator `!==` analogous to `!=`.

The strict equality operator is a bit longer to write, but makes it obvious what's going on and leaves less room for errors.

## Comparison with null and undefined

There's a non-intuitive behavior when `null` or `undefined` are compared to other values.

For a strict equality check `===`
: These values are different, because each of them is a different type.

    ```js run
    alert( null === undefined ); // false
    ```

For a non-strict check `==`
: There's a special rule. These two are a "sweet couple": they equal each other (in the sense of `==`), but not any other value.

    ```js run
    alert( null == undefined ); // true
    ```

For maths and other comparisons `< > <= >=`
: `null/undefined` are converted to numbers: `null` becomes `0`, while `undefined` becomes `NaN`.

Now let's see some funny things that happen when we apply these rules. And, what's more important, how to not fall into a trap with them.

### Strange result: null vs 0

Let's compare `null` with a zero:

```js run
alert( null > 0 );  // (1) false
alert( null == 0 ); // (2) false
alert( null >= 0 ); // (3) true
```

Mathematically, that's strange. The last result states that "`null` is greater than or equal to zero", so in one of the comparisons above it must be `true`, but they are both false.

The reason is that an equality check `==` and comparisons `> < >= <=` work differently. Comparisons convert `null` to a number, treating it as `0`. That's why (3) `null >= 0` is true and (1) `null > 0` is false.

On the other hand, the equality check `==` for `undefined` and `null` is defined such that, without any conversions, they equal each other and don't equal anything else. That's why (2) `null == 0` is false.

### An incomparable undefined

The value `undefined` shouldn't be compared to other values:

```js run
alert( undefined > 0 ); // false (1)
alert( undefined < 0 ); // false (2)
alert( undefined == 0 ); // false (3)
```

Why does it dislike zero so much? Always false!

We get these results because:

- Comparisons `(1)` and `(2)` return `false` because `undefined` gets converted to `NaN` and `NaN` is a special numeric value which returns `false` for all comparisons.
- The equality check `(3)` returns `false` because `undefined` only equals `null`, `undefined`, and no other value.

### Avoid problems

Why did we go over these examples? Should we remember these peculiarities all the time? Well, not really. Actually, these tricky things will gradually become familiar over time, but there's a solid way to avoid problems with them:

- Treat any comparison with `undefined/null` except the strict equality `===` with exceptional care.
- Don't use comparisons `>= > < <=` with a variable which may be `null/undefined`, unless you're really sure of what you're doing. If a variable can have these values, check for them separately.

## Summary

- Comparison operators return a boolean value.
- Strings are compared letter-by-letter in the "dictionary" order.
- When values of different types are compared, they get converted to numbers (with the exclusion of a strict equality check).
- The values `null` and `undefined` equal `==` each other and do not equal any other value.
- Be careful when using comparisons like `>` or `<` with variables that can occasionally be `null/undefined`. Checking for `null/undefined` separately is a good idea.
# Conditional branching: if, '?'

Sometimes, we need to perform different actions based on different conditions.

To do that, we can use the `if` statement and the conditional operator `?`, that's also called a "question mark" operator.

## The "if" statement

The `if(...)` statement evaluates a condition in parentheses and, if the result is `true`, executes a block of code.

For example:

```js run
let year = prompt('In which year was ECMAScript-2015 specification published?', '');


if (year == 2015) alert( 'You are right!' );

```

In the example above, the condition is a simple equality check (`year == 2015`), but it can be much more complex.

If we want to execute more than one statement, we have to wrap our code block inside curly braces:

```js
if (year == 2015) {
  alert( "That's correct!" );
  alert( "You're so smart!" );
}
```

We recommend wrapping your code block with curly braces `{}` every time you use an `if` statement, even if there is only one statement to execute. Doing so improves readability.

## Boolean conversion

The `if (…)` statement evaluates the expression in its parentheses and converts the result to a boolean.

Let's recall the conversion rules from the chapter <info:type-conversions>:

- A number `0`, an empty string `""`, `null`, `undefined`, and `NaN` all become `false`. Because of that they are called "falsy" values.
- Other values become `true`, so they are called "truthy".

So, the code under this condition would never execute:

```js
if (0) { // 0 is falsy
  ...
}
```

...and inside this condition -- it always will:

```js
if (1) { // 1 is truthy
  ...
}
```

We can also pass a pre-evaluated boolean value to `if`, like this:

```js
let cond = (year == 2015); // equality evaluates to true or false

if (cond) {
  ...
}
```

## The "else" clause

The `if` statement may contain an optional "else" block. It executes when the condition is false.

For example:
```js run
let year = prompt('In which year was the ECMAScript-2015 specification published?', '');

if (year == 2015) {
  alert( 'You guessed it right!' );
} else {
  alert( 'How can you be so wrong?' ); // any value except 2015
}
```

## Several conditions: "else if"

Sometimes, we'd like to test several variants of a condition. The `else if` clause lets us do that.

For example:

```js run
let year = prompt('In which year was the ECMAScript-2015 specification published?', '');

if (year < 2015) {
  alert( 'Too early...' );
} else if (year > 2015) {
  alert( 'Too late' );
} else {
  alert( 'Exactly!' );
}
```

In the code above, JavaScript first checks `year < 2015`. If that is falsy, it goes to the next condition `year > 2015`. If that is also falsy, it shows the last `alert`.

There can be more `else if` blocks. The final `else` is optional.

## Conditional operator '?'

Sometimes, we need to assign a variable depending on a condition.

For instance:

```js run no-beautify
let accessAllowed;
let age = prompt('How old are you?', '');


if (age > 18) {
  accessAllowed = true;
} else {
  accessAllowed = false;
}


alert(accessAllowed);
```

The so-called "conditional" or "question mark" operator lets us do that in a shorter and simpler way.

The operator is represented by a question mark `?`. Sometimes it's called "ternary", because the operator has three operands. It is actually the one and only operator in JavaScript which has that many.

The syntax is:
```js
let result = condition ? value1 : value2;
```

The `condition` is evaluated: if it's truthy then `value1` is returned, otherwise -- `value2`.

For example:

```js
let accessAllowed = (age > 18) ? true : false;
```

Technically, we can omit the parentheses around `age > 18`. The question mark operator has a low precedence, so it executes after the comparison `>`.

This example will do the same thing as the previous one:

```js
// the comparison operator "age > 18" executes first anyway
// (no need to wrap it into parentheses)
let accessAllowed = age > 18 ? true : false;
```

But parentheses make the code more readable, so we recommend using them.

smart
In the example above, you can avoid using the question mark operator because the comparison itself returns `true/false`:

```js
// the same
let accessAllowed = age > 18;
```


## Multiple '?'

A sequence of question mark operators `?` can return a value that depends on more than one condition.

For instance:
```js run
let age = prompt('age?', 18);

let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';

alert( message );
```

It may be difficult at first to grasp what's going on. But after a closer look, we can see that it's just an ordinary sequence of tests:

1. The first question mark checks whether `age < 3`.
2. If true -- it returns `'Hi, baby!'`. Otherwise, it continues to the expression after the colon '":"', checking `age < 18`.
3. If that's true -- it returns `'Hello!'`. Otherwise, it continues to the expression after the next colon '":"', checking `age < 100`.
4. If that's true -- it returns `'Greetings!'`. Otherwise, it continues to the expression after the last colon '":"', returning `'What an unusual age!'`.

Here's how this looks using `if..else`:

```js
if (age < 3) {
  message = 'Hi, baby!';
} else if (age < 18) {
  message = 'Hello!';
} else if (age < 100) {
  message = 'Greetings!';
} else {
  message = 'What an unusual age!';
}
```

## Non-traditional use of '?'

Sometimes the question mark `?` is used as a replacement for `if`:

```js run no-beautify
let company = prompt('Which company created JavaScript?', '');


(company == 'Netscape') ?
   alert('Right!') : alert('Wrong.');

```

Depending on the condition `company == 'Netscape'`, either the first or the second expression after the `?` gets executed and shows an alert.

We don't assign a result to a variable here. Instead, we execute different code depending on the condition.

**It's not recommended to use the question mark operator in this way.**

The notation is shorter than the equivalent `if` statement, which appeals to some programmers. But it is less readable.

Here is the same code using `if` for comparison:

```js run no-beautify
let company = prompt('Which company created JavaScript?', '');


if (company == 'Netscape') {
  alert('Right!');
} else {
  alert('Wrong.');
}

```

Our eyes scan the code vertically. Code blocks which span several lines are easier to understand than a long, horizontal instruction set.

The purpose of the question mark operator `?` is to return one value or another depending on its condition. Please use it for exactly that. Use `if` when you need to execute different branches of code.
# Logical operators

There are three logical operators in JavaScript: `||` (OR), `&&` (AND), `!` (NOT).

Although they are called "logical", they can be applied to values of any type, not only boolean. Their result can also be of any type.

Let's see the details.

## || (OR)

The "OR" operator is represented with two vertical line symbols:

```js
result = a || b;
```

In classical programming, the logical OR is meant to manipulate boolean values only. If any of its arguments are `true`, it returns `true`, otherwise it returns `false`.

In JavaScript, the operator is a little bit trickier and more powerful. But first, let's see what happens with boolean values.

There are four possible logical combinations:

```js run
alert( true || true );   // true
alert( false || true );  // true
alert( true || false );  // true
alert( false || false ); // false
```

As we can see, the result is always `true` except for the case when both operands are `false`.

If an operand is not a boolean, it's converted to a boolean for the evaluation.

For instance, the number `1` is treated as `true`, the number `0` as `false`:

```js run
if (1 || 0) { // works just like if( true || false )
  alert( 'truthy!' );
}
```

Most of the time, OR `||` is used in an `if` statement to test if *any* of the given conditions is `true`.

For example:

```js run
let hour = 9;


if (hour < 10 || hour > 18) {

  alert( 'The office is closed.' );
}
```

We can pass more conditions:

```js run
let hour = 12;
let isWeekend = true;

if (hour < 10 || hour > 18 || isWeekend) {
  alert( 'The office is closed.' ); // it is the weekend
}
```

## OR "||" finds the first truthy value

The logic described above is somewhat classical. Now, let's bring in the "extra" features of JavaScript.

The extended algorithm works as follows.

Given multiple OR'ed values:

```js
result = value1 || value2 || value3;
```

The OR `||` operator does the following:

- Evaluates operands from left to right.
- For each operand, converts it to boolean. If the result is `true`, stops and returns the original value of that operand.
- If all operands have been evaluated (i.e. all were `false`), returns the last operand.

A value is returned in its original form, without the conversion.

In other words, a chain of OR `"||"` returns the first truthy value or the last one if no truthy value is found.

For instance:

```js run
alert( 1 || 0 ); // 1 (1 is truthy)

alert( null || 1 ); // 1 (1 is the first truthy value)
alert( null || 0 || 1 ); // 1 (the first truthy value)

alert( undefined || null || 0 ); // 0 (all falsy, returns the last value)
```

This leads to some interesting usage compared to a "pure, classical, boolean-only OR".

1. **Getting the first truthy value from a list of variables or expressions.**

    For instance, we have `firstName`, `lastName` and `nickName` variables, all optional.

    Let's use OR `||` to choose the one that has the data and show it (or `anonymous` if nothing set):

    ```js run
    let firstName = "";
    let lastName = "";
    let nickName = "SuperCoder";

    
    alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder
    
    ```

    If all variables were falsy, `Anonymous` would show up.

2. **Short-circuit evaluation.**

    Another feature of OR `||` operator is the so-called "short-circuit" evaluation.

    It means that `||` processes its arguments until the first truthy value is reached, and then the value is returned immediately, without even touching the other argument.

    That importance of this feature becomes obvious if an operand isn't just a value, but an expression with a side effect, such as a variable assignment or a function call.

    In the example below, only the second message is printed:

    ```js run no-beautify
    true || alert("not printed");
    false || alert("printed");
    ```

    In the first line, the OR `||` operator stops the evaluation immediately upon seeing `true`, so the `alert` isn't run.

    Sometimes, people use this feature to execute commands only if the condition on the left part is falsy.

## && (AND)

The AND operator is represented with two ampersands `&&`:

```js
result = a && b;
```

In classical programming, AND returns `true` if both operands are truthy and `false` otherwise:

```js run
alert( true && true );   // true
alert( false && true );  // false
alert( true && false );  // false
alert( false && false ); // false
```

An example with `if`:

```js run
let hour = 12;
let minute = 30;

if (hour == 12 && minute == 30) {
  alert( 'The time is 12:30' );
}
```

Just as with OR, any value is allowed as an operand of AND:

```js run
if (1 && 0) { // evaluated as true && false
  alert( "won't work, because the result is falsy" );
}
```


## AND "&&" finds the first falsy value

Given multiple AND'ed values:

```js
result = value1 && value2 && value3;
```

The AND `&&` operator does the following:

- Evaluates operands from left to right.
- For each operand, converts it to a boolean. If the result is `false`, stops and returns the original value of that operand.
- If all operands have been evaluated (i.e. all were truthy), returns the last operand.

In other words, AND returns the first falsy value or the last value if none were found.

The rules above are similar to OR. The difference is that AND returns the first *falsy* value while OR returns the first *truthy* one.

Examples:

```js run
// if the first operand is truthy,
// AND returns the second operand:
alert( 1 && 0 ); // 0
alert( 1 && 5 ); // 5

// if the first operand is falsy,
// AND returns it. The second operand is ignored
alert( null && 5 ); // null
alert( 0 && "no matter what" ); // 0
```

We can also pass several values in a row. See how the first falsy one is returned:

```js run
alert( 1 && 2 && null && 3 ); // null
```

When all values are truthy, the last value is returned:

```js run
alert( 1 && 2 && 3 ); // 3, the last one
```

The precedence of AND `&&` operator is higher than OR `||`.

So the code `a && b || c && d` is essentially the same as if the `&&` expressions were in parentheses: `(a && b) || (c && d)`.



Sometimes, people use the AND `&&` operator as a "shorter to write `if`".

For instance:

```js run
let x = 1;

(x > 0) && alert( 'Greater than zero!' );
```

The action in the right part of `&&` would execute only if the evaluation reaches it. That is, only if `(x > 0)` is true.

So we basically have an analogue for:

```js run
let x = 1;

if (x > 0) alert( 'Greater than zero!' );
```

Although, the variant with `&&` appears shorter, `if` is more obvious and tends to be a little bit more readable. So we recommend using every construct for its purpose: use `if` if we want if and use `&&` if we want AND.



## ! (NOT)

The boolean NOT operator is represented with an exclamation sign `!`.

The syntax is pretty simple:

```js
result = !value;
```

The operator accepts a single argument and does the following:

1. Converts the operand to boolean type: `true/false`.
2. Returns the inverse value.

For instance:

```js run
alert( !true ); // false
alert( !0 ); // true
```

A double NOT `!!` is sometimes used for converting a value to boolean type:

```js run
alert( !!"non-empty string" ); // true
alert( !!null ); // false
```

That is, the first NOT converts the value to boolean and returns the inverse, and the second NOT inverses it again. In the end, we have a plain value-to-boolean conversion.

There's a little more verbose way to do the same thing -- a built-in `Boolean` function:

```js run
alert( Boolean("non-empty string") ); // true
alert( Boolean(null) ); // false
```

The precedence of NOT `!` is the highest of all logical operators, so it always executes first, before `&&` or `||`.
# Nullish coalescing operator '??'

[recent browser="new"]

The nullish coalescing operator `??` provides a short syntax for selecting a first "defined" variable from the list.

The result of `a ?? b` is:
- `a` if it's not `null` or `undefined`,
- `b`, otherwise.

So, `x = a ?? b` is a short equivalent to:

```js
x = (a !== null && a !== undefined) ? a : b;
```

Here's a longer example.

Imagine, we have a user, and there are variables `firstName`, `lastName` or `nickName` for their first name, last name and the nick name. All of them may be undefined, if the user decided not to enter any value.

We'd like to display the user name: one of these three variables, or show "Anonymous" if nothing is set.

Let's use the `??` operator to select the first defined one:

```js run
let firstName = null;
let lastName = null;
let nickName = "Supercoder";

// show the first not-null/undefined value

alert(firstName ?? lastName ?? nickName ?? "Anonymous"); // Supercoder

```

## Comparison with ||

The OR `||` operator can be used in the same way as `??`. Actually, we can replace `??` with `||` in the code above and get the same result, as it was described in the [previous chapter](info:logical-operators#or-finds-the-first-truthy-value).

The important difference is that:
- `||` returns the first *truthy* value.
- `??` returns the first *defined* value.

This matters a lot when we'd like to treat `null/undefined` differently from `0`.

For example, consider this:

```js
height = height ?? 100;
```

This sets `height` to `100` if it's not defined.

Let's compare it with `||`:

```js run
let height = 0;

alert(height || 100); // 100
alert(height ?? 100); // 0
```

Here, `height || 100` treats zero height as unset, same as `null`, `undefined` or any other falsy value. So the result is `100`.

The `height ?? 100` returns `100` only if `height` is exactly `null` or `undefined`. So the `alert` shows the height value `0` "as is".

Which behavior is better depends on a particular use case. When zero height is a valid value, then `??` is preferrable.

## Precedence

The precedence of the `??` operator is rather low: `5` in the [MDN table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence#Table).

So `??` is evaluated after most other operations, but before `=` and `?`.

If we need to choose a value with `??` in a complex expression, then consider adding parentheses:

```js run
let height = null;
let width = null;

// important: use parentheses
let area = (height ?? 100) * (width ?? 50);

alert(area); // 5000
```

Otherwise, if we omit parentheses, `*` has the higher precedence than `??` and would run first.

That would work be the same as:

```js
// probably not correct
let area = height ?? (100 * width) ?? 50;
```

There's also a related language-level limitation.

**Due to safety reasons, it's forbidden to use `??` together with `&&` and `||` operators.**

The code below triggers a syntax error:

```js run
let x = 1 && 2 ?? 3; // Syntax error
```

The limitation is surely debatable, but it was added to the language specification with the purpose to avoid programming mistakes, as people start to switch to `??` from `||`.

Use explicit parentheses to work around it:

```js run

let x = (1 && 2) ?? 3; // Works


alert(x); // 2
```

## Summary

- The nullish coalescing operator `??` provides a short way to choose a "defined" value from the list.

    It's used to assign default values to variables:

    ```js
    // set height=100, if height is null or undefined
    height = height ?? 100;
    ```

- The operator `??` has a very low precedence, a bit higher than `?` and `=`.
- It's forbidden to use it with `||` or `&&` without explicit parentheses.
# Loops: while and for

We often need to repeat actions.

For example, outputting goods from a list one after another or just running the same code for each number from 1 to 10.

*Loops* are a way to repeat the same code multiple times.

## The "while" loop

The `while` loop has the following syntax:

```js
while (condition) {
  // code
  // so-called "loop body"
}
```

While the `condition` is truthy, the `code` from the loop body is executed.

For instance, the loop below outputs `i` while `i < 3`:

```js run
let i = 0;
while (i < 3) { // shows 0, then 1, then 2
  alert( i );
  i++;
}
```

A single execution of the loop body is called *an iteration*. The loop in the example above makes three iterations.

If `i++` was missing from the example above, the loop would repeat (in theory) forever. In practice, the browser provides ways to stop such loops, and in server-side JavaScript, we can kill the process.

Any expression or variable can be a loop condition, not just comparisons: the condition is evaluated and converted to a boolean by `while`.

For instance, a shorter way to write `while (i != 0)` is `while (i)`:

```js run
let i = 3;

while (i) { // when i becomes 0, the condition becomes falsy, and the loop stops

  alert( i );
  i--;
}
```

If the loop body has a single statement, we can omit the curly braces `{…}`:

```js run
let i = 3;

while (i) alert(i--);

```


## The "do..while" loop

The condition check can be moved *below* the loop body using the `do..while` syntax:

```js
do {
  // loop body
} while (condition);
```

The loop will first execute the body, then check the condition, and, while it's truthy, execute it again and again.

For example:

```js run
let i = 0;
do {
  alert( i );
  i++;
} while (i < 3);
```

This form of syntax should only be used when you want the body of the loop to execute **at least once** regardless of the condition being truthy. Usually, the other form is preferred: `while(…) {…}`.

## The "for" loop

The `for` loop is more complex, but it's also the most commonly used loop.

It looks like this:

```js
for (begin; condition; step) {
  // ... loop body ...
}
```

Let's learn the meaning of these parts by example. The loop below runs `alert(i)` for `i` from `0` up to (but not including) `3`:

```js run
for (let i = 0; i < 3; i++) { // shows 0, then 1, then 2
  alert(i);
}
```

Let's examine the `for` statement part-by-part:

| part      |            |                                                                |
| --------- | ---------- | -------------------------------------------------------------- |
| begin     | `i = 0`    | Executes once upon entering the loop.                          |
| condition | `i < 3`    | Checked before every loop iteration. If false, the loop stops. |
| body      | `alert(i)` | Runs again and again while the condition is truthy.            |
| step      | `i++`      | Executes after the body on each iteration.                     |

The general loop algorithm works like this:

```
Run begin
→ (if condition → run body and run step)
→ (if condition → run body and run step)
→ (if condition → run body and run step)
→ ...
```

That is, `begin` executes once, and then it iterates: after each `condition` test, `body` and `step` are executed.

If you are new to loops, it could help to go back to the example and reproduce how it runs step-by-step on a piece of paper.

Here's exactly what happens in our case:

```js
// for (let i = 0; i < 3; i++) alert(i)

// run begin
let i = 0
// if condition → run body and run step
if (i < 3) { alert(i); i++ }
// if condition → run body and run step
if (i < 3) { alert(i); i++ }
// if condition → run body and run step
if (i < 3) { alert(i); i++ }
// ...finish, because now i == 3
```
Here, the "counter" variable `i` is declared right in the loop. This is called an "inline" variable declaration. Such variables are visible only inside the loop.

```js run
for (let i = 0; i < 3; i++) {
  alert(i); // 0, 1, 2
}
alert(i); // error, no such variable
```

Instead of defining a variable, we could use an existing one:

```js run
let i = 0;

for (i = 0; i < 3; i++) { // use an existing variable
  alert(i); // 0, 1, 2
}

alert(i); // 3, visible, because declared outside of the loop
```




### Skipping parts

Any part of `for` can be skipped.

For example, we can omit `begin` if we don't need to do anything at the loop start.

Like here:

```js run
let i = 0; // we have i already declared and assigned

for (; i < 3; i++) { // no need for "begin"
  alert( i ); // 0, 1, 2
}
```

We can also remove the `step` part:

```js run
let i = 0;

for (; i < 3;) {
  alert( i++ );
}
```

This makes the loop identical to `while (i < 3)`.

We can actually remove everything, creating an infinite loop:

```js
for (;;) {
  // repeats without limits
}
```

Please note that the two `for` semicolons `;` must be present. Otherwise, there would be a syntax error.

## Breaking the loop

Normally, a loop exits when its condition becomes falsy.

But we can force the exit at any time using the special `break` directive.

For example, the loop below asks the user for a series of numbers, "breaking" when no number is entered:

```js run
let sum = 0;

while (true) {

  let value = +prompt("Enter a number", '');


  if (!value) break; // (*)


  sum += value;

}
alert( 'Sum: ' + sum );
```

The `break` directive is activated at the line `(*)` if the user enters an empty line or cancels the input. It stops the loop immediately, passing control to the first line after the loop. Namely, `alert`.

The combination "infinite loop + `break` as needed" is great for situations when a loop's condition must be checked not in the beginning or end of the loop, but in the middle or even in several places of its body.

## Continue to the next iteration [#continue]

The `continue` directive is a "lighter version" of `break`. It doesn't stop the whole loop. Instead, it stops the current iteration and forces the loop to start a new one (if the condition allows).

We can use it if we're done with the current iteration and would like to move on to the next one.

The loop below uses `continue` to output only odd values:

```js run no-beautify
for (let i = 0; i < 10; i++) {

  // if true, skip the remaining part of the body
  if (i % 2 == 0) continue;

  alert(i); // 1, then 3, 5, 7, 9
}
```

For even values of `i`, the `continue` directive stops executing the body and passes control to the next iteration of `for` (with the next number). So the `alert` is only called for odd values.

A loop that shows odd values could look like this:

```js run
for (let i = 0; i < 10; i++) {

  if (i % 2) {
    alert( i );
  }

}
```

From a technical point of view, this is identical to the example above. Surely, we can just wrap the code in an `if` block instead of using `continue`.

But as a side-effect, this created one more level of nesting (the `alert` call inside the curly braces). If the code inside of `if` is longer than a few lines, that may decrease the overall readability.



Please note that syntax constructs that are not expressions cannot be used with the ternary operator `?`. In particular, directives such as `break/continue` aren't allowed there.

For example, if we take this code:

```js
if (i > 5) {
  alert(i);
} else {
  continue;
}
```

...and rewrite it using a question mark:


```js no-beautify
(i > 5) ? alert(i) : continue; // continue isn't allowed here
```

...it stops working: there's a syntax error.

This is just another reason not to use the question mark operator `?` instead of `if`.


## Labels for break/continue

Sometimes we need to break out from multiple nested loops at once.

For example, in the code below we loop over `i` and `j`, prompting for the coordinates `(i, j)` from `(0,0)` to `(2,2)`:

```js run no-beautify
for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    let input = prompt(`Value at coords (${i},${j})`, '');

    // what if we want to exit from here to Done (below)?
  }
}

alert('Done!');
```

We need a way to stop the process if the user cancels the input.

The ordinary `break` after `input` would only break the inner loop. That's not sufficient--labels, come to the rescue!

A *label* is an identifier with a colon before a loop:
```js
labelName: for (...) {
  ...
}
```

The `break <labelName>` statement in the loop below breaks out to the label:

```js run no-beautify
outer: for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    let input = prompt(`Value at coords (${i},${j})`, '');

    // if an empty string or canceled, then break out of both loops
    if (!input) break outer; // (*)

    // do something with the value...
  }
}
alert('Done!');
```

In the code above, `break outer` looks upwards for the label named `outer` and breaks out of that loop.

So the control goes straight from `(*)` to `alert('Done!')`.

We can also move the label onto a separate line:

```js no-beautify
outer:
for (let i = 0; i < 3; i++) { ... }
```

The `continue` directive can also be used with a label. In this case, code execution jumps to the next iteration of the labeled loop.


Labels do not allow us to jump into an arbitrary place in the code.

For example, it is impossible to do this:
```js
break label; // doesn't jumps to the label below

label: for (...)
```

A call to `break/continue` is only possible from inside a loop and the label must be somewhere above the directive.


## Summary

We covered 3 types of loops:

- `while` -- The condition is checked before each iteration.
- `do..while` -- The condition is checked after each iteration.
- `for (;;)` -- The condition is checked before each iteration, additional settings available.

To make an "infinite" loop, usually the `while(true)` construct is used. Such a loop, just like any other, can be stopped with the `break` directive.

If we don't want to do anything in the current iteration and would like to forward to the next one, we can use the `continue` directive.

`break/continue` support labels before the loop. A label is the only way for `break/continue` to escape a nested loop to go to an outer one.
# The "switch" statement

A `switch` statement can replace multiple `if` checks.

It gives a more descriptive way to compare a value with multiple variants.

## The syntax

The `switch` has one or more `case` blocks and an optional default.

It looks like this:

```js no-beautify
switch(x) {
  case 'value1':  // if (x === 'value1')
    ...
    [break]

  case 'value2':  // if (x === 'value2')
    ...
    [break]

  default:
    ...
    [break]
}
```

- The value of `x` is checked for a strict equality to the value from the first `case` (that is, `value1`) then to the second (`value2`) and so on.
- If the equality is found, `switch` starts to execute the code starting from the corresponding `case`, until the nearest `break` (or until the end of `switch`).
- If no case is matched then the `default` code is executed (if it exists).

## An example

An example of `switch` (the executed code is highlighted):

```js run
let a = 2 + 2;

switch (a) {
  case 3:
    alert( 'Too small' );
    break;

  case 4:
    alert( 'Exactly!' );
    break;

  case 5:
    alert( 'Too large' );
    break;
  default:
    alert( "I don't know such values" );
}
```

Here the `switch` starts to compare `a` from the first `case` variant that is `3`. The match fails.

Then `4`. That's a match, so the execution starts from `case 4` until the nearest `break`.

**If there is no `break` then the execution continues with the next `case` without any checks.**

An example without `break`:

```js run
let a = 2 + 2;

switch (a) {
  case 3:
    alert( 'Too small' );

  case 4:
    alert( 'Exactly!' );
  case 5:
    alert( 'Too big' );
  default:
    alert( "I don't know such values" );

}
```

In the example above we'll see sequential execution of three `alert`s:

```js
alert( 'Exactly!' );
alert( 'Too big' );
alert( "I don't know such values" );
```

Both `switch` and `case` allow arbitrary expressions.

For example:

```js run
let a = "1";
let b = 0;

switch (+a) {

  case b + 1:
    alert("this runs, because +a is 1, exactly equals b+1");
    break;


  default:
    alert("this doesn't run");
}
```
Here `+a` gives `1`, that's compared with `b + 1` in `case`, and the corresponding code is executed.


## Grouping of "case"

Several variants of `case` which share the same code can be grouped.

For example, if we want the same code to run for `case 3` and `case 5`:

```js run no-beautify
let a = 3;

switch (a) {
  case 4:
    alert('Right!');
    break;


  case 3: // (*) grouped two cases
  case 5:
    alert('Wrong!');
    alert("Why don't you take a math class?");
    break;


  default:
    alert('The result is strange. Really.');
}
```

Now both `3` and `5` show the same message.

The ability to "group" cases is a side-effect of how `switch/case` works without `break`. Here the execution of `case 3` starts from the line `(*)` and goes through `case 5`, because there's no `break`.

## Type matters

Let's emphasize that the equality check is always strict. The values must be of the same type to match.

For example, let's consider the code:

```js run
let arg = prompt("Enter a value?");
switch (arg) {
  case '0':
  case '1':
    alert( 'One or zero' );
    break;

  case '2':
    alert( 'Two' );
    break;

  case 3:
    alert( 'Never executes!' );
    break;
  default:
    alert( 'An unknown value' );
}
```

1. For `0`, `1`, the first `alert` runs.
2. For `2` the second `alert` runs.
3. But for `3`, the result of the `prompt` is a string `"3"`, which is not strictly equal `===` to the number `3`. So we've got a dead code in `case 3`! The `default` variant will execute.
# Functions

Quite often we need to perform a similar action in many places of the script.

For example, we need to show a nice-looking message when a visitor logs in, logs out and maybe somewhere else.

Functions are the main "building blocks" of the program. They allow the code to be called many times without repetition.

We've already seen examples of built-in functions, like `alert(message)`, `prompt(message, default)` and `confirm(question)`. But we can create functions of our own as well.

## Function Declaration

To create a function we can use a *function declaration*.

It looks like this:

```js
function showMessage() {
  alert( 'Hello everyone!' );
}
```

The `function` keyword goes first, then goes the *name of the function*, then a list of *parameters* between the parentheses (comma-separated, empty in the example above) and finally the code of the function, also named "the function body", between curly braces.

```js
function name(parameters) {
  ...body...
}
```

Our new function can be called by its name: `showMessage()`.

For instance:

```js run
function showMessage() {
  alert( 'Hello everyone!' );
}


showMessage();
showMessage();

```

The call `showMessage()` executes the code of the function. Here we will see the message two times.

This example clearly demonstrates one of the main purposes of functions: to avoid code duplication.

If we ever need to change the message or the way it is shown, it's enough to modify the code in one place: the function which outputs it.

## Local variables

A variable declared inside a function is only visible inside that function.

For example:

```js run
function showMessage() {

  let message = "Hello, I'm JavaScript!"; // local variable


  alert( message );
}

showMessage(); // Hello, I'm JavaScript!

alert( message ); // <-- Error! The variable is local to the function
```

## Outer variables

A function can access an outer variable as well, for example:

```js run no-beautify
let userName = 'John';

function showMessage() {
  let message = 'Hello, ' + userName;
  alert(message);
}

showMessage(); // Hello, John
```

The function has full access to the outer variable. It can modify it as well.

For instance:

```js run
let userName = 'John';

function showMessage() {
  userName = "Bob"; // (1) changed the outer variable

  let message = 'Hello, ' + userName;
  alert(message);
}

alert( userName ); // John before the function call

showMessage();

alert( userName ); // Bob, the value was modified by the function
```

The outer variable is only used if there's no local one.

If a same-named variable is declared inside the function then it *shadows* the outer one. For instance, in the code below the function uses the local `userName`. The outer one is ignored:

```js run
let userName = 'John';

function showMessage() {

  let userName = "Bob"; // declare a local variable


  let message = 'Hello, ' + userName; // Bob
  alert(message);
}

// the function will create and use its own userName
showMessage();

alert( userName ); // John, unchanged, the function did not access the outer variable
```

Variables declared outside of any function, such as the outer `userName` in the code above, are called *global*.

Global variables are visible from any function (unless shadowed by locals).

It's a good practice to minimize the use of global variables. Modern code has few or no globals. Most variables reside in their functions. Sometimes though, they can be useful to store project-level data.

## Parameters

We can pass arbitrary data to functions using parameters (also called *function arguments*) .

In the example below, the function has two parameters: `from` and `text`.

```js run
function showMessage(from, text) { // arguments: from, text
  alert(from + ': ' + text);
}


showMessage('Ann', 'Hello!'); // Ann: Hello! (*)
showMessage('Ann', "What's up?"); // Ann: What's up? (**)

```

When the function is called in lines `(*)` and `(**)`, the given values are copied to local variables `from` and `text`. Then the function uses them.

Here's one more example: we have a variable `from` and pass it to the function. Please note: the function changes `from`, but the change is not seen outside, because a function always gets a copy of the value:


```js run
function showMessage(from, text) {


  from = '*' + from + '*'; // make "from" look nicer


  alert( from + ': ' + text );
}

let from = "Ann";

showMessage(from, "Hello"); // *Ann*: Hello

// the value of "from" is the same, the function modified a local copy
alert( from ); // Ann
```

## Default values

If a parameter is not provided, then its value becomes `undefined`.

For instance, the aforementioned function `showMessage(from, text)` can be called with a single argument:

```js
showMessage("Ann");
```

That's not an error. Such a call would output `"Ann: undefined"`. There's no `text`, so it's assumed that `text === undefined`.

If we want to use a "default" `text` in this case, then we can specify it after `=`:

```js run
function showMessage(from, text = "no text given") {
  alert( from + ": " + text );
}

showMessage("Ann"); // Ann: no text given
```

Now if the `text` parameter is not passed, it will get the value `"no text given"`

Here `"no text given"` is a string, but it can be a more complex expression, which is only evaluated and assigned if the parameter is missing. So, this is also possible:

```js run
function showMessage(from, text = anotherFunction()) {
  // anotherFunction() only executed if no text given
  // its result becomes the value of text
}
```

In JavaScript, a default parameter is evaluated every time the function is called without the respective parameter.

In the example above, `anotherFunction()` is called every time `showMessage()` is called without the `text` parameter.

### Alternative default parameters

Sometimes it makes sense to set default values for parameters not in the function declaration, but at a later stage, during its execution.

To check for an omitted parameter, we can compare it with `undefined`:

```js run
function showMessage(text) {

  if (text === undefined) {
    text = 'empty message';
  }


  alert(text);
}

showMessage(); // empty message
```

...Or we could use the `||` operator:

```js
// if text parameter is omitted or "" is passed, set it to 'empty'
function showMessage(text) {
  text = text || 'empty';
  ...
}
```

Modern JavaScript engines support the [nullish coalescing operator](info:nullish-coalescing-operator) `??`, it's better when falsy values, such as `0`, are considered regular:

```js run
// if there's no "count" parameter, show "unknown"
function showCount(count) {
  alert(count ?? "unknown");
}

showCount(0); // 0
showCount(null); // unknown
showCount(); // unknown
```

## Returning a value

A function can return a value back into the calling code as the result.

The simplest example would be a function that sums two values:

```js run no-beautify
function sum(a, b) {
  return a + b;
}

let result = sum(1, 2);
alert( result ); // 3
```

The directive `return` can be in any place of the function. When the execution reaches it, the function stops, and the value is returned to the calling code (assigned to `result` above).

There may be many occurrences of `return` in a single function. For instance:

```js run
function checkAge(age) {
  if (age >= 18) {

    return true;

  } else {

    return confirm('Do you have permission from your parents?');

  }
}

let age = prompt('How old are you?', 18);

if ( checkAge(age) ) {
  alert( 'Access granted' );
} else {
  alert( 'Access denied' );
}
```

It is possible to use `return` without a value. That causes the function to exit immediately.

For example:

```js
function showMovie(age) {
  if ( !checkAge(age) ) {

    return;

  }

  alert( "Showing you the movie" ); // (*)
  // ...
}
```

In the code above, if `checkAge(age)` returns `false`, then `showMovie` won't proceed to the `alert`.

If a function does not return a value, it is the same as if it returns `undefined`:

```js run
function doNothing() { /* empty */ }

alert( doNothing() === undefined ); // true
```

An empty `return` is also the same as `return undefined`:

```js run
function doNothing() {
  return;
}

alert( doNothing() === undefined ); // true
```



For a long expression in `return`, it might be tempting to put it on a separate line, like this:

```js
return
 (some + long + expression + or + whatever * f(a) + f(b))
```
That doesn't work, because JavaScript assumes a semicolon after `return`. That'll work the same as:

```js
return;
 (some + long + expression + or + whatever * f(a) + f(b))
```

So, it effectively becomes an empty return.

If we want the returned expression to wrap across multiple lines, we should start it at the same line as `return`. Or at least put the opening parentheses there as follows:

```js
return (
  some + long + expression
  + or +
  whatever * f(a) + f(b)
  )
```
And it will work just as we expect it to.


## Naming a function [#function-naming]

Functions are actions. So their name is usually a verb. It should be brief, as accurate as possible and describe what the function does, so that someone reading the code gets an indication of what the function does.

It is a widespread practice to start a function with a verbal prefix which vaguely describes the action. There must be an agreement within the team on the meaning of the prefixes.

For instance, functions that start with `"show"` usually show something.

Function starting with...

- `"get…"` -- return a value,
- `"calc…"` -- calculate something,
- `"create…"` -- create something,
- `"check…"` -- check something and return a boolean, etc.

Examples of such names:

```js no-beautify
showMessage(..)     // shows a message
getAge(..)          // returns the age (gets it somehow)
calcSum(..)         // calculates a sum and returns the result
createForm(..)      // creates a form (and usually returns it)
checkPermission(..) // checks a permission, returns true/false
```

With prefixes in place, a glance at a function name gives an understanding what kind of work it does and what kind of value it returns.

A function should do exactly what is suggested by its name, no more.

Two independent actions usually deserve two functions, even if they are usually called together (in that case we can make a 3rd function that calls those two).

A few examples of breaking this rule:

- `getAge` -- would be bad if it shows an `alert` with the age (should only get).
- `createForm` -- would be bad if it modifies the document, adding a form to it (should only create it and return).
- `checkPermission` -- would be bad if it displays the `access granted/denied` message (should only perform the check and return the result).

These examples assume common meanings of prefixes. You and your team are free to agree on other meanings, but usually they're not much different. In any case, you should have a firm understanding of what a prefix means, what a prefixed function can and cannot do. All same-prefixed functions should obey the rules. And the team should share the knowledge.


Functions that are used *very often* sometimes have ultrashort names.

For example, the [jQuery](http://jquery.com) framework defines a function with `$`. The [Lodash](http://lodash.com/) library has its core function named `_`.

These are exceptions. Generally functions names should be concise and descriptive.

## Functions == Comments

Functions should be short and do exactly one thing. If that thing is big, maybe it's worth it to split the function into a few smaller functions. Sometimes following this rule may not be that easy, but it's definitely a good thing.

A separate function is not only easier to test and debug -- its very existence is a great comment!

For instance, compare the two functions `showPrimes(n)` below. Each one outputs [prime numbers](https://en.wikipedia.org/wiki/Prime_number) up to `n`.

The first variant uses a label:

```js
function showPrimes(n) {
  nextPrime: for (let i = 2; i < n; i++) {

    for (let j = 2; j < i; j++) {
      if (i % j == 0) continue nextPrime;
    }

    alert( i ); // a prime
  }
}
```

The second variant uses an additional function `isPrime(n)` to test for primality:

```js
function showPrimes(n) {

  for (let i = 2; i < n; i++) {
    if (!isPrime(i)) continue;

    alert(i);  // a prime
  }
}

function isPrime(n) {
  for (let i = 2; i < n; i++) {
    if ( n % i == 0) return false;
  }
  return true;
}
```

The second variant is easier to understand, isn't it? Instead of the code piece we see a name of the action (`isPrime`). Sometimes people refer to such code as *self-describing*.

So, functions can be created even if we don't intend to reuse them. They structure the code and make it readable.

## Summary

A function declaration looks like this:

```js
function name(parameters, delimited, by, comma) {
  /* code */
}
```

- Values passed to a function as parameters are copied to its local variables.
- A function may access outer variables. But it works only from inside out. The code outside of the function doesn't see its local variables.
- A function can return a value. If it doesn't, then its result is `undefined`.

To make the code clean and easy to understand, it's recommended to use mainly local variables and parameters in the function, not outer variables.

It is always easier to understand a function which gets parameters, works with them and returns a result than a function which gets no parameters, but modifies outer variables as a side-effect.

Function naming:

- A name should clearly describe what the function does. When we see a function call in the code, a good name instantly gives us an understanding what it does and returns.
- A function is an action, so function names are usually verbal.
- There exist many well-known function prefixes like `create…`, `show…`, `get…`, `check…` and so on. Use them to hint what a function does.

Functions are the main building blocks of scripts. Now we've covered the basics, so we actually can start creating and using them. But that's only the beginning of the path. We are going to return to them many times, going more deeply into their advanced features.
# Function expressions

In JavaScript, a function is not a "magical language structure", but a special kind of value.

The syntax that we used before is called a *Function Declaration*:

```js
function sayHi() {
  alert( "Hello" );
}
```

There is another syntax for creating a function that is called a *Function Expression*.

It looks like this:

```js
let sayHi = function() {
  alert( "Hello" );
};
```

Here, the function is created and assigned to the variable explicitly, like any other value. No matter how the function is defined, it's just a value stored in the variable `sayHi`.

The meaning of these code samples is the same: "create a function and put it into the variable `sayHi`".

We can even print out that value using `alert`:

```js run
function sayHi() {
  alert( "Hello" );
}


alert( sayHi ); // shows the function code

```

Please note that the last line does not run the function, because there are no parentheses after `sayHi`. There are programming languages where any mention of a function name causes its execution, but JavaScript is not like that.

In JavaScript, a function is a value, so we can deal with it as a value. The code above shows its string representation, which is the source code.

Surely, a function is a special value, in the sense that we can call it like `sayHi()`.

But it's still a value. So we can work with it like with other kinds of values.

We can copy a function to another variable:

```js run no-beautify
function sayHi() {   // (1) create
  alert( "Hello" );
}

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
```

Here's what happens above in detail:

1. The Function Declaration `(1)` creates the function and puts it into the variable named `sayHi`.
2. Line `(2)` copies it into the variable `func`. Please note again: there are no parentheses after `sayHi`. If there were, then `func = sayHi()` would write  *the result of the call* `sayHi()` into `func`, not *the function* `sayHi` itself.
3. Now the function can be called as both `sayHi()` and `func()`.

Note that we could also have used a Function Expression to declare `sayHi`, in the first line:

```js
let sayHi = function() {
  alert( "Hello" );
};

let func = sayHi;
// ...
```

Everything would work the same.


You might wonder, why does Function Expression have a semicolon `;` at the end, but Function Declaration does not:

```js
function sayHi() {
  // ...
}

let sayHi = function() {
  // ...
};
```

The answer is simple:
- There's no need for `;` at the end of code blocks and syntax structures that use them like `if { ... }`, `for {  }`, `function f { }` etc.
- A Function Expression is used inside the statement: `let sayHi = ...;`, as a value. It's not a code block, but rather an assignment. The semicolon `;` is recommended at the end of statements, no matter what the value is. So the semicolon here is not related to the Function Expression itself, it just terminates the statement.


## Callback functions

Let's look at more examples of passing functions as values and using function expressions.

We'll write a function `ask(question, yes, no)` with three parameters:

`question`
: Text of the question

`yes`
: Function to run if the answer is "Yes"

`no`
: Function to run if the answer is "No"

The function should ask the `question` and, depending on the user's answer, call `yes()` or `no()`:

```js run

function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}


function showOk() {
  alert( "You agreed." );
}

function showCancel() {
  alert( "You canceled the execution." );
}

// usage: functions showOk, showCancel are passed as arguments to ask
ask("Do you agree?", showOk, showCancel);
```

In practice, such functions are quite useful. The major difference between a real-life `ask` and the example above is that real-life functions use more complex ways to interact with the user than a simple `confirm`. In the browser, such function usually draws a nice-looking question window. But that's another story.

**The arguments `showOk` and `showCancel` of `ask` are called *callback functions* or just *callbacks*.**

The idea is that we pass a function and expect it to be "called back" later if necessary. In our case, `showOk` becomes the callback for "yes" answer, and `showCancel` for "no" answer.

We can use Function Expressions to write the same function much shorter:

```js run no-beautify
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}


ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);

```

Here, functions are declared right inside the `ask(...)` call. They have no name, and so are called *anonymous*. Such functions are not accessible outside of `ask` (because they are not assigned to variables), but that's just what we want here.

Such code appears in our scripts very naturally, it's in the spirit of JavaScript.

Regular values like strings or numbers represent the *data*.

A function can be perceived as an *action*.

We can pass it between variables and run when we want.


## Function Expression vs Function Declaration

Let's formulate the key differences between Function Declarations and Expressions.

First, the syntax: how to differentiate between them in the code.

- *Function Declaration:* a function, declared as a separate statement, in the main code flow.

    ```js
    // Function Declaration
    function sum(a, b) {
      return a + b;
    }
    ```
- *Function Expression:* a function, created inside an expression or inside another syntax construct. Here, the function is created at the right side of the "assignment expression" `=`:

    ```js
    // Function Expression
    let sum = function(a, b) {
      return a + b;
    };
    ```

The more subtle difference is *when* a function is created by the JavaScript engine.

**A Function Expression is created when the execution reaches it and is usable only from that moment.**

Once the execution flow passes to the right side of the assignment `let sum = function…` -- here we go, the function is created and can be used (assigned, called, etc. ) from now on.

Function Declarations are different.

**A Function Declaration can be called earlier than it is defined.**

For example, a global Function Declaration is visible in the whole script, no matter where it is.

That's due to internal algorithms. When JavaScript prepares to run the script, it first looks for global Function Declarations in it and creates the functions. We can think of it as an "initialization stage".

And after all Function Declarations are processed, the code is executed. So it has access to these functions.

For example, this works:

```js run refresh untrusted

sayHi("John"); // Hello, John


function sayHi(name) {
  alert( `Hello, ${name}` );
}
```

The Function Declaration `sayHi` is created when JavaScript is preparing to start the script and is visible everywhere in it.

...If it were a Function Expression, then it wouldn't work:

```js run refresh untrusted

sayHi("John"); // error!


let sayHi = function(name) {  // (*) no magic any more
  alert( `Hello, ${name}` );
};
```

Function Expressions are created when the execution reaches them. That would happen only in the line `(*)`. Too late.

Another special feature of Function Declarations is their block scope.

**In strict mode, when a Function Declaration is within a code block, it's visible everywhere inside that block. But not outside of it.**

For instance, let's imagine that we need to declare a function `welcome()` depending on the `age` variable that we get during runtime. And then we plan to use it some time later.

If we use Function Declaration, it won't work as intended:

```js run
let age = prompt("What is your age?", 18);

// conditionally declare a function
if (age < 18) {

  function welcome() {
    alert("Hello!");
  }

} else {

  function welcome() {
    alert("Greetings!");
  }

}

// ...use it later

welcome(); // Error: welcome is not defined

```

That's because a Function Declaration is only visible inside the code block in which it resides.

Here's another example:

```js run
let age = 16; // take 16 as an example

if (age < 18) {

  welcome();               // \   (runs)

                           //  |
  function welcome() {     //  |  
    alert("Hello!");       //  |  Function Declaration is available
  }                        //  |  everywhere in the block where it's declared
                           //  |

  welcome();               // /   (runs)


} else {

  function welcome() {    
    alert("Greetings!");
  }
}

// Here we're out of curly braces,
// so we can not see Function Declarations made inside of them.


welcome(); // Error: welcome is not defined

```

What can we do to make `welcome` visible outside of `if`?

The correct approach would be to use a Function Expression and assign `welcome` to the variable that is declared outside of `if` and has the proper visibility.

This code works as intended:

```js run
let age = prompt("What is your age?", 18);

let welcome;

if (age < 18) {

  welcome = function() {
    alert("Hello!");
  };

} else {

  welcome = function() {
    alert("Greetings!");
  };

}


welcome(); // ok now

```

Or we could simplify it even further using a question mark operator `?`:

```js run
let age = prompt("What is your age?", 18);

let welcome = (age < 18) ?
  function() { alert("Hello!"); } :
  function() { alert("Greetings!"); };


welcome(); // ok now

```


As a rule of thumb, when we need to declare a function, the first to consider is Function Declaration syntax. It gives more freedom in how to organize our code, because we can call such functions before they are declared.

That's also better for readability, as it's easier to look up `function f(…) {…}` in the code than `let f = function(…) {…};`. Function Declarations are more "eye-catching".

...But if a Function Declaration does not suit us for some reason, or we need a conditional declaration (we've just seen an example), then Function Expression should be used.

## Summary

- Functions are values. They can be assigned, copied or declared in any place of the code.
- If the function is declared as a separate statement in the main code flow, that's called a "Function Declaration".
- If the function is created as a part of an expression, it's called a "Function Expression".
- Function Declarations are processed before the code block is executed. They are visible everywhere in the block.
- Function Expressions are created when the execution flow reaches them.

In most cases when we need to declare a function, a Function Declaration is preferable, because it is visible prior to the declaration itself. That gives us more flexibility in code organization, and is usually more readable.

So we should use a Function Expression only when a Function Declaration is not fit for the task. We've seen a couple of examples of that in this chapter, and will see more in the future.
# Arrow functions, the basics

There's another very simple and concise syntax for creating functions, that's often better than Function Expressions.

It's called "arrow functions", because it looks like this:

```js
let func = (arg1, arg2, ...argN) => expression
```

...This creates a function `func` that accepts arguments `arg1..argN`, then evaluates the `expression` on the right side with their use and returns its result.

In other words, it's the shorter version of:

```js
let func = function(arg1, arg2, ...argN) {
  return expression;
};
```

Let's see a concrete example:

```js run
let sum = (a, b) => a + b;

/* This arrow function is a shorter form of:

let sum = function(a, b) {
  return a + b;
};
*/

alert( sum(1, 2) ); // 3
```

As you can, see `(a, b) => a + b` means a function that accepts two arguments named `a` and `b`. Upon the execution, it evaluates the expression `a + b` and returns the result.

- If we have only one argument, then parentheses around parameters can be omitted, making that even shorter.

    For example:

    ```js run
    
    let double = n => n * 2;
    // roughly the same as: let double = function(n) { return n * 2 }
    

    alert( double(3) ); // 6
    ```

- If there are no arguments, parentheses will be empty (but they should be present):

    ```js run
    let sayHi = () => alert("Hello!");

    sayHi();
    ```

Arrow functions can be used in the same way as Function Expressions.

For instance, to dynamically create a function:

```js run
let age = prompt("What is your age?", 18);

let welcome = (age < 18) ?
  () => alert('Hello') :
  () => alert("Greetings!");

welcome();
```

Arrow functions may appear unfamiliar and not very readable at first, but that quickly changes as the eyes get used to the structure.

They are very convenient for simple one-line actions, when we're just too lazy to write many words.

## Multiline arrow functions

The examples above took arguments from the left of `=>` and evaluated the right-side expression with them.

Sometimes we need something a little bit more complex, like multiple expressions or statements. It is also possible, but we should enclose them in curly braces. Then use a normal `return` within them.

Like this:

```js run
let sum = (a, b) => {  // the curly brace opens a multiline function
  let result = a + b;

  return result; // if we use curly braces, then we need an explicit "return" 

};

alert( sum(1, 2) ); // 3
```

Here we praised arrow functions for brevity. But that's not all!

Arrow functions have other interesting features.

To study them in-depth, we first need to get to know some other aspects of JavaScript, so we'll return to arrow functions later in the chapter <info:arrow-functions>.

For now, we can already use arrow functions for one-line actions and callbacks.

## Summary

Arrow functions are handy for one-liners. They come in two flavors:

1. Without curly braces: `(...args) => expression` -- the right side is an expression: the function evaluates it and returns the result.
2. With curly braces: `(...args) => { body }` -- brackets allow us to write multiple statements inside the function, but we need an explicit `return` to return something.
# JavaScript specials

This chapter briefly recaps the features of JavaScript that we've learned by now, paying special attention to subtle moments.

## Code structure

Statements are delimited with a semicolon:

```js run no-beautify
alert('Hello'); alert('World');
```

Usually, a line-break is also treated as a delimiter, so that would also work:

```js run no-beautify
alert('Hello')
alert('World')
```

That's called "automatic semicolon insertion". Sometimes it doesn't work, for instance:

```js run
alert("There will be an error after this message")

[1, 2].forEach(alert)
```

Most codestyle guides agree that we should put a semicolon after each statement.

Semicolons are not required after code blocks `{...}` and syntax constructs with them like loops:

```js
function f() {
  // no semicolon needed after function declaration
}

for(;;) {
  // no semicolon needed after the loop
}
```

...But even if we can put an "extra" semicolon somewhere, that's not an error. It will be ignored.

More in: <info:structure>.

## Strict mode

To fully enable all features of modern JavaScript, we should start scripts with `"use strict"`.

```js
'use strict';

...
```

The directive must be at the top of a script or at the beginning of a function body.

Without `"use strict"`, everything still works, but some features behave in the old-fashion, "compatible" way. We'd generally prefer the modern behavior.

Some modern features of the language (like classes that we'll study in the future) enable strict mode implicitly.

More in: <info:strict-mode>.

## Variables

Can be declared using:

- `let`
- `const` (constant, can't be changed)
- `var` (old-style, will see later)

A variable name can include:
- Letters and digits, but the first character may not be a digit.
- Characters `$` and `_` are normal, on par with letters.
- Non-Latin alphabets and hieroglyphs are also allowed, but commonly not used.

Variables are dynamically typed. They can store any value:

```js
let x = 5;
x = "John";
```

There are 8 data types:

- `number` for both floating-point and integer numbers,
- `bigint` for integer numbers of arbitrary length,
- `string` for strings,
- `boolean` for logical values: `true/false`,
- `null` -- a type with a single value `null`, meaning "empty" or "does not exist",
- `undefined` -- a type with a single value `undefined`, meaning "not assigned",
- `object` and `symbol` -- for complex data structures and unique identifiers, we haven't learnt them yet.

The `typeof` operator returns the type for a value, with two exceptions:
```js
typeof null == "object" // error in the language
typeof function(){} == "function" // functions are treated specially
```

More in: <info:variables> and <info:types>.

## Interaction

We're using a browser as a working environment, so basic UI functions will be:

[`prompt(question, [default])`](mdn:api/Window/prompt)
: Ask a `question`, and return either what the visitor entered or `null` if they clicked "cancel".

[`confirm(question)`](mdn:api/Window/confirm)
: Ask a `question` and suggest to choose between Ok and Cancel. The choice is returned as `true/false`.

[`alert(message)`](mdn:api/Window/alert)
: Output a `message`.

All these functions are *modal*, they pause the code execution and prevent the visitor from interacting with the page until they answer.

For instance:

```js run
let userName = prompt("Your name?", "Alice");
let isTeaWanted = confirm("Do you want some tea?");

alert( "Visitor: " + userName ); // Alice
alert( "Tea wanted: " + isTeaWanted ); // true
```

More in: <info:alert-prompt-confirm>.

## Operators

JavaScript supports the following operators:

Arithmetical
: Regular: `* + - /`, also `%` for the remainder and `**` for power of a number.

    The binary plus `+` concatenates strings. And if any of the operands is a string, the other one is converted to string too:

    ```js run
    alert( '1' + 2 ); // '12', string
    alert( 1 + '2' ); // '12', string
    ```

Assignments
: There is a simple assignment: `a = b` and combined ones like `a *= 2`.

Bitwise
: Bitwise operators work with 32-bit integers at the lowest, bit-level: see the [docs](mdn:/JavaScript/Reference/Operators/Bitwise_Operators) when they are needed.

Conditional
: The only operator with three parameters: `cond ? resultA : resultB`. If `cond` is truthy, returns `resultA`, otherwise `resultB`.

Logical operators
: Logical AND `&&` and OR `||` perform short-circuit evaluation and then return the value where it stopped (not necessary `true`/`false`). Logical NOT `!` converts the operand to boolean type and returns the inverse value.

Nullish coalescing operator
: The `??` operator provides a way to choose a defined value from a list of variables. The result of `a ?? b` is `a` unless it's `null/undefined`, then `b`.

Comparisons
: Equality check `==` for values of different types converts them to a number (except `null` and `undefined` that equal each other and nothing else), so these are equal:

    ```js run
    alert( 0 == false ); // true
    alert( 0 == '' ); // true
    ```

    Other comparisons convert to a number as well.

    The strict equality operator `===` doesn't do the conversion: different types always mean different values for it.

    Values `null` and `undefined` are special: they equal `==` each other and don't equal anything else.

    Greater/less comparisons compare strings character-by-character, other types are converted to a number.

Other operators
: There are few others, like a comma operator.

More in: <info:operators>, <info:comparison>, <info:logical-operators>, <info:nullish-coalescing-operator>.

## Loops

- We covered 3 types of loops:

    ```js
    // 1
    while (condition) {
      ...
    }

    // 2
    do {
      ...
    } while (condition);

    // 3
    for(let i = 0; i < 10; i++) {
      ...
    }
    ```

- The variable declared in `for(let...)` loop is visible only inside the loop. But we can also omit `let` and reuse an existing variable.
- Directives `break/continue` allow to exit the whole loop/current iteration. Use labels to break nested loops.

Details in: <info:while-for>.

Later we'll study more types of loops to deal with objects.

## The "switch" construct

The "switch" construct can replace multiple `if` checks. It uses `===` (strict equality) for comparisons.

For instance:

```js run
let age = prompt('Your age?', 18);

switch (age) {
  case 18:
    alert("Won't work"); // the result of prompt is a string, not a number
    break;

  case "18":
    alert("This works!");
    break;

  default:
    alert("Any value not equal to one above");
}
```

Details in: <info:switch>.

## Functions

We covered three ways to create a function in JavaScript:

1. Function Declaration: the function in the main code flow

    ```js
    function sum(a, b) {
      let result = a + b;

      return result;
    }
    ```

2. Function Expression: the function in the context of an expression

    ```js
    let sum = function(a, b) {
      let result = a + b;

      return result;
    };
    ```

3. Arrow functions:

    ```js
    // expression at the right side
    let sum = (a, b) => a + b;

    // or multi-line syntax with { ... }, need return here:
    let sum = (a, b) => {
      // ...
      return a + b;
    }

    // without arguments
    let sayHi = () => alert("Hello");

    // with a single argument
    let double = n => n * 2;
    ```


- Functions may have local variables: those declared inside its body. Such variables are only visible inside the function.
- Parameters can have default values: `function sum(a = 1, b = 2) {...}`.
- Functions always return something. If there's no `return` statement, then the result is `undefined`.

Details: see <info:function-basics>, <info:arrow-functions-basics>.

## More to come

That was a brief list of JavaScript features. As of now we've studied only basics. Further in the tutorial you'll find more specials and advanced features of JavaScript.


# Objects

As we know from the chapter <info:types>, there are eight data types in JavaScript. Seven of them are called "primitive", because their values contain only a single thing (be it a string or a number or whatever).

In contrast, objects are used to store keyed collections of various data and more complex entities. In JavaScript, objects penetrate almost every aspect of the language. So we must understand them first before going in-depth anywhere else.

An object can be created with figure brackets `{…}` with an optional list of *properties*. A property is a "key: value" pair, where `key` is a string (also called a "property name"), and `value` can be anything.

We can imagine an object as a cabinet with signed files. Every piece of data is stored in its file by the key. It's easy to find a file by its name or add/remove a file.

An empty object ("empty cabinet") can be created using one of two syntaxes:

```js
let user = new Object(); // "object constructor" syntax
let user = {};  // "object literal" syntax
```

Usually, the figure brackets `{...}` are used. That declaration is called an *object literal*.

## Literals and properties

We can immediately put some properties into `{...}` as "key: value" pairs:

```js
let user = {     // an object
  name: "John",  // by key "name" store value "John"
  age: 30        // by key "age" store value 30
};
```

A property has a key (also known as "name" or "identifier") before the colon `":"` and a value to the right of it.

In the `user` object, there are two properties:

1. The first property has the name `"name"` and the value `"John"`.
2. The second one has the name `"age"` and the value `30`.

The resulting `user` object can be imagined as a cabinet with two signed files labeled "name" and "age".

We can add, remove and read files from it any time.

Property values are accessible using the dot notation:

```js
// get property values of the object:
alert( user.name ); // John
alert( user.age ); // 30
```

The value can be of any type. Let's add a boolean one:

```js
user.isAdmin = true;
```

To remove a property, we can use `delete` operator:

```js
delete user.age;
```


We can also use multiword property names, but then they must be quoted:

```js
let user = {
  name: "John",
  age: 30,
  "likes birds": true  // multiword property name must be quoted
};
```


The last property in the list may end with a comma:
```js
let user = {
  name: "John",
  age: 30,
}
```
That is called a "trailing" or "hanging" comma. Makes it easier to add/remove/move around properties, because all lines become alike.

Please note: an object declared as `const` *can* be modified.

For instance:

```js run
const user = {
  name: "John"
};


user.name = "Pete"; // (*)


alert(user.name); // Pete
```

It might seem that the line `(*)` would cause an error, but no. The `const` fixes the value of `user`, but not its contents.

The `const` would give an error only if we try to set `user=...` as a whole.

There's another way to make constant object properties, we'll cover it later in the chapter <info:property-descriptors>.


## Square brackets

For multiword properties, the dot access doesn't work:

```js run
// this would give a syntax error
user.likes birds = true
```

JavaScript doesn't understand that. It thinks that we address `user.likes`, and then gives a syntax error when comes across unexpected `birds`.

The dot requires the key to be a valid variable identifier. That implies: contains no spaces, doesn't start with a digit and doesn't include special characters (`$` and `_` are allowed).

There's an alternative "square bracket notation" that works with any string:

```js run
let user = {};

// set
user["likes birds"] = true;

// get
alert(user["likes birds"]); // true

// delete
delete user["likes birds"];
```

Now everything is fine. Please note that the string inside the brackets is properly quoted (any type of quotes will do).

Square brackets also provide a way to obtain the property name as the result of any expression -- as opposed to a literal string -- like from a variable as follows:

```js
let key = "likes birds";

// same as user["likes birds"] = true;
user[key] = true;
```

Here, the variable `key` may be calculated at run-time or depend on the user input. And then we use it to access the property. That gives us a great deal of flexibility.

For instance:

```js run
let user = {
  name: "John",
  age: 30
};

let key = prompt("What do you want to know about the user?", "name");

// access by variable
alert( user[key] ); // John (if enter "name")
```

The dot notation cannot be used in a similar way:

```js run
let user = {
  name: "John",
  age: 30
};

let key = "name";
alert( user.key ) // undefined
```

### Computed properties

We can use square brackets in an object literal, when creating an object. That's called *computed properties*.

For instance:

```js run
let fruit = prompt("Which fruit to buy?", "apple");

let bag = {

  [fruit]: 5, // the name of the property is taken from the variable fruit

};

alert( bag.apple ); // 5 if fruit="apple"
```

The meaning of a computed property is simple: `[fruit]` means that the property name should be taken from `fruit`.

So, if a visitor enters `"apple"`, `bag` will become `{apple: 5}`.

Essentially, that works the same as:
```js run
let fruit = prompt("Which fruit to buy?", "apple");
let bag = {};

// take property name from the fruit variable
bag[fruit] = 5;
```

...But looks nicer.

We can use more complex expressions inside square brackets:

```js
let fruit = 'apple';
let bag = {
  [fruit + 'Computers']: 5 // bag.appleComputers = 5
};
```

Square brackets are much more powerful than the dot notation. They allow any property names and variables. But they are also more cumbersome to write.

So most of the time, when property names are known and simple, the dot is used. And if we need something more complex, then we switch to square brackets.

## Property value shorthand

In real code we often use existing variables as values for property names.

For instance:

```js run
function makeUser(name, age) {
  return {
    name: name,
    age: age,
    // ...other properties
  };
}

let user = makeUser("John", 30);
alert(user.name); // John
```

In the example above, properties have the same names as variables. The use-case of making a property from a variable is so common, that there's a special *property value shorthand* to make it shorter.

Instead of `name:name` we can just write `name`, like this:

```js
function makeUser(name, age) {

  return {
    name, // same as name: name
    age,  // same as age: age
    // ...
  };

}
```

We can use both normal properties and shorthands in the same object:

```js
let user = {
  name,  // same as name:name
  age: 30
};
```


## Property names limitations

As we already know, a variable cannot have a name equal to one of language-reserved words like "for", "let", "return" etc.

But for an object property, there's no such restriction:

```js run
// these properties are all right
let obj = {
  for: 1,
  let: 2,
  return: 3
};

alert( obj.for + obj.let + obj.return );  // 6
```

In short, there are no limitations on property names. They can be any strings or symbols (a special type for identifiers, to be covered later).

Other types are automatically converted to strings.

For instance, a number `0` becomes a string `"0"` when used as a property key:

```js run
let obj = {
  0: "test" // same as "0": "test"
};

// both alerts access the same property (the number 0 is converted to string "0")
alert( obj["0"] ); // test
alert( obj[0] ); // test (same property)
```

There's a minor gotcha with a special property named `__proto__`. We can't set it to a non-object value:

```js run
let obj = {};
obj.__proto__ = 5; // assign a number
alert(obj.__proto__); // [object Object] - the value is an object, didn't work as intended
```

As we see from the code, the assignment to a primitive `5` is ignored.

We'll cover the special nature of `__proto__` in [subsequent chapters](info:prototype-inheritance), and suggest the [ways to fix](info:prototype-methods) such behavior.

## Property existence test, "in" operator

A notable feature of objects in JavaScript, compared to many other languages, is that it's possible to access any property. There will be no error if the property doesn't exist!

Reading a non-existing property just returns `undefined`. So we can easily test whether the property exists:

```js run
let user = {};

alert( user.noSuchProperty === undefined ); // true means "no such property"
```

There's also a special operator `"in"` for that.

The syntax is:
```js
"key" in object
```

For instance:

```js run
let user = { name: "John", age: 30 };

alert( "age" in user ); // true, user.age exists
alert( "blabla" in user ); // false, user.blabla doesn't exist
```

Please note that on the left side of `in` there must be a *property name*. That's usually a quoted string.

If we omit quotes, that means a variable, it should contain the actual name to be tested. For instance:

```js run
let user = { age: 30 };

let key = "age";
alert( key in user ); // true, property "age" exists
```

Why does the `in` operator exist? Isn't it enough to compare against `undefined`?

Well, most of the time the comparison with `undefined` works fine. But there's a special case when it fails, but `"in"` works correctly.

It's when an object property exists, but stores `undefined`:

```js run
let obj = {
  test: undefined
};

alert( obj.test ); // it's undefined, so - no such property?

alert( "test" in obj ); // true, the property does exist!
```

In the code above, the property `obj.test` technically exists. So the `in` operator works right.

Situations like this happen very rarely, because `undefined` should not be explicitly assigned. We mostly use `null` for "unknown" or "empty" values. So the `in` operator is an exotic guest in the code.


## The "for..in" loop

To walk over all keys of an object, there exists a special form of the loop: `for..in`. This is a completely different thing from the `for(;;)` construct that we studied before.

The syntax:

```js
for (key in object) {
  // executes the body for each key among object properties
}
```

For instance, let's output all properties of `user`:

```js run
let user = {
  name: "John",
  age: 30,
  isAdmin: true
};

for (let key in user) {
  // keys
  alert( key );  // name, age, isAdmin
  // values for the keys
  alert( user[key] ); // John, 30, true
}
```

Note that all "for" constructs allow us to declare the looping variable inside the loop, like `let key` here.

Also, we could use another variable name here instead of `key`. For instance, `"for (let prop in obj)"` is also widely used.

### Ordered like an object

Are objects ordered? In other words, if we loop over an object, do we get all properties in the same order they were added? Can we rely on this?

The short answer is: "ordered in a special fashion": integer properties are sorted, others appear in creation order. The details follow.

As an example, let's consider an object with the phone codes:

```js run
let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  // ..,
  "1": "USA"
};


for (let code in codes) {
  alert(code); // 1, 41, 44, 49
}

```

The object may be used to suggest a list of options to the user. If we're making a site mainly for German audience then we probably want `49` to be the first.

But if we run the code, we see a totally different picture:

- USA (1) goes first
- then Switzerland (41) and so on.

The phone codes go in the ascending sorted order, because they are integers. So we see `1, 41, 44, 49`.

The "integer property" term here means a string that can be converted to-and-from an integer without a change.

So, "49" is an integer property name, because when it's transformed to an integer number and back, it's still the same. But "+49" and "1.2" are not:

```js run
// Math.trunc is a built-in function that removes the decimal part
alert( String(Math.trunc(Number("49"))) ); // "49", same, integer property
alert( String(Math.trunc(Number("+49"))) ); // "49", not same "+49" ⇒ not integer property
alert( String(Math.trunc(Number("1.2"))) ); // "1", not same "1.2" ⇒ not integer property
```


...On the other hand, if the keys are non-integer, then they are listed in the creation order, for instance:

```js run
let user = {
  name: "John",
  surname: "Smith"
};
user.age = 25; // add one more


// non-integer properties are listed in the creation order

for (let prop in user) {
  alert( prop ); // name, surname, age
}
```

So, to fix the issue with the phone codes, we can "cheat" by making the codes non-integer. Adding a plus `"+"` sign before each code is enough.

Like this:

```js run
let codes = {
  "+49": "Germany",
  "+41": "Switzerland",
  "+44": "Great Britain",
  // ..,
  "+1": "USA"
};

for (let code in codes) {
  alert( +code ); // 49, 41, 44, 1
}
```

Now it works as intended.

## Summary

Objects are associative arrays with several special features.

They store properties (key-value pairs), where:
- Property keys must be strings or symbols (usually strings).
- Values can be of any type.

To access a property, we can use:
- The dot notation: `obj.property`.
- Square brackets notation `obj["property"]`. Square brackets allow to take the key from a variable, like `obj[varWithKey]`.

Additional operators:
- To delete a property: `delete obj.prop`.
- To check if a property with the given key exists: `"key" in obj`.
- To iterate over an object: `for (let key in obj)` loop.

What we've studied in this chapter is called a "plain object", or just `Object`.

There are many other kinds of objects in JavaScript:

- `Array` to store ordered data collections,
- `Date` to store the information about the date and time,
- `Error` to store the information about an error.
- ...And so on.

They have their special features that we'll study later. Sometimes people say something like "Array type" or "Date type", but formally they are not types of their own, but belong to a single "object" data type. And they extend it in various ways.

Objects in JavaScript are very powerful. Here we've just scratched the surface of a topic that is really huge. We'll be closely working with objects and learning more about them in further parts of the tutorial.
# Object copying, references

One of the fundamental differences of objects vs primitives is that they are stored and copied "by reference".

Primitive values: strings, numbers, booleans -- are assigned/copied "as a whole value".

For instance:

```js
let message = "Hello!";
let phrase = message;
```

As a result we have two independent variables, each one is storing the string `"Hello!"`.

Objects are not like that.

**A variable stores not the object itself, but its "address in memory", in other words "a reference" to it.**

Here's the picture for the object:

```js
let user = {
  name: "John"
};
```

Here, the object is stored somewhere in memory. And the variable `user` has a "reference" to it.

**When an object variable is copied -- the reference is copied, the object is not duplicated.**

For instance:

```js no-beautify
let user = { name: "John" };

let admin = user; // copy the reference
```

Now we have two variables, each one with the reference to the same object:

We can use any variable to access the object and modify its contents:

```js run
let user = { name: 'John' };

let admin = user;


admin.name = 'Pete'; // changed by the "admin" reference


alert(user.name); // 'Pete', changes are seen from the "user" reference
```

The example above demonstrates that there is only one object. As if we had a cabinet with two keys and used one of them (`admin`) to get into it. Then, if we later use another key (`user`) we can see changes.

## Comparison by reference

The equality `==` and strict equality `===` operators for objects work exactly the same.

**Two objects are equal only if they are the same object.**

Here two variables reference the same object, thus they are equal:

```js run
let a = {};
let b = a; // copy the reference

alert( a == b ); // true, both variables reference the same object
alert( a === b ); // true
```

And here two independent objects are not equal, even though both are empty:

```js run
let a = {};
let b = {}; // two independent objects

alert( a == b ); // false
```

For comparisons like `obj1 > obj2` or for a comparison against a primitive `obj == 5`, objects are converted to primitives. We'll study how object conversions work very soon, but to tell the truth, such comparisons occur very rarely, usually as a result of a coding mistake.

## Cloning and merging, Object.assign

So, copying an object variable creates one more reference to the same object.

But what if we need to duplicate an object? Create an independent copy, a clone?

That's also doable, but a little bit more difficult, because there's no built-in method for that in JavaScript. Actually, that's rarely needed. Copying by reference is good most of the time.

But if we really want that, then we need to create a new object and replicate the structure of the existing one by iterating over its properties and copying them on the primitive level.

Like this:

```js run
let user = {
  name: "John",
  age: 30
};


let clone = {}; // the new empty object

// let's copy all user properties into it
for (let key in user) {
  clone[key] = user[key];
}


// now clone is a fully independent object with the same content
clone.name = "Pete"; // changed the data in it

alert( user.name ); // still John in the original object
```

Also we can use the method [Object.assign](mdn:js/Object/assign) for that.

The syntax is:

```js
Object.assign(dest, [src1, src2, src3...])
```

- The first argument `dest` is a target object.
- Further arguments `src1, ..., srcN` (can be as many as needed) are source objects.
- It copies the properties of all source objects `src1, ..., srcN` into the target `dest`. In other words, properties of all arguments starting from the second are copied into the first object.
- The call returns `dest`.

For instance, we can use it to merge several objects into one:
```js
let user = { name: "John" };

let permissions1 = { canView: true };
let permissions2 = { canEdit: true };


// copies all properties from permissions1 and permissions2 into user
Object.assign(user, permissions1, permissions2);


// now user = { name: "John", canView: true, canEdit: true }
```

If the copied property name already exists, it gets overwritten:

```js run
let user = { name: "John" };

Object.assign(user, { name: "Pete" });

alert(user.name); // now user = { name: "Pete" }
```

We also can use `Object.assign` to replace `for..in` loop for simple cloning:

```js
let user = {
  name: "John",
  age: 30
};


let clone = Object.assign({}, user);

```

It copies all properties of `user` into the empty object and returns it.

## Nested cloning

Until now we assumed that all properties of `user` are primitive. But properties can be references to other objects. What to do with them?

Like this:
```js run
let user = {
  name: "John",
  sizes: {
    height: 182,
    width: 50
  }
};

alert( user.sizes.height ); // 182
```

Now it's not enough to copy `clone.sizes = user.sizes`, because the `user.sizes` is an object, it will be copied by reference. So `clone` and `user` will share the same sizes:

Like this:

```js run
let user = {
  name: "John",
  sizes: {
    height: 182,
    width: 50
  }
};

let clone = Object.assign({}, user);

alert( user.sizes === clone.sizes ); // true, same object

// user and clone share sizes
user.sizes.width++;       // change a property from one place
alert(clone.sizes.width); // 51, see the result from the other one
```

To fix that, we should use the cloning loop that examines each value of `user[key]` and, if it's an object, then replicate its structure as well. That is called a "deep cloning".

There's a standard algorithm for deep cloning that handles the case above and more complex cases, called the [Structured cloning algorithm](https://html.spec.whatwg.org/multipage/structured-data.html#safe-passing-of-structured-data).

We can use recursion to implement it. Or, not to reinvent the wheel, take an existing implementation, for instance [_.cloneDeep(obj)](https://lodash.com/docs#cloneDeep) from the JavaScript library [lodash](https://lodash.com).

## Summary

Objects are assigned and copied by reference. In other words, a variable stores not the "object value", but a "reference" (address in memory) for the value. So copying such a variable or passing it as a function argument copies that reference, not the object.

All operations via copied references (like adding/removing properties) are performed on the same single object.

To make a "real copy" (a clone) we can use `Object.assign` for the so-called "shallow copy" (nested objects are copied by reference) or a "deep cloning" function, such as [_.cloneDeep(obj)](https://lodash.com/docs#cloneDeep).
# Garbage collection

Memory management in JavaScript is performed automatically and invisibly to us. We create primitives, objects, functions... All that takes memory.

What happens when something is not needed any more? How does the JavaScript engine discover it and clean it up?

## Reachability

The main concept of memory management in JavaScript is *reachability*.

Simply put, "reachable" values are those that are accessible or usable somehow. They are guaranteed to be stored in memory.

1. There's a base set of inherently reachable values, that cannot be deleted for obvious reasons.

    For instance:

    - Local variables and parameters of the current function.
    - Variables and parameters for other functions on the current chain of nested calls.
    - Global variables.
    - (there are some other, internal ones as well)

    These values are called *roots*.

2. Any other value is considered reachable if it's reachable from a root by a reference or by a chain of references.

    For instance, if there's an object in a global variable, and that object has a property referencing another object, that object is considered reachable. And those that it references are also reachable. Detailed examples to follow.

There's a background process in the JavaScript engine that is called [garbage collector](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)). It monitors all objects and removes those that have become unreachable.

## A simple example

Here's the simplest example:

```js
// user has a reference to the object
let user = {
  name: "John"
};
```

Here the arrow depicts an object reference. The global variable `"user"` references the object `{name: "John"}` (we'll call it John for brevity). The `"name"` property of John stores a primitive, so it's painted inside the object.

If the value of `user` is overwritten, the reference is lost:

```js
user = null;
```

Now John becomes unreachable. There's no way to access it, no references to it. Garbage collector will junk the data and free the memory.

## Two references

Now let's imagine we copied the reference from `user` to `admin`:

```js
// user has a reference to the object
let user = {
  name: "John"
};


let admin = user;

```

Now if we do the same:
```js
user = null;
```

...Then the object is still reachable via `admin` global variable, so it's in memory. If we overwrite `admin` too, then it can be removed.

## Interlinked objects

Now a more complex example. The family:

```js
function marry(man, woman) {
  woman.husband = man;
  man.wife = woman;

  return {
    father: man,
    mother: woman
  }
}

let family = marry({
  name: "John"
}, {
  name: "Ann"
});
```

Function `marry` "marries" two objects by giving them references to each other and returns a new object that contains them both.

The resulting memory structure:

As of now, all objects are reachable.

Now let's remove two references:

```js
delete family.father;
delete family.mother.husband;
```
It's not enough to delete only one of these two references, because all objects would still be reachable.

But if we delete both, then we can see that John has no incoming reference any more:

Outgoing references do not matter. Only incoming ones can make an object reachable. So, John is now unreachable and will be removed from the memory with all its data that also became unaccessible.

After garbage collection:

## Unreachable island

It is possible that the whole island of interlinked objects becomes unreachable and is removed from the memory.

The source object is the same as above. Then:

```js
family = null;
```

The in-memory picture becomes:

This example demonstrates how important the concept of reachability is.

It's obvious that John and Ann are still linked, both have incoming references. But that's not enough.

The former `"family"` object has been unlinked from the root, there's no reference to it any more, so the whole island becomes unreachable and will be removed.

## Internal algorithms

The basic garbage collection algorithm is called "mark-and-sweep".

The following "garbage collection" steps are regularly performed:

- The garbage collector takes roots and "marks" (remembers) them.
- Then it visits and "marks" all references from them.
- Then it visits marked objects and marks *their* references. All visited objects are remembered, so as not to visit the same object twice in the future.
- ...And so on until every reachable (from the roots) references are visited.
- All objects except marked ones are removed.

For instance, let our object structure look like this:

We can clearly see an "unreachable island" to the right side. Now let's see how "mark-and-sweep" garbage collector deals with it.

The first step marks the roots:

Then their references are marked:

...And their references, while possible:

Now the objects that could not be visited in the process are considered unreachable and will be removed:

We can also imagine the process as spilling a huge bucket of paint from the roots, that flows through all references and marks all reachable objects. The unmarked ones are then removed.

That's the concept of how garbage collection works. JavaScript engines apply many optimizations to make it run faster and not affect the execution.

Some of the optimizations:

- **Generational collection** -- objects are split into two sets: "new ones" and "old ones". Many  objects appear, do their job and die fast, they can be cleaned up aggressively. Those that survive for long enough, become "old" and are examined less often.
- **Incremental collection** -- if there are many objects, and we try to walk and mark the whole object set at once, it may take some time and introduce visible delays in the execution. So the engine tries to split the garbage collection into pieces. Then the pieces are executed one by one, separately. That requires some extra bookkeeping between them to track changes, but we have many tiny delays instead of a big one.
- **Idle-time collection** -- the garbage collector tries to run only while the CPU is idle, to reduce the possible effect on the execution.

There exist other optimizations and flavours of garbage collection algorithms. As much as I'd like to describe them here, I have to hold off, because different engines implement different tweaks and techniques. And, what's even more important, things change as engines develop, so studying deeper "in advance", without a real need is probably not worth that. Unless, of course, it is a matter of pure interest, then there will be some links for you below.

## Summary

The main things to know:

- Garbage collection is performed automatically. We cannot force or prevent it.
- Objects are retained in memory while they are reachable.
- Being referenced is not the same as being reachable (from a root): a pack of interlinked objects can become unreachable as a whole.

Modern engines implement advanced algorithms of garbage collection.

A general book "The Garbage Collection Handbook: The Art of Automatic Memory Management" (R. Jones et al) covers some of them.

If you are familiar with low-level programming, the more detailed information about V8 garbage collector is in the article [A tour of V8: Garbage Collection](http://jayconrod.com/posts/55/a-tour-of-v8-garbage-collection).

[V8 blog](https://v8.dev/) also publishes articles about changes in memory management from time to time. Naturally, to learn the garbage collection, you'd better prepare by learning about V8 internals in general and read the blog of [Vyacheslav Egorov](http://mrale.ph) who worked as one of V8 engineers. I'm saying: "V8", because it is best covered with articles in the internet. For other engines, many approaches are similar, but garbage collection differs in many aspects.

In-depth knowledge of engines is good when you need low-level optimizations. It would be wise to plan that as the next step after you're familiar with the language.  
# Object methods, "this"

Objects are usually created to represent entities of the real world, like users, orders and so on:

```js
let user = {
  name: "John",
  age: 30
};
```

And, in the real world, a user can *act*: select something from the shopping cart, login, logout etc.

Actions are represented in JavaScript by functions in properties.

## Method examples

For a start, let's teach the `user` to say hello:

```js run
let user = {
  name: "John",
  age: 30
};


user.sayHi = function() {
  alert("Hello!");
};


user.sayHi(); // Hello!
```

Here we've just used a Function Expression to create the function and assign it to the property `user.sayHi` of the object.

Then we can call it. The user can now speak!

A function that is the property of an object is called its *method*.

So, here we've got a method `sayHi` of the object `user`.

Of course, we could use a pre-declared function as a method, like this:

```js run
let user = {
  // ...
};


// first, declare
function sayHi() {
  alert("Hello!");
};

// then add as a method
user.sayHi = sayHi;


user.sayHi(); // Hello!
```

When we write our code using objects to represent entities, that's called [object-oriented programming](https://en.wikipedia.org/wiki/Object-oriented_programming), in short: "OOP".

OOP is a big thing, an interesting science of its own. How to choose the right entities? How to organize the interaction between them? That's architecture, and there are great books on that topic, like "Design Patterns: Elements of Reusable Object-Oriented Software" by E. Gamma, R. Helm, R. Johnson, J. Vissides or "Object-Oriented Analysis and Design with Applications" by G. Booch, and more.

### Method shorthand

There exists a shorter syntax for methods in an object literal:

```js
// these objects do the same

user = {
  sayHi: function() {
    alert("Hello");
  }
};

// method shorthand looks better, right?
user = {

  sayHi() { // same as "sayHi: function()"

    alert("Hello");
  }
};
```

As demonstrated, we can omit `"function"` and just write `sayHi()`.

To tell the truth, the notations are not fully identical. There are subtle differences related to object inheritance (to be covered later), but for now they do not matter. In almost all cases the shorter syntax is preferred.

## "this" in methods

It's common that an object method needs to access the information stored in the object to do its job.

For instance, the code inside `user.sayHi()` may need the name of the `user`.

**To access the object, a method can use the `this` keyword.**

The value of `this` is the object "before dot", the one used to call the method.

For instance:

```js run
let user = {
  name: "John",
  age: 30,

  sayHi() {

    // "this" is the "current object"
    alert(this.name);

  }

};

user.sayHi(); // John
```

Here during the execution of `user.sayHi()`, the value of `this` will be `user`.

Technically, it's also possible to access the object without `this`, by referencing it via the outer variable:

```js
let user = {
  name: "John",
  age: 30,

  sayHi() {

    alert(user.name); // "user" instead of "this"

  }

};
```

...But such code is unreliable. If we decide to copy `user` to another variable, e.g. `admin = user` and overwrite `user` with something else, then it will access the wrong object.

That's demonstrated below:

```js run
let user = {
  name: "John",
  age: 30,

  sayHi() {

    alert( user.name ); // leads to an error

  }

};


let admin = user;
user = null; // overwrite to make things obvious

admin.sayHi(); // Whoops! inside sayHi(), the old name is used! error!
```

If we used `this.name` instead of `user.name` inside the `alert`, then the code would work.

## "this" is not bound

In JavaScript, keyword `this` behaves unlike most other programming languages. It can be used in any function.

There's no syntax error in the following example:

```js
function sayHi() {
  alert( this.name );
}
```

The value of `this` is evaluated during the run-time, depending on the context.

For instance, here the same function is assigned to two different objects and has different "this" in the calls:

```js run
let user = { name: "John" };
let admin = { name: "Admin" };

function sayHi() {
  alert( this.name );
}


// use the same function in two objects
user.f = sayHi;
admin.f = sayHi;


// these calls have different this
// "this" inside the function is the object "before the dot"
user.f(); // John  (this == user)
admin.f(); // Admin  (this == admin)

admin['f'](); // Admin (dot or square brackets access the method – doesn't matter)
```

The rule is simple: if `obj.f()` is called, then `this` is `obj` during the call of `f`. So it's either `user` or `admin` in the example above.

We can even call the function without an object at all:

```js run
function sayHi() {
  alert(this);
}

sayHi(); // undefined
```

In this case `this` is `undefined` in strict mode. If we try to access `this.name`, there will be an error.

In non-strict mode the value of `this` in such case will be the *global object* (`window` in a browser, we'll get to it later in the chapter [](info:global-object)). This is a historical behavior that `"use strict"` fixes.

Usually such call is a programming error. If there's `this` inside a function, it expects to be called in an object context.


If you come from another programming language, then you are probably used to the idea of a "bound `this`", where methods defined in an object always have `this` referencing that object.

In JavaScript `this` is "free", its value is evaluated at call-time and does not depend on where the method was declared, but rather on what object is "before the dot".

The concept of run-time evaluated `this` has both pluses and minuses. On the one hand, a function can be reused for different objects. On the other hand, the greater flexibility creates more possibilities for mistakes.

Here our position is not to judge whether this language design decision is good or bad. We'll understand how to work with it, how to get benefits and avoid problems.

## Arrow functions have no "this"

Arrow functions are special: they don't have their "own" `this`. If we reference `this` from such a function, it's taken from the outer "normal" function.

For instance, here `arrow()` uses `this` from the outer `user.sayHi()` method:

```js run
let user = {
  firstName: "Ilya",
  sayHi() {
    let arrow = () => alert(this.firstName);
    arrow();
  }
};

user.sayHi(); // Ilya
```

That's a special feature of arrow functions, it's useful when we actually do not want to have a separate `this`, but rather to take it from the outer context. Later in the chapter <info:arrow-functions> we'll go more deeply into arrow functions.


## Summary

- Functions that are stored in object properties are called "methods".
- Methods allow objects to "act" like `object.doSomething()`.
- Methods can reference the object as `this`.

The value of `this` is defined at run-time.
- When a function is declared, it may use `this`, but that `this` has no value until the function is called.
- A function can be copied between objects.
- When a function is called in the "method" syntax: `object.method()`, the value of `this` during the call is `object`.

Please note that arrow functions are special: they have no `this`. When `this` is accessed inside an arrow function, it is taken from outside.
# Constructor, operator "new"

The regular `{...}` syntax allows to create one object. But often we need to create many similar objects, like multiple users or menu items and so on.

That can be done using constructor functions and the `"new"` operator.

## Constructor function

Constructor functions technically are regular functions. There are two conventions though:

1. They are named with capital letter first.
2. They should be executed only with `"new"` operator.

For instance:

```js run
function User(name) {
  this.name = name;
  this.isAdmin = false;
}


let user = new User("Jack");


alert(user.name); // Jack
alert(user.isAdmin); // false
```

When a function is executed with `new`, it does the following steps:

1. A new empty object is created and assigned to `this`.
2. The function body executes. Usually it modifies `this`, adds new properties to it.
3. The value of `this` is returned.

In other words, `new User(...)` does something like:

```js
function User(name) {

  // this = {};  (implicitly)


  // add properties to this
  this.name = name;
  this.isAdmin = false;


  // return this;  (implicitly)

}
```

So `let user = new User("Jack")` gives the same result as:

```js
let user = {
  name: "Jack",
  isAdmin: false
};
```

Now if we want to create other users, we can call `new User("Ann")`, `new User("Alice")` and so on. Much shorter than using literals every time, and also easy to read.

That's the main purpose of constructors -- to implement reusable object creation code.

Let's note once again -- technically, any function can be used as a constructor. That is: any function can be run with `new`, and it will execute the algorithm above. The "capital letter first" is a common agreement, to make it clear that a function is to be run with `new`.

If we have many lines of code all about creation of a single complex object, we can wrap them in constructor function, like this:

```js
let user = new function() {
  this.name = "John";
  this.isAdmin = false;

  // ...other code for user creation
  // maybe complex logic and statements
  // local variables etc
};
```

The constructor can't be called again, because it is not saved anywhere, just created and called. So this trick aims to encapsulate the code that constructs the single object, without future reuse.


## Constructor mode test: new.target

The syntax from this section is rarely used, skip it unless you want to know everything.

Inside a function, we can check whether it was called with `new` or without it, using a special `new.target` property.

It is empty for regular calls and equals the function if called with `new`:

```js run
function User() {
  alert(new.target);
}

// without "new":

User(); // undefined


// with "new":

new User(); // function User { ... }

```

That can be used inside the function to know whether it was called with `new`, "in constructor mode", or without it, "in regular mode".

We can also make both `new` and regular calls to do the same, like this:

```js run
function User(name) {
  if (!new.target) { // if you run me without new
    return new User(name); // ...I will add new for you
  }

  this.name = name;
}

let john = User("John"); // redirects call to new User
alert(john.name); // John
```

This approach is sometimes used in libraries to make the syntax more flexible. So that people may call the function with or without `new`, and it still works.

Probably not a good thing to use everywhere though, because omitting `new` makes it a bit less obvious what's going on. With `new` we all know that the new object is being created.

## Return from constructors

Usually, constructors do not have a `return` statement. Their task is to write all necessary stuff into `this`, and it automatically becomes the result.

But if there is a `return` statement, then the rule is simple:

- If `return` is called with an object, then the object is returned instead of `this`.
- If `return` is called with a primitive, it's ignored.

In other words, `return` with an object returns that object, in all other cases `this` is returned.

For instance, here `return` overrides `this` by returning an object:

```js run
function BigUser() {

  this.name = "John";

  return { name: "Godzilla" };  // <-- returns this object
}

alert( new BigUser().name );  // Godzilla, got that object
```

And here's an example with an empty `return` (or we could place a primitive after it, doesn't matter):

```js run
function SmallUser() {

  this.name = "John";

  return; // <-- returns this
}

alert( new SmallUser().name );  // John
```

Usually constructors don't have a `return` statement. Here we mention the special behavior with returning objects mainly for the sake of completeness.

By the way, we can omit parentheses after `new`, if it has no arguments:

```js
let user = new User; // <-- no parentheses
// same as
let user = new User();
```

Omitting parentheses here is not considered a "good style", but the syntax is permitted by specification.


## Methods in constructor

Using constructor functions to create objects gives a great deal of flexibility. The constructor function may have parameters that define how to construct the object, and what to put in it.

Of course, we can add to `this` not only properties, but methods as well.

For instance, `new User(name)` below creates an object with the given `name` and the method `sayHi`:

```js run
function User(name) {
  this.name = name;

  this.sayHi = function() {
    alert( "My name is: " + this.name );
  };
}


let john = new User("John");

john.sayHi(); // My name is: John


/*
john = {
   name: "John",
   sayHi: function() { ... }
}
*/
```

To create complex objects, there's a more advanced syntax, [classes](info:classes), that we'll cover later.

## Summary

- Constructor functions or, briefly, constructors, are regular functions, but there's a common agreement to name them with capital letter first.
- Constructor functions should only be called using `new`. Such a call implies a creation of empty `this` at the start and returning the populated one at the end.

We can use constructor functions to make multiple similar objects.

JavaScript provides constructor functions for many built-in language objects: like `Date` for dates, `Set` for sets and others that we plan to study.

In this chapter we only cover the basics about objects and constructors. They are essential for learning more about data types and functions in the next chapters.

After we learn that, we return to objects and cover them in-depth in the chapters <info:prototypes> and <info:classes>.

# Optional chaining '?.'

[recent browser="new"]

The optional chaining `?.` is an error-proof way to access nested object properties, even if an intermediate property doesn't exist.

## The problem

If you've just started to read the tutorial and learn JavaScript, maybe the problem hasn't touched you yet, but it's quite common.

For example, some of our users have addresses, but few did not provide them. Then we can't safely read `user.address.street`:

```js run
let user = {}; // the user happens to be without address

alert(user.address.street); // Error!
```

Or, in the web development, we'd like to get an information about an element on the page, but it may not exist:

```js run
// Error if the result of querySelector(...) is null
let html = document.querySelector('.my-element').innerHTML;
```

Before `?.` appeared in the language, the `&&` operator was used to work around that.

For example:

```js run
let user = {}; // user has no address

alert( user && user.address && user.address.street ); // undefined (no error)
```

AND'ing the whole path to the property ensures that all components exist, but is cumbersome to write.

## Optional chaining

The optional chaining `?.` stops the evaluation and returns `undefined` if the part before `?.` is `undefined` or `null`.

**Further in this article, for brevity, we'll be saying that something "exists" if it's not `null` and not `undefined`.**

Here's the safe way to access `user.address.street`:

```js run
let user = {}; // user has no address

alert( user?.address?.street ); // undefined (no error)
```

Reading the address with `user?.address` works even if `user` object doesn't exist:

```js run
let user = null;

alert( user?.address ); // undefined
alert( user?.address.street ); // undefined
```

Please note: the `?.` syntax makes optional the value before it, but not any further.

In the example above, `user?.` allows only `user` to be `null/undefined`.

On the other hand, if `user` does exist, then it must have `user.address` property, otherwise `user?.address.street` gives an error at the second dot.


We should use `?.` only where it's ok that something doesn't exist.

For example, if according to our coding logic `user` object must be there, but `address` is optional, then `user.address?.street` would be better.

So, if `user` happens to be undefined due to a mistake, we'll know about it and fix it. Otherwise, coding errors can be silenced where not appropriate, and become more difficult to debug.

If there's no variable `user` at all, then `user?.anything` triggers an error:

```js run
// ReferenceError: user is not defined
user?.address;
```
There must be `let/const/var user`. The optional chaining works only for declared variables. 


## Short-circuiting

As it was said before, the `?.` immediately stops ("short-circuits") the evaluation if the left part doesn't exist.

So, if there are any further function calls or side effects, they don't occur:

```js run
let user = null;
let x = 0;

user?.sayHi(x++); // nothing happens

alert(x); // 0, value not incremented
```

## Other cases: ?.(), ?.[]

The optional chaining `?.` is not an operator, but a special syntax construct, that also works with functions and square brackets.

For example, `?.()` is used to call a function that may not exist.

In the code below, some of our users have `admin` method, and some don't:

```js run
let user1 = {
  admin() {
    alert("I am admin");
  }
}

let user2 = {};


user1.admin?.(); // I am admin
user2.admin?.();

```

Here, in both lines we first use the dot `.` to get `admin` property, because the user object must exist, so it's safe read from it.

Then `?.()` checks the left part: if the admin function exists, then it runs (for `user1`). Otherwise (for `user2`) the evaluation stops without errors.

The `?.[]` syntax also works, if we'd like to use brackets `[]` to access properties instead of dot `.`. Similar to previous cases, it allows to safely read a property from an object that may not exist.

```js run
let user1 = {
  firstName: "John"
};

let user2 = null; // Imagine, we couldn't authorize the user

let key = "firstName";

alert( user1?.[key] ); // John
alert( user2?.[key] ); // undefined

alert( user1?.[key]?.something?.not?.existing); // undefined
```

Also we can use `?.` with `delete`:

```js run
delete user?.name; // delete user.name if user exists
```

The optional chaining `?.` has no use at the left side of an assignment:

```js run
// the idea of the code below is to write user.name, if user exists

user?.name = "John"; // Error, doesn't work
// because it evaluates to undefined = "John"
```

## Summary

The `?.` syntax has three forms:

1. `obj?.prop` -- returns `obj.prop` if `obj` exists, otherwise `undefined`.
2. `obj?.[prop]` -- returns `obj[prop]` if `obj` exists, otherwise `undefined`.
3. `obj?.method()` -- calls `obj.method()` if `obj` exists, otherwise returns `undefined`.

As we can see, all of them are straightforward and simple to use. The `?.` checks the left part for `null/undefined` and allows the evaluation to proceed if it's not so.

A chain of `?.` allows to safely access nested properties.

Still, we should apply `?.` carefully, only where it's ok that the left part doesn't to exist.

So that it won't hide programming errors from us, if they occur.

# Symbol type

By specification, object property keys may be either of string type, or of symbol type. Not numbers, not booleans, only strings or symbols, these two types.

Till now we've been using only strings. Now let's see the benefits that symbols can give us.

## Symbols

A "symbol" represents a unique identifier.

A value of this type can be created using `Symbol()`:

```js
// id is a new symbol
let id = Symbol();
```

Upon creation, we can give symbol a description (also called a symbol name), mostly useful for debugging purposes:

```js
// id is a symbol with the description "id"
let id = Symbol("id");
```

Symbols are guaranteed to be unique. Even if we create many symbols with the same description, they are different values. The description is just a label that doesn't affect anything.

For instance, here are two symbols with the same description -- they are not equal:

```js run
let id1 = Symbol("id");
let id2 = Symbol("id");


alert(id1 == id2); // false

```

If you are familiar with Ruby or another language that also has some sort of "symbols" -- please don't be misguided. JavaScript symbols are different.


Most values in JavaScript support implicit conversion to a string. For instance, we can `alert` almost any value, and it will work. Symbols are special. They don't auto-convert.

For instance, this `alert` will show an error:

```js run
let id = Symbol("id");

alert(id); // TypeError: Cannot convert a Symbol value to a string

```

That's a "language guard" against messing up, because strings and symbols are fundamentally different and should not accidentally convert one into another.

If we really want to show a symbol, we need to explicitly call `.toString()` on it, like here:
```js run
let id = Symbol("id");

alert(id.toString()); // Symbol(id), now it works

```

Or get `symbol.description` property to show the description only:
```js run
let id = Symbol("id");

alert(id.description); // id

```



## "Hidden" properties

Symbols allow us to create "hidden" properties of an object, that no other part of code can accidentally access or overwrite.

For instance, if we're working with `user` objects, that belong to a third-party code. We'd like to add identifiers to them.

Let's use a symbol key for it:

```js run
let user = { // belongs to another code
  name: "John"
};

let id = Symbol("id");

user[id] = 1;

alert( user[id] ); // we can access the data using the symbol as the key
```

What's the benefit of using `Symbol("id")` over a string `"id"`?

As `user` objects belongs to another code, and that code also works with them, we shouldn't just add any fields to it. That's unsafe. But a symbol cannot be accessed accidentally, the third-party code probably won't even see it, so it's probably all right to do.

Also, imagine that another script wants to have its own identifier inside `user`, for its own purposes. That may be another JavaScript library, so that the scripts are completely unaware of each other.

Then that script can create its own `Symbol("id")`, like this:

```js
// ...
let id = Symbol("id");

user[id] = "Their id value";
```

There will be no conflict between our and their identifiers, because symbols are always different, even if they have the same name.

...But if we used a string `"id"` instead of a symbol for the same purpose, then there *would* be a conflict:

```js run
let user = { name: "John" };

// Our script uses "id" property
user.id = "Our id value";

// ...Another script also wants "id" for its purposes...

user.id = "Their id value"
// Boom! overwritten by another script!
```

### Symbols in a literal

If we want to use a symbol in an object literal `{...}`, we need square brackets around it.

Like this:

```js
let id = Symbol("id");

let user = {
  name: "John",

  [id]: 123 // not "id": 123

};
```
That's because we need the value from the variable `id` as the key, not the string "id".

### Symbols are skipped by for..in

Symbolic properties do not participate in `for..in` loop.

For instance:

```js run
let id = Symbol("id");
let user = {
  name: "John",
  age: 30,
  [id]: 123
};


for (let key in user) alert(key); // name, age (no symbols)


// the direct access by the symbol works
alert( "Direct: " + user[id] );
```

`Object.keys(user)` also ignores them. That's a part of the general "hiding symbolic properties" principle. If another script or a library loops over our object, it won't unexpectedly access a symbolic property.

In contrast, [Object.assign](mdn:js/Object/assign) copies both string and symbol properties:

```js run
let id = Symbol("id");
let user = {
  [id]: 123
};

let clone = Object.assign({}, user);

alert( clone[id] ); // 123
```

There's no paradox here. That's by design. The idea is that when we clone an object or merge objects, we usually want *all* properties to be copied (including symbols like `id`).

## Global symbols

As we've seen, usually all symbols are different, even if they have the same name. But sometimes we want same-named symbols to be same entities. For instance, different parts of our application want to access symbol `"id"` meaning exactly the same property.

To achieve that, there exists a *global symbol registry*. We can create symbols in it and access them later, and it guarantees that repeated accesses by the same name return exactly the same symbol.

In order to read (create if absent) a symbol from the registry, use `Symbol.for(key)`.

That call checks the global registry, and if there's a symbol described as `key`, then returns it, otherwise creates a new symbol `Symbol(key)` and stores it in the registry by the given `key`.

For instance:

```js run
// read from the global registry
let id = Symbol.for("id"); // if the symbol did not exist, it is created

// read it again (maybe from another part of the code)
let idAgain = Symbol.for("id");

// the same symbol
alert( id === idAgain ); // true
```

Symbols inside the registry are called *global symbols*. If we want an application-wide symbol, accessible everywhere in the code -- that's what they are for.

In some programming languages, like Ruby, there's a single symbol per name.

In JavaScript, as we can see, that's right for global symbols.

### Symbol.keyFor

For global symbols, not only `Symbol.for(key)` returns a symbol by name, but there's a reverse call: `Symbol.keyFor(sym)`, that does the reverse: returns a name by a global symbol.

For instance:

```js run
// get symbol by name
let sym = Symbol.for("name");
let sym2 = Symbol.for("id");

// get name by symbol
alert( Symbol.keyFor(sym) ); // name
alert( Symbol.keyFor(sym2) ); // id
```

The `Symbol.keyFor` internally uses the global symbol registry to look up the key for the symbol. So it doesn't work for non-global symbols. If the symbol is not global, it won't be able to find it and returns `undefined`.

That said, any symbols have `description` property.

For instance:

```js run
let globalSymbol = Symbol.for("name");
let localSymbol = Symbol("name");

alert( Symbol.keyFor(globalSymbol) ); // name, global symbol
alert( Symbol.keyFor(localSymbol) ); // undefined, not global

alert( localSymbol.description ); // name
```

## System symbols

There exist many "system" symbols that JavaScript uses internally, and we can use them to fine-tune various aspects of our objects.

They are listed in the specification in the [Well-known symbols](https://tc39.github.io/ecma262/#sec-well-known-symbols) table:

- `Symbol.hasInstance`
- `Symbol.isConcatSpreadable`
- `Symbol.iterator`
- `Symbol.toPrimitive`
- ...and so on.

For instance, `Symbol.toPrimitive` allows us to describe object to primitive conversion. We'll see its use very soon.

Other symbols will also become familiar when we study the corresponding language features.

## Summary

`Symbol` is a primitive type for unique identifiers.

Symbols are created with `Symbol()` call with an optional description (name).

Symbols are always different values, even if they have the same name. If we want same-named symbols to be equal, then we should use the global registry: `Symbol.for(key)` returns (creates if needed) a global symbol with `key` as the name. Multiple calls of `Symbol.for` with the same `key` return exactly the same symbol.

Symbols have two main use cases:

1. "Hidden" object properties.
    If we want to add a property into an object that "belongs" to another script or a library, we can create a symbol and use it as a property key. A symbolic property does not appear in `for..in`, so it won't be accidentally processed together with other properties. Also it won't be accessed directly, because another script does not have our symbol. So the property will be protected from accidental use or overwrite.

    So we can "covertly" hide something into objects that we need, but others should not see, using symbolic properties.

2. There are many system symbols used by JavaScript which are accessible as `Symbol.*`. We can use them to alter some built-in behaviors. For instance, later in the tutorial we'll use `Symbol.iterator` for [iterables](info:iterable), `Symbol.toPrimitive` to setup [object-to-primitive conversion](info:object-toprimitive) and so on.

Technically, symbols are not 100% hidden. There is a built-in method [Object.getOwnPropertySymbols(obj)](mdn:js/Object/getOwnPropertySymbols) that allows us to get all symbols. Also there is a method named [Reflect.ownKeys(obj)](mdn:js/Reflect/ownKeys) that returns *all* keys of an object including symbolic ones. So they are not really hidden. But most libraries, built-in functions and syntax constructs don't use these methods.

# Object to primitive conversion

What happens when objects are added `obj1 + obj2`, subtracted `obj1 - obj2` or printed using `alert(obj)`?

In that case, objects are auto-converted to primitives, and then the operation is carried out.

In the chapter <info:type-conversions> we've seen the rules for numeric, string and boolean conversions of primitives. But we left a gap for objects. Now, as we know about methods and symbols it becomes possible to fill it.

1. All objects are `true` in a boolean context. There are only numeric and string conversions.
2. The numeric conversion happens when we subtract objects or apply mathematical functions. For instance, `Date` objects (to be covered in the chapter <info:date>) can be subtracted, and the result of `date1 - date2` is the time difference between two dates.
3. As for the string conversion -- it usually happens when we output an object like `alert(obj)` and in similar contexts.

## ToPrimitive

We can fine-tune string and numeric conversion, using special object methods.

There are three variants of type conversion, so-called "hints", described in the [specification](https://tc39.github.io/ecma262/#sec-toprimitive):

`"string"`
: For an object-to-string conversion, when we're doing an operation on an object that expects a string, like `alert`:

    ```js
    // output
    alert(obj);

    // using object as a property key
    anotherObj[obj] = 123;
    ```

`"number"`
: For an object-to-number conversion, like when we're doing maths:

    ```js
    // explicit conversion
    let num = Number(obj);

    // maths (except binary plus)
    let n = +obj; // unary plus
    let delta = date1 - date2;

    // less/greater comparison
    let greater = user1 > user2;
    ```

`"default"`
: Occurs in rare cases when the operator is "not sure" what type to expect.

    For instance, binary plus `+` can work both with strings (concatenates them) and numbers (adds them), so both strings and numbers would do. So if a binary plus gets an object as an argument, it uses the `"default"` hint to convert it.

    Also, if an object is compared using `==` with a string, number or a symbol, it's also unclear which conversion should be done, so the `"default"` hint is used.

    ```js
    // binary plus uses the "default" hint
    let total = obj1 + obj2;

    // obj == number uses the "default" hint
    if (user == 1) { ... };
    ```

    The greater and less comparison operators, such as `<` `>`, can work with both strings and numbers too. Still, they use the `"number"` hint, not `"default"`. That's for historical reasons.

    In practice though, we don't need to remember these peculiar details, because all built-in objects except for one case (`Date` object, we'll learn it later) implement `"default"` conversion the same way as `"number"`. And we can do the same.

Please note -- there are only three hints. It's that simple.

There is no "boolean" hint (all objects are `true` in boolean context) or anything else. And if we treat `"default"` and `"number"` the same, like most built-ins do, then there are only two conversions.

**To do the conversion, JavaScript tries to find and call three object methods:**

1. Call `obj[Symbol.toPrimitive](hint)` - the method with the symbolic key `Symbol.toPrimitive` (system symbol), if such method exists,
2. Otherwise if hint is `"string"`
    - try `obj.toString()` and `obj.valueOf()`, whatever exists.
3. Otherwise if hint is `"number"` or `"default"`
    - try `obj.valueOf()` and `obj.toString()`, whatever exists.

## Symbol.toPrimitive

Let's start from the first method. There's a built-in symbol named `Symbol.toPrimitive` that should be used to name the conversion method, like this:

```js
obj[Symbol.toPrimitive] = function(hint) {
  // must return a primitive value
  // hint = one of "string", "number", "default"
};
```

For instance, here `user` object implements it:

```js run
let user = {
  name: "John",
  money: 1000,

  [Symbol.toPrimitive](hint) {
    alert(`hint: ${hint}`);
    return hint == "string" ? `{name: "${this.name}"}` : this.money;
  }
};

// conversions demo:
alert(user); // hint: string -> {name: "John"}
alert(+user); // hint: number -> 1000
alert(user + 500); // hint: default -> 1500
```

As we can see from the code, `user` becomes a self-descriptive string or a money amount depending on the conversion. The single method `user[Symbol.toPrimitive]` handles all conversion cases.


## toString/valueOf

Methods `toString` and `valueOf` come from ancient times. They are not symbols (symbols did not exist that long ago), but rather "regular" string-named methods. They provide an alternative "old-style" way to implement the conversion.

If there's no `Symbol.toPrimitive` then JavaScript tries to find them and try in the order:

- `toString -> valueOf` for "string" hint.
- `valueOf -> toString` otherwise.

These methods must return a primitive value. If `toString` or `valueOf` returns an object, then it's ignored (same as if there were no method).

By default, a plain object has following `toString` and `valueOf` methods:

- The `toString` method returns a string `"[object Object]"`.
- The `valueOf` method returns the object itself.

Here's the demo:

```js run
let user = {name: "John"};

alert(user); // [object Object]
alert(user.valueOf() === user); // true
```

So if we try to use an object as a string, like in an `alert` or so, then by default we see `[object Object]`.

And the default `valueOf` is mentioned here only for the sake of completeness, to avoid any confusion. As you can see, it returns the object itself, and so is ignored. Don't ask me why, that's for historical reasons. So we can assume it doesn't exist.

Let's implement these methods.

For instance, here `user` does the same as above using a combination of `toString` and `valueOf` instead of `Symbol.toPrimitive`:

```js run
let user = {
  name: "John",
  money: 1000,

  // for hint="string"
  toString() {
    return `{name: "${this.name}"}`;
  },

  // for hint="number" or "default"
  valueOf() {
    return this.money;
  }

};

alert(user); // toString -> {name: "John"}
alert(+user); // valueOf -> 1000
alert(user + 500); // valueOf -> 1500
```

As we can see, the behavior is the same as the previous example with `Symbol.toPrimitive`.

Often we want a single "catch-all" place to handle all primitive conversions. In this case, we can implement `toString` only, like this:

```js run
let user = {
  name: "John",

  toString() {
    return this.name;
  }
};

alert(user); // toString -> John
alert(user + 500); // toString -> John500
```

In the absence of `Symbol.toPrimitive` and `valueOf`, `toString` will handle all primitive conversions.

## Return types

The important thing to know about all primitive-conversion methods is that they do not necessarily return the "hinted" primitive.

There is no control whether `toString` returns exactly a string, or whether `Symbol.toPrimitive` method returns a number for a hint `"number"`.

The only mandatory thing: these methods must return a primitive, not an object.

For historical reasons, if `toString` or `valueOf` returns an object, there's no error, but such value is ignored (like if the method didn't exist). That's because in ancient times there was no good "error" concept in JavaScript.

In contrast, `Symbol.toPrimitive` *must* return a primitive, otherwise there will be an error.

## Further conversions

As we know already, many operators and functions perform type conversions, e.g. multiplication `*` converts operands to numbers.

If we pass an object as an argument, then there are two stages:
1. The object is converted to a primitive (using the rules described above).
2. If the resulting primitive isn't of the right type, it's converted.

For instance:

```js run
let obj = {
  // toString handles all conversions in the absence of other methods
  toString() {
    return "2";
  }
};

alert(obj * 2); // 4, object converted to primitive "2", then multiplication made it a number
```

1. The multiplication `obj * 2` first converts the object to primitive (that's a string `"2"`).
2. Then `"2" * 2` becomes `2 * 2` (the string is converted to number).

Binary plus will concatenate strings in the same situation, as it gladly accepts a string:

```js run
let obj = {
  toString() {
    return "2";
  }
};

alert(obj + 2); // 22 ("2" + 2), conversion to primitive returned a string => concatenation
```

## Summary

The object-to-primitive conversion is called automatically by many built-in functions and operators that expect a primitive as a value.

There are 3 types (hints) of it:
- `"string"` (for `alert` and other operations that need a string)
- `"number"` (for maths)
- `"default"` (few operators)

The specification describes explicitly which operator uses which hint. There are very few operators that "don't know what to expect" and use the `"default"` hint. Usually for built-in objects `"default"` hint is handled the same way as `"number"`, so in practice the last two are often merged together.

The conversion algorithm is:

1. Call `obj[Symbol.toPrimitive](hint)` if the method exists,
2. Otherwise if hint is `"string"`
    - try `obj.toString()` and `obj.valueOf()`, whatever exists.
3. Otherwise if hint is `"number"` or `"default"`
    - try `obj.valueOf()` and `obj.toString()`, whatever exists.

In practice, it's often enough to implement only `obj.toString()` as a "catch-all" method for all conversions that return a "human-readable" representation of an object, for logging or debugging purposes.  


# Conclusion

That's Alot! We thank the authors from https://javascript.info/ For supporting this lesson, and without them, I don't think It would be possible to do such a huge work! In the next tutorial, We'll discuss how we can interact With websites in order to make our modern development success.