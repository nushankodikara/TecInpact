---
title: "HTML for Modern Web Development (Zero-To-Hero)"
date: 2020-07-14
Description: "HTML For modern web development"
Tags: ["web development","HTML","Zero To Hero","Crash Course"]
Categories: []
DisableComments: false
---

## Introduction
HTML is the structural markup language for the web development community, there are more than HTML in markup community but for websites, we use mainly HTML. I'll explain HTML from ground level so if you're a absolute beginner, you can follow up easily. If something went wrong, just contact me from the links provided.

## Environment
HTML doesn't need a specific environment to run, but Modern web development required you to host the main files. So let's start with our code editor. You can use anything if you know what you're doing, or else I'm using [Visual Studio Code](/post/vs-code-for-web-developers/) and I installed the live server extension for this demo. Or you can use [Codesandbox.io](https://codesandbox.io/) (Not Sponsored).

## Folder Structure
Modern web development has a rule to start the main HTML file with
>       index.html
Name scheme. remember the whole file name and the extension is in lowercase, and put it in the root folder. Now what is this root folder? Remember, this folder is the main folder of your Project. When You're uploading the site or developing the hybrid app, you are uploading this folder to the servers. so it's the main folder.

## Setting up the VS Code
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

## HTML Introduction
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

## Zero

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

### HTML Elements
Elements are tags, An HTML element is defined by a start tag, some content, and an end tag:
>       <tag> Content... </tag>

| Start tag |   Element content   | End tag |
| :-------- | :-----------------: | ------: |
| < h1>     |  My First Heading   |  </ h1> |
| < p>      | My first paragraph. |   </ p> |

### HTML Structure

Here's The basic Structure of a HTML Page
![basic](https://html.com/wp-content/uploads/html-homepage-layout-demo.webp)

Study this structure carefully, I don't think I'm going to add more layout sections to this course because we're doing something serious today.

### HTML History
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

### HTML Documents
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

### The <!DOCTYPE> Declaration
This declaration represents the document type, and helps browsers to display web pages correctly.
It must only appear once, at the top of the page (before any HTML tags).
the declaration for HTML 5 would be
>       <!DOCTYPE html>

### HTML Headings
There are 6 HTML Heading tags
>       <h1> Content 1 </h1>
>       <h2> Content 2 </h2>
>       <h3> Content 3 </h3>
>       <h4> Content 4 </h4>
>       <h5> Content 5 </h5>
>       <h6> Content 6 </h6>

Easy isn't it? yeah, it is. These heading tags are corresponding to several sizes of headings, in the decreasing order to be exact. Try it between body tags and see for your self.

### HTML Paragraph
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

### HTML Links / Anchors
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

### HTML Images

HTML images are defined with the img tag.

The source file (src), alternative text (alt), width, and height are provided as attributes

simply like this

>       <img src="./images/profile.jpg" alt="This would show if something went wrong" width="100px" height="100px">

### Title Attribute (Tooltips)

You can use the Title attribute anywhere to give the user a tooltip

>       <p title="hello">text</p>
>       <h1 title="hello">text</h1>
>       <a title="hello">text</a>

### Important Note
Always use single or double quotes when passing attribute values, no matter what.

### Text Formatting
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

### HTML Quotation and Citation Elements

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

### HTML Comments
Now now, this is not how you can add a comment section on your page, it's to comment out certain hints for you to understand the code in the future because humans are just a potato when remembering things, so it's useful to add comments in documents so you don't have to remember a 1200 line document entirely.

Comments are simple and straight forward.

>       <!-- This Won't Do anything with the code -->
>       <p> bla bla bla bla bla </p>
>       <!-- 
>            This
>            Is A
>            Multiline Comment
>        -->

### HTML Colors
you can create any color you want from hex codes but, there are pre defined 140 standard colors to begin with, [Here](/pdf/color-names.pdf) you can see the complete color list.

### Adding CSS
HTML Can't use it's element's to add styles to the page, so it needs CSS. I'll cover CSS in the future and I won't showcase any css codes today, but I'll show how you can add CSS to the HTML Page since It's compulsory to use CSS.

There are 3 ways of doing this
* Inline - Using style attribute in any of the elements
>       <tag style="css code here"> Content </tag>
* Internal - Using style tags in the head
>       <style> css goes here </style>
* External - you can link a css document in the head
>       <link rel="stylesheet" href="styles.css">

### HTML Links

Here we go a bit deeper in to the situation. we are discussing about target and url types.

##### The target Attribute
By default, the linked page will be displayed in the current browser window. To change this, you must specify another target for the link.

The target attribute specifies where to open the linked document.

The target attribute can have one of the following values:

* _self - Default. Opens the document in the same window/tab as it was clicked
* _blank - Opens the document in a new window or tab
* _parent - Opens the document in the parent frame
* _top - Opens the document in the full body of the window

example
>       <a href="https://www.tecinpact.tk" target="_blank" > Content </a>

##### Absolute URLs vs. Relative URLs
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

### HTML Tables

Here, you can use the table element to create tables. How ever there are more to this, In tables, you have to define Table Rows with tr element inside the table element and Inside the table rows, you have to define table heading or table data with th or tr elements, let me show you a Simple Table

>       <table>
>           <tr>
>               <th> First Heading </th>
>               <th> Second Heading </th>
>               <th> Third Heading </th>
>           </tr>
>           <tr>
>               <td> First Data </td>
>               <td> Second Data </td>
>               <td> Third Data </td>
>           </tr>
>       </table>

You can expand a data cell in columns or rows, this is the same process as merging cells in excel sheets. There are two ways on doing this,
* Spread in columns with Colspan
* Spread in rows with Rowspan

Here is a demonstration on how you can do this

Considering Colspan attribute

>       <table>
>           <tr>
>               <th>Name</th>
>               <th colspan="2">Telephone</th>
>           </tr>
>           <tr>
>               <td>Bill Gates</td>
>               <td>55577854</td>
>               <td>55577855</td>
>           </tr>
>       </table>

Considering Rowspan attribute

>       <table>
>           <tr>
>               <th>Name:</th>
>               <td>Bill Gates</td>
>           </tr>
>           <tr>
>               <th rowspan="2">Telephone:</th>
>               <td>55577854</td>
>           </tr>
>           <tr>
>               <td>55577855</td>
>           </tr>
>       </table>

Now here, you'll notice that I'm not providing you with any Images lately on the display side of the things, it's because by now, you should be trying these by your self! If not, Why are you even following this article?

Also You can add captions to the table with the caption element

>       <table>
>           <caption>Our First Table</caption>
>           <tr>
>               <th> First Heading </th>
>               <th> Second Heading </th>
>               <th> Third Heading </th>
>           </tr>
>           <tr>
>               <td> First Data </td>
>               <td> Second Data </td>
>               <td> Third Data </td>
>           </tr>
>       </table>

**Important Notice** The Caption element must be defined after the Table element as in the above example.

### HTML Lists

It's pretty straight forward from here on, There are three types of lists.
* Un-ordered lists
* Ordered lists
* Description lists

No matter what you use, you have to add the elements to the list using li element. Let me demonstrate to you

>       <!-- Un-ordered List -->
>       <ul>
>           <li> element 1 </li>
>           <li> element 2 </li>
>           <li> element 3 </li>
>       </ul>
> 
>       <!-- Ordered List -->
>       <ol>
>           <li> element 1 </li>
>           <li> element 2 </li>
>           <li> element 3 </li>
>       </ol>
> 
>       <!-- Description List -->
>       <dl>
>           <dt>Main Item</dt>
>           <dd>main Item description</dd>
>           <dt>Secondary Item</dt>
>           <dd>Secondary Item description</dd>
>       </dl>

### HTML Blocks
Now my friends if you're comfortable with the concepts of HTML, let me show you how to group anything in HTML. grouping elements can give you the possibilities and the ease to apply certain properties to a group of elements without doing it one by one, There are few blocks you can use for this purpose and they are pretty much self explanatory.

Here are some block-level elements in HTML.
* address
* article
* aside
* blockquote
* canvas
* dd
* div
* dl
* dt
* fieldset
* figcaption
* figure
* footer
* form
* h1-h6
* header
* hr
* li
* main
* nav
* noscript
* ol
* p
* pre
* section
* table
* tfoot
* ul
* video

To use HTML Block-level elements

>       <tag>
>           .
>           content goes here
>           .
>       </tag>

Now don't get panic seeing these, You'll understand these elements with some examples, and also the internet is open for more information. (Just google for more information.)

And Here are some Inline-elements
* a
* abbr
* acronym
* b
* bdo
* big
* br
* button
* cite
* code
* dfn
* em
* i
* img
* input
* kbd
* label
* map
* object
* output
* q
* samp
* script
* select
* small
* span
* strong
* sub
* sup
* textarea
* time
* tt
* var

To use inline elements

>       bla bla <tag> this is a </tag> paragraph in something in the document

Now, you don't have to use all of these to remembered in order to master in html, but it's handy to know what's there to use in case of "An Event".

##### Div element
Now this div element stand for division and this is something special because we have to use this in like everywhere because this is the main element on grouping elements, to use

>       <div>
>           .
>           .
>           Content Goes Here
>           .
>           .
>       </div>

And you can apply certain properties to that div specifically. (more details later)

##### Span element
This is exactly like the div element but this can be used inline.

>       bla bla <span> this is a </span> paragraph in something in the document

### HTML Classes
This is a method of selecting a certain set of elements, spread across the HTML document and without using elements, now this attribute would be used in CSS and JS to identify the element and I'll explain how to select using classes in the future, for now let's add classes to certain elements

>       <tag class="your-class second-class">
>           .
>           .
>           Content Goes Here
>           .
>           .
>       </tag>

you can have any number of classes assigned for a element and separate them with a space and you're good to go.

### HTML ID
This is exactly like classes but you can't use multiple IDs for a element or you can't assign a single ID to multiple tags. IDs are used to select specific tags such as a input box for password in a login forum. more details later. Let's assign an ID

>       <tag id="myID">
>           .
>           .
>           Content Goes Here
>           .
>           .
>       </tag>

### HTML Iframes
Iframes are also easy to use, you can embed another webpage (local or external) in to your webpage. and it's something you have to try for yourself to understand

>       <iframe src="https://www.tecinpact.tk/" title="description" width="100px" height="100px">
>       </iframe>

also you can change the src of the iframe using an anchor as this

>       <iframe src="https://www.tecinpact.tk/" name="iframe_a" title="Iframe Example"></iframe>
>       <p><a href="http://www.tecinpact.tk/post/html-for-modern-web-development/" target="iframe_a">W3Schools.com</a></p>

### Script Element
You can insert JS to your webpage externally or locally using script tag, to use it externally.

>       <script src="external-js-file.js"></script>

or Internally

>       <script>
>           // JS Goes Here
>       </script>

And don't consider this for now, after I published the JS crash course, you're good to go.

### Head element
Let's turn around to the boilerplate and our Head element, It's one of the main elements in HTML and you can use it to house the title, style, meta, link, script and base elements which describes the document

you should know by now how these work, so I'll provide some examples.

Linking external css files
>       <link rel="stylesheet" href="mystyle.css">

Define character set
>       <meta charset="UTF-8">

Define Keywords for SEO
>       <meta name="keywords" content="HTML, CSS, JavaScript">

Define Description for SEO
>       <meta name="description" content="Free Web tutorials">

Define the author of the page
>       <meta name="author" content="John Doe">

Refresh the page every 30 seconds
>       <meta http-equiv="refresh" content="30">

Setting the viewport to make your website look good on all devices
>       <meta name="viewport" content="width=device-width, initial-scale=1.0">

### HTML Computer codes
HTML Has a unique property to showcase computer codes in your documents, as I'm doing right now, you can use code and kbd elements to showcase codes and keyboard inputs easily, also samp for programing outputs and var for Variables

>       <code>
>           var x = 10;
>           var b = 5;
>       </code>

>       This is kbd function, to copy <kbd>Ctrl + C</kbd> is useful

>       <p>Message from my computer:</p>
>       <p><samp>File not found.<br>Press F1 to continue</samp></p>

>       <p>The area of a triangle is: 1/2 x <var>b</var> x <var>h</var>, where <var>b</var> is the base, and <var>h</var> is the vertical height.</p>

### HTML Forms
You can create a HTML Form using the form element, in it you can set
* Text Inputs
* Email Inputs
* Password Inputs
* Radio buttons
* Selections
* Submit button
* Reset button
* Text areas

We won't be considering the functionality of forms under modern web development until JS course, so let's learn the structure, here's an example for you to try out

>       <form>
>           <label>Text</label>
>           <input type="text" id="text" name="name" placeholder="Text">
>           <label>Email</label>
>           <input type="email" id="email" name="email" placeholder="Email">
>           <label>Password</label>
>           <input type="password" id="password" name="password" placeholder="password">
>           <label>Textarea</label>
>           <textarea placeholder="textArea" id="textarea" name="textarea" ></textarea>
>           <br/>
>           <input type="radio" id="male" name="gender" value="male">
>           <label for="male">Male</label><br>
>           <input type="radio" id="female" name="gender" value="female">
>           <label for="female">Female</label><br>
>           <input type="radio" id="other" name="gender" value="other">
>           <label for="other">Other</label>
>           <select id="cars" name="cars">
>               <option value="volvo">Volvo</option>
>               <option value="saab">Saab</option>
>               <option value="fiat">Fiat</option>
>               <option value="audi">Audi</option>
>           </select>
>           <datalist id="browsers">
>               <option value="Internet Explorer">
>               <option value="Firefox">
>               <option value="Chrome">
>               <option value="Opera">
>               <option value="Safari">
>           </datalist>
>       </form>

These are the basics and you can try to understand what each item does, and here's a list of Input types to try on

* button
* checkbox
* color
* date
* datetime-local
* email
* file
* hidden
* image
* month
* number
* password
* radio
* range
* reset
* search
* submit
* tel
* text
* time
* url
* week

How to use these again? Let me show you

>       <input type="type-from-above"/>

use a ID and name attribute to give it a uniqueness so we can select it later.

also for input element you can use these attributes, and they are also pretty much self explanatory
* **value** Specify an initial value
* **readonly** make the field readonly
* **disabled** Disable the field
* **size** visible width in characters.
* **maxlength** Max length of an input field
* **min** and **max** Minimum and maximum values for an input field
* **multiple** specifies that the user is allowed to enter more than one value in an input field
* **pattern** specifies a regular expression that the input field's value is checked against, when the form is submitted.
* **placeholder** specifies short a hint that describes the expected value of an input field.
* **required** attribute specifies that an input field must be filled out before submitting the form.
* **autofocus** specifies that an input field should automatically get focus when the page loads.
* **autocomplete** specifies whether a form or an input field should have autocomplete on or off.

Now how to use them, I'll provide an example with all of those above.

>       <input value="Jhon Doe" readonly>
>       <input value="Jhon Doe" disabled>
>       <input value="Jhon Doe" size="30" maxlength="40" required autofocus autocomplete="off" placeholder="Name">

### HTML Media

To embed videos, it's straight forward.

>           <video width="320" height="240" autoplay>
>               <source src="movie.mp4" type="video/mp4">
>               <source src="movie.ogg" type="video/ogg">
>               Your browser does not support the video tag.
>           </video>

Also embedding audio is straight forward.

>       <audio controls>
>           <source src="horse.ogg" type="audio/ogg">
>           <source src="horse.mp3" type="audio/mpeg">
>           Your browser does not support the audio element.
>       </audio>

### HTML Special Elements
Well, here are some special elements to use in your documents.
* br - This element is used for line breaks
* hr - This element is used for Horizontal lines

>       <p>Hello the world <br> Of HTML Magic</p>
>       <hr>
>       <p>In A Land of code, in the time of web development</p>

## WTF Is This? how can this make a Website?
Now now, calm down for a second, HTML is the structure for the websites, you can't and you shouldn't style your document with HTML attributes, we're using CSS for styling, and We're going to explore CSS in a further course. and for HTML, You're a Hero now!

## That's It?
That's it, for modern web development, but there are more tags and so many more things on html, but we don't want any of those, because we're creating our own layouts and they are much more responsible than default HTML 5 options. You're open to explore.

## What's next?
You can get a certificate from Us on completing HTML course for free. If you're interested send what certificates you want to [tecinpactagencies@gmail.com](mailto:tecinpactagencies@gmail.com) and After a brief test on your knowledge, We'll Issue a certificate. Also stay tuned for CSS and JS pages

## Cheatsheet ?
Yeah here's a cheatsheet for HTML
* [Html Cheatsheet](https://htmlcheatsheet.com/)
* [PDF](https://websitesetup.org/wp-content/uploads/2019/10/WSU-HTML-Cheat-Sheet.pdf)

## Conclusion
Well, It's hard to make these courses for you, if you can show some love, share these, It would great! Well, anyhow I'll post Css and Js as soon as possible so we can round this up. HTML can be used to create websites mainly and hybrid mobile and desktop apps, but it should be stylized with css and add functions with Js. Stay tuned and I'll make you a pro within no time.
