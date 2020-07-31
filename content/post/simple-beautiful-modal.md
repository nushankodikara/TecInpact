---
title: "Simple, Beautiful Modal"
date: 2020-07-28T06:00:00+05:30
Description: ""
Tags: ["Javascript","Jquery","HTML","SCSS","CSS","Web Guide", "web development"]
Categories: []
DisableComments: false
---

# Introduction
We all come across a situation when the default notify-the-user procedure is getting incompatible with our project theme and appearance, so in this guide I'm going to discuss about creating a beautiful modal for your web project, with a SCSS and JQuery ( a little bit ) before this, you have to master [HTML](/post/html-for-modern-web-development/) [CSS](/post/css-for-modern-web-development/) [SCSS](/post/scss-for-modern-web-development/) [JS part 1](/post/js-for-modern-web-development/) and [JS part 2](/content/post/js-for-modern-web-development-2/) guides.

Now in this guide, We're making This Beautiful modal from scratch with only 14 lines of JS codes. I'm using HTML SCSS and a JS file in the root folder.

![Modal](/uploads/20200728_01.gif)

Now it's not hard at all, [Here](/zip/Asset4.zip) you can also Download the whole project.

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>SCSS Demo</title>
</head>

<body>
    <div class="nav">
        <div class="list">
            <a>Contact Us</a>
            <a>About</a>
            <a>Home</a>
        </div>
    </div>
    <div class="content">
        <h4>Digital Guideline Of 21st Century</h4><br>
        <h1>TECINPACT</h1>
        <button onclick="butotnFunction()">Show Modal</button>
    </div>
    <div class="footer">Tecinpact © 2020 All Rights Reserved.</div>
    <div class="wrapper">
        <div class="modal">
            <close onclick="butotnFunction()">X</close>
            <header># Modal</header>
            <main>Modal Content Goes Here
                <ul>
                    <li>Press That X To close</li>
                    <li>It's Nice and simple</li>
                </ul>
            </main>
            <footer>Copyright 2020 Tecinpact Or Something</footer>
        </div>
    </div>
    <script src="https://code.jquery.com/jquery-3.5.1.min.js"
        integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
    <script src="./index.js"></script>
</body>

</html>
```

In the HTML file, I'm creating a very simple webpage and we made this page in [This Guide](/post/scss-for-modern-web-development/) From scratch and additionally I'm adding a Button to open the modal. Also after this code, I'm adding a div with a class of wrapper and in it i'm creating the modal, This wrapper makes the background darker when the modal is showing. And in the modal, I'm creating a close button, header section, main section for content and a footer section. and also I'm adding JQuery from CDN in the end of the document.

```scss
$background : url(https://images.unsplash.com/photo-1593642703055-4b72c180d9b5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80);
$dark : #1f1e2f;
$mode : #111E6C;
$lite : white;

html {
    height: 100%;
    width: 100%;
    position: fixed;
    user-select: none;

    body {
        font-family: monospace;
        background: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.3)), $background;
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;
        color: $lite;
        box-sizing: border-box;

        .nav {
            position: absolute;
            top: 0;
            width: 100%;
            font-size: 20px;

            .list {
                a {
                    float: right;
                    text-align: center;
                    padding: 14px 16px;
                    text-decoration: none;
                    font-size: 20px;
                    margin: 10px 20px;
                }
            }
        }

        .content {
            display: grid;
            place-items: center;
            position: absolute;
            width: 100%;
            top: 25%;

            h4 {
                font-size: 2em;
                margin: 0;
            }

            h1 {
                font-size: 8.5em;
                margin: 0;
            }

            button {
                padding: 15px 95px;
                margin: 10px;
                border-radius: 500px;
                outline: none;
                border: none;
                font-size: large;
                font-weight: bold;
                color: blanchedalmond;
                background-image: linear-gradient(to right, #b6bebd, #adb4b0, #a6aaa3, #a09f97, #9a948d, #958e86, #8f897e, #8a8377, #7f8272, #718171, #617f76, #547c7e);
                transition-timing-function: linear;
                transition-duration: 0.1s;
            }

            button:hover {
                padding: 15px 105px;
                border: solid #547c7e 2px;
            }
        }

        .footer {
            position: absolute;
            width: 100%;
            bottom: 0;
            text-align: center;
            margin: 20px;
        }

        .wrapper {
            position: fixed;
            z-index: 2;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            display: grid;
            place-items: center;
            background-color: rgba(0, 0, 0, 0.8);

            .modal {
                close {
                    position: absolute;
                    top: 0;
                    right: 0;
                    font-size: 50px;
                    color: red;
                    padding: 20px;
                }

                header {
                    margin-bottom: 20px;
                    font-size: 3.5em;
                }

                main {
                    font-size: 2em;
                }

                footer {
                    font-size: 1.5em;
                }

                width: 350px;
                height: 350px;
                border-radius: 20px;
                background-image: linear-gradient(to right top, #d16ba5, #c777b9, #ba83ca, #aa8fd8, #9a9ae1, #8aa7ec, #79b3f4, #69bff8, #52cffe, #41dfff, #46eefa, #5ffbf1);
                padding: 50px;
                text-align: center;
                display: grid;
                grid-template-rows: auto 1fr auto;
            }
        }
    }
}
```
And now here's the scss Now in here, I'm defining the page width and height in the HTML tags and setting the font aspects in the body, I explained this SCSS code once and here I'm only explaining the modal section. Now when considering the wrapper I fixed it's position and adjusted z-index to 2 to make it appear in-front of everything. Also I used a trick from [This Guide](/post/1line-css-tricks-part1/) to add the modal to the center of the wrapper. and then adjusted some basic aspects and again used a trick from [This Guide](/post/1line-css-tricks-part1/) to layout the modal.

```js
$(".wrapper").css({
    display: "none"
});
let modalStat = 0;

butotnFunction = () => {
    if (modalStat == 0) {
        $(".wrapper").fadeIn(500);
        modalStat = 1;
    } else {
        $(".wrapper").fadeOut(500);
        modalStat = 0;
    }
}
```

Here's where the magic happens. Now considering this code, It's very simple isn't it? yeah I'm using a library called JQuery for this section. and I'm sure you never saw this kinds of codes if you're a beginner. now let's explore and I'll post a JQuery guide in the near future. Here the $(".wrapper") is equal to
>   document.getElementByClass

from JS and I'm selecting the class wrapper and in the beginning changing it's css to hide when the page loads. and then I'm setting modalStat which is a way for my program to know wether the modal is hidden or not to 0 means hidden and 1 means active. now I'm creating a basic JS function called butotnFunction which I miss spelled but it works for the program, and adding a simple logic to make it appear if hidden and hide if appeared when the function calls. And you can see in the HTML page, that I assigned onclick attribute to this function. When the button in the main page or the X to close button is pressed, this works perfectly and And also Don't forget to use this in your next project.

# Conclusion
It's simple, It's beautiful, It's Elegant and I love it, I hope you like it too and the code is simple and easy to understand. I assume you learn something new today.