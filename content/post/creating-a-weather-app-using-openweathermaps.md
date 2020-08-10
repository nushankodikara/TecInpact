---
title: "Creating a Weather App Using Openweathermaps API"
date: 2020-08-11T06:00:00+05:30
Description: ""
Tags: ["Android","IOS","Mobile development","Hybrid Apps","web development"]
Categories: []
DisableComments: false
---

## Introduction

As I Promised, We're doing advanced app examples today, to be specific, we're creating a weather application using openweathermap API, owfont-regular, vivify for animation, font-awesome pack, progressbar.js for sun-timer , jquery.cookie, jquery-3.5.1 and apexcharts for weather details. We're making this application responsible and I'll link down the documentations off all the libraries we use, with them if you don't understand the code, you can always copy and paste it and it would work fine without a problem at all!

This application can be used as a website or you can create a hybrid app using cordova. Also remember to add location permission if you're creating a hybrid app.

![Weather Application](/uploads/20200811_01.gif)

## Adding hybrid app support

If you're using cordova with this code, run this command to add geo location support

> cordova plugin add cordova-plugin-geolocation

## Library Documentations

Here you can read about each library I used, if you found something simpler than these, please let me know in the comment section.

* https://openweathermap.org/api
* https://websygen.github.io/owfont/
* http://vivify.mkcreative.cz/
* https://fontawesome.com/
* https://kimmobrunfeldt.github.io/progressbar.js/
* https://api.jquery.com/
* https://apexcharts.com/docs/installation/

Alright, If you study these libraries in advance, you can accurately understand what's going on with the application. Also note I purchased font awesome pack and included it in here for free, so you can use it for anything you want! And let's dive into the code! as always, you can download the project [From This Link](/zip/WesperWeather.rar) also use WinRAR to unzip this project file.

## Getting an API key from OpenWeatherMaps

First go to https://openweathermap.org/api and click subscribe on currentWeatherData api section. and click on get api key and sign up with your details and you'll be presented with an api key, but it would take up-to 24h to activate it so be patient. I Did it so I'm logging in to my account.

![Getting a new API](/uploads/20200811_02.gif)

Note: Replace the key variable in the index.js file to start fetching.

## Let's Start Coding

Alright with that preparation done already, use any code editor you like to alter with this application, I put some comments for you to understand the code better, I'll explain if something big is going on.

HTML code

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wesper.io</title>
    <link rel="stylesheet" href="./css/style.css">
    <link rel="stylesheet" href="./css/owfont-regular.min.css">
    <link rel="stylesheet" href="./css/vivify.min.css">
    <link rel="stylesheet" href="./fontawesome/css/all.min.css">
    <link rel="preload" as="font" href="./fonts/owfont-regular.woff" type="font/woff2" crossorigin="anonymous">
</head>

<body>
    <!-- Splash screen at the first -->
    <div id="splashScreen" style="white-space: nowrap;">
        <img class="flipInY" src="./img/logo.png" />
        <h1 class="mainTitle flipInX"><i class="fad fa-eclipse-alt"></i> { Wesper.io }</h1>
    </div>
    <!-- All of the content goes here -->
    <div id="splashCont" style="display: none;">
        <!-- Main Heading -->
        <h1 class="mainTitle">{ Wesper.io }</h1>
        <!-- Search Bar -->
        <div class="search">
            <input type="text" value="" placeholder="Enter your search here..." id="searchBar">
            <button onclick="searchQuery()" id="searchButton"><i class="fas fa-search"></i></button>
        </div>
        <!-- Main top card at -->
        <div class="card redBG">
            <table>
                <tr>
                    <td><span style="padding: 20px;" class="subTemp floatLeft" id="minTempC">Min -&#730;C</span></td>
                    <td></td>
                    <td><span style="padding: 20px;" class="subTemp floatRight" id="maxTempC">Max -&#730;C</span></td>
                </tr>
                <tr>
                    <td colspan="3"><span class="subTemp" id="desTempC">---</span></td>
                </tr>
                <tr>
                    <td colspan="2"><span class="mainTemp" id="mainTempC">-&#730;C</span></td>
                    <td>
                        <i id="mainIconC" class="owf owf-5x owf-731"></i>
                    </td>
                </tr>
                <tr>
                    <td colspan="3"><span class="subTemp"><i class="far fa-compass"></i>
                            <span id="locationC">--</span>,
                            <span id="countryC">--</span>
                        </span></td>
                </tr>
                <tr>
                    <td colspan="3">
                        <span>
                            <i onclick="nightDay()"
                                style="color: white;float: left; padding-left: 20px; font-size: 35px;"
                                class="fad fa-moon-stars"></i>
                        </span>
                        <span class="feelLike" id="feelTempC">--</span>
                        <span>
                            <i onclick="locateQuery()"
                                style="color: white;float: right; padding-right: 20px; font-size: 35px;"
                                class="fad fa-location"></i>
                        </span>
                    </td>
                </tr>
            </table>
        </div>
        <!-- Sun Timer Card -->
        <div class="card">
            <table>
                <tr>
                    <td colspan="3"><span class="subTitle" id="sunTitle">Sun Timer</span></td>
                </tr>
                <tr>
                    <td colspan="3" id="sunIcon"><i class="fad fa-clouds-sun mainIcon"></i>
                    </td>
                </tr>
                <tr>
                    <td colspan="3">
                        <div id="progress"></div>
                    </td>
                </tr>
                <tr>
                    <td><span class="faicon"><i class="fad fa-sunrise" style="float: left;"></i></span></td>
                    <td></td>
                    <td><span class="faicon"><i class="fad fa-sunset" style="float: right;"></i></span></td>
                </tr>
                <tr>
                    <td><span class="clock floatLeft" id="sunRise"> --:-- </span></td>
                    <td><span class="clock" id="sunNow"> --:-- </span></td>
                    <td><span class="clock floatRight" id="sunSet"> --:-- </span></td>
                </tr>
            </table>
        </div>
        <!-- Daily Summery section -->
        <div class="card">
            <table>
                <tr>
                    <td colspan="3"><span class="subTitle">Summery Of Today</span></td>
                </tr>
                <tr>
                    <td colspan="3"><i class="fad fa-campfire mainIcon"></i></td>
                </tr>
                <tr>
                    <td colspan="2">
                        <div class="sqitem">
                            <span class="sqhead">Main Forecast</span><br>
                            <span class="sqicon" id="mainIC"><i class="fad fa-tree-large"></i></span><br>
                            <span class="sqbody" id="mainFC">-</span>
                        </div>
                    </td>
                </tr>
                <tr>
                    <td>
                        <div class="sqitem">
                            <span class="sqhead">Dew Point</span><br>
                            <span class="sqicon"><i class="fad fa-dewpoint"></i></span><br>
                            <span class="sqbody" id="dewPointC">0</span>
                        </div>
                    </td>
                    <td>
                        <div class="sqitem">
                            <span class="sqhead">Humidity</span><br>
                            <span class="sqicon"><i class="fad fa-humidity"></i></span><br>
                            <span class="sqbody" id="humidityC">0</span>
                        </div>
                    </td>
                </tr>
                <tr>
                    <td>
                        <div class="sqitem">
                            <span class="sqhead" id="mainFC">Presure</span><br>
                            <span class="sqicon"><i class="fad fa-tire-pressure-warning"></i></span><br>
                            <span class="sqbody" id="presureC">0</span>
                        </div>
                    </td>
                    <td>
                        <div class="sqitem">
                            <span class="sqhead" id="mainFC">UV Index</span><br>
                            <span class="sqicon"><i class="fad fa-sunglasses"></i></span><br>
                            <span class="sqbody" id="uviC">0</span>
                        </div>
                    </td>
                </tr>
                <tr>
                    <td>
                        <div class="sqitem">
                            <span class="sqhead" id="mainFC">Wind Speed</span><br>
                            <span class="sqicon"><i class="fad fa-wind"></i></span><br>
                            <span class="sqbody" id="windSC">0 KM/H</span>
                        </div>
                    </td>
                    <td>
                        <div class="sqitem">
                            <span class="sqhead" id="mainFC">Wind Direction</span><br>
                            <span class="sqicon"><i class="fad fa-compass"></i></span><br>
                            <span class="sqbody" id="windDC">0</span>
                        </div>
                    </td>
                </tr>
                <tr>
                    <td>
                        <div class="sqitem">
                            <span class="sqhead" id="mainFC">Rain</span><br>
                            <span class="sqicon"><i class="fad fa-cloud-sun-rain"></i></span><br>
                            <span class="sqbody" id="rainC">0</span>
                        </div>
                    </td>
                    <td>
                        <div class="sqitem">
                            <span class="sqhead" id="mainFC">Snow</span><br>
                            <span class="sqicon"><i class="fad fa-snowman"></i></span><br>
                            <span class="sqbody" id="snowC">0</span>
                        </div>
                    </td>
                </tr>
                <tr>
                    <td colspan="2">
                        <div class="sqitem">
                            <span class="sqhead">Cloudiness</span><br>
                            <span class="sqicon"><i class="fad fa-clouds"></i></span><br>
                            <span class="sqbody"><span id="cloudinessC">0</span></span>
                        </div>
                    </td>
                </tr>
            </table>
        </div>
        <!-- 48 Hour Summery Tile -->
        <div class="card sweetmorningBG">
            <span class="subTitle">Summery Of 48 Hours</span>
            <div id="H48Table">
                <table>
                    <tr id="H48Hou" style="text-align: center;">
                    </tr>
                    <tr id="H48Ico" style="text-align: center;">
                    </tr>
                    <tr id="H48Con" style="text-align: center;">
                    </tr>
                    <tr id="H48Tem" style="text-align: center;">
                    </tr>
                    <tr id="H48Row">
                    </tr>
                    <tr style="text-align: center;" id="H48Wdi">
                        <td><span class="windDir"><img style="transform: rotate(-45deg);" class="winDirImgDark"
                                    src="./fontawesome/svgs/duotone/location-arrow.svg"></span></td>
                    </tr>
                </table>
            </div>
        </div>
        <!-- 48 Hour Temperature -->
        <div class="card yellowBG" style="overflow: auto; height: 450px;">
            <span class="subTitle">48h Temperature</span><br>
            <div id="chart" style="display: inline-block; width: 100%;"></div>
        </div>
        <!-- 7Day Summery -->
        <div class="card riverBG">
            <span class="subTitle">Summery Of 7 Days</span>
            <div id="D7Table">
                <table>
                    <tr id="D7Day" style="text-align: center;">
                    </tr>
                    <tr id="D7Ico" style="text-align: center;">
                    </tr>
                    <tr id="D7Con" style="text-align: center;">
                    </tr>
                    <tr id="D7Tem" style="text-align: center;">
                    </tr>
                    <tr id="D7Row">
                    </tr>
                    <tr style="text-align: center;" id="D7Wdi">
                        <td><span class="windDir"><img style="transform: rotate(-45deg);" class="winDirImg"
                                    src="./fontawesome/svgs/duotone/location-arrow.svg"></span></td>
                    </tr>
                </table>
            </div>
        </div>
        <!-- Social Icons and the footer -->
        <footer>
            <div class="socialIcons">
                <table>
                    <tr>
                        <td></td>
                        <td>
                            <a href="https://www.facebook.com/nushan.kodikara.7"><i style="color: gray;"
                                    class="fab fa-facebook-square"></i></a>
                            <a href="https://www.instagram.com/____nushan_/"><i style="color: gray;"
                                    class="fab fa-instagram-square"></i></a>
                            <a href="https://twitter.com/kodikara_nushan"><i style="color: gray;"
                                    class="fab fa-twitter-square"></i></a>
                            <a href="https://www.snapchat.com/add/nushankod"><i style="color: gray;"
                                    class="fab fa-snapchat-square"></i></a>
                        </td>
                        <td></td>
                    </tr>
                    <tr>
                        <td colspan="3">
                            <div class="attribution">Copyright 2020 Nushan Kodikara. All Rights Reserved. Powered By
                                Openweathermaps.</div>
                        </td>
                    </tr>
                </table>
            </div>
        </footer>
    </div>

    <script src="./js/apexcharts.js"></script>
    <script src="./js/jquery-3.5.1.min.js"></script>
    <script src="./js/jquery.cookie.js"></script>
    <script src="./js/progressbar.js"></script>
    <script src="./js/index.js"></script>
</body>

</html>
```

I Downloaded all of the above libraries and added it in the project file, so don't forget to get it if you're doing it with me, or link up CDN from the documentations.

```scss
html {
    scroll-behavior: smooth;
}

body {
    color: rgb(56, 56, 56);
    background-color: floralwhite;
    text-align: center;
    font-family: monospace;
}

.card {
    width: 90vw;
    border-radius: 20px;
    padding-top: 10px;
    padding-bottom: 10px;
    margin-top: 20px;
    display: inline-block;
}

.fullWidth {
    width: 90vw;
}

.redBG {
    background-image: linear-gradient(to right bottom, #eb3349, #ee3f47, #f04946, #f25344, #f45c43);
    color: rgb(56, 56, 56);
}

.blueBG {
    background-image: linear-gradient(to right bottom, #2193b0, #37a3bf, #4ab3ce, #5cc4de, #6dd5ed);
    color: rgb(56, 56, 56);
}

.greenBG {
    background-image: linear-gradient(to right bottom, #56ab2f, #6bb83c, #80c549, #94d356, #a8e063);
    color: rgb(56, 56, 56);
}

.yellowBG {
    background-image: linear-gradient(109.6deg, rgba(255, 207, 84, 1) 11.2%, rgba(255, 158, 27, 1) 91.1%);
    color: rgb(56, 56, 56);

}

.roseBG {
    background-image: radial-gradient(circle farthest-corner at 50.4% 50.5%, rgba(251, 32, 86, 1) 0%, rgba(135, 2, 35, 1) 90%);
    color: floralwhite;
}

.riverBG {
    background-image: linear-gradient(to right bottom, #43cea2, #00b5b3, #0099bb, #007ab4, #185a9d);
    color: floralwhite;
}

.sweetmorningBG {
    background-image: linear-gradient(to right bottom, #ff5f6d, #ff7a65, #ff9362, #ffac66, #ffc371);
    color: rgb(56, 56, 56);
}

table {
    position: relative;
    width: 100%;
    height: 100%;
}

table tr {
    height: 65px;
}

.mainTemp {
    color: rgb(56, 56, 56);
    font-size: 80px;
    font-weight: bold;
}

.subTemp {
    font-size: 20px;
    color: floralwhite;
}

.feelLike {
    font-size: 16px;
    color: floralwhite;
}

.mainTitle {
    font-size: 40px;
}

#progress {
    width: 90%;
    position: relative;
    display: inline-block;
}

.subTitle {
    font-size: 28px;
    font-family: monospace;
    font-weight: bolder;
}

.subTitle2 {
    font-size: 20px;
    font-weight: bold;
}

.faicon {
    font-size: 50px;
}

.clock {
    font-size: 20px;
    padding: 15px;
    margin: 2px;
    border-radius: 3px;
    border: solid rgb(56, 56, 56) 1px;
}

.floatLeft {
    float: left;
}

.floatRight {
    float: right;
}

.sqitem {
    height: 100%;
    padding: 20px;
    border-radius: 20px;
    border: solid #e0e0e071 2px;
    background-color: #e0e0e09d;
}

.sqitem .sqhead {
    font-size: 16px;
    font-family: monospace;
}

.sqitem .sqbody {
    font-size: 25px;
    font-family: monospace;
    color: rgba(47, 79, 79, 0.384);
}

.sqitem .sqicon {
    font-size: 60px;
}

.mainIcon {
    font-size: 90px;
    padding: 20px;
}

#D7Table {
    overflow: auto;
}

#D7Table table {
    width: 1800px;
}

#D7Table table tr {
    text-align: left;
}

#D7Table table tr td {
    width: 100px;
}

.windDir {
    font-size: 90px;
}

.winDirImg {
    filter: invert(100%);
    width: 65px;
}

.winDirImgDark {
    filter: invert(20%);
    width: 65px;
}

#H48Table {
    overflow: auto;
}

#H48Table table {
    width: 12500px;
}

#H48Table table tr {
    text-align: left;
}

#H48Table table tr td {
    width: 100px;
}

.search {
    width: 90vw;
    margin: 0 auto;
}

#searchBar {
    background: none;
    border-bottom: 1px solid white;
    border-top: none;
    border-left: none;
    border-right: none;
    width: 50vw;
    height: 30px;
}

#searchBar:focus {
    outline: none;
    border-bottom: 3px solid white;
    color: white;
}

#searchButton {
    width: 10vw;
    height: 50px;
    background: none;
    border: none;
}

#searchButton:focus {
    outline: none;
}

#searchButton .fas {
    color: white;
    font-size: 2em;
}

footer {
    height: 100px;
    padding: 20px;
}

.socialIcons {
    font-size: 35px;
}

.attribution {
    font-family: monospace;
    font-size: 10px;
}

* {
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    text-transform: capitalize;
}

::-webkit-scrollbar {
    width: 0px;
}

@media screen and (orientation:portrait) {
    #splashScreen img {
        padding-top: 20vh;
        width: 60vw;
    }
}

@media screen and (orientation:landscape) {
    #splashScreen img {
        padding-top: 20vh;
        height: 40vh;
    }
}

#chart {
    color: black;
}
```

I'm not explaining this one, SCSS is easy to understand and if you can't go check out my scss course.

Javascript

```js
const storage = window.localStorage;
const key = 'key'; // Add your openweathermaps key here

// Loading Animation and day-night theme checker
$('.card').addClass('popInBottom duration-2000');
$('i').addClass('pulsate duration-2000 infinite icon');
(storage.getItem("dayNightS") == 1) ? setLight(): setDark();

// Checking for previous searched location from localStorage
$(document).ready(function () {
    setTimeout(function () {
        (storage.getItem("preLocation")) ? locationSearch(storage.getItem("preLocation")): locateQuery();
    }, 3000);
});

// night theme toggle
function nightDay() {
    (storage.getItem("dayNightS") == 1) ? setDark(): setLight();
}

// Setting night theme
function setDark() {
    $('body').css({
        'color': 'floralwhite',
        'background-color': 'black'
    })
    $('.sqitem').css({
        'border': 'solid #2e2e2e71 2px',
        'background-color': '#5a5a5a9d'
    })
    $('.sqitem .sqbody').css({
        'color': 'rgba(182, 182, 182, 0.4)'
    })

    $('#searchBar').css({
        'color': 'floralwhite',
        'border-bottom': '1px solid white'
    })
    $('#searchBar:focus').css({
        'border-bottom': '1px solid white'
    })
    $('#searchButton .fas').css({
        'color': 'white'
    })

    // Setting theme variable
    storage.setItem("dayNightS", 0)
}

// setting day theme
function setLight() {
    $('body').css({
        'background-color': 'floralwhite',
        'color': 'rgb(56, 56, 56)'
    })
    $('.sqitem').css({
        'border': 'solid #e0e0e071 2px',
        'background-color': '#e0e0e09d'
    })
    $('.sqitem .sqbody').css({
        'color': 'rgba(47, 79, 79, 0.384)'
    })

    $('#searchBar').css({
        'color': 'rgb(56, 56, 56)',
        'border-bottom': '1px solid rgb(56, 56, 56)'
    })
    $('#searchBar:focus').css({
        'border-bottom': '1px solid rgb(56, 56, 56)'
    })
    $('#searchButton .fas').css({
        'color': 'rgb(56, 56, 56)'
    })

    // Setting theme variable
    storage.setItem("dayNightS", 1)
}

//Sun Bar initialization and setup
function sunTimer(pres) {
    $("#progress").html('')
    var bar = new ProgressBar.SemiCircle("#progress", {
        strokeWidth: 3,
        easing: 'easeInOut',
        duration: 1400,
        color: '#FFEA82',
        trailColor: '#2f4f4f',
        trailWidth: 1,
        svgStyle: null
    });

    bar.animate(pres);
}

// Clearing out previous results
sunTimer(0)

// Search initialization
function searchQuery() {
    locationSearch($('#searchBar').val())
}

// Locate using GPS
function locateQuery() {

    navigator.geolocation.getCurrentPosition(function (position) {
        fetch('https://api.openweathermap.org/data/2.5/weather?lon=' + position.coords.longitude + '&lat=' + position.coords.latitude + '&appid=' + key)
            .then(function (resp) {
                return resp.json()
            })
            .then(function (data) {
                if (data.cod == 404) {
                    alert("City Not Found")
                } else {
                    geoSearch(data.coord.lat, data.coord.lon, data);
                }
            })
            .catch(function (error) {
                alert("Something Went Wrong 1" + error)
            });
    }, function (error) {
        locationSearch('Bandarawela')
    });
}

// locate using search term
function locationSearch(city) {
    fetch('https://api.openweathermap.org/data/2.5/weather?q=' + city + '&appid=' + key)
        .then(function (resp) {
            return resp.json()
        })
        .then(function (data) {
            if (data.cod == 404) {
                alert("City Not Found")
            } else {
                geoSearch(data.coord.lat, data.coord.lon, data);
            }
        })
        .catch(function () {

        });
}

// Search Using GPS
function geoSearch(lat, lon, dataO) {
    storage.setItem("preLocation", dataO.name)
    // Returning Data from Openweathermap API
    fetch('https://api.openweathermap.org/data/2.5/onecall?lat=' + lat + '&lon=' + lon + '&units=metric&appid=' + key)
        .then(function (resp) {
            return resp.json()
        })
        .then(function (data) {
            drawWeather(data, dataO);
        })
        .catch(function () {

        });
}

// Adding values to the application
function drawWeather(data, dataO) {

    //Main Card
    $('#minTempC').html('Min ' + Math.round(data.daily[0].temp.min) + '&#730;C')
    $('#desTempC').html(data.current.weather[0].description)
    $('#maxTempC').html('Max ' + Math.round(data.daily[0].temp.max) + '&#730;C')
    $('#mainTempC').html(Math.round(data.hourly[0].temp) + '&#730;C')
    drawIcon(dataO)
    $('#locationC').html(dataO.name)
    $('#countryC').html(dataO.sys.country)
    $('#feelTempC').html('Feels like ' + Math.round(data.current.feels_like) + '&#730;C')

    //SunTime Card
    calSunTime(dataO.sys.sunrise, dataO.sys.sunset)

    //SummeryOfToday Card
    $('#mainFC').html(data.daily[0].weather[0].main)
    $('#dewPointC').html(Math.round(data.daily[0].dew_point) + '&#730;C')
    $('#humidityC').html(data.daily[0].humidity + "%")
    $('#presureC').html(data.daily[0].pressure + "HPa")
    $('#uviC').html(data.daily[0].uvi)
    $('#windSC').html(data.daily[0].wind_speed + "KM/H")
    $('#windDC').html(data.daily[0].wind_deg + "&#730;")
    $('#rainC').html(data.daily[0].rain + "mm")
    $('#snowC').html((data.daily[0].snow) ? data.daily[0].snow + "mm" : 0 + "mm")
    $('#cloudinessC').html(data.daily[0].clouds + "%")

    //48HSummery Card
    Hour48Filler(data)

    //Day7Summery Card
    Day7Filler(data)

    //Remove Splash
    $("#splashScreen").hide()
    $("#splashCont").show()

}

// Adding Items data
function drawIcon(d) {
    var hours = new Date().getHours();
    var hours = (hours + 24 - 2) % 24;
    var mid = '-d';
    if (hours == 0) {

    } else if (hours > 12) {

        mid = '-n';
    }
    var lastClass = $('#mainIconC').attr('class').split(' ').pop();
    $('#mainIconC').removeClass(lastClass);
    $('#mainIconC').addClass("owf-" + d.weather[0].id + mid)
}

// Unix server stamp time to local time
function UnixToTime(unix_timestamp) {
    var date = new Date(unix_timestamp * 1000);
    var hours = "0" + date.getHours();
    var minutes = "0" + date.getMinutes();
    var formattedTime = hours.substr(-2) + ':' + minutes.substr(-2);
    return formattedTime;
}

// Calculating sun timer bar
function calSunTime(sunin, sunout) {
    sunnow = new Date().getTime() / 1000 - sunin
    $('#sunRise').html(UnixToTime(sunin))
    $('#sunNow').html(UnixToTime(sunnow + sunin))
    $('#sunSet').html(UnixToTime(sunout))
    sunout = sunout - sunin
    sunpre = sunnow / sunout
    if (sunnow < sunout) {
        $("#sunTitle").html('Rise And Shine')
        sunTimer(sunpre)
        $('#sunIcon').html('<i class="fad fa-clouds-sun mainIcon pulsate infinite duration-2000"></i>')
    } else {
        $("#sunTitle").html('Sun Is Sleeping')
        sunTimer(0)
        $('#sunIcon').html('<i class="fad fa-clouds-moon mainIcon pulsate infinite duration-2000"></i>')
    }
}

// Filling 7 Day card
function Day7Filler(data) {
    D7Day = []
    D7Ico = []
    D7Con = []
    D7Tem = []
    D7Row = []
    D7Wdi = []

    for (i = 0; i <= 7; i++) {
        D7Day.push('<td> <span >' + dayReturn(data.daily[(i)].dt) + '</span> </td>')
        D7Ico.push('<td> <i class="owf owf-5x owf-' + data.daily[(i)].weather[0].id + '"></i> </td>')
        D7Con.push('<td> <span class="subCondition" >' + data.daily[(i)].weather[0].description + '</span> </td>')
        D7Tem.push('<td> <i class="fad fa-temperature-frigid"></i> ' + Math.round(data.daily[(i)].temp.min) + '&#730;C - ' + Math.round(data.daily[(i)].temp.max) + '&#730;C </td>')
        D7Row.push(`
        <td style="padding: 30px;">
            <span><i class=" fad fa-clouds"></i> Clouds</span><span class="floatRight"
                id="clo1">` + Math.round(data.daily[(i)].clouds) + `%</span><br>
            <span><i class="fad fa-cloud-sun-rain"></i> Rain</span><span class="floatRight"
                id="rai1">` + Math.round(data.daily[(i)].rain) + `mm</span><br>
            <span><i class="fad fa-tire-pressure-warning "></i> Pressure</span><span class="floatRight"
                id="rai1">` + Math.round(data.daily[(i)].pressure) + `HPa</span><br>
            <span><i class="fad fa-sunglasses"></i> UV Index</span><span class="floatRight"
                id="uvi1">` + Math.round(data.daily[(i)].uvi) + `</span><br>
            <span><i class="fad fa-sunrise"></i> Sun Rise</span><span class="floatRight"
                id="uvi1">` + UnixToTime(data.daily[(i)].sunrise) + `</span><br>
            <span><i class="fad fa-sunset"></i> Sun Set</span><span class="floatRight"
                id="uvi1">` + UnixToTime(data.daily[(i)].sunset) + `</span><br>
            <span><i class="fad fa-dewpoint"></i> Dew Point</span><span class="floatRight"
                id="dew1">` + Math.round(data.daily[(i)].dew_point) + `&#730;C</span><br>
            <span><i class="fad fa-humidity"></i> Humidity</span><span class="floatRight"
                id="hum1">` + Math.round(data.daily[(i)].humidity) + `%</span><br>
            <span><i class="fad fa-wind"></i> Wind Speed</span><span class="floatRight"
                id="wis1">` + data.daily[(i)].wind_speed + `KM/H</span><br>
            <span><i class="fad fa-compass"></i> Wind Direction</span><span class="floatRight"
                id="wid1">` + data.daily[(i)].wind_deg + `&#730;</span><br>
        </td>`)
        D7Wdi.push(`<td><span class="windDir"><img style="transform: rotate(` + (data.daily[(i)].wind_deg - 45) + `deg);" class="winDirImg"
        src="./fontawesome/svgs/duotone/location-arrow.svg"></span></td>`)
    }

    $('#D7Day').html(D7Day.join(''))
    $('#D7Ico').html(D7Ico.join(''))
    $('#D7Con').html(D7Con.join(''))
    $('#D7Tem').html(D7Tem.join(''))
    $('#D7Row').html(D7Row.join(''))
    $('#D7Wdi').html(D7Wdi.join(''))
}

// 48Hour forecast
function Hour48Filler(data) {

    H48Hou = []
    H48Ico = []
    H48Con = []
    H48Tem = []
    H48Row = []
    H48Wdi = []

    for (i = 0; i <= 47; i++) {
        H48Hou.push('<td> <span >' + UnixToTime(data.hourly[(i)].dt) + '</span> </td>')
        H48Ico.push('<td> <i class="owf owf-5x owf-' + data.hourly[(i)].weather[0].id + '"></i> </td>')
        H48Con.push('<td> <span class="subCondition" >' + data.hourly[(i)].weather[0].description + '</span> </td>')
        H48Tem.push('<td> <i class="fad fa-temperature-frigid"></i> ' + Math.round(data.hourly[(i)].temp) + '&#730;C </td>')

        H48Row.push(`
        <td style="padding: 30px;">
            <span><i class=" fad fa-clouds"></i> Clouds</span><span class="floatRight"
                id="clo1">` + Math.round(data.hourly[(i)].clouds) + `%</span><br>
                ` + rainCheck(data, i) + `
            <span><i class="fad fa-tire-pressure-warning "></i> Pressure</span><span class="floatRight"
                id="rai1">` + Math.round(data.hourly[(i)].pressure) + `HPa</span><br>
            <span><i class="fad fa-dewpoint"></i> Dew Point</span><span class="floatRight"
                id="dew1">` + Math.round(data.hourly[(i)].dew_point) + `&#730;C</span><br>
            <span><i class="fad fa-humidity"></i> Humidity</span><span class="floatRight"
                id="hum1">` + Math.round(data.hourly[(i)].humidity) + `%</span><br>
            <span><i class="fad fa-wind"></i> Wind Speed</span><span class="floatRight"
                id="wis1">` + data.hourly[(i)].wind_speed + `KM/H</span><br>
            <span><i class="fad fa-compass"></i> Wind Direction</span><span class="floatRight"
                id="wid1">` + data.hourly[(i)].wind_deg + `&#730;</span><br>
        </td>`)
        H48Wdi.push(`<td><span class="windDir"><img style="transform: rotate(` + (data.hourly[(i)].wind_deg - 45) + `deg);" class="winDirImgDark"
        src="./fontawesome/svgs/duotone/location-arrow.svg"></span></td>`)
    }

    renderTempChart(data)
    $('#H48Hou').html(H48Hou.join(""))
    $('#H48Ico').html(H48Ico.join(""))
    $('#H48Con').html(H48Con.join(""))
    $('#H48Tem').html(H48Tem.join(""))
    $('#H48Row').html(H48Row.join(""))
    $('#H48Wdi').html(H48Wdi.join(""))
}

// Temperature tile

function renderTempChart(data) {

    temp = []
    cato = []
    rain = []

    for (i = 0; i <= 47; i++) {
        temp.push(Math.round(data.hourly[(i)].temp))
        rain.push(rainReturn(data, i))
        cato.push(UnixToTime(data.hourly[(i)].dt))
    }

    var options = {
        series: [{
            name: 'Temperature (&#730;C)',
            data: temp
        }, {
            name: 'Rain (mm)',
            data: rain
        }],
        chart: {
            height: 400,
            type: 'area'
        },
        dataLabels: {
            enabled: false
        },
        stroke: {
            curve: 'smooth'
        },
        xaxis: {
            categories: cato
        },
        tooltip: {
            x: {
                format: 'HH:mm'
            },
        },
    };

    var chart = new ApexCharts(document.querySelector("#chart"), options);
    $('#chart').html('')
    chart.render();
}

// Return rain data

function rainReturn(data, index) {
    if (typeof data.hourly[(index)].rain != "undefined") {
        return Math.round(data.hourly[(i)].rain['1h'])
    } else {
        return 0
    }
}

// Return rain data

function rainCheck(data, index) {
    if (typeof data.hourly[(index)].rain != "undefined") {
        return `<span><i class="fad fa-cloud-sun-rain"></i> Rain</span><span class="floatRight"
        id="rai1">` + Math.round(data.hourly[(i)].rain['1h']) + `mm</span><br>`
    } else {
        return `<span><i class="fad fa-cloud-sun-rain"></i> Rain</span><span class="floatRight"
        id="rai1"> 0mm</span><br>`
    }
}

// Return the day of the week using servertimestamp

function dayReturn(timestamp) {
    days = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday']
    date = new Date(timestamp * 1000)
    return (days[date.getDay()])
}
```

Alright! It's the fun part, replace the value of key variable at the top and wolah! you have a working weather app!

## Conclusion

It's not that hard to do these kinds of applications, but if you aren't familiar with the fetching apis and that sort of stuffs, you'll be in a uncomfortable situation. But overall the functionality is much complicated so go easy on it. I know this isn't the cleanest code in the world, But it works!
