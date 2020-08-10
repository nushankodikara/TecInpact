---
title: "Let's Create a Mobile App for TECINPACT"
date: 2020-08-02T06:00:00+05:30
Description: "Here, We're creating an app for tecinpact using previous tutorial"
Tags: ["Android","IOS","Mobile development","Hybrid Apps"]
Categories: []
DisableComments: false
---

## Introduction

Today we're creating an app for our agency using Hybrid technology which we discussed in [THIS ARTICLE](/post/creating-mobile-apps-with-cordova/), And if you didn't checked it out, Go ahead and try now, I'm only showing you the codes I used here And also This is an demo on how to use the technology, Then we're publishing it on playstore Tomorrow! How cool is that? started as a web developer and now you're an official mobile developer. Let's get started.

## Setup

Read the previous article and get a feel for it, now you should have,

* created the project
* added android plugin
* added multidex
* configured an Icon
* added android key and build.json

If you did these things, Let's get started with the coding. Now first you have to configure your config.xml file. let me show you what I did. This is how my config.xml file looks like.

```xml
<?xml version='1.0' encoding='utf-8'?>
<widget id="tk.tecinpact.app" version="1.1.0" xmlns="http://www.w3.org/ns/widgets" xmlns:cdv="http://cordova.apache.org/ns/1.0">
    <name>Tecinpact</name>
    <description>
        Tecinpact Official Application
    </description>
    <author email="nushankodi@gmail.com" href="https://tecinpact.tk">
        Nushan Kodikara
    </author>
    <content src="index.html" />
    <plugin name="cordova-plugin-whitelist" spec="1" />
    <access origin="*" />
    <allow-intent href="http://*/*" />
    <allow-intent href="https://*/*" />
    <allow-intent href="tel:*" />
    <allow-intent href="sms:*" />
    <allow-intent href="mailto:*" />
    <allow-intent href="geo:*" />
    <icon src="./res/icon.png"/>
    <platform name="android">
        <allow-intent href="market:*" />
    </platform>
    <platform name="ios">
        <allow-intent href="itms:*" />
        <allow-intent href="itms-apps:*" />
    </platform>
</widget>
```

Notice some differences? Yeah I added package name to widget id and version is the version number, you have to increase the version number every time you release an update. Then in the name tags, I added my app name also a description and then in author tags, I filled every thing with my personal details. Also notice I added an Icon before platform tags.

Now that out to the way, delete everything in the WWW folder and add your responsive web design to this folder. This is where your main code lives. and notice the `<content src="index.html" />` in the config.xml It's the main file of the www folder. I keep it as index.html and this is what my index.html looks like

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="./font-awesome-4.7.0/css/font-awesome.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Aclonica&display=swap" rel="stylesheet">
    <title>SCSS Demo</title>
</head>

<body>
    <div class="preloader">
        <div class="loading">
            <div></div>
            <div></div>
            <div></div>
        </div>
        <h1 class="loadingText">Loading Please Wait</h1>
    </div>
    <div class="content">
        <div class="body">
            <div class="nav">
                <div class="list">
                    <a onclick="butotnFunction()">About</a>
                </div>
            </div>
            <div class="content">
                <h4>Digital Guideline Of 21st Century</h4><br>
                <h1>TECINPACT</h1>
                <button onclick="window.location.replace('https://www.tecinpact.tk');">Visit Website</button>
                <button onclick="showFeed()">View Posts</button>
            </div>
            <div class="footer">Tecinpact © 2020 All Rights Reserved.</div>
            <div class="wrapper">
                <div class="modal">
                    <close onclick="butotnFunction()">X</close>
                    <header># Tecinpact</header>
                    <main>
                        TECINPACT is a Digital Guide Book to navigate through the 21st century cyber space in a safe and
                        cheap
                        manner. As we can get most of the products and services we’re paying for pennies, my vision here
                        is
                        to
                        support the non-geeks and starters to start their Cyber career with a boost.
                    </main>
                    <footer>Copyright 2020 Tecinpact</footer>
                </div>
            </div>
            <table>
                <tr>
                    <td class="facebook" onclick="window.location.replace('https://www.facebook.com/tecinpact');"><a
                            href="https://www.facebook.com/tecinpact"><i class="fa fa-facebook"></i></a>
                    </td>
                    <td class="twitter" onclick="window.location.replace('https://www.twitter.com/tecinpact');"><a
                            href="https://www.twitter.com/tecinpact"><i class="fa fa-twitter"></i></a></td>
                    <td class="instagram" onclick="window.location.replace('https://www.instagram.com/tecinpact');"><a
                            href="https://www.instagram.com/tecinpact"><i class="fa fa-instagram"></i></a>
                    </td>
                </tr>
                <tr>
                    <td class="whatsapp" onclick="window.location.replace('https://wa.me/94769477743');"><a
                            href="https://wa.me/94769477743"><i class="fa fa-whatsapp"></i></a></td>
                    <td class="email" onclick="window.location.replace('mailto:tecinpactagencies@gmail.com');"><a
                            href="mailto:tecinpactagencies@gmail.com"><i class="fa fa-envelope"></a></td>
                    <td class="telegram" onclick="window.location.replace('https://t.me/tecinpact');"><a
                            href="https://t.me/tecinpact"><i class="fa fa-telegram"></i></a></td>
                </tr>
            </table>
        </div>
        <div class="feed">
            <p class="back" onclick="showFeed()">Go Back</p>
            <div class="textBox"></div>
        </div>
    </div>

    <script src="./jquery-3.5.1.min.js"></script>
    <script src="./index.js"></script>
</body>

</html>
```

Here in the head tags, I linked my main css, a fontawesome pack and a custom font from google to make it fancy or so. and my document has 2 sections divided with div tags called preloader and content. Preloader is where the loading animation lives, I animate it with a CSS code section. and the content section. Is this looks familiar? Yes it should be! We made this template in the [JS CSS modal](/post/simple-beautiful-modal/) tutorial! and oh boy it came in handy isn't it. And for something new, I added a new button and a div with a ID of feed, this is where I grab My website's rss feed and convert it to html. so you can see it as new posts and when I update my app, You'll be able to see it instantly here! also because xml is a small file, it would cost you arround 5-10kb per session and that's like nothing these days! My logic here is to hide unwanted sections and show only one section at a time, so it would look like a native app with smooth animations. I'll explain it in the future.

Now let's see the SCSS code, If you don't know what scss is, I have a tutorial for it too and go and study it [HERE](/post/scss-for-modern-web-development)

```scss
$background : url(background.jpg);
$buttons : linear-gradient(to right top, #191d3c, #151831, #121425, #0e0d1b, #05050f);
$modal : linear-gradient(to right top, #532527, #401d29, #2c1826, #19121d, #05050f);
$fonts : 'Aclonica',
sans-serif,
monospace;
$dark : #1f1e2f;
$mode : #111E6C;
$lite : white;

html {
    height: 100%;
    width: 100%;
    position: fixed;
    user-select: none;

    body {

        font-family: $fonts;
        background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), $background;
        background-color: #282d53;
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;
        color: $lite;
        box-sizing: border-box;

        .preloader {
            display: grid;
            place-items: center;
            width: 100%;
            height: 100%;
            position: fixed;
            top: 0;
            left: 0;

            .loading {
                display: flex;
                justify-content: center;

                div {
                    width: 1rem;
                    height: 1rem;
                    margin: 2rem 0.3rem;
                    background: white;
                    border-radius: 50%;
                    animation: 0.9s bounce infinite alternate;

                    &:nth-child(2) {
                        animation-delay: 0.3s;
                    }

                    &:nth-child(3) {
                        animation-delay: 0.6s;
                    }
                }
            }

            @keyframes bounce {
                to {
                    opacity: 0.3;
                    transform: translate3d(0, -1rem, 0);
                }
            }
        }

        .content {
            display: none;

            .feed {
                .textBox {
                    position: fixed;
                    overflow-y: auto;
                    top: 100px;
                    left: 0;
                    height: 80%;
                    background-color: rgba(0, 0, 0, 0.8);
                    padding: 20px;
                    margin: 0;
                    border-radius: 20px;

                    .link {
                        color: skyblue;
                        font-size: large;
                        text-decoration: none;
                    }
                }

                .back {
                    position: fixed;
                    left: 50%;
                    transform: translate(-50%, 0);
                    z-index: 2;
                    padding: 10px 50px;
                    border-radius: 500px;
                    background-image: $buttons;
                    transition-timing-function: linear;
                    transition-duration: 0.1s;
                    border: solid #14162b 2px;
                }

                .back:hover {
                    padding: 10px 55px;
                    border: solid #ffffff 2px;
                }
            }

            .body {

                table {
                    position: fixed;
                    bottom: 80px;
                    left: 0;
                    width: 100%;
                    justify-content: center;
                    text-align: center;

                    tr {
                        td {
                            padding: 10px;
                            border-radius: 500px;

                            a {
                                color: white;
                                font-size: 1.5em;
                                text-decoration: none;
                                margin: 10px;
                            }
                        }

                        .facebook {
                            background-color: #3b5998;
                            border: solid 2px #3b5998;
                        }

                        .twitter {
                            background-color: #00acee;
                            border: solid 2px #00acee;
                        }

                        .instagram {
                            background-color: #ee0077;
                            border: solid 2px #ee0077;
                        }

                        .whatsapp {
                            background-color: #075E54;
                            border: solid 2px #075E54;
                        }

                        .email {
                            background-color: #aaaaaa;
                            border: solid 2px #aaaaaa;
                        }

                        .telegram {
                            background-color: #0088CC;
                            border: solid 2px #0088CC;
                        }

                        td:hover {
                            background-color: black;
                            transition-timing-function: linear;
                            transition-duration: 0.1s;
                            border: solid 2px yellow;

                            a {
                                color: yellow;
                            }
                        }
                    }
                }

                .nav {
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    font-size: 20px;

                    .list {
                        text-align: center;
                        margin-top: 20px;

                        a {
                            text-align: center;
                            padding: 14px 16px;
                            text-decoration: none;
                            font-size: 20px;
                            padding: 10px 60px;
                            background-image: $buttons;
                            border: solid #14162b 2px;
                            border-radius: 500px;
                            color: white;
                        }

                        a:hover {
                            transition-timing-function: linear;
                            transition-duration: 0.1s;
                            border: solid rgb(255, 255, 255) 2px;
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
                        font-size: 4em;
                        margin: 0;
                    }

                    button {
                        font-family: $fonts;
                        padding: 15px 95px;
                        margin: 10px;
                        border-radius: 500px;
                        outline: none;
                        border: none;
                        font-size: large;
                        color: white;
                        background-image: $buttons;
                        transition-timing-function: linear;
                        transition-duration: 0.1s;
                        border: solid #14162b 2px;
                    }

                    button:hover {
                        padding: 15px 105px;
                        border: solid #ffffff 2px;
                    }
                }

                .footer {
                    position: fixed;
                    width: 100%;
                    bottom: 0;
                    left: 0;
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
                            font-size: 1em;
                        }

                        footer {
                            font-size: 1.5em;
                        }

                        max-width: 350px;
                        height: 350px;
                        border-radius: 20px;
                        background-image: $modal;
                        padding: 50px;
                        text-align: center;
                        display: grid;
                        grid-template-rows: auto 1fr auto;
                    }
                }
            }
        }
    }
}
```

This code isn't hard, anyone can understand this with my CSS and SCSS guides because they are different from what you find in the other sites. and Also I used tricks from my single line css tricks guide. Those are the things that would get hard and I already explained almost everything in other guides so I'm not going to do it here.

This is where the fun begins, Let's see how I did the JS code. Here, I used a library called JQuery and I didn't covered it yet, I'll do it in the near future however, but the code is easy to understand and I explained JQuery a bit in one of my previous guides.

Also don't consider the animation part for now, we're doing a full css animation guide in the future, let me know would you like to see it sooner or later in the comments bellow.

```js
$(".wrapper").css({
    display: "none"
});
$(".feed").fadeOut(500);
let modalStat = 0;
let feed = 0;
let xml = ["<h1>Data Loading<br>Please Check Your Internet Connection<br><span onclick='loadData()' style = 'color:#0088CC;' >Reload</span></h1 > "];
$(".textBox").html(xml.join(''))

butotnFunction = () => {
    if (modalStat == 0) {
        $(".wrapper").fadeIn(500);
        modalStat = 1;
    } else {
        $(".wrapper").fadeOut(500);
        modalStat = 0;
    }
}

showFeed = () => {
    if (feed == 0) {
        $(".body").fadeOut(500);
        $(".feed").fadeIn(500);
        feed = 1;
    } else {
        $(".body").fadeIn(500);
        $(".feed").fadeOut(500);
        feed = 0;
    }
}

loadComplete = () => {
    $(".preloader").fadeOut(500);
    $(".content").fadeIn(500);
}

loadData = () => {
    $.get('https://www.tecinpact.tk/index.xml', function (data) {
        xml = ["<h1>Latest Posts With Summaries</h1>"];
        $(data).find("item").each(function () { // or "item" or whatever suits your feed
            var el = $(this);
            var retstring = `<div class='card' >------------------------
        <br>
        <h1>${el.find("title").text()}</h1>
        <br>
        <small>${el.find("pubDate").text()}</small>
        <br>
        <p>${el.find("description").text()}<br><a class="link" href="${el.find('link').text()}">Read More>></a></p>
        </div>`;
            xml.push(retstring)
        });
        $(".textBox").html(xml.join(''))
    });
}

$(document).ready(function () {
    setTimeout(function () {
        loadComplete();
    }, 3000);
});

document.addEventListener('deviceready', function (event) {
    document.addEventListener('backbutton', function (e) {
        $(".feed").fadeOut(500);
        $(".body").fadeIn(500);
        $(".wrapper").fadeOut(500);
    })
}, false);

loadData()
```

Let's see what's this does. Here first I'm selecting the div with the class of wrapper and hiding it using css with JQuery, then I'm doing the same thing to the feed but I used a function called fadeOut with it and it's fading out for 500 milliseconds, Then I'm creating 3 variables, modalstat to check wether the modal is showing or not, feed to check wether the feed is showing or not and xml to hold data from the site and I set it a value at the beginning with a message so if something got wrong with the connection, the message would show up and there's a button to refresh the process too!

Then for the functions, I first made this butotnFunction which I miss spelled (But works anyways) for modal to show if hidden and hide if shown. it's checking the variable and if it's 1, modal will hide and if it's 0, modal will show up. also it sets the values to the opposite of the condition they're checking. This is the same for the showFeed function too, but here it's hiding body section while showing itself and vice versa.

Then I have a function called loadComplete, it hides the preloader and shows the content, we're firing this function with a eventhandler lately.

Then we have loadData function. it's the brain behind the dynamic feed of the application. this function fetches the rss feed from my site and phrases it for certain tags and looping through them to get out the content. this is pretty much universal for every feed, so don't mind it. then I add those values to the xml array and in the end, I'm rendering it in the div with the class of textBox.

Now we have the event handler which runs when the document loaded. in it I put a delay function of 3 seconds ( 3000 milliseconds ), this delay is for the post processing and after that we fire our loadComplete function.

Then I have a event handler from cordova to handle backbutton events. this would close modal or get you out of the feed when backing up.

And guys that's it for the application and that's all we have to put to create a supper simple app!

Now you have to run

```js
cordova build android --release
```

to create the application, and Wolah! that's our application!

Let me show you some screenshots!

![Screenshot 1](/uploads/20200802_01.jpg)
![Screenshot 2](/uploads/20200802_02.jpg)
![Screenshot 3](/uploads/20200802_03.jpg)
![Screenshot 4](/uploads/20200802_04.jpg)

## Conclusion

This is how I crate almost every app I develop, and remember, with cordova plugins, you can achieve more advanced functionality and for a simple process as this, This is the future guys!
