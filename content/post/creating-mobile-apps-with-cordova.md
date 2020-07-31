---
title: "Let's Create Mobile Apps With Cordova"
date: 2020-07-29T18:51:05+05:30
Description: "Creating Mobile apps using cordova"
Tags: ["Android","IOS","Mobile development"]
Categories: []
DisableComments: false
---

# Introduction
Mobile app development is a cool thing, and most of us use android studio or swift in order to create mobile apps for Android and IOS devices, But what if I tell you that now you can create mobile apps for android and IOS with a single code base and It's working with HTML CSS and JS? Yeah that's true, with node.js now we're able to create mobile apps using platforms such as Cordova.

# What is Cordova

![Cordova](https://images.prismic.io/ionicframeworkcom/3d6dfd9bd31653194a051e7a2b859d0890a1554e_article---what-is-cordova-phone-gap.png?auto=compress,format)

Apache Cordova is an open-source mobile development framework. It allows you to use standard web technologies - HTML5, CSS3, and JavaScript for cross-platform development. Applications execute within wrappers targeted to each platform, and rely on standards-compliant API bindings to access each device's capabilities such as sensors, data, network status, etc.

# Architecture

There are several components to a Cordova application. The following diagram shows a high-level view of the Cordova application architecture.

![Cordova Architecture](https://cordova.apache.org/static/img/guide/cordovaapparchitecture.png)

Pretty cool isn't it? Let's go on. Today, we're considering on Android app development using a Windows PC, also you can convert this code base to IOS, Windows, Mac, Linux and any platform you think of.

# Setting up the environment

In order to develop android apps, You need to have android Studio installed, If you didn't installed it you can download android studio from https://developer.android.com/studio And also the core, You need node.js to installed in your system, you can download and install the latest LTS or Current version from https://nodejs.org/en/download 

Now you have to setup Android SDKs, currently you need to install Android SDK28 in order to create android apps, This could change, if it's changed you'll get an error when compiling with the version you need, so stay focused on it. You can check and install Android SDKs from android Studio application as this. Don't worry this supports from Android 4.4 upwards.

![Showing Android SDK](/uploads/20200801_01.gif)

Now after that, We need to install cordova on our system. You need to install node.js, if you didn't did it, go ahead and do it now, and come to the terminal with administrator access and enter the command

>       npm install -g cordova

And after that, Let's Create our first project and add android platform to begin with.

# Creating Our First Project

Let's now start creating our first project, It isn't hard or so, let's get right in to the process. First you need to have a terminal in your working directory, and in there you need to use the command

>       cordova create <path> <package-name> <app-name>

To create the app directory, for an example you can use

>       cordova create tecinpact com.tecinpactdev.app Tecinpact

from this command, we're creating an app called Tecinpact with the package name of com.tecinpactdev.app in the path called tecinpact. and we have to get into this folder using the CD command, and it's

>       cd <path>

within this example

>       cd tecinpact

Now let's add the android platform to the project using platform add command

>       cordova platform add <platform>

in this case

>       cordova platform add android

and We're officially done for now. you can run the app using

>       cordova run <platform>

in this case

>       cordova run android

And remember, to run the application, you have to connect your Android device and enable Android Debugging bridge by,

1. Open the Settings app.
1. Select System.
1. Scroll to the bottom and select About phone.
1. Scroll to the bottom and tap Build number 7 times.
1. Return to the previous screen to find Developer options near the bottom.
1. Scroll down and enable USB debugging.

Guys! I have something odd to say here, While I'm preparing this post, my PC crashed and got into a boot loop suddenly! I had no idea how to do anything with it so I clean installed windows Just now, I posted some stories on instagram explaining the situation and I Usually backup my work while doing it, It saved my life and you also must check out cloud storages and I hava an article about it [HERE](/post/storage-free-cloud-life-2020/))

And I'm installing Everything using choco once again

![Installing Android Studio](/uploads/20200801_02.png)

Now that out to the way, Let's continue with the guide. Where were we, Okay we made and ran our First cordova application and I was about to show you how I do it, Let me show you.

![Showing Android SDK](/uploads/20200801_03.gif)

# Multidex
Now, If you don't know what multidex is, it allows android apps to have over 64k functions and you'll hit that threshold as soo as installing some plugins and doing some work, so I usually install multidex at the begining of the project, to do this you can use the following command.

>       cordova plugin add cordova-plugin-enable-multidex

This is a must! so do it as soon as posible. After this you're done with the initial setup. Now let's see how we can create apps using cordova.

# Folder Structure

![Cordova Folder Structure](/uploads/20200801_04.png)

Here we only need to discuss about few files,
* config.xml
* www

## config.xml

For this project I have a config file like this and I'm pretty sure yours also looks like this.

```xml
<?xml version='1.0' encoding='utf-8'?>
<widget id="com.tecinpact.app" version="1.0.0" xmlns="http://www.w3.org/ns/widgets" xmlns:cdv="http://cordova.apache.org/ns/1.0">
    <name>Tecinpact</name>
    <description>
        A sample Apache Cordova application that responds to the deviceready event.
    </description>
    <author email="dev@cordova.apache.org" href="http://cordova.io">
        Apache Cordova Team
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
    <platform name="android">
        <allow-intent href="market:*" />
    </platform>
    <platform name="ios">
        <allow-intent href="itms:*" />
        <allow-intent href="itms-apps:*" />
    </platform>
</widget>
```

Now here, This is the file that controls our application, this is our meta data file, you can change the package name, application name and many more things by tweaking this file, later in this tutorial, we're explaining how we can do things by tweaking this file. For now, don't be afraid to modify and tweak it BUT DO NOT REMOVE ANYTHING WITHOUT KNOWING WHAT IT DOES. And that's a warning.

Let me introduce each element to you. Name tags holds the application name, description tag holds a description of the app, author tag as others author details. content must be pointed to the main HTML file and that's what you need for now, and there should be a self closing icon tag pointing to a icon file with src attribute and that's all you need to know in the base level. if non of these made sense to you, go check out my Web Development series [HTML](/post/html-for-modern-web-development/), [CSS](/post/css-for-modern-web-development/), [SCSS](/post/scss-for-modern-web-development/), [JS part 1](/post/js-for-modern-web-development/) and [JS part 2](/content/post/js-for-modern-web-development-2/) First and then come to this section.

## www Directory

Now the www directory is where we create our hybrid app. Hybrid means you can create your application out of HTML CSS and JS and compile it into a native app, using some sort of a magic. Magics are not real and they are illusions, so the trick behind the sleave is, Cordova has a separate stable web view activity which can run the HTML file internally. The end user won't feel a difference and if you're careful enough, We can make this app looks way way better. Now you can find these even in the cordova documentation page, but let me show you what you cannot find in the documentation and what I really use in my workflow. BTW go and modify the content in the www folder and create your mobile app there with HTML CSS and JS and I'll do it in the next guide. For now I'm using the default pages.

# Setting up an Icon

This isn't a hard one you need to create a res folder and add your icon in there, also after that you just need to add a single line of code to the config file and you're pretty much good to go. Here's how I do it.

![Adding Icon To the Folder](/uploads/20200801_05.gif)

And That out to the way we need to map the icon to the config file. How can we do that? Simple, Just add this line of code to your config file

```xml
<icon src="./res/demoIcon.png"/>
```

And That's it. After that the whole XML config file should look like this. You have to rename the demoIcon.png part to your icon name and you're done.

```xml
<?xml version='1.0' encoding='utf-8'?>
<widget id="com.tecinpact.app" version="1.0.0" xmlns="http://www.w3.org/ns/widgets" xmlns:cdv="http://cordova.apache.org/ns/1.0">
    <name>Tecinpact</name>
    <description>
        A sample Apache Cordova application that responds to the deviceready event.
    </description>
    <author email="dev@cordova.apache.org" href="http://cordova.io">
        Apache Cordova Team
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
    <icon src="./res/demoIcon.png"/>
    <platform name="android">
        <allow-intent href="market:*" />
    </platform>
    <platform name="ios">
        <allow-intent href="itms:*" />
        <allow-intent href="itms-apps:*" />
    </platform>
</widget>
```

Alright now there's something called signing your app when developing android apps, and to do that, you have to develop your application into a apk file and do a complex thing called Zip aligning. Lucky for us, I Found a way which a handful of members know of, you can automatically sign Cordova apps with a build.json file and That's the easiest as it gets. But before that, you have to create a key for your app. In order to do this you have to follow up the usual procedure of obtaining a key. You can learn how to get a keystore key for android from [THIS VIDEO](https://www.youtube.com/watch?v=HNbtFTtq-8o), You don't have to follow the whole guide, Just generate the .keystore file and you're good to go. Now you have to create a new file called build.json

![Cordova Folder Structure](/uploads/20200801_06.png)

Here you can see I created a build.json file and copied my mykey.keystore file. Now in the json file, I you have to add these lines

```json
{
    "android": {
        "debug": {
            "keystore": "mykey.keystore",
            "storePassword": "password",
            "alias": "alias name",
            "password" : "password",
            "keystoreType": ""
        },
        "release": {
            "keystore": "mykey.keystore",
            "storePassword": "password",
            "alias": "alias name",
            "password" : "password",
            "keystoreType": ""
        }
    }
}
```

Here you have to change mykey.keystore to your keystore file, enter your storepassword to the password, alias name to that section and alias password in password section. You are writing these when creating the keystore file and DO NOT LOSE THIS FILE, if you did so you won't be able to update your app in the future. Now we're officially done with the process and we only have to Build the app itself. Before that, Let's summarize what we did for now

1. Created a Cordova Project
1. Added Android Platform
1. Added Icon File
1. Added HTML Documents in www directory
1. Added Keystore and build files

And Disclaimer, If you're an absolute beginner, You have to setup environments for each pieces of software you need, I'm only showing this step for windows users because mac users can install AndroidStudio, Java and get Gradle tools and you're going to need one more step and I'll show it, Linux users, you have to figure it out, You're using linux because you know somewhat about developments and you have to know how other programs use environmental variables and also install everything without overriding other applications. If that's complicated for you, yes that's totally complicated in linux. Use a windows OS Instead. Let's Setup Our Environments

# Environmental Variables

You have to download Java SE Development Kit And Gradle Bundle Links Would Be https://gradle.org/install for gradle and https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html for Java. Good news mac users. you can use brew to install the gradle and the command is

```
$ brew install gradle
```

And Windows users, Download these Files and Install Java if you didn't already. Then also download and Extract Gradle bundle to C: Drive. You have to add your Application paths. In this step, We're setting up ANDROID_SDK_ROOT, JAVA_HOME and path variables. Follow my steps

1. Right Click This PC > Properties
1. Click on Advanced System Settings
1. Click on Environmental Variables
1. Click new under user variables and add ANDROID_SDK_ROOT path
1. Click new under user variables and add JAVA_HOME path
1. double click on path variable and add gradle path, java path, android sdk tools path and android sdk platform tools path

![Environmental Variables Structure](/uploads/20200801_07.gif)

now we're ready to build the application. fire up the terminal window and type the command to build our signed APK

```
cordova build android
```

If you did everything correctly, By now you should see a window like this and Your APK file should be build in 

..\platforms\android\app\build\outputs\apk\debug

Folder. to create a release version you can use

```
cordova build android -release
```

And that command would output an apk file in

..\platforms\android\app\build\outputs\apk\release

![Cordova Folder Structure](/uploads/20200801_08.png)

This is what you get if everything went correctly, In the terminal. And wolah! You are officially made an android app that can be published to mobile stores. Also you can install this apk to your mobile by sending it in any way you prefer.

# Conclusion

Here, we successfully created an android app and it's simple as it. environmental setup is the most advanced step in this whole process and if you ran into an issue which you can't figure out what to do, just contact me or post down below in the comment section. Tomorrow we're creating an app for Tecinpact and On monday, We're Publishing it to the play store!