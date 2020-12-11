---
title: "Cloud Function"
date: 2020-8-3 11:26:28 -0400
categories: Cloud Function
---


### What is Cloud Function? What makes it different from functions from programming language?
Cloud Function is a function that runs on cloud system.   
It is a function but quite different from functions that you learn from most programming languages such as python, c, java or else.   
For example, in python you declare function like below.

```python
def func(a):
    print("Hello", a)

func("World")
```

First, you need to declare function with or without parameter.   
Second, function must be called from same file or another file, but wherever it is, it needs to be in the same project.

But in cloud function, you don't need to declare functions in same project.   
And you don't need to call function directly.   
Instead, you will need to know concept of trigger.

### What is Trigger?
Trigger refers to situations that makes targets to do specific actions.   
For example, if you want to wake up at 7:30.   
What will you do?   
Of course you will set up alarm.   
After your phone turns alarm on, you will respond with waking up.   
Trigger is like that.   
If you want to delete every record of someone after user leaves, then you can set up the trigger for that.   
Once user leaves app(action: trigger), cloud function searches for the every record of that user in database and delete it(response).

### Using Trigger
On front-end side, you need to define trigger action.     
Trigger action can be creating, updating or deleting document.   

```dart
Firestore.instance
    .collection("Student")
    .document(sid)
    .setData({
        "id": sid
        "name": name
    });
 ```

Above code creates document in Student Collection.   
On backend-side, as a response to trigger action, you need to define what the function will do.

```typescript
export const addStudent = functions.firestore
  .document("Student/{sid}")
  .onCreate((snap, context) => {
      // Define what you will do with new student
      // ex) matching team professor
  }
```

Once student document is created which is trigger action, function automatically respond by matching team professor or any other actions you define.

### Why do we need to use cloud function?
Cloud Function is a very useful tool for saving costs of executing commands.   
What I mean by cost is time and app data.     
Even if you do not use cloud functions, you can implement all the functions you need.   
For example, you hava uploaded single story in a HUGIN Applicaiton.   
Since HUGIN application shares moment globally, user from all over the world comments on story, press like, comment like and share it with bookmarks.   
If you delete single story, you must delete all those records.   
Then the problem occurs when you do not use cloud function since deleting all the records takes quite a lot of time, and you only have to wait until all the documents get deleted. And since all those processes are running on app, your app data becomes higher.   
In small apps, that won't matter, but if you wish to launch global apps, you must take it into considerations.   
By using cloud function, you will save user's data as much as possible and increase efficiency.

### Disadvantage of clooud function
There are disadvantages of using cloud function.   
As I already explained, cloud function works as trigger rather than direct calling.   
It means it can be triggered when you do not expect to use it.   
So, you need to be a lot more careful when changing database when you cloud function.

### Setting up your environment for cloud function.
First, you need to set up environment for deploying cloud function.   
Install nodejs from https://nodejs.org/ko/download/.   
Then, install npm packages with npm install command.   
After installing npm packages, check if npm packages are updated to latest version.   
Enter those commands.   

```
npm install -g firebase-tools   
npm install firebase-functions@latest   
npm install firebase-admin@latest --save
```

After installing packages, you are ready to use cloud function.   
You can write your own code in index.ts(or index.js if you are using javascript).   
Study typescript &amp; nodejs by yourself.(This page does not teach those languages)

### After writing code
After setting up your own environment deploy your code with command below   

```
firebase deploy --only functions
```

Check your application if your code has been successfully deployed.

### Hugin Application Cloud Function Environment
#### Backend
* NodeJS
* NPM(NodeJS Package Management System)   
* Typescript(can use javascript instead)   
* Firebase Cloud Database System   
* Visual Studio Code as editor

#### Frontend
* Flutter Framework   
* Dart Language   
* Android Studio

### Studies for cloud function
* NodeJS
* Javascript or typescript
* Front-end(ex: Flutter)
* Database System(ex: Firebase -> To write query)

### To learn typscript syntax
* [reference](https://poiemaweb.com/typescript-introduction)

### To learn javascript syntax
* [reference1](https://poiemaweb.com/coding), [reference2](https://www.w3schools.com/js/default.asp)

### To learn nodejs
* [reference1](https://poiemaweb.com/nodejs-basics), [reference2](https://www.w3schools.com/nodejs/default.asp)