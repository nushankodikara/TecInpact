---
title: "Firebase Hosting and Analytics"
date: 2020-08-08T06:00:00+05:30
Description: "Let's Explore firebase Hosting And Firebase Analytics"
Tags: ["Mobile Development","web Development","Firebase"]
Categories: []
DisableComments: false
---

## Introduction

We can use firebase as a hosting service, Firebase Hosting provides fast and secure hosting for your web app, static and dynamic content, and microservices, Also Firebase Hosting is production-grade web content hosting for developers, With a single command, you can quickly deploy web apps and serve both static and dynamic content to a global CDN (content delivery network), You can also pair Firebase Hosting with Cloud Functions or Cloud Run to build and host microservices on Firebase.

## How does it work

Firebase Hosting is built for the modern web developer. Websites and apps are more powerful than ever with the rise of front-end JavaScript frameworks like Angular and static generator tools like Jekyll. Whether you are deploying a simple app landing page or a complex Progressive Web App (PWA), Hosting gives you the infrastructure, features, and tooling tailored to deploying and managing websites and apps.

Using the Firebase CLI, you deploy files from local directories on your computer to your Hosting server. Beyond serving static content, you can use Cloud Functions for Firebase or Cloud Run to serve dynamic content and host microservices on your sites. All content is served over an SSL connection from the closest edge server on our global CDN.

Firebase Hosting has lightweight hosting configuration options for you to build sophisticated PWAs. You can easily rewrite URLs for client-side routing or set up custom headers.

For serving your content, Firebase offers several domain and subdomain options:

* By default, every Firebase project has free subdomains on the web.app and firebaseapp.com domains. These two sites serve the same deployed content and configuration.

* You can create multiple sites if you have related sites and apps that serve different content but still share the same Firebase project resources (for example if you have a blog, admin panel, and public app).

* You can connect your own domain name to a Firebase-hosted site.

Firebase automatically provisions SSL certificates for all your domains so that all your content is served securely.

## What is Firebase Hosting

Firebase Hosting is a fully-managed hosting service for static and dynamic content as well as microservices. The service is backed by SSD storage and a global CDN (content delivery network). Zero-configuration SSL is built into Firebase Hosting, so content is always delivered securely.

## What can you host

## Build then host your microservices, API, and forms

Pair Firebase Hosting with Cloud Functions to build microservices using the Express.js framework. This pairing allows you to host your microservices and APIs on Firebase. In addition, you can use a deep integration with Cloud Firestore to build very powerful forms and web apps which can update data in real time.

## Host your single-page web apps, marketing websites, and static and dynamic assets

Benefit from Firebase Hosting's unique optimization for serving single-page web apps and static websites. Delivery of static assets (HTML, CSS, JavaScript, fonts, etc.) is powered by our SSD backend storage and a global CDN with edge locations across all major locations in the world. You can even cache your dynamic content on the global CDN. All sites hosted by Firebase also get a free SSL certificate, so your content is always delivered securely.

## Add a custom domain (or a subdomain)

With Firebase Hosting, you're automatically given a Firebase sub-domain, but you can choose to serve your content on a custom domain (like example.com or myrealtimeapp.example.com). Firebase Hosting provisions an SSL certificate for each of your domains and serves your content over a global CDN.

## Keep all your sites in one place

Firebase Hosting supports multiple sites in a single Firebase project. Each site hosts its own collection of content, has its own hosting configuration, and can have one or more associated domains. Since the sites are all in the same Firebase project, all the sites can access the other Firebase resources of the project.

You can use multiple sites in a Firebase project to keep related sites together (for example your single-page app, blog, and marketing website).

## Automate continuous deployment with Cloud Build

Firebase Hosting partnered with Cloud Build offers a DevOps-ready solution for automating a continuous deployment workflow for your static and dynamic content as well as for your microservices.

After you configure these tools, you can deploy your web app to Firebase Hosting by simply checking in your code to your git repository.

## Restrict access and counter a DDoS attack for your web apps

Using the power of Express.js middleware, you can build custom logic into serving your microservices, APIs, and other HTTP endpoints. For example, with just a few lines of code, you can integrate popular Node.js middleware offerings to build additional security layers, like access management by IP or protection from denial-of-service (DDoS) attacks.

## Customize everything

* Error pages — Return a neatly fully customized 404 page from your web app.
* Rewrites — Customize which endpoints serve what traffic, and even display the same content from multiple URLs.
* Headers — Want to access cookies? Use custom headers!
* Caching and CDN behavior — Control how your web app is cached across the CDN through custom headers.

## Deploy to Firebase from various web-based IDEs

Firebase Hosting is integrated with various web-based IDEs so that you can deploy to Firebase Hosting directly from within [StackBlitz](https://stackblitz.com/) and [Glitch](https://glitch.com/), two web-based IDEs.

![StackBlitz](https://firebase.google.com/docs/hosting/images/hosting-deploy-stackblitz.gif)
![Glitch](https://firebase.google.com/docs/hosting/images/hosting-deploy-glitch.gif)

These IDEs automatically detect when you're creating a Firebase app and allow you to deploy to Firebase Hosting with the click of a button, without ever leaving the IDE!

## Build deep integrations with other Firebase services

![FriendlyChat web codelab](https://firebase.google.com/docs/hosting/images/friendlychat-web-codelab.png)

Firebase Hosting works out-of-the-box with Firebase services, including Cloud Functions, Authentication, Realtime Database, Cloud Firestore, and Cloud Messaging. You can build powerful microservices and web apps using these complementary Firebase services.

Try out our FriendlyChat web codelab to learn how Hosting pairs with these Firebase services.

## Create a custom deployment workflow using REST API and our Node.js modules

Firebase Hosting supports a REST API for advanced developers to build custom workflows, like deploying through a JavaScript app.

We also have a Node.js module which you can import into your Node.js apps to build advanced functionality.

## Get started with Firebase Hosting

Firebase Hosting gives you a fast, secure, and reliable way to host your app's static assets (HTML, CSS, JavaScript, media files, etc.) as well as to serve dynamic content and host microservices.

Our production-grade hosting is backed by a global content delivery network (CDN). Hosting serves your content over SSL, by default, and can be used with your own custom domain or on your project's free subdomains on web.app and firebaseapp.com.

## Before you begin

Before you can set up Firebase Hosting, you need to create a Firebase project. We did this already in our previous guides, If you didn't checked those out, Go ahead.

## Step 1: Install the Firebase CLI

Visit the Firebase CLI documentation on https://firebase.google.com/docs/cli to learn how to install the CLI or update to its latest version. or install node js and run the command

```js
npm install -g firebase-tools
```

## Step 2: Initialize your project

To connect your local project to your Firebase project, run the following command from the root of your local project directory:

```js
firebase init
```

During project initialization, from the Firebase CLI prompts:

1. Select to set up Hosting.

If you want to set up other Firebase products for your project, refer to their documentation for setup information. Note that you can always run firebase init later to set up more Firebase products.

2. Select a Firebase project to connect to your local project directory.

The selected Firebase project is your "default" Firebase project for your local project directory. To connect additional Firebase projects to your local project directory, set up project aliases.

3. Specify a directory to use as your public root directory.

This directory contains all your publicly served static files, including your index.html file and any other assets that you want to deploy to Firebase Hosting.

* The default for the public root directory is called public.
* You can specify your public root directory now or you can specify it later in your firebase.json configuration file.
* If you select the default and don't already have a directory called public, Firebase creates it for you.
* If you don't already have a valid index.html file or 404.html file in your public root directory, Firebase creates them for you.

4. Choose a configuration for your site.

If you select to make a one-page app, then Firebase automatically adds rewrite configurations for you.

At the end of initialization, Firebase automatically creates and adds two files to the root of your local app directory:

* A firebase.json configuration file that lists your project configuration. Learn more about this file on the configure hosting behavior page.
* A .firebaserc file that stores your project aliases.

## Step 3: Deploy to your site

To deploy to your site, run the following command from the root of your local project directory:

```js
firebase deploy
```

This command deploys a release to your Firebase project's default Hosting sites:

* PROJECT_ID.web.app
* PROJECT_ID.firebaseapp.com
  
Learn more about deploys and even locally testing your site.

## Test locally then deploy to your site

You can view and test your site locally, even emulate your HTTPS functions, before deploying your site to production.

## Get started

Complete the steps listed on the Hosting Get Started page, which include installing the Firebase CLI and connecting your local project to your Firebase project.

## Serve and test your Firebase project locally (optional)

You can view and test your Firebase project on locally hosted URLs before deploying to production. If you only want to test select features, you can use a comma-separated list in a flag on the firebase serve command.

Run the following command from the root of your local project directory if you want to do either of the following tasks:

* View the static content for your Firebase-hosted app.
* Use Cloud Functions to generate dynamic content for Firebase Hosting and you want to use your production (deployed) HTTP functions to emulate Hosting on a local URL.

```js
firebase serve --only hosting
```

## Emulate your project using local HTTP functions

Run any of the following commands from your project directory to emulate your project using local HTTP functions.

* To emulate HTTP functions and hosting for testing on local URLs, use either of the following commands:

```js
firebase serve
```

```js
firebase serve --only functions,hosting // uses a flag
```

* To emulate HTTP functions only, use the following command:

```js
firebase serve --only functions
```

## Test from other local devices

By default, firebase serve only responds to requests from localhost. This means that you'll be able to access your hosted content from your computer's web browser but not from other devices on your network. If you'd like to test from other local devices, use the --host flag, like so:

```js
firebase serve --host 0.0.0.0  // accepts requests to any host
```

## Deploy to your site

To deploy to your site, run the following command from the root of your local project directory:

```js
firebase deploy
```

This command deploys a release to the following sites:

* Your Firebase project's default Hosting sites, PROJECT_ID.web.app and PROJECT_ID.firebaseapp.com

* Any custom domains that you've connected to your Hosting site.

You can optionally add a comment to a deploy. This comment will display with the other deployment information on your project's Hosting page. For example:

```js
firebase deploy -m "Deploying the best new feature ever."
```

## Deploys for projects with multiple sites

If you've added additional sites to your Firebase project, use the following command to deploy to one of those sites:

```js
firebase deploy --only hosting:TARGET_NAME
```

The TARGET_NAME parameter is the unique identifier that you specified for the additional Hosting site during its setup.

## Add predeploy and postdeploy scripted tasks

You can optionally connect shell scripts to the firebase deploy command to perform predeploy or postdeploy tasks. For example, a postdeploy hook could notify administrators of new site content deploys. Refer to the Firebase CLI documentation for more details.

## Caching deployed content

When a request is made for static content, Firebase Hosting automatically caches the content on the CDN. If you redeploy your site's content, Firebase automatically clears all your cached static content across the CDN so that new requests receive your new content.

Note that you can configure the caching of dynamic content.

## Serving over HTTPS

Firebase Hosting is SSL-only, meaning that content is only served over HTTPS.
As you're developing your application, make sure that all external resources that are not hosted on Firebase Hosting are loaded over SSL (HTTPS), including any external scripts. Most browsers do not allow users to load "mixed content" (SSL and non-SSL traffic).

## Share project resources across multiple sites

You can set up one or more Firebase Hosting sites in a single Firebase project. Since the sites are all in the same Firebase project, all the sites can access the other Firebase resources of the project.

* Each site has its own hosting configuration.
* Each site hosts its own collection of content.
* Each site can have one or more associated domains.

By setting up multiple Hosting sites within the same Firebase project, you can more easily share Firebase resources between related sites and apps. For example, if you set up your blog, admin panel, and public app as individual sites in the same Firebase project, they can all share the same Firebase Authentication user database, while also having their own unique domains or content.

## Step 1: Update your Firebase CLI version

Access the most current Firebase Hosting features by updating to the latest version of the Firebase CLI.

## Step 2: Add additional sites

Add additional sites to a Firebase project directly from your Firebase Hosting page. To each site, you can also optionally add custom domains to serve the same content and configuration to multiple URLs.

## Delete a secondary site

Delete unwanted sites directly from your Firebase Hosting page. Note that you cannot delete the default site, which has the same site name as your Firebase project ID.

## Step 3: Set up deploy targets for your sites

When you have multiple sites and you run Firebase CLI deploy commands, the CLI needs a way to communicate which settings should be deployed to each site. With deploy targets you can uniquely identify a specific site by its target name in your firebase.json configuration file and in your Firebase CLI commands for testing or deploying to your sites.

To create a deploy target and apply a target name to a Hosting site, run the following CLI command from the root of your project directory:

```js
firebase target:apply hosting TARGET_NAME RESOURCE_NAME
```

Where the parameters are:

* TARGET_NAME — a unique identifier (that you've defined yourself) for the Hosting site that you're deploying to

* RESOURCE_NAME — the name of the Hosting site as listed in your Firebase project

For example, if you've created two sites (myapp-blog and myapp-app) in your Firebase project, you could apply a unique target name to each site (blog and app, respectively) by running the following commands:

```js
firebase target:apply hosting blog myapp-blog
```

```js
firebase target:apply hosting app myapp-app
```

The settings for deploy targets are stored in the .firebaserc file in your project directory, so you only need to set up deploy targets one time per project.

## Step 4: Define the hosting configuration for each site

Use a site's applied target name when you're defining its hosting configuration in your firebase.json file.

* If your firebase.json file defines the configuration for multiple sites, use an array format:

```js
{
  "hosting": [ {
      "target": "blog",  // "blog" is the applied target name for the Hosting site "myapp-blog"
      "public": "blog/dist",  // contents of this folder are deployed to the site "myapp-blog"

      // ...
    },
    {
      "target": "app",  // "app" is the applied target name for the Hosting site "myapp-app"
      "public": "app/dist",  // contents of this folder are deployed to the site "myapp-app"

      // ...

      "rewrites": [...]  // You can define specific Hosting configurations for each site
    }
  ]
}
```

* If your firebase.json file defines the configuration for only one site, it's not necessary to use an array format:

```js
{
  "hosting": {
      "target": "blog",
      "public": "dist",

      // ...

      "rewrites": [...]
  }
}
```

## Step 5: Deploy to your sites or serve locally

Run any of the following commands from the root of your project directory.

| Command                                    | Description                                                              |
| :----------------------------------------- | :----------------------------------------------------------------------- |
| firebase deploy                            | Creates a release of all deployable resources in your project directory  |
| firebase deploy --only hosting:TARGET_NAME | Creates a release of only the resources for the specified Hosting target |
| firebase serve                             | Serves your Firebase project locally                                     |
| firebase serve --only hosting:TARGET_NAME  | Serves locally only the resources for the specified Hosting target       |

## Connect a custom domain

You don't have to give up your unique, brand-centric domain names with Firebase Hosting. You can use a custom domain (like example.com or app.example.com) instead of a Firebase-generated domain for your Firebase-hosted site.

Firebase Hosting provisions an SSL certificate, signed by Let's Encrypt, for each of your domains and serves your content over a global CDN.

[CustomDomains](https://firebase.google.com/docs/hosting/images/custom-domain.png)

The rest of this document walks you through these steps to connect your custom domain.

## Set up your domain for Hosting

Make sure that you've completed the "Get Started" wizard from your project's Firebase Hosting page so that you have a Firebase Hosting site in your Firebase project.

## Step 1: Add domain

1. From your project's Hosting page, enter the wizard for connecting a custom domain:

* If you have only one Hosting site, click Connect domain.
* If you have more than one Hosting site, click View for the desired site, then click Connect domain.

2. Enter the custom domain name that you'd like to connect to your Hosting site.

3. (Optional) Check the box to redirect all requests on the custom domain to a second specified domain (such that example.com and www.example.com redirect to the same content).

4. Click Continue to initiate the validation process.

## Step 2: Verify domain ownership

If requested in the Connect Domain setup wizard, verify your apex domain.

These steps ensure that your domain is not already linked with a Firebase project and that you own the specified domain.

1. In your domain provider's site, locate the DNS management page.

2. Add and save a new record with the following inputs:

* Type: Add a TXT record.

Firebase Hosting requires that you keep this TXT record continually present in your DNS settings to prove your ownership of the domain and to authorize Firebase to assign and renew SSL certificates for your site.

Your domain provider may list this term as "Record Type".

* Host: Enter your apex domain key.

Proving your ownership of an apex domain, or root domain, proves your ownership of all its subdomains.

Your domain provider may list this term as "Host Name", "Name", or "Domain".

* Value: Copy the unique verification value into the field.

Firebase Hosting checks for this value to prove your domain ownership.

Your domain provider may list this term as "Data".

3. Allow up to 24 hours for propagation of your updated TXT records, then click Verify.

Note that you may click Cancel to safely close the Connect Domain window and reopen at a later time. This does not affect the propagation time, but you will be prompted to re-enter your domain name when you reopen the window.

After ample propagation time, clicking Verify in the Connect Domain window of the Firebase console allows you to begin the SSL certificate provisioning process.

In most cases, propagation of your records and verification of your domain will happen within a few hours, depending on your domain provider. Refer to your domain provider's documentation for detailed instructions for adding TXT records and propagation times.

If clicking Verify prompts an error message, your records have not propagated or your values may be incorrect.

## Step 3: Go live

In the Connect Domain window of the Firebase console, select Quick Setup for a new site or Advanced Setup if you already have a site running on another hosting provider and need a zero-downtime migration.

## Quick Setup

1. Return to your domain name provider's DNS management site to create DNS A records pointing your page to Firebase Hosting. Add and save records with the following inputs:

* Type: Add two DNS A records.
* Host: Enter your custom domain key for both records.
The host you indicate is the domain on which you want to serve content; this domain can be an apex domain or subdomain.

Your domain provider may list this term as "Host Name", "Name", or "Domain".

* Value: Assign one value to each DNS A record to point your domain to the specified IP addresses.
Your domain provider may list this term as "Data", "Points To", "Content", "Address", or "IP Address".

2. Allow time for your SSL certificate to be provisioned. This may take up to 24 hours after you point your A records to Firebase Hosting. In most cases, propagation of your records and provisioning of your SSL cerificate will happen within a few hours, depending on your domain provider.

## Advanced Setup

1. The Connect Domain window of the Firebase console will request that you provide a token to migrate your existing site. You only need to complete one of the following to provide the token:

* Update DNS TXT records: Visit your domain provider's DNS management site. Add a TXT record with your domain key and the provided value.
* Allow up to 24 hours for propagation of your TXT records.
Upload a file to an existing site: Upload the token onto your existing site at the specified URL and verify its existence.
This page must be served over HTTPS and doesn't have to be valid or secure. The encrypted token is only valid for one try. If migration fails, a new token will be generated for your records.

1. Allow time for your SSL certificate to be provisioned. This may take up to 24 hours. In most cases, propagation of your records and provisioning of your SSL certificate will happen within a few hours, depending on your domain provider.

2. After your SSL certificate is provisioned, return to your DNS provider's DNS management site to add DNS A records pointing your page to Firebase Hosting. Add and save records with the following inputs:

* Type: Add two DNS A records.
* Host: Enter your custom domain key for both records.
The host you indicate is the domain on which you want to serve content; this domain can be an apex domain or subdomain.

Your domain provider may list this term as "Host name", "Name", or "Domain".

* Value: Assign one value to each DNS A record to point your domain to the specified IP addresses.
Your domain provider may list this term as "Data", "Points To", "Content", "Address", or "IP Address".

## Wait for SSL certificate provisioning

After we verify domain ownership, we provision an SSL certificate for your domain and deploy it across our global CDN within 24 hours after you point your DNS A records to Firebase Hosting.

Your domain will be listed as one of the Subject Alternative Names (SAN) in the FirebaseApp SSL certificate. You can view this certificate using the browser's security tools. While the domain is provisioning, you might see an invalid certificate that does not include your domain name. This is a normal part of the process and will resolve after your domain's certificate is available.

For Advanced Setup users, your website will be hosted by your previous hosting provider until the setup status in your project's Firebase Hosting page updates to Connected.

## Your custom domain key

When adding or editing DNS records, different domain providers expect you to enter different inputs for the Host field within their DNS management sites. We've compiled common inputs from popular providers below. Refer to your domain provider's documentation for detailed instructions.

| Domain type | Custom domain key                                                                                                                                                                                              |
| :---------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Apex domain | Common inputs include: @ The apex domain name (for example, example.com), Leaving the Host field blank                                                                                                         |
| Subdomain   | Common inputs include: The full subdomain name (for example, app.example.com), Only the subdomain portion (for example, app only, and leaving out .example.com) ,Only www for the subdomain of www.example.com |

## Let's do a demo

Now we know the basics of the firebase hosting, Let's deploy a testing site to Our Firebase Project.

First I'm installing the tool set using npm

![Installing Firebase](/uploads/20200808_01.gif)

Then start a terminal in the project folder and Login to firebase CLI if you haven't already.

![Login To Firebase](/uploads/20200808_02.gif)

Now Run the initialization command `firebase init` And select hosting from the service menu using space bar and select your project using enter.

![Initializing Firebase](/uploads/20200808_03.gif)

Now you should have these folders in your directory.

![Project Directory](/uploads/20200808_04.png)

I Created a simple Web page for demonstrate the hosting process.

![Project Directory](/uploads/20200808_05.png)

![Project Directory](/uploads/20200808_06.png)

And now let's run our project locally for testing.

![Initializing Firebase](/uploads/20200808_07.gif)

After testing with the server, Let's Deploy!

![Initializing Firebase](/uploads/20200808_08.gif)

And Wolah! It's deployed and hosted on https://tecinpact-demo.web.app

![Project Directory](/uploads/20200808_09.png)

Now Let's Connect a custom domain for the project. Here I'm using a free Domain from [This Guide](/post/free-top-level-domain-names-2020/) . for this demonstration the Domain will be tecinpactdemonstration.gq so let's add it to the firebase project.

![Project Directory](/uploads/20200808_11.png)

Go-to Firebase Console and go-to the hosting tab.

![Project Directory](/uploads/20200808_12.png)
![Project Directory](/uploads/20200808_13.png)

Click on add domain button and Enter the Domain name with the subdomain (optionally the sub domain) And Click continue

![Project Directory](/uploads/20200808_14.png)

Here you can see the verification DNS Records. Go-to your domain provider and add these records and click verify.

![Project Directory](/uploads/20200808_15.png)
![Project Directory](/uploads/20200808_16.png)
![Project Directory](/uploads/20200808_17.png)

Here you have the actual DNS Records to redirect users to the site. Add those too. And click finish

![Project Directory](/uploads/20200808_18.png)
![Project Directory](/uploads/20200808_19.png)
![Project Directory](/uploads/20200808_20.png)
![Project Directory](/uploads/20200808_21.png)
![Project Directory](/uploads/20200808_22.png)

I'm also adding the www subdomain for my project, I Can add it easily by clicking the add button from the notification. or copy the details from my page.

![Project Directory](/uploads/20200808_23.gif)

And finally you should see the pending status. Here you can see Firebase is generating A Secure Certificate for the domain. This could take a while and it's totally automated.

![Project Directory](/uploads/20200808_24.png)

After few hours you can see the SSL certificate has beed delivered and there's a padlock next to your URL. Also in the console, the status would be `connected`.

![Project Directory](/uploads/20200808_25.png)
![Project Directory](/uploads/20200808_26.png)

And you are a master in Firebase Hosting! If you made some changes, just deploy and you're good to go!

## Firebase Analytics

Google Analytics is a free app measurement solution that provides insight on app usage and user engagement.

At the heart of Firebase is Google Analytics, a free and unlimited analytics solution. Analytics integrates across Firebase features and provides you with unlimited reporting for up to 500 distinct events that you can define using the Firebase SDK. Analytics reports help you understand clearly how your users behave, which enables you to make informed decisions regarding app marketing and performance optimizations.

## How does it work actually

Google Analytics helps you understand how people use your web, iOS, or Android app. The SDK automatically captures a number of events and user properties and also allows you to define your own custom events to measure the things that uniquely matter to your business. Once the data is captured, it's available in a dashboard through the Firebase console. This dashboard provides detailed insights about your data — from summary data such as active users and demographics, to more detailed data such as identifying your most purchased items.

Analytics also integrates with a number of other Firebase features. For example, it automatically logs events that correspond to notification messages sent via the Notifications composer and provides reporting on the impact of each campaign.

Analytics helps you understand how your users behave, so you can make informed decisions about how to market your app. See the performance of your campaigns across organic and paid channels to understand which methods are most effective at driving high-value users. If you need to perform custom analysis or join your data with other sources you can link your Analytics data to BigQuery, which allows for more complex analysis like querying large data sets and joining multiple data sources.

## Let's Implement Analytics

Now, what do we need to see our application data usage in a single dashboards? We are web developers. And we can add a single line of code to get all these benefits! That's the beauty of the modern web development with BaaS services.

```js
<!-- If you enabled Analytics in your project, add the Firebase SDK for Analytics -->
<script src="/__/firebase/7.17.1/firebase-analytics.js"></script>
```

That's it for Analytics. Go to the dashboard and your reports would get generated!

## Conclusion

You can have a download bandwidth of 10GB/month free and expansion isn't that expensive. You can host any kind of static site using This technique, but we can get more benefits by using Firebase as a hosting service while using other firebase tools BECAUSE, these services are provided by a single supplier and when we using more and more of their services, They can ensure the maximum security and pin point accurate analytics for us.
