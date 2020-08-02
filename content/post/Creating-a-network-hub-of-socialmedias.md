---
title: "Creating a Network Hub for Social Medias"
date: 2020-08-03T06:00:00+05:30
Description: "Network hub for social medias"
Tags: ["Social Game"]
Categories: []
DisableComments: false
---

# Introduction

We all see the new instagram bio link apps are getting popular and popular day by day, and They are just a simple lines of HTML and CSS even without no JS! And I totally think I can re-create this bio link page with HTML and CSS and add some JS to the taste and also add some dynamic functionalities you can use. Today we're discussing about how I made https://bio.tecinpact.tk or in other words, Our Network HUB.

# I Never saw it

In case you didn't saw it before, let me show you a quick overview of what I did there, I added all of my Social links with some description and because I'm a mainstream developer, I added something that would be cool. A RSS Feed, Dynamically Updating from my site and this is it!

![BIO SECTION](/uploads/20200803_01.gif)

# Let's Start Shall we

Because I made this in a hurry, I used two commonly used libraries from the internet to make my life easier, Bootstrap 4 and JQuery 3, If you aren't comfortable with these, check their official documents, Otherwise, Just copy my codes and you'll be good to go! As usual [HERE](/zip/TecinpactBio.zip) is the link to download the documents directly. Let's Start with HTML First, This is a single page setup so the index.html file would be

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css"
        integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">
    <link rel="stylesheet" href="css/style.css">
    <link rel="shortcut icon" href="./img/internet-b.png" type="image/x-icon">
    <title>Bio Section</title>
</head>

<body>
    <div class="preloader">
        <div class="lds-facebook">
            <div></div>
            <div></div>
            <div></div>
        </div>
        <h1>Loading Bio Section</h1>
    </div>
    <div class="content">
        <div class="jumbotron">
            <img src="https://www.tecinpact.tk/images/profile.jpg" />
            <h1 class="display-4">Tecinpact <span class="badge badge-dark">Bio</span></h1>
            <p class="lead">Here you can navigate through all of our sites and groups easily and safely</p>
            <button type="button" onclick="viewQP()" class="btn btn-warning">Show / Hide Quick Posts</button>
        </div>
        <div class="links">
            <div class="alert alert-primary" role="alert">
                <div class="media">
                    <img src="img/internet.png" class="align-self-center mr-3" alt="...">
                    <div class="media-body">
                        <h5 class="mt-0">Main Website</h5>
                        <p>Here's our main blog site, we update content daily and Hope you'll learn something new! Don't
                            forget to let us know your feelings in the comment section.</p>
                        <hr>
                        <a href="https://www.tecinpact.tk" class="alert-link">Visit Site</a>
                    </div>
                </div>
            </div>
            <div class="alert alert-secondary" role="alert">
                <div class="media">
                    <img src="img/facebook.png" class="align-self-center mr-3" alt="...">
                    <div class="media-body">
                        <h5 class="mt-0">Facebook Page</h5>
                        <p>Yes! We have a facebook page and it's also updating with the site. would be glad if you can
                            show some love.</p>
                        <hr>
                        <a href="https://www.facebook.com/tecinpact" class="alert-link">Goto FB Page</a>
                    </div>
                </div>
            </div>
            <div class="alert alert-success" role="alert">
                <div class="media">
                    <img src="img/telegram.png" class="align-self-center mr-3" alt="...">
                    <div class="media-body">
                        <h5 class="mt-0">Telegram Group</h5>
                        <p>We have an amazing community here in Telegram, Everyone's friendly and so helpful. Ask
                            anything you get a doubt about and within minutes, Someone will reply with a super helpful
                            answer!</p>
                        <hr>
                        <a href="https://t.me/tecinpact" class="alert-link">Join Group</a>
                    </div>
                </div>
            </div>
            <div class="alert alert-warning" role="alert">
                <div class="media">
                    <img src="img/playstore.png" class="align-self-center mr-3" alt="...">
                    <div class="media-body">
                        <h5 class="mt-0">Android App</h5>
                        <p>Hey! We have a new android app on the playstore! It's great if you can go and check it out!
                        </p>
                        <hr>
                        <a href="https://play.google.com/store/apps/details?id=tk.tecinpact.app"
                            class="alert-link">Install application</a>
                    </div>
                </div>
            </div>
            <div class="alert alert-danger" role="alert">
                <div class="media">
                    <img src="img/instagram.png" class="align-self-center mr-3" alt="...">
                    <div class="media-body">
                        <h5 class="mt-0">Instagram Account</h5>
                        <p>I Don't know how, But we developed a huge community on instagram and growing, Don't forget to
                            join us and you'll learn something new for sure! and also I'm updating stories hourly.</p>
                        <hr>
                        <a href="https://instagram.com/tecinpact" class="alert-link">Follow Us</a>
                    </div>
                </div>
            </div>
            <div class="alert alert-warning" role="alert">
                <div class="media">
                    <img src="img/whatsapp.png" class="align-self-center mr-3" alt="...">
                    <div class="media-body">
                        <h5 class="mt-0">Whatsapp</h5>
                        <p>We always face different problems to solve and sometimes, we get stuck. Ask me anything via
                            whatsapp so I can reply you within minutes.</p>
                        <hr>
                        <a href="https://wa.me/94769477743" class="alert-link">Send A Message</a>
                    </div>
                </div>
            </div>
            <div class="alert alert-info" role="alert">
                <div class="media">
                    <img src="img/twitter.png" class="align-self-center mr-3" alt="...">
                    <div class="media-body">
                        <h5 class="mt-0">Twitter</h5>
                        <p>We also have a twitter account! if you're clever enough, You can probably get notification
                            through SMS to your phone.</p>
                        <hr>
                        <a href="https://twitter.com/tecinpact" class="alert-link">Follow Us</a>
                    </div>
                </div>
            </div>
            <div class="alert alert-dark" role="alert">
                <div class="media">
                    <img src="img/gmail.png" class="align-self-center mr-3" alt="...">
                    <div class="media-body">
                        <h5 class="mt-0">E-Mail</h5>
                        <p>Hope you have an official inquiry to discuss with us. we always have an email account for
                            these kinds of work.</p>
                        <hr>
                        <a href="mailto:tecinpactagencies@gmail.com" class="alert-link">Send Us An Email</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="quickPosts">

        </div>
        <div class="copyright">
            Copyright 2020 Tecinpact. All Rights Reserved.
        </div>
    </div>

    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
        integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous">
    </script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
        integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous">
    </script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js"
        integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous">
    </script>
    <script src="https://code.jquery.com/jquery-3.5.1.min.js"
        integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
    <script src="js/app.js"></script>
</body>

</html>
```

The infrastructure of this document isn't that hard, First we're using two sections for preloader and content, and the content is loading secretly in the background while the preloader runs an animation. Then in the content section, I Divide the document again into four main sections, First I have a jumbotron (A Section with a bigger heading and a description sometimes also have an image) Then the main link section, quick posts section and finally the copyright line. Here the link section and quick post section hides and un-hides according to the needs. Let's explore the SCSS page now

```scss
* {
    user-select: none;
}

.content {
    display: none;

    .jumbotron {
        background: url(../img/background.png);
        background-position: center;
        background-size: cover;
        display: grid;
        place-items: center;

        img {
            width: 200px;
            border-radius: 50%;
        }

        h1 {

            span {
                animation: coloranimation 15s infinite;

                @keyframes coloranimation {
                    0% {
                        background-color: #845EC2;
                    }

                    20% {
                        background-color: #D65DB1;
                    }

                    40% {
                        background-color: #FF6F91;
                    }

                    60% {
                        background-color: #FF9671;
                    }

                    80% {
                        background-color: #FFC75F;
                    }

                    100% {
                        background-color: #845EC2;
                    }
                }
            }
        }
    }

    .links {
        padding: 20px;
        display: grid;
        place-items: center;

        .alert {
            max-width: 600px;

            .media {
                img {
                    width: 20%;
                }
            }
        }
    }

    .quickPosts {
        padding: 20px;
        display: grid;
        place-items: center;

        .alert {
            max-width: 600px;

            .media {
                img {
                    width: 20%;
                }
            }
        }
    }

    .copyright {
        text-align: center;
        padding: 10px;
    }
}

.preloader {
    display: grid;
    place-items: center;
    position: fixed;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;


    .lds-facebook {
        display: inline-block;
        position: relative;
        width: 80px;
        height: 80px;
    }

    .lds-facebook div {
        display: inline-block;
        position: absolute;
        left: 8px;
        width: 16px;
        background: #000;
        animation: lds-facebook 1.2s cubic-bezier(0, 0.5, 0.5, 1) infinite;
    }

    .lds-facebook div:nth-child(1) {
        left: 8px;
        animation-delay: -0.24s;
    }

    .lds-facebook div:nth-child(2) {
        left: 32px;
        animation-delay: -0.12s;
    }

    .lds-facebook div:nth-child(3) {
        left: 56px;
        animation-delay: 0;
    }

    @keyframes lds-facebook {
        0% {
            top: 8px;
            height: 64px;
        }

        50%,
        100% {
            top: 24px;
            height: 32px;
        }
    }
}
```

Firstly, I Made all sections un-selectable using a SCSS trick, and then I start the content section of scss, here I hide it at the beginning to load elements silently and adding some minor tweaks to how the elements appear and then in the preload section, I add the animations for the loading bar. And that's pretty simple. Let's see what we did to the JS section.

```js
loadComplete = () => {
    $(".preloader").fadeOut(500)
    $(".quickPosts").fadeOut(500);
    $(".content").fadeIn(500)
}

$(window).on('load', function () {
    setTimeout(function () {
        loadComplete()
    }, 3000);
});

let xml = ["<h1>Loading Data Please Wait</h1>"]
$(".quickPosts").html(xml.join(''))
let colors = ["alert-primary", "alert-secondary", "alert-success", "alert-danger", "alert-warning", "alert-info", "alert-dark"]
let prev = 0
let newn = 0

getnumber = () => {
    newn = getRandomInt(6)
    while (newn == prev) {
        newn = getRandomInt(6)
    }
    prev = newn
    return newn
}

function getRandomInt(max) {
    return Math.floor(Math.random() * Math.floor(max));
}

loadData = () => {
    $.get('https://www.tecinpact.tk/index.xml', function (data) {
        xml = ["<h1>Quick Post View</h1><br>"];
        $(data).find("item").each(function () { // or "item" or whatever suits your feed
            var el = $(this);

            var retstring = `
            <div class="alert ${colors[getnumber()]}" role="alert">
            <div class="media">
                <img src="img/folder.png" width="20%" class="align-self-center mr-3" alt="...">
                <div class="media-body">
                    <h5 class="mt-0">${el.find("title").text()}</h5>
                    <small>${el.find("pubDate").text()}</small>
                    <p>${el.find("description").text()}</p>
                    <hr>
                    <a href="${el.find('link').text()}" class="alert-link">Visit Post</a>
                </div>
            </div>
        </div>`;

            xml.push(retstring)
        });
        $(".quickPosts").html(xml.join(''))
    });
}

let QP = 0;

viewQP = () => {
    setTimeout(function () {
        loadData();
    }, 2000);
    if (QP == 0) {
        $(".links").fadeOut(500);
        $(".quickPosts").fadeIn(500);
        QP = 1
    } else {
        $(".links").fadeIn(500);
        $(".quickPosts").fadeOut(500);
        QP = 0
    }
}

loadData()
```

At the beginning as usual, I defined the function to remove the preloader, here also I'm hiding the quickpost section to show only the content page. Then, I added a event listener to trigger the function I explained above, after the page loads completely. and The next code part is the same, if you saw my guide on how I made the tecinpact application. so I'm not explaining the mechanic in detail. however I added a simple function to get a random number form 0 to 6 when it ran, to get a randomly picked color for the posts, also here, I added a simple logic to prevent the function from giving me the same number twice in a row. and also the loadData function is as the same from the previous guide and View QP is as the same as the function which I used to show a feed in my app. 

And here you go! that's all it needs to create a bio section (A Network hub), you can skip the feed part if you don't use RSS in your project and use github Pages, Netlify or Heroku to host this site for no cost at all!

# Conclusion

As a developer, my opinion is we don't have to depend on others every single time, there are times which we can do something better than someone else, and in that process, maybe we would be able to create something more appealing to the user. Who Knows! what could be better.