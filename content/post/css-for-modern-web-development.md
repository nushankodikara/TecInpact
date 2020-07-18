---
title: "CSS for Modern Web Development (Zero-To-Hero)"
date: 2020-07-18T09:40:00+05:30
Description: ""
Tags: ["web development","CSS","Zero To Hero","Crash Course"]
Categories: []
DisableComments: false
---

# Introduction
Well well, here we are in the section of styling our HTML Page, if you don't know what HTML is, Check [HERE](/post/html-for-modern-web-development/) for the HTML Course on modern web development, Today we're using CSS and HTML knowledge to create a beautiful looking website.

Today we're creating 

# Adding to HTML
There are three ways we can add a css file to our HTML Document and you can use unlimited css files in a single HTML page, Let's Explore.
* Externally
* Internally
* Inline

### External CSS Files.
Here we can create a .css file in our root directory, And to link it to the HTML Page, you have to add a link tag in the head section of our HTML page
>       <link rel="stylesheet" href="<path-with-name>">

As a practical usage
>       <link rel="stylesheet" href="style.css">

Here, I'm linking a style.css file near the index.html file. Now This is how my file directory looks like

![File Structure](/uploads/20200718_01.png)

And This is how my HTML Document Looks like.

![HTML Document](/uploads/20200718_02.png)

Also you can include a style tag in html page and put css in it like this

>       <head>
>           <style>
>               div {background:black;}
>           </style>
>       </head>

Or use inline style attribution to apply css directly to that block

>       <div style="background:black; font-family: monospace;"></div>

## Purpose Of CSS
Remember, this css language is for styling oyt html page and Here with my modern development course, I'm explaining only what you will use for real projects, there are a lot of properties you can play with and you're always open to explore. And remember because this is modern web development, we'll use scss and these are what you only use.

## Selectors
Here, there are three types of selectors. you can select a tag in our HTML page, you can select a class in our HTML page and you can also select an ID on our HTML page. And to select each type

| Type      | How To Select It                        | Examples |
| :-------- | :-------------------------------------- | :------- |
| HTML Tags | tag name without any special characters | h1       |
| Classes   | class name with a dot in-front          | .myClass |
| IDs       | ID Name with a Hash in-front            | #myID    |

I'll show an example just to understand what these used for,

>       h1 {
>           color: red;
>           font-family: monospace;    
>       }
> 
>       .myClass {
>           background:Maroon;
>           padding:10px;
>           margin:10px;
>           width:100vw;
>       }
> 
>       #myID {
>           position:fixed;
>           bottom:0;
>           width:100%;
>           background:green;
>       }

Here, you can see how the selector is used. now in those curly braces, those are properties and those properties change certain display aspects of HTML Elements. Here in the first part, I selected h1 heading and in curly braces applied font color of red and changed it's font to monospace. let's try in our page. I'm only doing this once so see how I do this and follow along. I'm creating h1 element, a div element with class of myClass and a div element with the id of myID. and This is how html looks like

>       <!DOCTYPE html>
>       <html lang="en">
>       
>       <head>
>           <title>Modern Web Development Tutorial</title>
>           <link rel="stylesheet" href="style.css">
>       </head>
>       
>       <body>
>           <h1>Hello World</h1>
>           <div class="myClass">Testing World</div>
>           <div id="myID">Testing ID World</div>
>       </body>
>       
>       </html>

And this is how I did it.

![HTML Document](/uploads/20200718_02.png)
![CSS Document](/uploads/20200718_02.png)

and now you can see the web page looks like this.

![Webpage Preview](/uploads/20200718_02.png)

Let's explore what properties we have to work with and how to use it.

![css form](https://www.w3schools.com/css/selector.gif)

## Comments in css
you can use the opening tag /* and closing tag */ for comments

>       /* Comment */

>       /* Multiline
>           Comment */

## Properties

### Animation Properties

| Property                  | Description                                                                                         |
| :------------------------ | :-------------------------------------------------------------------------------------------------- |
| animation                 | Specifies the keyframe-based animations.                                                            |
| animation-delay           | Specifies when the animation will start.                                                            |
| animation-direction       | Specifies whether the animation should play in reverse on alternate cycles or not.                  |
| animation-duration        | Specifies the number of seconds or milliseconds an animation should take to complete one cycle.     |
| animation-fill-mode       | Specifies how a CSS animation should apply styles to its target before and after it is executing.   |
| animation-iteration-count | Specifies the number of times an animation cycle should be played before stopping.                  |
| animation-name            | Specifies the name of @keyframes defined animations that should be applied to the selected element. |
| animation-play-state      | Specifies whether the animation is running or paused.                                               |
| animation-timing-function | Specifies how a CSS animation should progress over the duration of each cycle.                      |

### Background Properties

| Property              | Description                                                               |
| :-------------------- | :------------------------------------------------------------------------ |
| background            | Defines a variety of background properties within one declaration.        |
| background-attachment | Specify whether the background image is fixed in the viewport or scrolls. |
| background-clip       | Specifies the painting area of the background.                            |
| background-color      | Defines an element's background color.                                    |
| background-image      | Defines an element's background image.                                    |
| background-origin     | Specifies the positioning area of the background images.                  |
| background-position   | Defines the origin of a background image.                                 |
| background-repeat     | Specify whether/how the background image is tiled.                        |
| background-size       | Specifies the size of the background images.                              |

### Border Properties

| Property                   | Description                                                                        |
| :------------------------- | :--------------------------------------------------------------------------------- |
| border                     | Sets the width, style, and color for all four sides of an element's border.        |
| border-bottom              | Sets the width, style, and color of the bottom border of an element.               |
| border-bottom-color        | Sets the color of the bottom border of an element.                                 |
| border-bottom-left-radius  | Defines the shape of the bottom-left border corner of an element.                  |
| border-bottom-right-radius | Defines the shape of the bottom-right border corner of an element.                 |
| border-bottom-style        | Sets the style of the bottom border of an element.                                 |
| border-bottom-width        | Sets the width of the bottom border of an element.                                 |
| border-color               | Sets the color of the border on all the four sides of an element.                  |
| border-image               | Specifies how an image is to be used in place of the border styles.                |
| border-image-outset        | Specifies the amount by which the border image area extends beyond the border box. |
| border-image-repeat        | Specifies whether the image-border should be repeated, rounded or stretched.       |
| border-image-slice         | Specifies the inward offsets of the image-border.                                  |
| border-image-source        | Specifies the location of the image to be used as a border.                        |
| border-image-width         | Specifies the width of the image-border.                                           |
| border-left                | Sets the width, style, and color of the left border of an element.                 |
| border-left-color          | Sets the color of the left border of an element.                                   |
| border-left-style          | Sets the style of the left border of an element.                                   |
| border-left-width          | Sets the width of the left border of an element.                                   |
| border-radius              | Defines the shape of the border corners of an element.                             |
| border-right               | Sets the width, style, and color of the right border of an element.                |
| border-right-color         | Sets the color of the right border of an element.                                  |
| border-right-style         | Sets the style of the right border of an element.                                  |
| border-right-width         | Sets the width of the right border of an element.                                  |
| border-style               | Sets the style of the border on all the four sides of an element.                  |
| border-top                 | Sets the width, style, and color of the top border of an element.                  |
| border-top-color           | Sets the color of the top border of an element.                                    |
| border-top-left-radius     | Defines the shape of the top-left border corner of an element.                     |
| border-top-right-radius    | Defines the shape of the top-right border corner of an element.                    |
| border-top-width           | Sets the width of the top border of an element.                                    |
| border-width               | Sets the width of the border on all the four sides of an element.                  |

### Color Properties

| Property | Description                                  |
| :------- | :------------------------------------------- |
| color    | Specify the color of the text of an element. |
| opacity  | Specifies the transparency of an element.    |

### Dimension Properties

| Property   | Description                               |
| :--------- | :---------------------------------------- |
| height     | Specify the height of an element.         |
| max-height | Specify the maximum height of an element. |
| max-width  | Specify the maximum width of an element.  |
| min-height | Specify the minimum height of an element. |
| min-width  | Specify the minimum width of an element.  |
| width      | Specify the width of an element.          |

### Generated Content Properties

| Property          | Description                              |
| :---------------- | :--------------------------------------- |
| content           | Inserts generated content.               |
| quotes	Specifies  | quotation marks for embedded quotations. |
| counter-reset     | Creates or resets one or more counters.  |
| counter-increment | Increments one or more counter values.   |

### Flexible Box Layout

| Property        | Description                                                                                                                                    |
| :-------------- | :--------------------------------------------------------------------------------------------------------------------------------------------- |
| align-content   | Specifies the alignment of flexible container's items within the flex container.                                                               |
| align-items     | Specifies the default alignment for items within the flex container.                                                                           |
| align-self      | Specifies the alignment for selected items within the flex container.                                                                          |
| flex            | Specifies the components of a flexible length.                                                                                                 |
| flex-basis      | Specifies the initial main size of the flex item.                                                                                              |
| flex-direction  | Specifies the direction of the flexible items.                                                                                                 |
| flex-flow       | A shorthand property for the flex-direction and the flex-wrap properties.                                                                      |
| flex-grow       | Specifies how the flex item will grow relative to the other items inside the flex container.                                                   |
| flex-shrink     | Specifies how the flex item will shrink relative to the other items inside the flex container.                                                 |
| flex-wrap       | Specifies whether the flexible items should wrap or not.                                                                                       |
| justify-content | Specifies how flex items are aligned along the main axis of the flex container after any flexible lengths and auto margins have been resolved. |
| order           | Specifies the order in which a flex items are displayed and laid out within a flex container.                                                  |

### Font Properties

| Property         | Description                                                  |
| :--------------- | :----------------------------------------------------------- |
| font             | Defines a variety of font properties within one declaration. |
| font-family      | Defines a list of fonts for element.                         |
| font-size        | Defines the font size for the text.                          |
| font-size-adjust | Preserves the readability of text when font fallback occurs. |
| font-stretch     | Selects a normal, condensed, or expanded face from a font.   |
| font-style       | Defines the font style for the text.                         |
| font-variant     | Specify the font variant.                                    |
| font-weight      | Specify the font weight of the text.                         |

### List Properties

| Property            | Description                                             |
| :------------------ | :------------------------------------------------------ |
| list-style          | Defines the display style for a list and list elements. |
| list-style-image    | Specifies the image to be used as a list-item marker.   |
| list-style-position | Specifies the position of the list-item marker.         |
| list-style-type     | Specifies the marker style for a list-item.             |

### Margin Properties

| Property      | Description                                  |
| :------------ | :------------------------------------------- |
| margin	Sets   | the margin on all four sides of the element. |
| margin-bottom | Sets the bottom margin of the element.       |
| margin-left   | Sets the left margin of the element.         |
| margin-right  | Sets the right margin of the element.        |
| margin-top    | Sets the top margin of the element.          |

### Multi-column Layout Properties

| Property          | Description                                                                                      |
| :---------------- | :----------------------------------------------------------------------------------------------- |
| column-count      | Specifies the number of columns in a multi-column element.                                       |
| column-fill       | Specifies how columns will be filled.                                                            |
| column-gap        | Specifies the gap between the columns in a multi-column element.                                 |
| column-rule       | Specifies a straight line, or "rule", to be drawn between each column in a multi-column element. |
| column-rule-color | Specifies the color of the rules drawn between columns in a multi-column layout.                 |
| column-rule-style | Specifies the style of the rule drawn between the columns in a multi-column layout.              |
| column-rule-width | Specifies the width of the rule drawn between the columns in a multi-column layout.              |
| column-span       | Specifies how many columns an element spans across in a multi-column layout.                     |
| column-width      | Specifies the optimal width of the columns in a multi-column element.                            |
| columns           | A shorthand property for setting column-width and column-count properties.                       |

### Outline Properties

| Property       | Description                                                                  |
| :------------- | :--------------------------------------------------------------------------- |
| outline        | Sets the width, style, and color for all four sides of an element's outline. |
| outline-color  | Sets the color of the outline.                                               |
| outline-offset | Set the space between an outline and the border edge of an element.          |
| outline-style  | Sets a style for an outline.                                                 |
| outline-width  | Sets the width of the outline.                                               |

### Padding Properties

| Property       | Description                                        |
| :------------- | :------------------------------------------------- |
| padding        | Sets the padding on all four sides of the element. |
| padding-bottom | Sets the padding to the bottom side of an element. |
| padding-left   | Sets the padding to the left side of an element.   |
| padding-right  | Sets the padding to the right side of an element.  |
| padding-top    | Sets the padding to the top side of an element.    |

### Print Properties

| Property          | Description                             |
| :---------------- | :-------------------------------------- |
| page-break-after  | Insert a page breaks after an element.  |
| page-break-before | Insert a page breaks before an element. |
| page-break-inside | Insert a page breaks inside an element. |

### Table Properties

| Property        | Description                                                      |
| :-------------- | :--------------------------------------------------------------- |
| border-collapse | Specifies whether table cell borders are connected or separated. |
| border-spacing  | Sets the spacing between the borders of adjacent table cells.    |
| caption-side    | Specify the position of table's caption.                         |
| empty-cells     | Show or hide borders and backgrounds of empty table cells.       |
| table-layout    | Specifies a table layout algorithm.                              |

### Text Properties

| Property              | Description                                                                                                              |
| :-------------------- | :----------------------------------------------------------------------------------------------------------------------- |
| direction             | Define the text direction/writing direction.                                                                             |
| tab-size              | Specifies the length of the tab character.                                                                               |
| text-align            | Sets the horizontal alignment of inline content.                                                                         |
| text-align-last       | Specifies how the last line of a block or a line right before a forced line break is aligned when text-align is justify. |
| text-decoration       | Specifies the decoration added to text.                                                                                  |
| text-decoration-color | Specifies the color of the text-decoration-line.                                                                         |
| text-decoration-line  | Specifies what kind of line decorations are added to the element.                                                        |
| text-decoration-style | Specifies the style of the lines specified by the text-decoration-line property.                                         |
| text-indent           | Indent the first line of text.                                                                                           |
| text-justify          | Specifies the justification method to use when the text-align property is set to justify.                                |
| text-overflow         | Specifies how the text content will be displayed, when it overflows the block containers.                                |
| text-shadow           | Applies one or more shadows to the text content of an element.                                                           |
| text-transform        | Transforms the case of the text.                                                                                         |
| line-height           | Sets the height between lines of text.                                                                                   |
| vertical-align        | Sets the vertical positioning of an element relative to the current text baseline.                                       |
| letter-spacing        | Sets the extra spacing between letters.                                                                                  |
| word-spacing          | Sets the spacing between words.                                                                                          |
| white-space           | Specifies how white space inside the element is handled.                                                                 |
| word-break            | Specifies how to break lines within words.                                                                               |
| word-wrap             | Specifies whether to break words when the content overflows the boundaries of its container.                             |

### Transform Properties

| Property            | Description                                                                                        |
| :------------------ | :------------------------------------------------------------------------------------------------- |
| backface-visibility | Specifies whether or not the "back" side of a transformed element is visible when facing the user. |
| perspective         | Defines the perspective from which all child elements of the object are viewed.                    |
| perspective-origin  | Defines the origin (the vanishing point for the 3D space) for the perspective property.            |
| transform           | Applies a 2D or 3D transformation to an element.                                                   |
| transform-origin    | Defines the origin of transformation for an element.                                               |
| transform-style     | Specifies how nested elements are rendered in 3D space.                                            |

### Transitions Properties

| Property                   | Description                                                                                  |
| :------------------------- | :------------------------------------------------------------------------------------------- |
| transition                 | Defines the transition between two states of an element.                                     |
| transition-delay           | Specifies when the transition effect will start.                                             |
| transition-duration        | Specifies the number of seconds or milliseconds a transition effect should take to complete. |
| transition-property        | Specifies the names of the CSS properties to which a transition effect should be applied.    |
| transition-timing-function | Specifies the speed curve of the transition effect.                                          |

### Visual formatting Properties

| Property   | Description                                                                                     |
| :--------- | :---------------------------------------------------------------------------------------------- |
| display    | Specifies how an element is displayed onscreen.                                                 |
| position   | Specifies how an element is positioned.                                                         |
| top        | Specify the location of the top edge of the positioned element.                                 |
| right      | Specify the location of the right edge of the positioned element.                               |
| bottom     | Specify the location of the bottom edge of the positioned element.                              |
| left       | Specify the location of the left edge of the positioned element.                                |
| float      | Specifies whether or not a box should float.                                                    |
| clear      | Specifies the placement of an element in relation to floating elements.                         |
| z-index    | Specifies a layering or stacking order for positioned elements.                                 |
| overflow   | Specifies the treatment of content that overflows the element's box.                            |
| overflow-x | Specifies how to manage the content when it overflows the width of the element's content area.  |
| overflow-y | Specifies how to manage the content when it overflows the height of the element's content area. |
| resize     | Specifies whether or not an element is resizable by the user.                                   |
| clip       | Defines the clipping region.                                                                    |
| visibility | Specifies whether or not an element is visible.                                                 |
| cursor     | Specify the type of cursor.                                                                     |
| box-shadow | Applies one or more drop-shadows to the element's box.                                          |
| box-sizing | Alter the default CSS box model.                                                                |

## Discussion

Now that's all we need for CSS, look carefully and you'll find something you like, now let's create some simple but beautiful webpages to emphasize our skills, and get to know how to use css.

## Let's Create A Login Page

Now, Let's Cerate this beautiful Login page And I'll Show you the code and then explain what's going on here, Now considering this, it's not a difficult one to make as it seams. Also you can download the complete project [HERE](/static/zip/Sample-site.zip).

![HTML Document](/uploads/20200718_06.png)

#### HTML
First of all, let's see what's in the HTML Section of this code.

>       <!DOCTYPE html>
>       <html>
>       
>       <head>
>           <title>Modern Web Development Tutorial</title>
>           <link rel="stylesheet" href="style.css">
>       </head>
>       
>       <body>
>           <div id="loginSection">
>               <img src="avatar.webp" title="User Image">
>               <h1>Log In</h1>
>               <form>
>                   <input type="text" id="username" name="username" placeholder="Username">
>                   <input type="password" id="password" name="password" placeholder="Password">
>                   <button>Login</button><br>
>                   <small>By Signing in, You Are agreeing to the terms and conditions</small>
>                   <small id="resetLink"><a>Reset Password</a></small>
>               </form>
>           </div>
>       </body>
>       
>       </html>

Let me explain. Here first I made a div section with the id of loginSection. and in it I placed a image tag, h1 tag, a form with two input fields for username and password, a button to login, A disclaimer note and a link to reset the password. Here, the functionality isn't considered and we are making this functional in the Javascript course. And That's it for HTML.

#### CSS

Here Begins the fun part. It's not that hard but you have to remember what you need and use it carefully, let me show you the code base first.

>       * {
>           font-family: monospace;
>       }
>       
>       body {
>           width: 100%;
>           margin: 0;
>           padding: 0;
>           background-image: url(background.jpg);
>           background-repeat: no-repeat;
>           background-position: center;
>           background-size: cover;
>       }
>       
>       #loginSection {
>           background-color: rgba(250, 235, 215, 0.6);
>           max-width: 250px;
>           padding: 20px;
>           text-align: center;
>           position: fixed;
>           top: 50%;
>           left: 50%;
>           transform: translate(-50%, -70%);
>           border-radius: 20px;
>       }
>       
>       img {
>           width: 180px;
>       }
>       
>       input {
>           width: 80%;
>           padding: 15px 20px;
>           outline: none;
>           margin-bottom: 15px;
>           border-radius: 500px;
>           border: none;
>       }
>       
>       button {
>           padding: 15px 30px;
>           outline: none;
>           border-radius: 500px;
>           color: black;
>           background-color: GreenYellow;
>           border: none;
>       }
>       
>       button:hover {
>           background-color: rgb(153, 255, 0);
>       }
>       
>       #resetLink {
>           color: cornflowerblue;
>       }

Here, Let me explain. first I made a selector called * and this is a special selector, which selects everything, means the properties in the * selector can affect every element in the HTML page, here I changed the font family to monospace ( It's my favorite ).

in then i selected the whole body section of the document with body selector and made it stretch 100% which means from the left side to the right side completely, and removed margin and padding. also added a background image (Here you have to use that url section) and I set that background repeat to no repeat. and I made that background to stay anchored to the center. also made the background size a cover, which means the background covers the whole screen.

Now loginSection part. Here I selected the login section with the ID I provided, and set it's background color to a pale white with RGB colors and the alpha channel to 0.6 (Transparency). Then fixed it's width to 250px and added a padding of 20px. Aligned it's text to center which makes everything in login section centered. Now I made the position of it fixed which means it doesn't scroll with the window. and it has to be fixed in the center so I made it hang 50% from the top and 50% from the left. Also I have to set a offset to make it to the dead center, I did it by using a transform property, there, I made translate -50% in the X axis and -70% in the Y axis to make it a little bit to the top. Then I rounded it's borders using border-radius property.

for the avatar image, I just selected img tag and set it's width to 180px and here, when I'm not providing the height, It automatically assigns it's height and that's it for the image.

Then the input boxes, here I only have two input tags and they are username and password so I can just select input tag and It'll apply to both of those, here I made it's width 80% from parent container which is the login section. and added a padding top and bottom of 15px to make it a bit taller and 20px to left and right to make it a bit longer, also I removed it's outline and border, and added a margin to the bottom of 15px and to make it pill shaped, added a border radius of 500px (That's a trick)

Buttons are the same, I added some padding to 4 sides to make it a bit taller and a bit longer, removed border and outline, made it's text black and background color of greenYellow. 

Then Button:hover section is a special selector, these properties applies when the user hovers the mouse above the button, so I made it to go a bit darker when hovering. and I selected the password reset link with it's ID and added a color of cornflowerblue.

And That's pretty much it guys, Play with these values to get a feeling for it. and css isn't something that's hard, you just have to get a feeling.

# Conclusion
Well well well, here we are at the end of another course, CSS Zero to Hero and this one is a bit different than others, just explanation and an example. Is it enough? yeah, get a feeling to it and you'll flow on css, CSS is not something difficult something for you to think for hours upon hours, play with it for sometime, it's just a styling guide and when you're comfortable with it, You're an artist drawing in a web browser with some codes.