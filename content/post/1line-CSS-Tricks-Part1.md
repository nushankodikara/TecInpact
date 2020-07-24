---
title: "Single line CSS Tricks (Part 1)"
date: 2020-07-24T06:00:00+05:30
Description: ""
Tags: ["CSS","Life Hacks","Guide"]
Categories: []
DisableComments: false
---

# Introduction
CSS is the main styler over the internet, We all can't use everything on css and because it's a huge base, We're probably lost somewhere inside it, So today, Let's explore some creative and simple to use but effective single line codes for your next project. You can visit the CSS Full course [HERE](/post/css-for-modern-web-development/) And without much explanations, Let's get in to the post.

# 01. Super Centered

We can do so much things to make a code centered, But have you use the place-items property of the grid layout? Here's how to use it.

![CSS Style](/uploads/20200724_01.png)

```html
<div class="parent" >
  <div class="box" contenteditable>
    Hello World
  </div>
</div>
```

```css
  .parent {
    display: grid;
    place-items: center;
  }
```
# 02. The Easy Card

We all have a moment which we need to create some responsive cards on CSS but how are we going to do that depends on our knowledge on CSS, But had you ever came across this technique? Use the stretching code if you want to stretch the cards to fit the container, or use the no stretching code.

![CSS Style](/uploads/20200724_02.png)

```html
  <div class="parent white">
    <div class="box green">1</div>
    <div class="box green">2</div>
    <div class="box green">3</div>
  </div>
```

```css
  .parent {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

  .box {
    flex: 1 1 150px; /*  Stretching: */
    flex: 0 1 150px; /*  No stretching: */
    margin: 5px;
  }
```

# 03. Easy Side bar

This is how you can add a simple but elegant side bar to your HTML document without a much effort

![CSS Style](/uploads/20200724_03.png)

```html
 <div class="parent">
    <div class="section yellow" contenteditable>
    Min: 150px / Max: 25%
    </div>
    <div class="section purple" contenteditable>
      This element takes the second grid position (1fr), meaning
      it takes up the rest of the remaining space.
    </div>
  </div>
```
```css
  .parent {
    display: grid;
    grid-template-columns: minmax(150px, 25%) 1fr;
  }
```

# 04. Pancake Stack

This is a common occurrence in modern web development, but had it been this easy to set up?

![CSS Style](/uploads/20200724_04.png)

```html
  <div class="parent">
    <header class="blue section" contenteditable>Header</header>
    <main class="coral section" contenteditable>Main</main>
    <footer class="purple section" contenteditable>Footer Content</footer>
  </div>
```
```css
  .parent {
    display: grid;
    grid-template-rows: auto 1fr auto;
  }
```

# 05. Classic Holy Grail Layout

As the name suggest, It's a all time classic, less seen these days but there are many Auctions which this presents.

![CSS Style](/uploads/20200724_05.png)

```html
  <div class="parent">
    <header class="pink section">Header</header>
    <div class="left-side blue section" contenteditable>Left Sidebar</div>
    <main class="section coral" contenteditable> Main Content</main>
    <div class="right-side yellow section" contenteditable>Right Sidebar</div>
    <footer class="green section">Footer</footer>
  </div>
```
```css
  .parent {
    display: grid;
    grid-template: auto 1fr auto / auto 1fr auto;
  }
  
  header {
    padding: 2rem;
    grid-column: 1 / 4;
  }

  .left-side {
    grid-column: 1 / 2;
  }

  main {
    grid-column: 2 / 3;
  }

  .right-side {
    grid-column: 3 / 4;
  }

  footer {
    grid-column: 1 / 4;
  }
```

# 06. 12-Span Grid

We don't always use bootstrap or a framework like that, We can implement the 12-span grid without much effort like this.

![CSS Style](/uploads/20200724_06.png)

```html
  <div class="parent white">
    <div class="span-12 green section">Span 12</div>
    <div class="span-6 coral section">Span 6</div>
    <div class="span-4 blue section">Span 4</div>
    <div class="span-2 yellow section">Span 2</div>
  </div>
```
```css
  .parent {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
  }
  
  .span-12 {
    grid-column: 1 / span 12;
  }

  .span-6 {
    grid-column: 1 / span 6;
  }

  .span-4 {
    grid-column: 4 / span 4;
  }

  .span-2 {
    grid-column: 3 / span 2;
  }

  /* centering text */
  .section {
    display: grid;
    place-items: center;
    text-align: center
  }
```

# 07. RAM (Repeat, Auto, Minmax)

Now what's this? Imagine this as a responsive grid layout for like a photo gallery or for a post gallery, anyway for a gallery.

![CSS Style](/uploads/20200724_07.png)

```html
  <div class="parent white">
    <div class="box pink">1</div>
    <div class="box purple">2</div>
    <div class="box blue">3</div>
    <div class="box green">4</div>
  </div>
```
```css
  .parent {
    display: grid;
    grid-gap: 1rem;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  }
```

# 08. Line Up

This is the perfect grid for a post set, for a blog or anything formal. Check this out and use your imaginative mindset for good use.

![CSS Style](/uploads/20200724_08.png)

```html
  <div class="parent white">
    <div class="card yellow">
      <h3>Title - Card 1</h3>
      <p contenteditable>Medium length description with a few more words here.</p>
      <div class="visual pink"></div>
    </div>
    <div class="card yellow">
      <h3>Title - Card 2</h3>
      <p contenteditable>Long Description. Lorem ipsum dolor sit, amet consectetur adipisicing elit.</p>
      <div class="visual blue"></div>
    </div>
    <div class="card yellow">
      <h3>Title - Card 3</h3>
      <p contenteditable>Short Description.</p>
      <div class="visual green"></div>
    </div>
  </div>
```
```css
  .ex8 .parent {
    height: auto;
    display: grid;
    grid-gap: 1rem;
    grid-template-columns: repeat(3, 1fr);
  }

  .ex8 .visual {
    height: 100px;
    width: 100%;
  }

  .ex8 .card {
    display: flex;
    flex-direction: column;
    padding: 1rem;
    justify-content: space-between;
  }

  .ex8 h3 {
    margin: 0
  }
```

# 09. Clamping Posts

This is best suite for a feature post style thing in my opinion, Look for yourself. and you'll maybe use it in your next project.

![CSS Style](/uploads/20200724_09.png)

```html
  <div class="parent white">
    <div class="card purple">
      <h1>Title Here</h1>
      <div class="visual yellow"></div>
      <p>Descriptive Text. Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sed est error repellat veritatis.</p>
    </div>
  </div>
```
```css
  .parent {
    display: grid;
    place-items: center;
  }

  .card {
    width: clamp(23ch, 50%, 46ch);
    display: flex;
    flex-direction: column;
    padding: 1rem;
  }
```

# 10. Keep the Aspect

Let's be real, there are sometimes we need to hold an aspect ratio for an element which we don't know the parent container's dimensions, Now we can use this for it

![CSS Style](/uploads/20200724_10.png)

```html
  <div class="parent white">
    <div class="card blue">
      <h1>Video Title</h1>
      <div class="visual green"></div>
      <p>Descriptive Text. This demo works in Chromium 84+.</p>
    </div>
  </div>
```
```css
  .parent {
    display: grid;
    place-items: center;
  }

  .visual {
    aspect-ratio: 16 / 9;
  }

  .card {
    width: 50%;
    display: flex;
    flex-direction: column;
    padding: 1rem;
  }
```

# Conclusion
You could be an expert on css, maybe a beginner or whatever, Did you saw this coming? I use them daily in my projects and They are like bread and butter. I hope you'll use them in your next project.