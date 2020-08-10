---
title: "Secure Your JavaScript Files"
date: 2020-08-10T06:00:00+05:30
Description: ""
Tags: "web development","Javascript","Zero To Hero","Crash Course"
Categories: []
DisableComments: false
---

## Introduction

Let's be real, with firebase and all these knowledge, we should protect our JS files, They can't be wide open for a smart ass to get there and mess around with the code or so, Yeah I know the firebase provides a much secure system in the security side but the code has to be secure too! To day let's discuss on that, let's explore what we can do to Protect our JS files.

## My Steps

I Usually use 5 steps of protection in my personal projects,

1. Trust No one!
2. Minification and Obfuscation
3. Lint your code
4. Strict mode
5. Brake-down The code
6. Simple and elegant

## First Step, Trust No one

One super important technique to avoid JavaScript vulnerabilities is to have a good validation architecture in place.

May it be the data coming from users. Or may it be the data coming from your servers. Always validate the data before it enters the application.

In the case of user input forms- validate each and every field. Sql injections and XSS are dramatically increasing these days. So, make sure you validate each and every field on the form before you save the data to the server.

Even when the data is saved on the servers, do not trust them. Always sanitize the data coming from the servers.

If yours is a node based application have a look at validator.js. It’s something you should start using right away.

## Minification and Obfuscation

Another way of securing your data is minifying and obfuscating the code. What minification is it simply makes the whole code in to a single line and remove extra white-spaces. We discussed about this techniques in the past and I'm not explaining them in detail again. you can visit it [HERE](/post/web-code-minification/).

Then Obfuscation. As the Wikipedia says Obfuscation is ❝In software development, obfuscation is the deliberate act of creating source or machine code that is difficult for humans to understand. Like obfuscation in natural language, it may use needlessly roundabout expressions to compose statements. Programmers may deliberately obfuscate code to conceal its purpose (security through obscurity) or its logic or implicit values embedded in it, primarily, in order to prevent tampering, deter reverse engineering, or even to create a puzzle or recreational challenge for someone reading the source code. This can be done manually or by using an automated tool, the latter being the preferred technique in industry.❞

In simple words, It makes the code nearly impossible to read and modify. A De-obfuscator can return the code back to the original form, but not simple as it says, so only highly skilled penetrators would be able to kick something like that.

Tools for minification

* https://www.willpeavy.com/tools/minifier/
* https://jscompress.com/
* http://javascript-minifier.com/
* http://refresh-sf.com/

Tools for obfuscation

* https://obfuscator.io/
* https://javascriptobfuscator.com/
* https://github.com/mishoo/UglifyJS

## Lint your code

This is a process which you can analyze and scan for suspicious code snippets on your JS files. It's much needed when you're working with a dynamic code base. Otherwise no one can hack into a stone. So if you're using or working with any kind of dynamic code base, don't forget to check out these tools

* http://eslint.org/
* http://jshint.com/
* http://www.jslint.com/

## Use Strict mode

Modern JS has a mode called Strict mode. Where the JS files get to a highly strict mode as it says, only using a simple code. This would prevent others from injecting codes into the codebase and it could save you from 90% of the attacks you can encounter with. We discussed this with the JS fundamental course which you can visit [HERE](/post/js-for-modern-web-development/).

## Brake-Down the code

This is something I personally use and this could make reverse engineering very confusing. I usually brake-down my codes in various parts and put different parts in like 5 or 6 js files to only be combined when it's running. I Even brake down strings and all of the variables, so if someone going to reverse engineer my codes, They would be in serious troubles on figuring out which are which.

## Simple and elegant

Always use simple codes, This can make your code easy for you to understand and prevent mistakes which could occur due to human nature of forgetting what we're doing or so. And here, this is against my previous point? No absolutely not! Being Simple is something and Being Advanced or messy is something else, You can be simple and messy, what I prefer in codes.

## Conclusion

This could be a small post considering my previous attempts. But this is something you must do before publishing your codes. for more security based information, join our whatsapp and telegram groups using the links above. and if you're wandering I never used these in my source codes, dumb-ass you! If I did so, How could you understand the code!
