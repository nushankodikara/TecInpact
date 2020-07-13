---
title: "HTML for Modern Web Development ( Zero to Hero )"
date: 2020-07-12T15:13:33+05:30
Description: ""
Tags: ["web development","HTML","Zero To Hero","Crash Course"]
Categories: []
draft: true
DisableComments: false
---

# Introduction
HTML is the structural markup language for the web development community, there are more than HTML in markup community but for websites, we use mainly HTML. I'll explain HTML from ground level so if you're a absolute beginner, you can follow up easily. If something went wrong, just contact me from the links provided.

# Environment
HTML doesn't need a specific environment to run, but Modern web development required you to host the main files. So let's start with our code editor. You can use anything if you know what you're doing, or else I'm using [Visual Studio Code](/post/vs-code-for-web-developers.md) and I installed the live server extension for this demo. Or you can use [Codesandbox.io](https://codesandbox.io/) (Not Sponsored).

# Folder Structure
Modern web development has a rule to start the main HTML file with
>       index.html
Name scheme. remember the whole file name and the extension is in lowercase, and put it in the root folder. Now what is this root folder? Remember, this folder is the main folder of your Project. When You're uploading the site or developing the hybrid app, you are uploading this folder to the servers. so it's the main folder.

# Setting up the VS Code
If you are using something else, just skip this part. Otherwise open the root folder in visual studio by using First
>       Ctrl + k
Then
>       Ctrl + o

Use this combination accordingly or go to File > Open Folder

Then create the index.html file in the root folder and use the Go Live button at the bottom right corner, or use the following key combination
>       Alt + L
Then
>       Alt + O

then the index.html file should be hosted and opened in the browser, or just use
>       localhost:5000
in the browser to get to the hosted file. remember the 5000 port is the default, but it could change. so replace it with whatever the GO Live button turn into. after hosting, the go live button will show a port. replace 5000 with that port and you're good to go.

Now Open the index.html File and let's begin coding.

# HTML Introduction
Main concept in the HTML language is, you just have to open a tag, add content, close the tag. This would make the content in the tag inherit the properties of the tag. Opening Tags looks like this.
>       <tag>
This is a Closing Tag
>       </tag>

Remember, You MUST CLOSE AN OPENED TAG NO MATTER WHAT. But you can also Nest the tags accordingly to your functionality.
>       <tag1>
>           <tag2>
>               <tag3></tag3>
>               <tag4></tag4>
>           </tag2>
>       </tag>

Any how you must close an opened tag! that's a must. Otherwise your code hierarchy would get broken.

Now that out of the way, Let's start Actual coding. Remember this is the Structure so you can't create something only from HTML. you need CSS and JS for a website, Until I explain everything, just follow up with ease.

# Zero

Let me show you what a HTML Page looks like first. you can copy this code and see for your self. just paste it in the index.html page and save it. then just double click and open it or run it from the live server. for codesandbox.io users, just paste the code and the preview should refresh.

>       <!DOCTYPE html>
>       <html>
>           <head>
>               <title>Page Title</title>
>           </head>
>           <body>
>       
>               <h1>This is a Heading</h1>
>               <p>This is a paragraph.</p>
>       
>           </body>
>       </html>

Let me explain this code section
* The DOCTYPE html declaration defines that this document is an HTML5 document, This must be in the top
>       <!DOCTYPE html> 
* The html element is the root element of an HTML page
>       <html>
* The head element contains meta information about the HTML page
>       <head>
* The title element specifies a title for the HTML page (which is shown in the browser's title bar or in the page's tab)
>       <title>
* The body element defines the document's body, and is a container for all the visible contents, such as headings, paragraphs, images, hyperlinks, tables, lists, etc.
>       <body>
* The h1 element defines a large heading
>       <h1>
* The p element defines a paragraph
>       <p>

## HTML Elements
Elements are tags, An HTML element is defined by a start tag, some content, and an end tag:
>       <tag> Content... </tag>

| Start tag |   Element content   | End tag |
| :-------- | :-----------------: | ------: |
| < h1>     |  My First Heading   |  </ h1> |
| < p>      | My first paragraph. |   </ p> |

## HTML Structure

Here's The basic Structure of a HTML Page
![basic](https://html.com/wp-content/uploads/html-homepage-layout-demo.webp)

Study this structure carefully, I don't think I'm going to add more layout sections to this course because we're doing something serious today.

## HTML History
Let's get to know what we're dealing with, Now we're using HTML 5.2 and 6 would be out in the near future, I'll let you know when we got something new.

| Year |                                 Version |
| :--- | --------------------------------------: |
| 1989 |            Tim Berners-Lee invented www |
| 1991 |           Tim Berners-Lee invented HTML |
| 1993 |              Dave Raggett drafted HTML+ |
| 1995 |     HTML Working Group defined HTML 2.0 |
| 1997 |            W3C Recommendation: HTML 3.2 |
| 1999 |           W3C Recommendation: HTML 4.01 |
| 2000 |           W3C Recommendation: XHTML 1.0 |
| 2008 |         WHATWG HTML5 First Public Draft |
| 2012 |            WHATWG HTML5 Living Standard |
| 2014 |               W3C Recommendation: HTML5 |
| 2016 |  W3C Candidate Recommendation: HTML 5.1 |
| 2017 | W3C Recommendation: HTML5.1 2nd Edition |
| 2017 |             W3C Recommendation: HTML5.2 |

## HTML Documents
VS Code users could use the ! attribution to get the basic boilerplate to their HTML document, and here's what the basic boilerplate looks like.

>       <!DOCTYPE html>
>       <html>
>           <head>
>               <title>Page Title</title>
>           </head>
>           <body>
>       
>               <h1>This is a Heading</h1>
>               <p>This is a paragraph.</p>
>       
>           </body>
>       </html>

But It's Same as the first example? Exactly. You have to use the Declaration at the top, the HTML tags, in it head and body tags. head contains preload scripts and body holds all of the document. this is it my friends, let's dig deep

## The <!DOCTYPE> Declaration
This declaration represents the document type, and helps browsers to display web pages correctly.
It must only appear once, at the top of the page (before any HTML tags).
the declaration for HTML 5 would be
>       <!DOCTYPE html>

## HTML Headings
There are 6 HTML Heading tags
>       <h1> Content 1 </h1>
>       <h2> Content 2 </h2>
>       <h3> Content 3 </h3>
>       <h4> Content 4 </h4>
>       <h5> Content 5 </h5>
>       <h6> Content 6 </h6>

Easy isn't it? yeah, it is. These heading tags are corresponding to several sizes of headings, in the decreasing order to be exact. Try it between body tags and see for your self.

## HTML Paragraph
This would be the tag you're working with for the most part because HTML is just book writing but with the bleeding edge technology.

>       <p> lorem ipsum </p>

No matter how much white space you used, you can't sure HTML would pre format it before displaying

>       <p> lorem ipsum </p>
>       <p> lorem                            ipsum </p>

These would display the same in HTML. Try it for your self. You can add a horizontal line across the document using hr tag

>       <hr/>

Notice this doesn't have a closing tag? This is a self closing tag, and there are few self closing tags around here, so stay sharp for them. Also if you need a line break, use the br tag and it's also a self closing tag.

>       <br/>

If you want to write a poem
>       <p>
>         Twinkle Twinkle little star
>         How I wander what you are
>         Up above the world so high
>         Like a diamond in the sky
>       </p>

Believe or not, this won't work, so for pre formatting ourselves, we use the pre tag

>       <p>
>           <pre>
>               Twinkle Twinkle little star
>               How I wander what you are
>               Up above the world so high
>               Like a diamond in the 
>           </pre>
>       </p>

Try these examples to see for your self.

## HTML Links / Anchors
Every single one of us knows what links are? aren't we? if you don't know what links are, I'm not sure you should be continuing on, so check this [link](https://en.wikipedia.org/wiki/Link), We have something called attributes in HTML. attributes are like properties for elements. they declared inside Elements and changes that element's behavior. for links, 

we use < a > tag and in it, we can use

| Attribute      | Description                                                                                                                                                            |
| :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| download       | Prompts the user to save the linked URL instead of navigating to it. Can be used with or without a value                                                               |
| href           | The URL that the hyperlink points to. Links are not restricted to HTTP-based URLs — they can use any URL scheme supported by browsers                                  |
| hreflang       | Hints at the human language of the linked URL. No built-in functionality. Allowed values are the same as the global lang attribute.                                    |
| ping           | A space-separated list of URLs. When the link is followed, the browser will send POST requests with the body PING to the URLs. Typically for tracking.                 |
| referrerpolicy | How much of the referrer to send when following the link. See Referrer-Policy for possible values and their effects.                                                   |
| rel            | The relationship of the linked URL as space-separated link types.                                                                                                      |
| target         | Where to display the linked URL, as the name for a browsing context (a tab, window, or iframe). The following keywords have special meanings for where to load the URL |

a simple link would be like this
>       <a href="https://www.tecinpact.tk">Click Here</a>

## HTML Images

HTML images are defined with the img tag.

The source file (src), alternative text (alt), width, and height are provided as attributes

simply like this

>       <img src="./images/profile.jpg" alt="This would show if something went wrong" width="100px" height="100px">

## Title Attribute (Tooltips)

You can use the Title attribute anywhere to give the user a tooltip

>       <p title="hello">text</p>
>       <h1 title="hello">text</h1>
>       <a title="hello">text</a>

## Important Note
Always use single or double quotes when passing attribute values, no matter what.

## Text Formatting
This is like a word document with extra steps, so we also have text formatting here, and to use it, we just have to use some tags, I'll show you a single example but you can try others too
Formatting elements were designed to display special types of text, so use these tags.

* b - Bold text
* strong - Important text
* i - Italic text
* em - Emphasized text
* mark - Marked text
* small - Smaller text
* del - Deleted text
* ins - Inserted text
* sub - Subscript text
* sup - Superscript text

To use these formatters, I'll demonstrate it with a paragraph and a heading, but you can use it anywhere

>       <p> Hello <b>Bold text</b> World </p>
>       <h1> Hello <i>Italic text</i> World </h1>

## HTML Quotation and Citation Elements

We will go through the blockquote,q, abbr, address, cite, bdo HTML elements.
| Element    | Description                                                                                                                                               |
| :--------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------- |
| blockquote | this element can blockquote text sections.                                                                                                                |
| q          | this element is used for short quotations                                                                                                                 |
| abbr       | This element defines an abbreviation or an acronym.Marking abbreviations can give useful information to browsers, translation systems and search-engines. |
| address    | as it says, it's for typing out addresses, now this tag would improve SEO index on the page                                                               |
| cite       | this tag defines the title of a creative work for an example a book, a painting, a poem, a song etc.                                                      |
| bdo        | BDO stands for Bi-Directional Override.                                                                                                                   |

let me show you an example
>       <address>
>           No.100,
>           somewhere street,
>           somewhere state,
>           101010,
>           a country.
>       </address>

and BDO has something to show you
>       <bdo dir="rtl">This text will be written from right to left</bdo>

This is how you use a bdo element. for others, just enclose the text with it and you're pretty much done.

## HTML Comments
Now now, this is not how you can add a comment section on your page, it's to comment out certain hints for you to understand the code in the future because humans are just a potato when remembering things, so it's useful to add comments in documents so you don't have to remember a 1200 line document entirely.

Comments are simple and straight forward.

>       <!-- This Won't Do anything with the code -->
>       <p> bla bla bla bla bla </p>
>       <!-- 
>            This
>            Is A
>            Multiline Comment
>        -->

## HTML Colors
you can create any color you want from hex codes but, there are pre defined 140 standard colors to begin with, [Here](/pdf/color-names.pdf) you can see the complete color list.

## Adding CSS
HTML Can't use it's element's to add styles to the page, so it needs CSS. I'll cover CSS in the future and I won't showcase any css codes today, but I'll show how you can add CSS to the HTML Page since It's compulsory to use CSS.

There are 3 ways of doing this
* Inline - Using style attribute in any of the elements
>       <tag style="css code here"> Content </tag>
* Internal - Using style tags in the head
>       <style> css goes here </style>
* External - you can link a css document in the head
>       <link rel="stylesheet" href="styles.css">

## HTML Links

Here we go a bit deeper in to the situation. we are discussing about target and url types.

#### The target Attribute
By default, the linked page will be displayed in the current browser window. To change this, you must specify another target for the link.

The target attribute specifies where to open the linked document.

The target attribute can have one of the following values:

* _self - Default. Opens the document in the same window/tab as it was clicked
* _blank - Opens the document in a new window or tab
* _parent - Opens the document in the parent frame
* _top - Opens the document in the full body of the window

example
>       <a href="https://www.tecinpact.tk" target="_blank" > Content </a>

#### Absolute URLs vs. Relative URLs
all examples above are using an absolute URL (a full web address) in the href attribute. A local link (a link to a page within the same website) is specified with a relative URL (without the "https://www" part)

Absolute URL
>       <a href="https://www.tecinpact.tk/index.html">HTML</a>
Relative URL
>       <a href="index.html">HTML</a>

Both of these are referring to the same page if it's placed in the roots of my blog.
Also you can add anything in anchor tags, and what inside would turn into the link, even you can use images like this

>       <a href="https://www.tecinpact.tk/"><img src="images/site-feature-image.png"/></a>

I Think you got the point here. But linking for emails, that's something else. this is the format for it.

>       <a href="mailto:someone@example.com">Send email</a>

Also you can use a link as a bookmark, which means if someone clicked on that link, he or she will be scrolled to a certain location in the document. for this first you need to assign IDs, i'll explains IDs in a while, but for now, say if you have a id assigned to a element called myID. to scroll to it,

>       <a href="#myID">Scroll to My ID</a>

of if you're using an external page,

>       <a href="that-page.html#myID">Scroll to My ID</a>

## HTML Image Maps

Noticed We're getting hard codes or so? It's not hard but seems like, so we're digging in to a deeper part in HTML, These aren't that hard, because it's just a markup. Now, Image maps are something you can do with images, for an example, let's take this image.

![imaps](https://www.w3schools.com/html/workplace.jpg)

Here, let's say that I want the user to redirect to another page when the user selects certain objects in the image. let's see here

I want the user to redirect to several pages. and I'm mapping the image as this.
* if the user selects the laptop, he will be redirected to google
* if the user selects the coffee, he will be redirected to bing
* if the user selects the phone, he will be redirected to microsoft

So first we have to add the image,

>       <img src="workplace.jpg" alt="Workplace" usemap="#workmap">

Here you can see, I'm setting usemap attribution to workmap with a hash. now let me create the map itself.

>       <map name="workmap">

Simple isn't it. now here comes the fun part. I'm selecting the map areas as this.


