---
title: "Web Code Minification"
date: 2020-07-25T06:00:00+05:30
Description: ""
Tags: ["web development","Minification","Zero To Hero","Crash Course"]
Categories: []
DisableComments: false
---

# Introduction

Code minification is a process modern web developers use on developments to speed up the loading of the codes, reduce the code size and decrease the ability to reverse-engineer the code. And it's pretty easy to use too, but sadly not most of the developers know how to do it themselves. Let's Explore Shall we.

# Minification

Now, We use an online tool for this process, https://www.willpeavy.com/tools/minifier/ Goto this website for the tool, and It's pretty simple to use but highly effective. Let's consider a huge HTML code like this.

![Minifier](/uploads/20200725_01.jpg)

Let's see how we can minify the code.

```html
<!doctype html>
<html lang=en data-theme=light>
   <head>
      <title>Tecinpact | Page</title>
      <meta charset=utf-8>
      <meta name=generator content="Hugo 0.73.0">
      <meta name=viewport content="width=device-width,initial-scale=1,viewport-fit=cover">
      <meta name=description content="Welcome Visitor! here you can find out new technologies, Reviews, suggestions about technologies and step-by-step guides to the EASY World. If you need any help, Just contact Me.">
      <link rel=stylesheet href=https://www.tecinpact.tk/css/style.min.67cd718c0a3c8009c771494d381fb7128246a454bd0518fed97cb65d257db948.css integrity="sha256-Z81xjAo8gAnHcUlNOB+3EoJGpFS9BRj+2Xy2XSV9uUg=" crossorigin=anonymous type=text/css>
      <link href=https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css rel=stylesheet integrity=sha384-wvfXpqpZZVQGK6TAh5PVlGOfQNHSoD2xbE+QkPxCAFlNEevoEH3Sl0sibVcOQVnN crossorigin=anonymous>
      <link rel="shortcut icon" href=https://www.tecinpact.tk/favicons/favicon.ico type=image/x-icon>
      <link rel=apple-touch-icon sizes=180x180 href=https://www.tecinpact.tk/favicons/apple-touch-icon.png>
      <link rel=icon type=image/png sizes=32x32 href=https://www.tecinpact.tk/favicons/favicon-32x32.png>
      <link rel=icon type=image/png sizes=16x16 href=https://www.tecinpact.tk/favicons/favicon-16x16.png>
      <link rel=canonical href=https://www.tecinpact.tk/>
      <script type=text/javascript src=https://www.tecinpact.tk/js/anatole-header.min.c275265a259296f3dd50e8236a77fcbcadb1dbb9597d3045c675dcc2c7c58a93.js integrity="sha256-wnUmWiWSlvPdUOgjanf8vK2x27lZfTBFxnXcwsfFipM=" crossorigin=anonymous></script>
      <meta name=twitter:card content="summary_large_image">
      <meta name=twitter:image content="https://www.tecinpact.tk/images/site-feature-image.png">
      <meta name=twitter:title content="Page">
      <meta name=twitter:description content="TECINPACT Technology Guide">
   </head>
   <body>
      <div class="sidebar animated fadeInDown">
         <div class=logo-title>
            <div class=title>
               <img src=https://www.tecinpact.tk/images/profile.jpg alt="profile picture">
               <h3><a href=/>I'm Nushan Kodikara</a></h3>
               <div class=description>
                  <p>Welcome Visitor! here you can find out new technologies, Reviews, suggestions about technologies and step-by-step guides to the EASY World. If you need any help, Just contact Me.</p>
               </div>
            </div>
         </div>
         <ul class=social-links>
            <li><a href=https://www.facebook.com/Tecinpact rel=me aria-label=Facebook><i class="fa fa-2x fa-facebook" aria-hidden=true></i></a></li>
            <li><a href=https://twitter.com/Tecinpact rel=me aria-label=Twitter><i class="fa fa-2x fa-twitter" aria-hidden=true></i></a></li>
            <li><a href=https://github.com/Tecinpact rel=me aria-label=GitHub><i class="fa fa-2x fa-github" aria-hidden=true></i></a></li>
            <li><a href=https://t.me/tecinpact rel=me aria-label=Telegram><i class="fa fa-2x fa-telegram" aria-hidden=true></i></a></li>
            <li><a href=https://wa.me/94719988189 rel=me aria-label=Whatsapp><i class="fa fa-2x fa-whatsapp" aria-hidden=true></i></a></li>
            <li><a href=https://www.instagram.com/Tecinpact rel=me aria-label=instagram><i class="fa fa-2x fa-instagram" aria-hidden=true></i></a></li>
            <li><a href=mailto:tecinpactagencies@gmail.com rel=me aria-label=e-mail><i class="fa fa-2x fa-envelope" aria-hidden=true></i></a></li>
         </ul>
         <div class=footer>
            <div class=by_farbox>&copy; Tecinpact 2020</div>
         </div>
      </div>
      </div>
      <div class=main>
         <div class="page-top animated fadeInDown">
            <ul class=nav>
               <li><a class=current href=/>Home</a></li>
               <li><a href=/post/>Posts</a></li>
               <li><a href=/about/>About</a></li>
               <li><a href=/portfolio/>Portfolio</a></li>
               <li><a href=/search/>Search</a></li>
            </ul>
            <div class=themeswitcher><a class=theme-switch title="Switch Theme"><i class="fa fa-adjust fa-fw" aria-hidden=true></i></a></div>
         </div>
         <div class=autopagerize_page_element>
            <div class=content>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/js-for-modern-web-development/>Js for Modern Web Development</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction Here we are at the end of the modern web development course, At the right basics of the language which make the web interactive and functional.</p>
                        <a href=/post/js-for-modern-web-development/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Thu, Jul 23, 2020</span>
                           <a class=tag href=/tags/web-development/>web development</a><a class=tag href=/tags/html/>HTML</a><a class=tag href=/tags/zero-to-hero/>Zero To Hero</a><a class=tag href=/tags/crash-course/>Crash Course</a>
                        </div>
                     </div>
                  </div>
               </div>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/download-youtube-videos-2020/>Download Youtube Videos 2020</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction Let&rsquo;s be real, We need to download Youtube Videos for so many reasons, Maybe mp3 from youtube, And we still don&rsquo;t have a clear way, But today I&rsquo;m here to change that, I Found some interesting apps and websites which can download From youtube directly as video or Audio.</p>
                        <a href=/post/download-youtube-videos-2020/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Wed, Jul 22, 2020</span>
                           <a class=tag href=/tags/android/>Android</a><a class=tag href=/tags/windows/>Windows</a><a class=tag href=/tags/mac/>Mac</a><a class=tag href=/tags/ios/>IOS</a><a class=tag href=/tags/youtube/>Youtube</a>
                        </div>
                     </div>
                  </div>
               </div>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/scss-for-modern-web-development/>Scss for Modern Web Development (Supercharged CSS)</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction If you noticed, I Didn&rsquo;t mentioned css for browser types in our previous CSS tutorial, The case is, I don&rsquo;t want to, SCSS is doing everything for us so why should we even bother?</p>
                        <a href=/post/scss-for-modern-web-development/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Tue, Jul 21, 2020</span>
                           <a class=tag href=/tags/web-development/>web development</a><a class=tag href=/tags/scss/>SCSS</a><a class=tag href=/tags/zero-to-hero/>Zero To Hero</a><a class=tag href=/tags/crash-course/>Crash Course</a>
                        </div>
                     </div>
                  </div>
               </div>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/create-an-eco-system-with-join/>Create an Eco System With Join by joaoapps</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction Let&rsquo;s be real, We all like to work in one place but access all of our devices, Apple has a solution for this but what if you don&rsquo;t have an apple eco system?</p>
                        <a href=/post/create-an-eco-system-with-join/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Mon, Jul 20, 2020</span>
                           <a class=tag href=/tags/android/>Android</a><a class=tag href=/tags/windows/>Windows</a><a class=tag href=/tags/ecosystem/>EcoSystem</a><a class=tag href=/tags/apple/>Apple</a>
                        </div>
                     </div>
                  </div>
               </div>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/storage-free-cloud-life-2020/>Storage Free Cloud Life 2020</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction Storage, in other words, Information had evolved in to almost to be a basic need of modern human life, Everything form studies, household things, social awareness programs and pretty much anything you name, has a digital counterpart that stored somewhere in the world, And as humans, we have to constantly phrase and read them to keep up with the modern society, and sometimes, It&rsquo;s a pain.</p>
                        <a href=/post/storage-free-cloud-life-2020/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Sun, Jul 19, 2020</span></div>
                     </div>
                  </div>
               </div>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/css-for-modern-web-development/>CSS for Modern Web Development (Zero-To-Hero)</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction Well well, here we are in the section of styling our HTML Page, if you don&rsquo;t know what HTML is, Check HERE for the HTML Course on modern web development, Today we&rsquo;re using CSS and HTML knowledge to create a beautiful looking website.</p>
                        <a href=/post/css-for-modern-web-development/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Sat, Jul 18, 2020</span>
                           <a class=tag href=/tags/web-development/>web development</a><a class=tag href=/tags/css/>CSS</a><a class=tag href=/tags/zero-to-hero/>Zero To Hero</a><a class=tag href=/tags/crash-course/>Crash Course</a>
                        </div>
                     </div>
                  </div>
               </div>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/adobe-softwares-ultimate-list-with-crack-2020/>Ultimate Adobe Softwares List With Universal Crack 2020</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction We all have used adobe software in some point of our lives and wandered how many others there are to explore.</p>
                        <a href=/post/adobe-softwares-ultimate-list-with-crack-2020/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Fri, Jul 17, 2020</span>
                           <a class=tag href=/tags/windows/>Windows</a><a class=tag href=/tags/software-review/>Software Review</a><a class=tag href=/tags/android/>Android</a><a class=tag href=/tags/mac/>Mac</a><a class=tag href=/tags/ios/>IOS</a><a class=tag href=/tags/adobe/>Adobe</a><a class=tag href=/tags/cracked/>Cracked</a>
                        </div>
                     </div>
                  </div>
               </div>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/photoshop-trending-autumn-effect-2020/>Photoshop Trending Autumn Effect 2020</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction Autumn effect is something now getting in trend on social medias, It&rsquo;s a simple filter but most of the softwares get it wrong and making a messed up look but untrained eye isn&rsquo;t going to notice that until doing some post processing.</p>
                        <a href=/post/photoshop-trending-autumn-effect-2020/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Fri, Jul 17, 2020</span>
                           <a class=tag href=/tags/photoshop-effects/>Photoshop Effects</a><a class=tag href=/tags/photoshop/>Photoshop</a><a class=tag href=/tags/photoshop-quick-effects/>Photoshop Quick Effects</a>
                        </div>
                     </div>
                  </div>
               </div>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/python-ultimate-crash-course-2020/>Python Ultimate Crash Course (Zero-To-Hero)</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction Python is one of most popular and most powerful and one of the fastest programming languages until now, Millions upon millions developers use python in their projects to script easily.</p>
                        <a href=/post/python-ultimate-crash-course-2020/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Thu, Jul 16, 2020</span>
                           <a class=tag href=/tags/programming/>Programming</a><a class=tag href=/tags/software-development/>Software Development</a><a class=tag href=/tags/zero-to-hero/>Zero To Hero</a><a class=tag href=/tags/crash-course/>Crash Course</a>
                        </div>
                     </div>
                  </div>
               </div>
               <div class="post animated fadeInDown">
                  <div class=post-title>
                     <h3><a href=/post/google-drive-serverless-web-hosting-2020/>Google Drive Serverless Web Hosting 2020</a></h3>
                  </div>
                  <div class=post-content>
                     <div class=p_part>
                        <p>Introduction Serverless web hosting getting popular day by day, with the rise of static websites, So here today, I&rsquo;m going to show you how to host your created website ( HTML JS And CSS files ) In the google drive, and setting up a proper domain name for it using Freenom and netlify.</p>
                        <a href=/post/google-drive-serverless-web-hosting-2020/>[Read More]</a>
                     </div>
                     <div class=p_part>
                        <p></p>
                     </div>
                  </div>
                  <div class=post-footer>
                     <div class=meta>
                        <div class=info><i class="fa fa-sun-o"></i><span class=date>Wed, Jul 15, 2020</span>
                           <a class=tag href=/tags/web-development/>Web development</a><a class=tag href=/tags/static-sites/>Static Sites</a>
                        </div>
                     </div>
                  </div>
               </div>
               <div class=pagination>
                  <ul class=pagination>
                     <li class=page-item><a href=/ class=page-link aria-label=First><span aria-hidden=true>&#171;&#171;</span></a></li>
                     <li class="page-item disabled"><a class=page-link aria-label=Previous><span aria-hidden=true>&#171;</span></a></li>
                     <li class="page-item active"><a class=page-link href=/>1</a></li>
                     <li class=page-item><a class=page-link href=/page/2/>2</a></li>
                     <li class=page-item><a href=/page/2/ class=page-link aria-label=Next><span aria-hidden=true>&#187;</span></a></li>
                     <li class=page-item><a href=/page/2/ class=page-link aria-label=Last><span aria-hidden=true>&#187;&#187;</span></a></li>
                  </ul>
               </div>
            </div>
         </div>
      </div>
   </body>
   <script type=text/javascript src=https://www.tecinpact.tk/js/jquery.min.86b1e8f819ee2d9099a783e50b49dff24282545fc40773861f9126b921532e4c.js integrity="sha256-hrHo+BnuLZCZp4PlC0nf8kKCVF/EB3OGH5EmuSFTLkw=" crossorigin=anonymous></script><script type=text/javascript src=https://www.tecinpact.tk/js/bundle.min.0f9c74cb78f13d1f15f33daff4037c70354f98acfbb97a6f61708966675c3cae.js integrity="sha256-D5x0y3jxPR8V8z2v9AN8cDVPmKz7uXpvYXCJZmdcPK4=" crossorigin=anonymous></script><script type=text/javascript src=https://www.tecinpact.tk/js/medium-zoom.min.92f21c856129f84aeb719459b3e6ac621a3032fd7b180a18c04e1d12083f8aba.js integrity="sha256-kvIchWEp+ErrcZRZs+asYhowMv17GAoYwE4dEgg/iro=" crossorigin=anonymous></script><script type=application/javascript>var doNotTrack=false;if(!doNotTrack){window.ga=window.ga||function(){(ga.q=ga.q||[]).push(arguments)};ga.l=+new Date;ga('create','UA-172360495-1','auto');ga('send','pageview');}</script><script async src=https://www.google-analytics.com/analytics.js></script>
</html>
</body></html>
```

Now This is the code of our main page, I know it's huge but I also need a huge but working code to demonstrate it to you. And now Let's Minify it using the tool. copy the whole code and paste in the compression section and press the minify button And you're completed.

```html
<!doctype html><html lang=en data-theme=light> <head> <title>Tecinpact | Page</title> <meta charset=utf-8> <meta name=generator content="Hugo 0.73.0"> <meta name=viewport content="width=device-width,initial-scale=1,viewport-fit=cover"> <meta name=description content="Welcome Visitor! here you can find out new technologies, Reviews, suggestions about technologies and step-by-step guides to the EASY World. If you need any help, Just contact Me."> <link rel=stylesheet href=https://www.tecinpact.tk/css/style.min.67cd718c0a3c8009c771494d381fb7128246a454bd0518fed97cb65d257db948.css integrity="sha256-Z81xjAo8gAnHcUlNOB+3EoJGpFS9BRj+2Xy2XSV9uUg=" crossorigin=anonymous type=text/css> <link href=https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css rel=stylesheet integrity=sha384-wvfXpqpZZVQGK6TAh5PVlGOfQNHSoD2xbE+QkPxCAFlNEevoEH3Sl0sibVcOQVnN crossorigin=anonymous> <link rel="shortcut icon" href=https://www.tecinpact.tk/favicons/favicon.ico type=image/x-icon> <link rel=apple-touch-icon sizes=180x180 href=https://www.tecinpact.tk/favicons/apple-touch-icon.png> <link rel=icon type=image/png sizes=32x32 href=https://www.tecinpact.tk/favicons/favicon-32x32.png> <link rel=icon type=image/png sizes=16x16 href=https://www.tecinpact.tk/favicons/favicon-16x16.png> <link rel=canonical href=https://www.tecinpact.tk/> <script type=text/javascript src=https://www.tecinpact.tk/js/anatole-header.min.c275265a259296f3dd50e8236a77fcbcadb1dbb9597d3045c675dcc2c7c58a93.js integrity="sha256-wnUmWiWSlvPdUOgjanf8vK2x27lZfTBFxnXcwsfFipM=" crossorigin=anonymous></script> <meta name=twitter:card content="summary_large_image"> <meta name=twitter:image content="https://www.tecinpact.tk/images/site-feature-image.png"> <meta name=twitter:title content="Page"> <meta name=twitter:description content="TECINPACT Technology Guide"> </head> <body> <div class="sidebar animated fadeInDown"> <div class=logo-title> <div class=title> <img src=https://www.tecinpact.tk/images/profile.jpg alt="profile picture"> <h3><a href=/>I'm Nushan Kodikara</a></h3> <div class=description> <p>Welcome Visitor! here you can find out new technologies, Reviews, suggestions about technologies and step-by-step guides to the EASY World. If you need any help, Just contact Me.</p></div></div></div><ul class=social-links> <li><a href=https://www.facebook.com/Tecinpact rel=me aria-label=Facebook><i class="fa fa-2x fa-facebook" aria-hidden=true></i></a></li><li><a href=https://twitter.com/Tecinpact rel=me aria-label=Twitter><i class="fa fa-2x fa-twitter" aria-hidden=true></i></a></li><li><a href=https://github.com/Tecinpact rel=me aria-label=GitHub><i class="fa fa-2x fa-github" aria-hidden=true></i></a></li><li><a href=https://t.me/tecinpact rel=me aria-label=Telegram><i class="fa fa-2x fa-telegram" aria-hidden=true></i></a></li><li><a href=https://wa.me/94719988189 rel=me aria-label=Whatsapp><i class="fa fa-2x fa-whatsapp" aria-hidden=true></i></a></li><li><a href=https://www.instagram.com/Tecinpact rel=me aria-label=instagram><i class="fa fa-2x fa-instagram" aria-hidden=true></i></a></li><li><a href=mailto:tecinpactagencies@gmail.com rel=me aria-label=e-mail><i class="fa fa-2x fa-envelope" aria-hidden=true></i></a></li></ul> <div class=footer> <div class=by_farbox>&copy; Tecinpact 2020</div></div></div></div><div class=main> <div class="page-top animated fadeInDown"> <ul class=nav> <li><a class=current href=/>Home</a></li><li><a href=/post/>Posts</a></li><li><a href=/about/>About</a></li><li><a href=/portfolio/>Portfolio</a></li><li><a href=/search/>Search</a></li></ul> <div class=themeswitcher><a class=theme-switch title="Switch Theme"><i class="fa fa-adjust fa-fw" aria-hidden=true></i></a></div></div><div class=autopagerize_page_element> <div class=content> <div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/js-for-modern-web-development/>Js for Modern Web Development</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction Here we are at the end of the modern web development course, At the right basics of the language which make the web interactive and functional.</p><a href=/post/js-for-modern-web-development/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Thu, Jul 23, 2020</span> <a class=tag href=/tags/web-development/>web development</a><a class=tag href=/tags/html/>HTML</a><a class=tag href=/tags/zero-to-hero/>Zero To Hero</a><a class=tag href=/tags/crash-course/>Crash Course</a> </div></div></div></div><div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/download-youtube-videos-2020/>Download Youtube Videos 2020</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction Let&rsquo;s be real, We need to download Youtube Videos for so many reasons, Maybe mp3 from youtube, And we still don&rsquo;t have a clear way, But today I&rsquo;m here to change that, I Found some interesting apps and websites which can download From youtube directly as video or Audio.</p><a href=/post/download-youtube-videos-2020/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Wed, Jul 22, 2020</span> <a class=tag href=/tags/android/>Android</a><a class=tag href=/tags/windows/>Windows</a><a class=tag href=/tags/mac/>Mac</a><a class=tag href=/tags/ios/>IOS</a><a class=tag href=/tags/youtube/>Youtube</a> </div></div></div></div><div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/scss-for-modern-web-development/>Scss for Modern Web Development (Supercharged CSS)</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction If you noticed, I Didn&rsquo;t mentioned css for browser types in our previous CSS tutorial, The case is, I don&rsquo;t want to, SCSS is doing everything for us so why should we even bother?</p><a href=/post/scss-for-modern-web-development/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Tue, Jul 21, 2020</span> <a class=tag href=/tags/web-development/>web development</a><a class=tag href=/tags/scss/>SCSS</a><a class=tag href=/tags/zero-to-hero/>Zero To Hero</a><a class=tag href=/tags/crash-course/>Crash Course</a> </div></div></div></div><div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/create-an-eco-system-with-join/>Create an Eco System With Join by joaoapps</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction Let&rsquo;s be real, We all like to work in one place but access all of our devices, Apple has a solution for this but what if you don&rsquo;t have an apple eco system?</p><a href=/post/create-an-eco-system-with-join/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Mon, Jul 20, 2020</span> <a class=tag href=/tags/android/>Android</a><a class=tag href=/tags/windows/>Windows</a><a class=tag href=/tags/ecosystem/>EcoSystem</a><a class=tag href=/tags/apple/>Apple</a> </div></div></div></div><div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/storage-free-cloud-life-2020/>Storage Free Cloud Life 2020</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction Storage, in other words, Information had evolved in to almost to be a basic need of modern human life, Everything form studies, household things, social awareness programs and pretty much anything you name, has a digital counterpart that stored somewhere in the world, And as humans, we have to constantly phrase and read them to keep up with the modern society, and sometimes, It&rsquo;s a pain.</p><a href=/post/storage-free-cloud-life-2020/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Sun, Jul 19, 2020</span></div></div></div></div><div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/css-for-modern-web-development/>CSS for Modern Web Development (Zero-To-Hero)</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction Well well, here we are in the section of styling our HTML Page, if you don&rsquo;t know what HTML is, Check HERE for the HTML Course on modern web development, Today we&rsquo;re using CSS and HTML knowledge to create a beautiful looking website.</p><a href=/post/css-for-modern-web-development/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Sat, Jul 18, 2020</span> <a class=tag href=/tags/web-development/>web development</a><a class=tag href=/tags/css/>CSS</a><a class=tag href=/tags/zero-to-hero/>Zero To Hero</a><a class=tag href=/tags/crash-course/>Crash Course</a> </div></div></div></div><div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/adobe-softwares-ultimate-list-with-crack-2020/>Ultimate Adobe Softwares List With Universal Crack 2020</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction We all have used adobe software in some point of our lives and wandered how many others there are to explore.</p><a href=/post/adobe-softwares-ultimate-list-with-crack-2020/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Fri, Jul 17, 2020</span> <a class=tag href=/tags/windows/>Windows</a><a class=tag href=/tags/software-review/>Software Review</a><a class=tag href=/tags/android/>Android</a><a class=tag href=/tags/mac/>Mac</a><a class=tag href=/tags/ios/>IOS</a><a class=tag href=/tags/adobe/>Adobe</a><a class=tag href=/tags/cracked/>Cracked</a> </div></div></div></div><div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/photoshop-trending-autumn-effect-2020/>Photoshop Trending Autumn Effect 2020</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction Autumn effect is something now getting in trend on social medias, It&rsquo;s a simple filter but most of the softwares get it wrong and making a messed up look but untrained eye isn&rsquo;t going to notice that until doing some post processing.</p><a href=/post/photoshop-trending-autumn-effect-2020/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Fri, Jul 17, 2020</span> <a class=tag href=/tags/photoshop-effects/>Photoshop Effects</a><a class=tag href=/tags/photoshop/>Photoshop</a><a class=tag href=/tags/photoshop-quick-effects/>Photoshop Quick Effects</a> </div></div></div></div><div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/python-ultimate-crash-course-2020/>Python Ultimate Crash Course (Zero-To-Hero)</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction Python is one of most popular and most powerful and one of the fastest programming languages until now, Millions upon millions developers use python in their projects to script easily.</p><a href=/post/python-ultimate-crash-course-2020/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Thu, Jul 16, 2020</span> <a class=tag href=/tags/programming/>Programming</a><a class=tag href=/tags/software-development/>Software Development</a><a class=tag href=/tags/zero-to-hero/>Zero To Hero</a><a class=tag href=/tags/crash-course/>Crash Course</a> </div></div></div></div><div class="post animated fadeInDown"> <div class=post-title> <h3><a href=/post/google-drive-serverless-web-hosting-2020/>Google Drive Serverless Web Hosting 2020</a></h3> </div><div class=post-content> <div class=p_part> <p>Introduction Serverless web hosting getting popular day by day, with the rise of static websites, So here today, I&rsquo;m going to show you how to host your created website ( HTML JS And CSS files ) In the google drive, and setting up a proper domain name for it using Freenom and netlify.</p><a href=/post/google-drive-serverless-web-hosting-2020/>[Read More]</a> </div><div class=p_part> <p></p></div></div><div class=post-footer> <div class=meta> <div class=info><i class="fa fa-sun-o"></i><span class=date>Wed, Jul 15, 2020</span> <a class=tag href=/tags/web-development/>Web development</a><a class=tag href=/tags/static-sites/>Static Sites</a> </div></div></div></div><div class=pagination> <ul class=pagination> <li class=page-item><a href=/ class=page-link aria-label=First><span aria-hidden=true>&#171;&#171;</span></a></li><li class="page-item disabled"><a class=page-link aria-label=Previous><span aria-hidden=true>&#171;</span></a></li><li class="page-item active"><a class=page-link href=/>1</a></li><li class=page-item><a class=page-link href=/page/2/>2</a></li><li class=page-item><a href=/page/2/ class=page-link aria-label=Next><span aria-hidden=true>&#187;</span></a></li><li class=page-item><a href=/page/2/ class=page-link aria-label=Last><span aria-hidden=true>&#187;&#187;</span></a></li></ul> </div></div></div></div></body> <script type=text/javascript src=https://www.tecinpact.tk/js/jquery.min.86b1e8f819ee2d9099a783e50b49dff24282545fc40773861f9126b921532e4c.js integrity="sha256-hrHo+BnuLZCZp4PlC0nf8kKCVF/EB3OGH5EmuSFTLkw=" crossorigin=anonymous></script><script type=text/javascript src=https://www.tecinpact.tk/js/bundle.min.0f9c74cb78f13d1f15f33daff4037c70354f98acfbb97a6f61708966675c3cae.js integrity="sha256-D5x0y3jxPR8V8z2v9AN8cDVPmKz7uXpvYXCJZmdcPK4=" crossorigin=anonymous></script><script type=text/javascript src=https://www.tecinpact.tk/js/medium-zoom.min.92f21c856129f84aeb719459b3e6ac621a3032fd7b180a18c04e1d12083f8aba.js integrity="sha256-kvIchWEp+ErrcZRZs+asYhowMv17GAoYwE4dEgg/iro=" crossorigin=anonymous></script><script type=application/javascript>var doNotTrack=false;if(!doNotTrack){window.ga=window.ga||function(){(ga.q=ga.q||[]).push(arguments)};ga.l=+new Date;ga('create','UA-172360495-1','auto');ga('send','pageview');}</script><script async src=https://www.google-analytics.com/analytics.js></script></html></body></html>
```

Now notice the code get compressed? this is a simple but effective way to improve your site's loading speed. And That's what in the top code but compressed. I know I know that looks cute and believe it or not, That works. You can use this with HTML CSS and JS and all of your files combined, That's allot of space to save on.

# Conclusion
This is something like a joke, I know. But it really works. Even you can check my site out using ctrl + U on desktop PCs, and you can explore the code of my website. It dramatically improves on SEO, Loading time and many more on your website. I Hope, It'll get in handy for your next project.