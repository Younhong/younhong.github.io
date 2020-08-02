---
title: "What is Cloud Function and how do you use it?"
date: 2020-8-3 11:26:28 -0400
categories: jekyll update
---

> Cloud Function is a function that runs on cloud system.   
Cloud function is a bit different from functions that you learn from most programming languages.   
First, mostly functions are declared in source code.   
Second, most functions needs to be called by other classes or functions to be activated.   
But in cloud function, you don't have to declare functions in dart code.   
And there is no calling functions.   
Then how do we use cloud functions?   It is more like a trigger rather than direct calling.   
If you do some kind of actions, then it might trigger to activate functions.   
For example, if you delete certain document from database, it can become trigger to activate certain type of functions.   

# Why do we need to use cloud function?
> Cloud Function is a very useful tool for saving costs of executing commands. Costs here refer to time and app data.   
Even if you do not use cloud functions, you can implement all the functions you need.   
For example, if you uploaded single story in a HUGIN Applicaiton.   
Since HUGIN application shares moment globally, user from all over the world comments on story, press like, comment like and share it with bookmarks.   
If you delete single story, you must delete all those records.   
Then the problem occurs when you do not use cloud function since deleting all the records takes quite a lot of time, and you only have to wait until all the documents get deleted. And since all those processes are running on app, your app data becomes higher.   
In small apps, that won't matter, but if you wish to launch global apps, you must take it into considerations.

# Disadvantage of clooud function
> There is disadvantage of using cloud function.   
As I already explained, cloud function works as trigger rather than direct calling.   
It means it can be triggered when you do not expect to use it.   
So, you need to be a lot more careful when changing database when you cloud function.

# Setting up your environment for cloud function.
> First, you need to set up environment for deploying cloud function.   
Install nodejs from https://nodejs.org/ko/download/.   
Then, install npm packages with npm install command.   
After installing npm packages, check if npm packages are updated to latest version.   
Enter those commands.   
> npm install -g firebase-tools   
npm install firebase-functions@latest   
npm install firebase-admin@latest --save

> After installing packages, you are ready to use cloud function.   
You can write your own code in index.ts(or index.js if you are using javascript).
Study typescript &amp; nodejs by yourself.(This page does not teach those languages)

# After writing code
> Then, deploy your functions with command below   
> firebase deploy --only functions

> Check your application if your code has been successfully deployed.

# Hugin Application Cloud Function Environment
## Backend
> NodeJS
NPM(NodeJS Package Management System)   
Typescript(can use javascript instead)   
Firebase Cloud Database System   
Visual Studio Code as editor

## Frontend
> Flutter Framework   
Dart Language   
Android Studio

# Studies for cloud function

1. NodeJS
2. Javascript
3. Front-end(ex: Flutter)
4. Database System(To write Query Statement)
5. Optionally study how to do setting for OS level.

# To learn typscript syntax
> Refer to [reference](https://poiemaweb.com/typescript-introduction)

# To learn javascript syntax
> Refer to [reference1](https://poiemaweb.com/coding), [reference2](https://www.w3schools.com/js/default.asp)

# To learn nodejs
> Refer to [reference1](https://poiemaweb.com/nodejs-basics), [reference2](https://www.w3schools.com/nodejs/default.asp)