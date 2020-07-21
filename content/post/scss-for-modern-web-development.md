---
title: "Scss for Modern Web Development (Supercharged CSS)"
date: 2020-07-21T06:59:06+05:30
Description: "Let's Supercharge css with scss"
Tags: ["web development","SCSS","Zero To Hero","Crash Course"]
Categories: []
DisableComments: false
---

# Introduction

If you noticed, I Didn't mentioned css for browser types in our previous CSS tutorial, The case is, I don't want to, SCSS is doing everything for us so why should we even bother? Let's get started with SCSS and supercharge our css.

# Pre-Setup

SCSS isn't a universal solution, it's here to help us with variables, nesting and automatic css generation. So we need a software to compile scss into css, here I'm using VSCode and an extension called live SCSS compiler. you can download it [Here](https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass). Install it to VSCode and you're good to go. You can see how to setup VSCode [Here](/post/vs-code-for-web-developers/).

# Folder Structure and Setup

Now, SCSS works like this, you have to create a HTML file and a SCSS file, and through the extension, we have to activate the SCSS watcher and It generates a css file in the same name as the scss file, so We can link up the css file as usual. Enough theory for that part, let's do some work. You need basic CSS knowledge, and if you didn't followed any of our tutorials Before, Check the CSS Guide [Here](/post/css-for-modern-web-development/) And the HTML Guide [Here](/post/html-for-modern-web-development/)

So to start With, I Have a index.html and style.scss file in the root folder 

![Folder Structure](/uploads/20200721_01.png)

And I'm using a simple boilerplate in HTML file and nothing else.

![Folder Structure](/uploads/20200721_02.png)

Now we have to start scss generation, here we have to open the scss file and select watch sass button to the bottom and you can see a css and css.map file generates automatically.

![VSCode](/uploads/20200721_03.png)
![VSCode](/uploads/20200721_04.png)

Now link that css file to our html page and we are pretty much done and ready to code.

![VSCode](/uploads/20200721_05.png)

# Coding Section

Let's Start Coding The, First of all, SCSS is almost like css but We have extended functionalities such as nested elements functions and Variables, Here's an Example for you.

>       /* Define standard variables and values for website */
>       $bgcolor: lightblue;
>       $textcolor: darkblue;
>       $fontsize: 18px;
>       
>       /* Use the variables */
>       body {
>         background-color: $bgcolor;
>         color: $textcolor;
>         font-size: $fontsize;
>       }

Let's get started.

## Sass Variables
variables are variables in every language and I explained variables so much and here again explaining the same concept, Variable holds data and there are several types of data we can set a variable to,
* String
* numbers
* colors
* booleans
* lists
* nulls

It's a bit different in SCSS but works the same, Variables are defined and used with a $ sign in-front of it's name. For and example,

>       /* Defining Variables */
> 
>       $myColor: red;
>       $myFontSize: 18px;
> 
>       /* Using Variables */
> 
>       body {
>         font-size: $myFontSize;
>         color: $myColor;
>       }
>       
>       #container {
>         background: $myColor;
>       }

And The Automatically generated CSS File would be like this

>       body {
>         font-size: 18px;
>         color: red;
>       }
>       
>       #container {
>         background: red;
>       }

## Sass Variable Scope

There are two types of scopes, Global and local. Global scoped variables can be defined in the root line, outside any selectors, and local variables are defined inside selectors.

>       /* Global Variables */
>       $myColor: red;
>       
>       h1 {
>         /* Local Variables */
>         $myColor: green;
>         color: $myColor;
>       }
>       
>       p {
>         color: $myColor;
>       }

And the CSS Output would be

>       h1 {
>         color: green;
>       }
>       
>       p {
>         color: red;
>       }

## Using Sass !global

Using this, you can change global scoped variables. For an example,

>       $myColor: red;
>       
>       h1 {
>         $myColor: green !global;
>         color: $myColor;
>       }
>       
>       p {
>         color: $myColor;
>       }

And the css output would be

>       h1 {
>         color: green;
>       }
>       
>       p {
>         color: green;
>       }

## Sass Nested Rules and Properties

Assume you have a h1 tag inside a div element and we need to change only it's color to red. you can select it directly with scss using the same nesting procedure as the HTML, let's explore, now to select only the h1 tag in the div, we can use

>       div {
>           h1 {
>               color:red;
>           }
>       }

CSS Output would be

>       div h1 {
>           color:reed;
>       }

## Sass Nested Properties

This is something new, but I'm pretty sure you can wrap your head around it pretty easily. Remember font-size, font-family, font-weight properties? and text-align, text-transform, text-overflow properties? these have font and text in common, so we can use these common words to nest properties like this.

>       font: {
>         family: Helvetica, sans-serif;
>         size: 18px;
>         weight: bold;
>       }
>       
>       text: {
>         align: center;
>         transform: lowercase;
>         overflow: hidden;
>       }

And the CSS Output would be

>       font-family: Helvetica, sans-serif;
>       font-size: 18px;
>       font-weight: bold;
>       
>       text-align: center;
>       text-transform: lowercase;
>       text-overflow: hidden;

## SCSS @import and export

Let's talk about these files, you can import properties from different files, which means for an example, you can save variables in a file and use them in another file. but to export, you have to end that file name with an Underscore ( _ ).

>       _variables.scss

and you can import it to working file using

>       @import "variables";

And that's all for importing.

## Sass @mixin and @include

assume this as a function in other languages, you can create code blocks to re use in scss using @mixin.

>       @mixin itext {
>         color: red;
>         font-size: 25px;
>       }

Now you can use @include to use that mixin in SCSS

>       div {
>           h1{
>               @include itext;
>           }
>           h2{
>               @include itext;
>           }
>       }

And the CSS Output would be

>       div h1{
>           color: red;
>           font-size: 25px;
>       }
>       div h2{
>           color: red;
>           font-size: 25px;
>       }

### Passing Variables to a Mixin
Just like in functions, you can preform some dynamic actions with Mixin. you can define dynamic mixin as this.

>       @mixin bordered($color, $width) {
>         border: $width solid $color;
>       }

Now you can use this mixin like this

>       div {
>           h1{
>               @include bordered(red, 2px);
>           }
>           h2{
>               font-size: 25px;
>           }
>       }

And the CSS Output Would be

>       div h1{
>           border: 2px solid red;
>       }
>       div h2{
>           font-size: 25px;
>       }

### Default Values for a Mixin

Also you can set default values in case you forgot to include one,

>       @mixin bordered($color: blue, $width: 1px) {
>         border: $width solid $color;
>       }

## Sass @extend and Inheritance

Here's the last thing you need to know about SCSS, It's a simple code block which allows you to re-use a code from a selector you already wrote

>       .button-basic  {
>         border: none;
>         padding: 15px 30px;
>         text-align: center;
>         font-size: 16px;
>         cursor: pointer;
>       }
>       
>       .button-report  {
>         @extend .button-basic;
>         background-color: red;
>       }

Here with the extend inheritance, you just added what's in button-basic to button-report, The css out would be.

>       .button-basic  {
>         border: none;
>         padding: 15px 30px;
>         text-align: center;
>         font-size: 16px;
>         cursor: pointer;
>       }
>       
>       .button-report  {
>         border: none;
>         padding: 15px 30px;
>         text-align: center;
>         font-size: 16px;
>         cursor: pointer;
>         background-color: red;
>       }

And That's IT! You're a pro now.

# Let's Create a super cool website using SCSS and HTML

Now it's time to the fun part, Let's create A Super cool website and as always, you can download it [Here](/zip/ModernWebDevelopmentAssetPack02.zip).

We already made the boilerplate and in My HTML page is like this.

>       <!DOCTYPE html>
>       <html lang="en">
>       
>       <head>
>           <meta charset="UTF-8">
>           <meta name="viewport" content="width=device-width, initial-scale=1.0">
>           <link rel="stylesheet" href="style.css">
>           <title>SCSS Demo</title>
>       </head>
>       
>       <body>
>           <div class="nav">
>               <div class="list">
>                   <a>Contact Us</a>
>                   <a>About</a>
>                   <a>Home</a>
>               </div>
>           </div>
>           <div class="content">
>               <h4>Digital Guideline Of 21st Century</h4><br>
>               <h1>TECINPACT</h1>
>           </div>
>           <div class="footer">Tecinpact © 2020 All Rights Reserved.</div>
>       </body>
>       
>       </html>

And My SCSS File looks like this, Also I downloaded a background from UNSplash and you can read about free assets [Here](/post/royalty-free-internet-resources/).

>       $background : url(bg.jpg);
>       $dark : #1f1e2f;
>       $mode : #111E6C;
>       $lite : white;
>       
>       html {
>           height: 100%;
>       
>           body {
>               font-family: monospace;
>               background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), $background;
>               background-repeat: no-repeat;
>               background-size: cover;
>               background-position: center;
>               color: $lite;
>               box-sizing: border-box;
>       
>               .nav {
>                   position: absolute;
>                   top: 0;
>                   width: 100%;
>                   font-size: 20px;
>       
>                   .list {
>                       a {
>                           float: right;
>                           text-align: center;
>                           padding: 14px 16px;
>                           text-decoration: none;
>                           font-size: 20px;
>                           margin: 10px 20px;
>                       }
>                   }
>               }
>       
>               .content {
>                   display: grid;
>                   place-items: center;
>                   position: absolute;
>                   width: 100%;
>                   top: 25%;
>       
>                   h4 {
>                       font-size: 2em;
>                       margin: 0;
>                   }
>       
>                   h1 {
>                       font-size: 8.5em;
>                       margin: 0;
>                   }
>               }
>       
>               .footer {
>                   position: absolute;
>                   width: 100%;
>                   bottom: 0;
>                   text-align: center;
>                   margin: 20px;
>               }
>           }
>       }

And if you look in to the css file, It's complicated and Cool because it's what we need and It's there without much effort

![Site](/uploads/20200721_06.png)

# Conclusion

Let's be real, we don't like to write so-much code for so many vendors and it would be super cool if most of the things has been automated, I use SCSS Regularly on my projects so I can save a lot of time and code easily. So even you should use it for sure!