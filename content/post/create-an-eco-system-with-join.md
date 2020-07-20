---
title: "Create an Eco System With Join by joaoapps"
date: 2020-07-20T12:19:26+05:30
Description: "This is the guide to help you create an ecosystem like apple, with what you have."
Tags: ["Android","Windows","EcoSystem","Apple"]
Categories: []
DisableComments: false
---

# Introduction
Let's be real, We all like to work in one place but access all of our devices, Apple has a solution for this but what if you don't have an apple eco system? Today, Let's discuss how we can create an ecosystem for with what we have and for a little price to pay, With Join by joaoapps.

There are more services like this, Push bullet is one of them but their prices are, for my tastes, unfair. So I decided to move on to this app called join and I wasn't able to find a clear explanation on this. So let me explain from tip to toe, what is join and how we can use it.

# What Is Join
This app let's you to sync your notifications, messages, clipboard and many more features across all of your devices and also it let's you to sync information such as battery health and many more. So, in other words, this let's you to connect all of your devices phones, computers to gather and it allows you to control them remotely. In my personal experience, this is something I use daily and I can't imagine how many times it saved me from awkward situations.

# How to install this?
Installation is pretty simple as it seams, for android and iphones, you have an app called join by joaoapps in the playstore and in the appstore to download and continue with a pretty simple steps, you're good to go. for pcs, you have to install an extension in chrome and also you're good to go. Let's see how we can setup these step wise.

### Download

* [Android](https://play.google.com/store/apps/details?id=com.joaomgcd.join)
* [Chrome](https://chrome.google.com/webstore/detail/flejfacjooompmliegamfbpjjdlhokhj)
* [Windows 10](https://www.microsoft.com/store/apps/join-by-joaoapps/9nblggh5krjx)
* [Join On The Web](http://joaoapps.com/join/web)
* [Google Assistant](https://joaoapps.com/google-assistant-ifttt-join-tasker-awesomeness/)

### Android
When you open Join for the first time, you will need to sign in with your Google account. Then enable to push your SMS and calls to other devices.

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-set-up-1.jpg)

Then you have to allow notification access

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Notification-access-498x1024.jpg)

You also have the option to enable Join’s accessibility service. This option is handy for when you push the clipboard from your computer to your device, it would automatically paste the text for you instead of manually having to press and hold to get the Paste option.

### Chrome extension
Now, our main setup is done and here you have to download the chrome extension from above links and you can login to the account you just made and you're done!

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-Chrome-pop-up.jpg)

Click on the gear at the type right corner of the Join pop-up to access the settings. There are seven tabs available:

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-Chrome-extention-4.jpg)

* The Shortcuts tab allows you to create keyboard shortcuts to perform different tasks on your device.
* In Options tab, you can change the way Join looks. You also have the option to hide commands and devices from the Join pop-up.
* On the Clipboard tab, you can manage the clipboard settings.
* Encryption allows to set up a password so all pushes are encrypted.
* The Diagnostics tab can be used to test the Join connection between your devices.
* The Advanced tab has multiple settings. You can manage how links, files, EventGhost and Tasker commands interact when they are pushed.
* Last but not least, we have the Help tab which has multiple links available to other websites and social media communities where you can find help for any type of issues or questions that you might have about Join.

# Encryption

To setup encryption, go to the Encryption tab and set up a new password. Then, open Join on your phone and go to Settings > Encryption > Password and enter the same password you set up in the Chrome extension. Now Join will encrypt the data before pushing it to other devices.

# Notifications

Next, we need to select what notifications we want to push and to which device or devices. Go to Settings > Notifications > Notification Devices. Then after that, go to Notification Apps and select the apps that you would like to push notifications to the selected devices via Join.

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-set-up-2.jpg)

Also in this way, you can select how to sync your clipboard too.

# Join on the web

What if you want to access Join from an IOS device, like an iPhone or iPad or from a computer at work? Well, the developer has you covered. Join also has a web interface that allows you to access all your connected devices and send commands to it from most browsers by going to the following URL, https://joinjoaomgcd.appspot.com.

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-Web.jpg)

# Push websites from an IOS device to other devices using Join

To send links from an IOS device to other devices, we will need to save the Send Tab option in a bookmark on your browser. Open Join web on an IOS device using Google Chrome and select the device that you want to push links. Then, click on Join API, under API Key, click on Show and then close the Join API pop-up window. Now press and hold the Send Tab button and click on Copy Link URL. The link would look like this:

>       javascript:(function(){ var img = new Image(1,1); img.src = 'https://joinjoaomgcd.appspot.com/_ah/api/messaging/v1/sendPush?url=' + encodeURIComponent(document.URL) + '&deviceId=YOUR_DEVICE_ID&apikey=YOUR_API_KEY' ; })();

If you use Safari on your IOS device. Open Safari, go to any website and add it as a bookmark. Now, we need to edit it and change the name and the URL, so go into your Bookmarks, click on Edit, Select the new bookmark. Change the name to the device name that you will be pushing links to, change the URL to the Send Tab link and then click on done. Now, whenever you want to send the current website on your IOS device to another device, just click on this bookmark and it will push the current link.

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-IMG_0004-cropped.png)

>   Note: If you have multiple devices that you would like to set up, you will have to repeat this process for each device. Also, at the time of this guide, it is not possible to push any data to an IOS device using Join.

# Join API
The Join API is a very useful feature. It allows sending custom commands to Tasker to execute different tasks. You can also use the API with the Webhook service in IFTTT. To access the API, go to the Join web interface. Then, select a device, click on Join API and click on Show to display the API key. The Join API feature has many parameters available that you can add to the API URL.

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-API-setup-2.jpg)

To have an idea of how it works, let’s create an Applet in IFTTT that will allow us to receive a notification from a website on a smartphone every time there is a new article. If you never used IFTTT before and would like to learn how to use it, you can watch a tutorial video [Here](https://youtu.be/lznDsCwGxDM).

To start, let’s go to IFTTT, click on your username and then on New Applet. Now, click on this to create a trigger, search and select RSS Feed and click on New feed item. We are going to set up to get the latest articles from Android Police so enter the following link in the Feed URL field, http://www.androidpolice.com/feed/ Then click on Create Trigger. We now need to create the Action so click on that, search and select Webhooks and click on Make a web request.

Now open another tab and go to the Join web interface, Select a device and then click on Join API. Under the API Key, click on Show so the Key gets displayed and the URL gets populated. Now we are going to be using the Text, Tittle, Icon and URL parameter so on each field just enter 1234 for now. We will replace this after we paste the Join URL in IFTTT.

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-API-setup.jpg)

The whole URL will look somewhat this:

>       https://joinjoaomgcd.appspot.com/_ah/api/messaging/v1/sendPush?text=1234&title=1234&icon=1234&url=1234&deviceId=YOUR_DEVICE_ID_HERE&apikey=YOUR_API_KEY_HERE

Now go back to IFTTT and under the URL field enter the Join URL. For the text parameter, we are going to replace 1234 with <<<>>> Then in the middle add the ingredient EntryTittle. The text parameter will look like this <<<{{EntryTitle}}>>>. Now for the Tittle, replace 1234 with Android+Police now for the Icon, we are going to replace 1234 with the Android Police icon that I found [Here](https://lh3.googleusercontent.com/-2lq9WcxRgB0/AAAAAAAAAAI/AAAAAAAAETw/Yk2jY1eiZss/s640/photo.jpg). We will need to encode the icon URL so copy the URL and go [Here](https://meyerweb.com/eric/tools/dencoder/) to encode it. Go back to IFTTT and enter the encoded link for the Icon parameter. For the URL, add the ingredient EntryUrl enclosed with <<<>>>. The URL parameter will look like this <<<{{EntryUrl}}>>>. The whole URL will not look like this:

>       https://joinjoaomgcd.appspot.com/_ah/api/messaging/v1/sendPush?text=<<<{{EntryTitle}}>>>&title=Android+Police&icon=https%3A%2F%2Flh3.googleusercontent.com%2F-2lq9WcxRgB0%2FAAAAAAAAAAI%2FAAAAAAAAETw%2FYk2jY1eiZss%2Fs640%2Fphoto.jpg&url=<<<{{EntryUrl}}>>>&deviceId=YOUR_DEVICE_ID&apikey=YOUR_API_KEY

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-IFTTT.jpg)

Ok now click on Create action and then Finish. Whenever a new article is available, we will get a notification on the device that will look like this:

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-Notification-test.jpg)

The title of the notification is the name of the website and the text, is the title of the article. Clicking the notification will take you to the article page.

>       Note: This Android Police notification was originally covered in a tutorial by João Dias, the developer of Join. I wanted to update it a little and include it in this guide so, all credit goes to him.

# Join Plugin for Tasker
What if we wanted to trigger a task in Tasker when we get the above Join notification? Simple, we can create an Event Profile in Tasker using the Join Plugin. Go to Tasker, click on the “+” icon, then Event > Plugin > Join. There are four available options: Text, Title, URL and Screen Capture.

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-received-push-498x1024.jpg)

Select Title and then click on Title Filter. Type Android Police in the field and click OK. Then, you have a few available options: Exact, Regex, Case Insensitive and Contains All. Select Exact and back out to connect the new profile to any task you would like to trigger.

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-Join-title-page-498x1024.jpg)

# Join and EventGhost
![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-EventGhost-1.jpg)

Another great thing about Join is that you can add it to EventGhost and send commands to the computer from other devices to execute different tasks.

You can download EventGhost from here, then go here to download the AutoRemote EventGhost Plugin. As João stated on his website: download the AutoRemote EvenGhost plugin and go to **C:\Program Files (x86)\EventGhost\plugins\AutoRemote** or **C:\Program Files\EventGhost\plugins\AutoRemote**, then create a folder named AutoRemote and save the Plugin in there. Now, open EventGhost, Go to **Configuration > Add Plugin > Select AutoRemote > Press Ok**. Here we are going to set up the following fields:

* Enter the name for the Join device under Device Name
* Paste the Join API URL under Device Personal URL
* Type the Join Device ID under Device Key

![Join](https://juanmtech.b-cdn.net/wp-content/uploads/2018/09/Web-EventGhost-2.jpg)

Now click on Add and then OK. We need to save the changes in EventGhost so go to File and click on Save. Last but not least, open the Join Settings on the Chrome extension, go to Advance and under EventGhost, enter the port 1818 which is the default port for EventGhost.

OK so we are done and Join is now set up with EventGhost so whenever we send a command from another device to the computer, EventGhost will see it and will be able to execute different tasks on the computer.

To see Join and EventGhost in action, check out this tutorial [Video](https://youtu.be/PtiX4TcdDSg) where I show how to turn a computer on and off using Google Home and the Google Assistant in a smartphone.

As we can see Join is a powerful app to have. I hope this guide was helpful and you now have a better understanding of how to use Join and its available features. I will try to keep this guide updated whenever there is a new updated done to the app.