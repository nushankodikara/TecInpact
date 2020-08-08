---
title: "Creating a Messaging App With Firebase"
date: 2020-08-09T06:00:00+05:30
Description: "Creating a simple messaging app with firebase"
Tags: ["Mobile Development","web Development","Firebase"]
Categories: []
DisableComments: false
---

## Introduction

Now we have covered firebase realtime and firestore databases, Authentication, Hosting and analytics, We can create a simple chat/messaging application within 15-minuets or less! Aren't you sure of that? Let's get started!

## Background and Environment

I'm using what we did in firebase realtime database, authentication and hosting for this project. So if you didn't saw them already, go ahead now. let's explore the code and as always [HERE](/zip/FirebaseAssetsPack3.zip) you can download the completed project file. Also you can visit the project live for sometime on https://tecinpactdemonstration.gq/ and If the link isn't not working, just download and host the file yourself!

HTML File

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="./style.css">
    <link type="text/css" rel="stylesheet" href="https://cdn.firebase.com/libs/firebaseui/3.5.2/firebaseui.css" />
    <link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/emojify.js/1.1.0/css/basic/emojify.min.css" />
    <title>Chat Room</title>
</head>

<body>
    <div class="content">
        <!-- Heading Section -->
        <div class="headline">
            <h1>Public Chat Room Demo</h1>
            <input type="submit" value="SignOut" onclick="signOut(); return false" id="sout" class="button">
        </div>
        <!-- Login Button -->
        <div class="login">
            <input type="submit" class="button" value="Login With Google" onclick="googleLogin();return false" />
        </div>
        <!-- Messages would be added here -->
        <div class="chatbody">
            <div class="messagebox" id="messagebox">
            </div>
        </div>
        <!-- Sending bar -->
        <div class="sendmessage">
            <form onsubmit="sendMsg();return false">
                <input maxlength="256" type="text" id="message" />
                <input type="submit" class="button" value="Send" />
            </form>
        </div>
    </div>

    <!-- Adding JQuery for extra Functionality -->
    <script src="https://code.jquery.com/jquery-3.5.1.min.js"
        integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>

    <!-- Firebase App (the core Firebase SDK) is always required and must be listed first -->
    <script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-app.js"></script>

    <!-- If you enabled Analytics in your project, add the Firebase SDK for Analytics -->
    <script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-analytics.js"></script>

    <!-- Add Firebase products that you want to use -->
    <script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-auth.js"></script>
    <script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-database.js"></script>

    <script>
        // Your web app's Firebase configuration
        var firebaseConfig = {
            apiKey: "AIzaSyDOMUpm4WNldKOVuQCeizCTZAUdSRLqAeU",
            authDomain: "tecinpact-demo.firebaseapp.com",
            databaseURL: "https://tecinpact-demo.firebaseio.com",
            projectId: "tecinpact-demo",
            storageBucket: "tecinpact-demo.appspot.com",
            messagingSenderId: "977048224763",
            appId: "1:977048224763:web:b5e6053c4ced9116b8c15e",
            measurementId: "G-DM6KKVPWRR"
        };
        // Initialize Firebase
        firebase.initializeApp(firebaseConfig);
        firebase.analytics();
    </script>

    <!-- Adding emoji support (Optional) -->
    <script src="//cdnjs.cloudflare.com/ajax/libs/emojify.js/1.1.0/js/emojify.min.js"></script>

    <script src="./app.js"></script>
</body>

</html>
```

SCSS File

```scss
$background : linear-gradient(to right top, #041f3d, #002a45, #00354b, #00404f, #004a51, #035959, #14675e, #2a7661, #428d69, #5fa46f, #81bb72, #a7d175);
$myMessage : #041F3D;
$button: #52A874;

* {
    font-family: monospace;
}

html {
    height: 100%;

    body {
        background: $background;
        position: fixed;
        height: 100vh;
        width: 100vw;
        top: 0;
        left: 0;
        color: white;

        .content {
            .headline {
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 60px;
                display: grid;
                place-items: center;
            }

            .sendmessage {
                position: fixed;
                bottom: 0;
                left: 0;
                width: 100%;
                height: 80px;
                display: grid;
                place-items: center;

                form {
                    width: 100%;
                    max-width: 400px;

                    #message {
                        width: 68%;
                        border-radius: 500px;
                        padding: 10px 20px;
                        outline: none;
                        border: none;
                    }

                    .button {
                        width: 20%;
                    }
                }
            }

            .chatbody {
                position: fixed;
                top: 110px;
                bottom: 80px;
                left: 50%;
                transform: translate(-50%, 0);
                width: 100%;
                max-width: 400px;
                padding: 20px 20px;
                background-color: white;
                border-radius: 40px;
                overflow-y: auto;

                display: flex;
                flex-wrap: wrap;
                justify-content: center;

                .messagebox {
                    width: 100%;

                    .card {
                        flex: 1 1 300px;
                        margin: 5px 0px;
                        color: rgb(24, 24, 24);
                        background-color: rgb(202, 202, 202);
                        width: 100%;
                        max-width: 360px;
                        padding: 20px;
                        border-radius: 20px;

                        p {
                            word-break: break-all;
                            text-align: left;
                        }
                    }

                    .mcard {
                        text-align: right;
                        @extend .card;
                        color: white;
                        background-color: $myMessage;
                    }
                }
            }

            .login {
                position: fixed;
                top: 110px;
                bottom: 80px;
                left: 50%;
                transform: translate(-50%, 0);
                width: 100%;
                max-width: 400px;
                padding: 20px 20px;
                background-color: white;
                border-radius: 40px;
                overflow-y: auto;

                display: grid;
                place-items: center;
            }
        }
    }

    .button {
        background-color: $button;
        padding: 10px;
        border-radius: 500px;
        outline: none;
        border: none;
    }
}
```

JS File

```js
// This makes easier to hide and show chat window based on login status
let chatview = 1
// Login Provider
let provider = new firebase.auth.GoogleAuthProvider();

// Show and hide Chat window and others based on login status
chattoggle = () => {
    if (chatview == 0) {
        $(".chatbody").css("display", "flex").hide().fadeIn();
        $(".login").css("display", "grid").hide().fadeOut();
        $(".sendmessage").css("display", "grid").hide().fadeIn();
        $("#sout").fadeIn();
        chatview = 1
    } else {
        $(".chatbody").css("display", "flex").hide().fadeOut();
        $(".login").css("display", "grid").hide().fadeIn();
        $(".sendmessage").css("display", "grid").hide().fadeOut();
        $("#sout").fadeOut();
        chatview = 0
    }
}

// Initializing First Run
chattoggle();

// Login With Google when pressed the button
googleLogin = () => {
    firebase.auth().signInWithPopup(provider).then(function (result) {}).catch(function (error) {});
}

// Send messages
sendMsg = () => {
    message = $('#message').val()
    $('#message').val('')
    if (message) {
        sendData(message, username)
    }
}

// Defining username
let username;

// Authentication listener , this triggers when auth state changed
firebase.auth().onAuthStateChanged(function (user) {
    if (user) {
        chattoggle();
        loadData();
        username = user.displayName
    } else {

    }
});

// A Sign out function
signOut = () => {
    firebase.auth().signOut().then(function () {
        chattoggle();
    }).catch(function (error) {});
}

// Pushes data to the database
sendData = (message, author) => {
    let newPostRef = firebase.database().ref('messageList1').push();
    newPostRef.set({
        msg: message,
        aut: author
    });
}

// Loads data from the database realtime
loadData = () => {
    let msgList = firebase.database().ref('messageList1').limitToLast(20); // Only loading last 20 messages for performance and network optimization
    msgList.on('value', function (snapshot) {
        let html = []
        snapshot.forEach(element => {
            // I Have a strategy to minimize latency, First putting everything we need to add to our HTML Document to a array and finally appending the whole array to the document at once
            if (username == element.val()['aut']) {
                html.push(`
            <div class="mcard">
                <b>${purge(element.val()['aut'])}</b>
                <p>${purge(element.val()['msg'])}</p>
            </div>`)
            } else {
                html.push(`
            <div class="card">
                <b>${purge(element.val()['aut'])}</b>
                <p>${purge(element.val()['msg'])}</p>
            </div>`)
            }
        });
        $(".messagebox").html(html.join(''))
        document.getElementById('messagebox').scrollIntoView(false);
    });
}

// This is a little security feature to make it fool proof And prevent cross site scripting. Also adding a limit to the purge.
purge = (string) => {
    let newStr = (string).replace(/<|>/g, "").substring(0, 256);
    return (newStr)
}
```

And That's The complete project. Side note, We're doing something more advanced in the future.

![Application Demonstration](/uploads/20200809_01.gif)

## Conclusion

It's a simple project to polish up your skills, but if you're a beginner with firebase, It's a great simple project to kick start your abilities. I Made the project with comments in it so it's easier to understand other than explaining it later.
