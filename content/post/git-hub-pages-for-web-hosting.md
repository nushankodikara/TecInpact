---
title: "Git Hub Pages for Web Hosting"
date: 2020-08-12T06:00:00+05:30
Description: ""
Tags: ["Git Hub","web hosting"]
Categories: []
DisableComments: false
---

## Introduction

Github pages is one of the most used and in my opinion the best static hosting site available right now, It only has a free version and it's all we need, let me show you how we can create and deploy a static website to github, and then how we can assign a custom domain to the site and enable SSL certificate in few minuets.

## Starting With git-hub

First we need to goto github and login to your account. Then click on the new button to create a new repository then clone it to your machine using GitHub desktop application. Remember to keep the repo public to make it available to github pages.

![Github Cloning](/uploads/20200812_01.gif)

Then you can open github desktop application and got the repository > code > open in github desktop to open it with the application, then clone it as usual.

![Github Cloning](/uploads/20200812_02.gif)

After cloning the application, you can go to the directory and put your site files there, Here I'm creating a static website using Firebase to demonstrate this platform can be used to deploy your applications

![Github Cloning](/uploads/20200812_03.gif)

You can see what changes has been made in the desktop application or the visual studio application if you're using it

![Github Cloning](/uploads/20200812_04.png)
![Github Cloning](/uploads/20200812_05.png)

Now I'm generating a new app in firebase in order to connect our application to a database, we discussed these in previous tutorials but here I'm doing it again.

![Github Cloning](/uploads/20200812_06.gif)

As you can see I also added the firebase realtime database functionality after the initialization.

![Github Cloning](/uploads/20200812_07.png)

This is a simple application without much complex codes, and here it's in action in my localhost server. Also this is how my folder structure looks like.

![Github Cloning](/uploads/20200812_08.gif)
![Github Cloning](/uploads/20200812_09.png)

Now let's push our site to github. In order to do this go to the main application and add summery to commit the update. After committing you can push the site with the push button.

![Github Cloning](/uploads/20200812_10.gif)

After that you can see the repository has been updated with new documents we just pushed. Now go to the repository in github website and goto settings. here you can scroll down to github pages section and in the source select your branch (default is master) and the directory of your site, my site is in the root folder so I select it and click save. Then you can see a link appear on the top of the page section and that's all for deployment. It won't be updated asap so be patient with it. After few minutes you can see the site up and running

![Github Cloning](/uploads/20200812_11.gif)
![Github Cloning](/uploads/20200812_12.gif)

## Adding a custom domain

Now let's add a custom domain to our site. In order to do this, goto your name server and add a DNS record pointing to your main repository. it would be `<username>.github.io` in my case It's `nushankodikara.github.io` and point it to www or whatever sub-domain you prefer. I'm using a domain from [This Guide](/post/free-top-level-domain-names-2020/) Remember it could take 2-3 minutes to update. Then go to the github pages section under settings and enter the domain in custom domain section and save it. if everything went correctly, now you can see your site in your custom domain.

![Github Cloning](/uploads/20200812_13.gif)

## Enabling SSL

This is an important feature in 2020, SSL Certification is compulsory if you're creating a commercial product. You can do this in a flip of a switch. Just tick the Enforce HTTPS tick and you're pretty-much done!

![Github Cloning](/uploads/20200812_14.gif)
![Github Cloning](/uploads/20200812_15.png)

(You can see the Lock Pad with the URL)

And That's All!

## Conclusion

It's That simple! And I use it for almost all of my projects. Believe or not, even I use this technique to host this website and I'm not paying a single penny on it! Considering security, no one can hack into your site unless they have your github passwords, so considering it that's a big plus point! Hope you learn something new today, and wish you luck on you journey!
