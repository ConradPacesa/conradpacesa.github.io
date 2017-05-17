---
layout: post
title: BlocChat
thumbnail-path: "img/bloc-chat-2.PNG"
short-description: BlocChat is a messaging application built with AngularJS and Firebase.

---

{:.center}
![]({{ site.baseurl }}/img/bloc-chat-2.PNG)

## Summary

BlocChat is a web-based chat application and the second project I completed as a part of the Bloc curriculum. Like BlocJams, BlocChat uses AngularJS along with Firebase for the back-end.

## Explanation

I was given little guidance when building BlocChat and instead was able to leverage my previous experience with BlocJams and online resources. Because I had previous experience working with AngularJS and Firebase, I was able to build BlocChat fairly quickly.

## Problem

BlocChat is a chat-room based application, with multiple different chat-rooms that users can click on and post messages in. BlocChat required a real-time database to store and update messages for each chat room, as well as the ability for users to set their username and create new rooms. For extra credit, I was tasked with creating an authentication service as well as private chat rooms for admins.

## Solution

In order create chat-rooms for the application, I used Firebase's database to store my chat-rooms. I also included UI Bootstrap in my application to create the pop-up modal, where the user could create and name a new chat-room. The new chat-room created by the user is added to the Firebase database. I also leveraged the UI Bootstrap modal as the method for the user to set their username, which would appear with their messages in the chat rooms. I used Angular's $cookies service to store and track their username throughout the app.  

Once chat-rooms were created, I needed a way to display messages that are relevant to each chat room. I did this by associating each message with a unique chat-room id, so that when the user selects a chat-room, my app would query the Firebase database and filter for all messages that matched the chat-room id. The filtered messages would then be shown to the user after they select a chat room.

My implementation of the authentication service was similar to BlocJams. Rather than having the user manually set a username when prompted by the modal, they were prompted to sign in with GitHub. The application would then set the users username from their GitHub username. I added an admin field to the user and rooms in the Firebase database in order to distinguish between admin and non-admin users and rooms. I added some extra login in the main controller to check if an admin is attempting to access the admin room before selecting the room, only allowing admin type users to access the admin rooms.      

## Results

Building BlocChat went much more smoothly than building BlocJams, mainly because I was already familiar with AngularJS and Firebase API's. I did have to learn some new API's (UI Bootstrap) and how to use new Angular services. The application performed very well, instantly displaying messages sent by the user thanks to Firebase's live database. This exercise proved to be great way to test how much I had learned from my previous application and how self-sufficient I had become as a programmer.   

## Conclusion

BlocChat further reinforced what I had learned in BlocJams in terms of Firebase and AngularJS. It went further to teach me self-sufficiency in building by own application and using documentation to learn how to use external API's and framework features.
