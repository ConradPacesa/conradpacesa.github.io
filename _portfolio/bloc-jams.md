---
layout: post
title: BlocJams
thumbnail-path: "img/bloc-jams-2.PNG"
short-description: BlocJams is a music player app built with AngularJS and Firebase.

---

{:.center}
![]({{ site.baseurl }}/img/bloc-jams-3.PNG)

## Summary

BlocJams is a music player app and the first application I built as a developer. It is a part of the Bloc curriculum aimed at teaching students front-end web development.

## Explanation

BlocJams was Initially built with HTML, CSS and plain vanilla JavaScript. The first iteration of the application was intended to teach the basics front-end web development without the assistance of external libraries or frameworks. Next I was introduced to JavaScript libraries by refactoring my app and continuing to build features with jQuery. By using a library like jQuery I was able to significantly reduce the amount of code I needed to write and add additional features easily. Finally the application was rebuilt using AngularJS and in the process I learned how work with the AngularJS framework.

## Problem

After building the application in AngularJS, for extra credit, I was tasked with adding some additional features to the application on my own. The goal of the extra credit was to push me towards self-reliance, and so I was given a brief description of the feature to build with few additional resources. It was my job to determine the best way to implement each feature using resources found online. The most difficult features to implement in the application were user authentication as well as a search feature, allowing the user to search for any song, album or artist.

## Solution

Up until this point in my education with Bloc, I had been focused on front-end web development and did not yet possess the knowledge of back-end development needed to implement these features. I used Google's Firebase API along with AngularFire to provide the back-end services for BlocJams, which included authentication and database.

I decided to use Firebase to authenticate with a third party identity provider. I used GitHub as the identity provider to provide a fast and simple way for a user to authenticate and begin using the application. Once I was able to implement the authentication service, I had to modify the application to show/hide certain elements depending on the users authentication state. I also had to modify the router to restrict access to the application to authenticated users.

In order to create a search function, I had to create a Firebase database for all of my song and album data. All of the information had previously been stored in its own Angular service, from where it was accessed by other parts of the application. I also had to restructure the data in order to make querying the database possible for my search service. As a result of restructuring the data and moving it into a Firebase database, I also had to modify other parts of my application which accessed the data.

Once I had my database structured properly it was time to build the search service. My implementation of a search feature in this application is rather simplistic, it takes a string from a search bar and passes it into a Firebase database query. The query searches the database for the album object which contains an album, artist or song value matching the string. Upon success it returns the album object and then sends the user to the album page which matches the query result.

## Results

I was able to get authentication working with GitHub as the identity provider and pull user information from Firebase and display it in a user profile page. I was also able to restrict access to parts of the application to authorized users only. Given my limited time, I was able to create a working search feature, with some minimum functionality. A user is able to search for a song, album or artist, taking them to the album page containing their query. Given more time I would like to build a more robust search feature with the ability to display multiple results for the user to click on. Also, in its current implementation, the search feature requires the user to get the exact spelling in order to return a result. I would like to build some additional intelligence into the search feature, returning results even if the user misspells the word.

## Conclusion

This project was an excellent way for me to get started with front-end web development. It taught me how to use HTML, CSS and vanilla JS, in addition to libraries (jQuery), and my first framework (AngularJS). I also learned how to use third party API's to integrate external services into my application.
