---
title: "Google Drive Serverless Web Hosting 2020"
date: 2020-07-15T08:39:18+05:30
Description: "Google Drive as a web hosting platform, it works for static sites."
Tags: ["Web development","Static Sites"]
Categories: []
DisableComments: false
---

# Introduction
Serverless web hosting getting popular day by day, with the rise of static websites, So here today, I'm going to show you how to host your created website ( HTML JS And CSS files ) In the google drive, and setting up a proper domain name for it using Freenom and netlify. If you are a typical follower of my blog, this would be awkward because I didn't completed the web development course just yet. But I will very soon and a side note : This is a side post Until I'm preparing the Python Programming course.

# Website
Well, for now you have the HTML file (index.html) you made from our [HTML Zero To Hero](/post/html-for-modern-web-development/) Course or you should have a static website pre built. First thing's first, we have to upload the webpage to a folder in our google drive. [Here](/zip/Sample-site.zip) you can download the sample file I'm going to use in this project.

# Pre Note And FAQ
##### Is This Hard?
Nop this is a piece of cake and for static websites, this is golden.

##### Is This Not Premium?
The User won't feel a difference at all, so Don't worry on that.

##### Features?
Servers are online pretty much all the time. Because it's hosted in the gdrive, you have Unlimited everything except for the storage. In terms of storage you have 15GB Free and you can pay to get more. Considering this is a static site, you'll never going to pay a penny on this.

##### Looks Fake?
Yeah it looks not true at all, but trust me it is true and let me show you How I do it.

## Uploading The Pages
It's simple as it seems. Login to your google drive platform and create a folder and name it public

![uploading](/uploads/20200715a_01.png)
![uploading](/uploads/20200715a_02.png)
![uploading](/uploads/20200715a_03.png)

Now double click to get in to that folder and put your documents in there.

![uploading](/uploads/20200715a_04.png)

Now get back to the root folder and right-click on the public folder and click on share.

![uploading](/uploads/20200715a_05.png)

If the get link section says It's restricted, select Change to anyone with the link. And the get link section should change to green.

![uploading](/uploads/20200715a_06.png)
![uploading](/uploads/20200715a_07.png)

now go to [Drive To Web (www.drv.tw)](https://drv.tw/) and click on Host on google Drive.

![uploading](/uploads/20200715a_08.png)

Select your google account to login to your drive with the service.

![uploading](/uploads/20200715a_09.png)

And allow the service to manage your gdrive by pressing allow button

![uploading](/uploads/20200715a_10.png)
![uploading](/uploads/20200715a_11.png)

If everything got correctly, now You'll be redirected to the admin panel and wait for it to recognize GDrive public folder.

![uploading](/uploads/20200715a_12.png)
![uploading](/uploads/20200715a_13.png)

Now you should see a link with a /public/ folder and that's your hosted link. You can visit it by clicking on the link and You're pretty much done with hosting.

![uploading](/uploads/20200715a_15.png)


## Assigning A Domain

If you don't have a domain name, You can visit [This Guide](/post/free-top-level-domain-names-2020/) To get a free domain and setting up it's Name Servers.

Now Let's focus on setting it up. Here, I'm using a domain I Registered on that previous tutorial on Free TLDs. you can visit it [HERE](/post/free-top-level-domain-names-2020/). 

So I'm using www.tecinpactdemonstration.tk as my domain. so Now I have to go back to the gdrive and rename our public folder to www.tecinpactdemonstration.tk and This is compulsory

![uploading](/uploads/20200715aa_01.png)

This is what my DNS Management page looks like, so now I'm renaming my GDrive folder.

![uploading](/uploads/20200715aa_03.png)

Now after that go to your [Drive To Web drv.tw](https://drv.tw/) page and refresh it. It should show you a link with your domain at the end. remember this is the directory of your page. now copy the first part of that domain, for me I'm copying the tfwk9wuluwzzw28ngta5qa-on.drv.tw part.

![uploading](/uploads/20200715aa_04.png)

Now come back to your Domain management section and select on add new record button, this would popup with the DNS Record manager.

![uploading](/uploads/20200715aa_05.png)

Now you have to select CNAME for record type and in the name, enter www. and in the value section, paste what you just copied. and for the TTL enter 1. and save it.

![uploading](/uploads/20200715aa_09.png)

What happens now is a magic. Your site would be hosted in the domain for me, my sample page is hosted in http://www.tecinpactdemonstration.tk/ And You're pretty much done!

![uploading](/uploads/20200715aa_10.png)
![uploading](/uploads/20200715aa_11.png)

# Conclusion
Now What is this? I'm sure you'll be amazed seeing how great this work. Yeah this is something I'm considering. there was a time I did my blogging like this, the chances are It's totally free and you're golden with it. In terms of security, no one can "Hack" your website because It's protected with google's securities and you didn't had to spend a penny on this project! How crazy is that! I'm providing you how you can continue with this knowledge and some better ways I use now, even for this blog. Ah and I'm not even paying a single penny for this blog (Later on that). No matter what tier you're in, you must consider the possibilities and you should check this out.