---
title: "VS Code for Web Developers"
date: 2020-07-12T07:38:18+05:30
Description: "Visual studio is a code editor by microsoft and It's popular among most of the developers for a reason."
Tags: ["Windows","Linux","Web Development"]
Categories: []
DisableComments: false
---
## Introduction
Visual studio code is a powerful and a user-friendly code editor, It has extended functionality, which makes it an all-in-one solution for most of the web developers and This would be a follow up guide to a Web and Hybrid app development course I'm planning forward to.

### Installation
VS Code is available for Windows, Mac and linux, so pretty much It's a cross platform code editor. one of my favourite. You can download it [Here](https://code.visualstudio.com/) for all platforms. Or You can get it from Linux and mac app stores too. And for [choco](/post/the-package-manager-for-windows-chocolatey/) instance,
>       > choco install vscode

### Command Palette
Access all available commands based on your current context.

>       Ctrl + Shift + P

![VS Code](https://code.visualstudio.com/assets/docs/getstarted/tips-and-tricks/OpenCommandPalatte.gif)

### Default keyboard shortcuts
All of the commands are in the Command Palette with the associated key binding (if it exists). If you forget a keyboard shortcut, use the Command Palette to help you out.

![VS Code](https://code.visualstudio.com/assets/docs/getstarted/tips-and-tricks/keyboard-references.png)

![VS Code](https://code.visualstudio.com/assets/docs/getstarted/tips-and-tricks/KeyboardReferenceSheet.png)

### Quick Open
Quickly open files.

>       Ctrl + P

![VS Code](https://code.visualstudio.com/assets/docs/getstarted/tips-and-tricks/QuickOpen.gif)

### Navigate between recently opened files
Repeat the Quick Open keyboard shortcut to cycle quickly between recently opened files.

### Open multiple files from Quick Open
You can open multiple files from Quick Open by pressing the Right arrow key. This will open the currently selected file in the background and you can continue selecting files from Quick Open.

### Navigate between recently opened folders and workspaces
Open Recent

>       Ctrl + R

Displays a Quick Pick dropdown with the list from File > Open Recent with recently opened folders and workspaces followed by files.

### Status Bar
Errors and warnings
>       Ctrl + Shift + M

Quickly jump to errors and warnings in the project.

Cycle through errors with F8 or Shift+F8

![VS Code](https://code.visualstudio.com/assets/docs/getstarted/tips-and-tricks/Errors_Warnings.gif)

You can filter problems either by type ('errors', 'warnings') or text matching.

### Change language mode
>       Ctrl + K M

![VS Code](https://code.visualstudio.com/assets/docs/getstarted/tips-and-tricks/change_syntax.gif)

f you want to persist the new language mode for that file type, you can use the Configure File Association for command to associate the current file extension with an installed language.

For more information Check [This article.](https://code.visualstudio.com/docs/getstarted/tips-and-tricks)

### Extensions
VS Code has a Extension store on it's own, so no more hard work for working extensions.
![VS Code](/uploads/20200712_01.png "VS Code")

Here you can see the extension store of the VS Code, you can also trigger it using 
>       Ctrl + Shift + X

or for mac

>       Command + Shift + X

#### What I Extensions Should You Use
Well, for today, I'll show you some extensions I use for my personal Projects, Use the extension Store to get These Extensions.

| Extension                  |                                                                                    Icon                                                                                    |                                                                                                                                                                         Description |
| :------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Beautify                   |             ![Beautify](https://hookyqr.gallerycdn.vsassets.io/extensions/hookyqr/beautify/1.5.0/1556863124877/Microsoft.VisualStudio.Services.Icons.Default)              |                                                                                                        This Extension Helps to beautify and format HTML JS CSS SCSS JSON documents. |
| Community Material Theme   | ![Theme](https://equinusocio.gallerycdn.vsassets.io/extensions/equinusocio/vsc-community-material-theme/1.4.1/1581768092718/Microsoft.VisualStudio.Services.Icons.Default) |                                                                           This Would increase the contras between code and the editor, so It's easier to see and easy for the eyes. |
| JS & CSS Minifier (Minify) |            ![Minify](https://olback.gallerycdn.vsassets.io/extensions/olback/es6-css-minify/3.3.2/1578585334332/Microsoft.VisualStudio.Services.Icons.Default)             |                                                                     This Extension would help you to minify written codes into .min files, so our sites would be faster in no time. |
| Live Sass Compiler         |            ![SCSS](https://ritwickdey.gallerycdn.vsassets.io/extensions/ritwickdey/live-sass/3.0.0/1531332580258/Microsoft.VisualStudio.Services.Icons.Default)            |                                                                               We're Using this extension to compile our SCSS Codes into css files so we can link them in our files. |
| Live Server                |          ![SERVER](https://ritwickdey.gallerycdn.vsassets.io/extensions/ritwickdey/liveserver/5.6.1/1555497731217/Microsoft.VisualStudio.Services.Icons.Default)           | As it says in the name, It's a simple web server. why do we need it? because modern JS won't work completely in local files. so we need a some kind of a Server to test everything. |
| Mark Down All In One       |           ![MDE](https://yzhang.gallerycdn.vsassets.io/extensions/yzhang/markdown-all-in-one/3.1.0/1592619570838/Microsoft.VisualStudio.Services.Icons.Default)            |                                                                         This one will help us on our markdown files, to format markdown files and it also has some Snippets to use. |
| Mark Down Preview Enhanced |                                          ![MDP](https://cdn.vsassets.io/v/M172_20200708.16/_content/Header/default_icon_128.png)                                           |                                                                                          This extension will show a live preview of our markdown files so it's easier to work with. |
| Material Icon Theme        |            ![MIT](https://pkief.gallerycdn.vsassets.io/extensions/pkief/material-icon-theme/4.2.0/1592422271844/Microsoft.VisualStudio.Services.Icons.Default)             |                                                                   Here's another theme for you. This would change default file extension icons in VS Code and I Highly Recommend it |
| Toggle format on save      |                                          ![FOS](https://cdn.vsassets.io/v/M172_20200708.16/_content/Header/default_icon_128.png)                                           |                                                                                      This extension would format our documents on save. I use it most of the times, and you should. |

And That's Pretty much It for now. Also you can search for more extensions in the store anytime you want. Just click install to install it.

### Useful Commands And Guide

Press F1 to popup the quick command panel, It'll help you to run quick commands and extensions.

#### Toggle format on save

Press F1 and type Toggle Format on save and your extension window will pop up, click on it and you're good to go. That's pretty much how you do it for almost every extension.

![VS Code](/uploads/20200712_02.png)

#### Terminal / Power shell on current Directory

You can open your working directory by using
>       > code .

on terminal Or going to File > Open Folder

Then you can popup an integrated terminal on that specific folder by using
>       Ctrl + `

or in Mac
>       Command + `

![VS Code](/uploads/20200712_03.png)

#### Live Server

If you installed the live server Extension, you can see a small Go Live button on bottom right when you're working with HTML Pages.

![VS Code](/uploads/20200712_04.png)

#### Quick Tips

You Can use ! Symbol to load up a HTML boilerplate whenever you need.

![VS Code](/uploads/20200712_05.png)
![VS Code](/uploads/20200712_06.png)

#### Emmet in Visual Studio Code

![Emmet](https://code.visualstudio.com/assets/docs/editor/emmet/emmet.gif)

This is a complete toolkit for web developers. It's Easier to learn and use, and It'll improve your productivity overtime. I'll explain it in another post because there are so much to go. I'll provide you what we need in specific documents in the future.

Or [Check This Guide](https://docs.emmet.io/cheat-sheet/) On Emmet. Also a Cheat Sheet to [Download](http://bit.ly/2mLmFAn)

## GIT Integration
Yes, VS Code has built in Git support, but you have to download and install git bash to associate with this functions. I'll Explain everything in the future so if you aren't comfortable with anything above, Don't worry you'll be comfortable after everything completes.

## What's Next?
From Here on I'll Discuss a complete guide to Web development and Hybrid app development. And in the End I'll Provide with a Course hub "Maybe" If You are interested (Let me know in the comments).

## Conclusion
It's Harder for humans to brake up with their habits, but for a starter, Start with what's best and you'll be more productive with the time. VS Code is a great and easy to use editor or "A Development Environment", as nothing as I seen in the past, No doubts it's the most favourite.