---
title: "Getting Started With Firebase"
date: 2020-08-05T06:00:00+05:30
Description: "How we can use Firebase"
Tags: ["web development","mobile development"]
Categories: []
DisableComments: false
---

# Introduction

This is a different post from what I did before, Today I'm introducing you to a technology, It's a BaaS from google which stands for Backend As A Service and that's weird in many ways, First It is not what you would expect out of a traditional site and Here I only speak about Modern development So Let's get started with this new technology and make our Lives Easier!

# What Is Firebase

Firebase is a platform for creating mobile and web applications developed by Google. It was originally an independent company founded in 2011. In 2014, Google acquired the platform and it is now their flagship offering for app development. Considering google, They are the biggest tech company in earth by now. (Yeah we have more planets and there are aliens, I have proofs and Let's not talk about it ever again) So as an Earth being, if a service gets delivered by google, That's a pot of gold. Let's explore what we can do with firebase shall we?

# Firebase Products

Before getting in to what are the benefits, Let's Explore what Firebase offers Us in advance. you can check this link https://firebase.google.com/docs for more details.

For Building your app
* Cloud Firestore
* Firebase ML
* Cloud Functions
* Authentication
* Hosting
* Cloud Storage
* Realtime Database

Improve app quality
* Crashlytics
* App Distribution
* Performance Monitoring
* Test Lab

Grow your business
* Analytics
* Extensions
* Predictions
* Firebase A/B Testing
* Cloud Messaging
* In-App Messaging
* Remote Config
* Dynamic Links
* App Indexing

Now let me introduce you, what are these and Let's get to know firebase a bit better.

![Firebase](https://cdn-media-1.freecodecamp.org/images/0*CPTNvq87xG-sUGdx.png)

## Cloud Firestore

Cloud Firestore is a flexible, scalable database for mobile, web, and server development from Firebase and Google Cloud Platform. Like Firebase Realtime Database, it keeps your data in sync across client apps through realtime listeners and offers offline support for mobile and web so you can build responsive apps that work regardless of network latency or Internet connectivity. Cloud Firestore also offers seamless integration with other Firebase and Google Cloud Platform products, including Cloud Functions.

## Firebase ML

Firebase Machine Learning is a mobile SDK that brings Google's machine learning expertise to Android and iOS apps in a powerful yet easy-to-use package. Whether you're new or experienced in machine learning, you can implement the functionality you need in just a few lines of code. There's no need to have deep knowledge of neural networks or model optimization to get started. On the other hand, if you are an experienced ML developer, Firebase ML provides convenient APIs that help you use your custom TensorFlow Lite models in your mobile apps.

## Cloud Functions

Cloud Functions for Firebase is a serverless framework that lets you automatically run backend code in response to events triggered by Firebase features and HTTPS requests. Your JavaScript or TypeScript code is stored in Google's cloud and runs in a managed environment. There's no need to manage and scale your own servers.

## Firebase Authentication

Most apps need to know the identity of a user. Knowing a user's identity allows an app to securely save user data in the cloud and provide the same personalized experience across all of the user's devices. Firebase Authentication provides backend services, easy-to-use SDKs, and ready-made UI libraries to authenticate users to your app. It supports authentication using passwords, phone numbers, popular federated identity providers like Google, Facebook and Twitter, and more. Firebase Authentication integrates tightly with other Firebase services, and it leverages industry standards like OAuth 2.0 and OpenID Connect, so it can be easily integrated with your custom backend.

## Firebase Hosting

Firebase Hosting provides fast and secure hosting for your web app, static and dynamic content, and microservices. Firebase Hosting is production-grade web content hosting for developers. With a single command, you can quickly deploy web apps and serve both static and dynamic content to a global CDN (content delivery network). You can also pair Firebase Hosting with Cloud Functions or Cloud Run to build and host microservices on Firebase.

## Cloud Storage

Cloud Storage is built for app developers who need to store and serve user-generated content, such as photos or videos. Cloud Storage for Firebase is a powerful, simple, and cost-effective object storage service built for Google scale. The Firebase SDKs for Cloud Storage add Google security to file uploads and downloads for your Firebase apps, regardless of network quality. You can use our SDKs to store images, audio, video, or other user-generated content. On the server, you can use Google Cloud Storage, to access the same files.

## Firebase Realtime Database

Store and sync data with our NoSQL cloud database. Data is synced across all clients in realtime, and remains available when your app goes offline. The Firebase Realtime Database is a cloud-hosted database. Data is stored as JSON and synchronized in realtime to every connected client. When you build cross-platform apps with our iOS, Android, and JavaScript SDKs, all of your clients share one Realtime Database instance and automatically receive updates with the newest data.

## Firebase Crashlytics

Get clear, actionable insight into app issues with this powerful crash reporting solution for iOS, Android, and Unity. Firebase Crashlytics is a lightweight, realtime crash reporter that helps you track, prioritize, and fix stability issues that erode your app quality. Crashlytics saves you troubleshooting time by intelligently grouping crashes and highlighting the circumstances that lead up to them. Find out if a particular crash is impacting a lot of users. Get alerts when an issue suddenly increases in severity. Figure out which lines of code are causing crashes.

## Firebase App Distribution

Firebase App Distribution makes distributing your apps to trusted testers painless. By getting your apps onto testers' devices quickly, you can get feedback early and often. And if you use Crashlytics in your apps, you’ll automatically get stability metrics for all your builds, so you know when you’re ready to ship.

## Firebase Performance Monitoring

Gain insight into your app's performance issues. Firebase Performance Monitoring is a service that helps you to gain insight into the performance characteristics of your iOS, Android, and web apps. You use the Performance Monitoring SDK to collect performance data from your app, then review and analyze that data in the Firebase console. Performance Monitoring helps you to understand where and when the performance of your app can be improved so that you can use that information to fix performance issues.

## Firebase Test Lab

Test your app on devices hosted in a Google data center. Firebase Test Lab is a cloud-based app-testing infrastructure. With one operation, you can test your Android or iOS app across a wide variety of devices and device configurations, and see the results—including logs, videos, and screenshots—in the Firebase console.

## Google Analytics

Google Analytics is a free app measurement solution that provides insight on app usage and user engagement. At the heart of Firebase is Google Analytics, a free and unlimited analytics solution. Analytics integrates across Firebase features and provides you with unlimited reporting for up to 500 distinct events that you can define using the Firebase SDK. Analytics reports help you understand clearly how your users behave, which enables you to make informed decisions regarding app marketing and performance optimizations.

## Firebase Extensions

Firebase Extensions help you deploy functionality to your app quickly with pre-packaged solutions. Once installed, a Firebase Extension performs a specific task or set of tasks in response to HTTPS requests or to triggering events from other Firebase products, like Cloud Firestore or Firebase Cloud Messaging.

## Firebase Predictions

Firebase Predictions applies machine learning to your analytics data to create dynamic user segments based on your users' predicted behavior. These predictions are automatically available for use with Firebase Remote Config, the Notifications composer, Firebase In-App Messaging, and A/B Testing. You can also export your app's Predictions data to BigQuery for further analysis or to push to third party tools. When you use Predictions with Remote Config, you can increase conversions by providing a custom experience based on each of your users' anticipated needs. You can also use Predictions with the Notifications composer to deliver one-time messages or recurring campaigns. For example, you can automatically send a notification to users who are predicted to stop using your app. With A/B Testing, you can compare the effectiveness between different the Notifications composer campaigns, or use Remote Config to test the result of different ways of customizing the in-app experience for users in a predicted segment.

## Firebase A/B Testing

Powered by Google Optimize, Firebase A/B Testing helps you optimize your app experience by making it easy to run, analyze, and scale product and marketing experiments. It gives you the power to test changes to your app’s UI, features, or engagement campaigns to see if they actually move the needle on your key metrics (like revenue and retention) before you roll them out widely. A/B Testing works with FCM so you can test different marketing messages, and with Remote Config so you can test changes within your app.

## Firebase Cloud Messaging

Firebase Cloud Messaging (FCM) is a cross-platform messaging solution that lets you reliably send messages at no cost. Using FCM, you can notify a client app that new email or other data is available to sync. You can send notification messages to drive user re-engagement and retention. For use cases such as instant messaging, a message can transfer a payload of up to 4KB to a client app. Using deprecated Google Cloud Messaging APIs? Learn more about how to migrate to FCM.

## Firebase In-App Messaging

Engage active app users with contextual messages. Firebase In-App Messaging helps you engage your app's active users by sending them targeted, contextual messages that encourage them to use key app features. For example, you could send an in-app message to get users to subscribe, watch a video, complete a level, or buy an item. You can customize messages as cards, banners, modals, or images, and set up triggers so that they appear exactly when they'd benefit your users most. Use Firebase In-App Messaging to encourage exploration and discovery: highlight a sale or coupon in your ecommerce app, give clues or tips in your game, or prompt a like or share in your social media app.

## Firebase Remote Config

Change the behavior and appearance of your app without publishing an app update, at no cost, for unlimited daily active users. Firebase Remote Config is a cloud service that lets you change the behavior and appearance of your app without requiring users to download an app update. When using Remote Config, you create in-app default values that control the behavior and appearance of your app. Then, you can later use the Firebase console or the Remote Config backend APIs to override in-app default values for all app users or for segments of your user base. Your app controls when updates are applied, and it can frequently check for updates and apply them with a negligible impact on performance.

## Firebase Dynamic Links

Firebase Dynamic Links are links that work the way you want, on multiple platforms, and whether or not your app is already installed. With Dynamic Links, your users get the best available experience for the platform they open your link on. If a user opens a Dynamic Link on iOS or Android, they can be taken directly to the linked content in your native app. If a user opens the same Dynamic Link in a desktop browser, they can be taken to the equivalent content on your website. In addition, Dynamic Links work across app installs: if a user opens a Dynamic Link on iOS or Android and doesn't have your app installed, the user can be prompted to install it; then, after installation, your app starts and can access the link.

## Firebase App Indexing

Firebase App Indexing gets your app into Google Search. If users have your app installed, they can launch your app and go directly to the content they're searching for. App Indexing reengages your app users by helping them find public content right on their device, even offering query autocompletions to help them more quickly find what they need. If users don’t yet have your app, relevant queries trigger an install card for your app in Search results.

And That's It! That's all we get for a free quota which updates every month! and believe it or not these are the cheapest services you can get right now!

# How Should I Start?

We're considering Firebase with Javascript. So in this guide series we're considering more and more web apps and hybrid mobile apps to develop. And you also need some basic knowledge on [HTML](/post/html-for-modern-web-development/), [CSS](/post/css-for-modern-web-development/), [SCSS](/post/scss-for-modern-web-development/), [JS part 1](/post/js-for-modern-web-development/) and [JS part 2](/content/post/js-for-modern-web-development-2/) After that we can get into this series. This isn't hard but you have to keep your focus high.

# Conclusion

Firebase is a set of services ( A Collection of services ) which can make your life easier. I Use firebase personally in my projects whenever I can and It made my life so much easier. From today on we're discussing how we can use these services. So stay Tuned!