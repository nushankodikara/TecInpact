---
title: "Playstore Publishing Guide 101"
date: 2020-08-04T06:00:00+05:30
Description: "Let's Publish some apps on playstore"
Tags: ["Android","mobile development"]
Categories: []
DisableComments: false
---

# Introduction

Playstore is the king of all appstores in the world right now, It hold's a market share of 75% around the globe and google single handedly offers the best tools for Android developers as none other, We already discussed how we can create android applications using Cordova as a hybrid app platform and today, We're uploading our newly signed apk file to the playstore from our own account.

# Preparation

The ingredients for this recipe
* Playstore Account
* Signed APK File
* 512px x 512px icon file (PNG)
* 1024px x 500px banner file (PNG)
* Short description of the APK
* Long description of the APK
* 2 or more Screenshots in 16:9 ratio (landscape or portrait)
* Optionally Screen shots from 7 inch and 10 inch devices

Before gathering these, I have to tell you that you need to pay 25$ for google in order to get a new playstore console account. And you can get one from https://play.google.com/apps/publish/signup This link. Always remember, use your Generic information on this account, Don't fake it.

# Let's Start Then?

And One thing before start. Google has released a new play console and today we're exploring it. It's still in the beta phrase ( Today is 4-Aug-2020 ) and could be changed in the future. But they wont do anything big, so the process would be the same. And also there are more options to explore.

Let's Start Shall we, you have to login to your play console account from https://play.google.com/console This URL by now, If it's changed in the future, just google for google play console and you'll get the link to it.

I made an app out of our Yesterday's post about bio section (Network hub) and I'm uploading it now With you. Also I made some quick arts for Screenshot, Icon and banner. Let's start the project.

# First Thing's First

Let's login to the console, Goto https://play.google.com/console after you paid the one-time payment and created the account, And select your developer account from the list.

![Log in](/uploads/20200804_01.png)
![Log in](/uploads/20200804_02.png)

Then Let me show you my account, I have 5 published apps and noticed there's a Create app button top right to the screen? Yes that's what we need. Click it and You'll Greet up with a form to fill, Fillup with your Application data and click create app

![Log in](/uploads/20200804_03.png)
![Log in](/uploads/20200804_04.gif)
![Log in](/uploads/20200804_05.png)

Now Let's get in to the Dashboard. The new play console have a step-by-step guide for you. So It's soo easy and soo much better than the OLD play console. I Ran into a habit of mine and got stucked during the guide (I'll tell you when) and Because I can't upload the same app twice, I decided to continue the guide, that's not a big thing or so but keep noted.

![Log in](/uploads/20200804_06.png)

Now you loaded the dashboard, Scroll down to the initialization section and expand the list by clicking on view task dropdown.

![Log in](/uploads/20200804_07.png)
![Log in](/uploads/20200804_08.png)

Now Click on our first task, I'm doing it with you so if you got stucked, come back to the guide. Our first task is `App access` settings. Here we are letting the playstore know wether our app has anything to do with special access permissions. For my application, I don't need any special access so I'm selecting the first option and saving. Remember you have to go to the dashboard manually after saving it.

![Log in](/uploads/20200804_09.png)
![Log in](/uploads/20200804_10.png)

Alright! Let's go to the second task `Ads`. This will let the playstore know wether you're displaying ads on your application or not. And this will show a `contains ads` label within the playstore. I don't have any ads on my application so I'm not selecting it.

![Log in](/uploads/20200804_11.png)
![Log in](/uploads/20200804_12.png)

Third Step! We're rocking through this right now, Okay now `Content rating` This will give you a badge with what age groups are suitable to use your application (That 12+ 18+ 3+ etc...). It's also an easy to manage option and answer to their questions with precise, otherwise your application would get rejected. Also I'm attaching a gif on how I did it.

![Log in](/uploads/20200804_13.png)
![Log in](/uploads/20200804_14.png)
![Log in](/uploads/20200804_15.gif)

Fourth Step, `Target Audience`, This is a hit or miss section. I always choose 18 and over because it'll make the app review process run faster. and also if you're designing this app for children, Google have some policies and don't forget to check them here in google's designed for families program https://support.google.com/googleplay/android-developer/answer/7018303?hl=en

![Log in](/uploads/20200804_16.png)
![Log in](/uploads/20200804_17.gif)

Fifth Step, `Select an app category and provide contact details` This is pretty much self explanatory and also not that hard to proceed. And pro, let google do external marketing, It'll make the app available on pretty much every apk store for download! (if you prefer)

![Log in](/uploads/20200804_18.png)
![Log in](/uploads/20200804_19.gif)

Sixth Step (Very Important) `Store Listing`. Hope you have all of your ingredients nearby, because we're going to use them here. They'll ask you for all of those here, and upload everything, make it perfect. This is what the user sees before they installs their application, so be aware of it. I lost the uploading process but here you go with the final product. I filled everything and you can see for yourself.

![Log in](/uploads/20200804_20.png)
![Log in](/uploads/20200804_21.gif)

Alright guys, this is where I get messed up. Old console trained us to go directly to the production setting in the first place so I did it. Don't do it if you're doing this along. go to the end of the dashboard and you'll see there Publish your app on google play steps, how ever we're getting there so don't be worried.

![Log in](/uploads/20200804_22.png)
![Log in](/uploads/20200804_23.png)

Anyways you have to get to this production track in the 2nd step of Publish your app on google play section. and Follow up from here. Notice a create a release section? Yeah you have to click it. After that click on the continue button, upload your APK, set a Release name and Release note then save it. After that you have something else to do, so go to the dashboard. Here, when I realized I got messed up, I got panicked and in the last gif you can clearly see it. Just trust me, save it and go to the dashboard.

![Log in](/uploads/20200804_24.png)
![Log in](/uploads/20200804_25.gif)
![Log in](/uploads/20200804_26.png)
![Log in](/uploads/20200804_27.gif)

Alright In the dashboard, Notice the Select countries and regions step? head there and you have to complete it, here you can control which countries can download your application, It's much useful when releasing regional softwares or so. Here I'm adding every country available to add.

![Log in](/uploads/20200804_28.png)
![Log in](/uploads/20200804_29.png)
![Log in](/uploads/20200804_30.png)
![Log in](/uploads/20200804_31.png)
![Log in](/uploads/20200804_32.png)

Final Step! get to the dashboard again, And here you can see the final step, `Review and Rollout The release` section. Head in there, Because I had messed up my flow, I can edit this draft I uploaded and continue from there, yours may get different but steps are the same. And finally you can add the application on review by review release button.

![Log in](/uploads/20200804_33.png)
![Log in](/uploads/20200804_34.png)
![Log in](/uploads/20200804_35.gif)

And finally It's under review! Playstore employees manually tests each application and guess what, These days it could get up-to 24 hours for them to review your applications, so Be patient. But anyhow if it's taking more than 24 hours, You have clearly messed up somewhere and usually it'll get rejected. So review your content ratings, target audience and so on. Hope you learn something today and wish you luck on your journey.

I'll post a link to the application [HERE]() when it get released.

# Conclusion

Google play store is the biggest mobile store in earth. Knowing to release applications there is a skill these days, It could get complicated within seconds. so watch for it and Good luck.