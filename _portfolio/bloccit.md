---
layout: post
title: Bloccit
thumbnail-path: "img/bloccit/bloccit-landing.PNG"
short-description: Bloccit is an online forum, similar to Reddit.

---

{:.center}
![]({{ site.baseurl }}/img/bloccit/bloccit-landing.PNG)

## Summary

Bloccit is an online forum for discussing topics, sharing links and voting on content. It is built to offer basic functionality offered in Reddit, including topics, posts and comments, as well as voting and user sign-up.

## Explanation

I built Bloccit as part of the back-end curriculum at Bloc. The goal of this project is to teach the fundamentals of back-end web development by building a simple CRUD application. I used Ruby on Rails along with PostgreSQL for the database. The goal of this project was to gain an understanding of Ruby on Rails and implement commonly used functionality in Rails, including authentication, authorization and CRUD. I was also introduced to test driven development with Ruby's Rspec testing tool.

## Problem

Bloccit required a number of features to be implemented in order to begin to resemble Reddit. Authentication was required to allow users to sign up and begin posting. An authorization feature was required to ensure users were signed in before they could post. Topics, posts, comments and voting were required for the app's primary functionality. As added functionality, I gave users the ability to add a post to their favourites, which would send them an email notification when there was a new comment on the post.  

## Solution

One of the first features that I implemented was user authentication. To set up authentication, I built a users model, along with a users controller for signing up and a sessions controller for signing in. I used [Gravatar](https://en.gravatar.com/) as the user avatar and included a public user profile page, displaying the user's name, Gravatar and most recent posts and comments.

In order to implement authorization, I needed three types of users, admin, member and guest. An admin is able to create/edit/delete any topic, post or comment. A member user could comment, create new posts and vote, but only edit/delete their own posts/comments. And finally, a guest which is someone who was not signed in, could only view any topic or post but is unable to post/comment/vote. In order to create this functionality, I first added a role field to the user model, with the possible options being member or admin. In the topics, posts, comments and voting controllers, I added a check to ensure that a user had the correct permissions before they could perform any CRUD actions. I also added a check inside the view, which would hide any buttons that a user was not authorized to use.

In order to implement the favourites feature, I built a favourites model, which belongs to the user and post model, and a favourites controller, with create and delete methods. In order to send emails to users, I used Rails' ActionMailer functionality, along with [Sendgrid](https://devcenter.heroku.com/articles/sendgrid) hosted on Heroku.

## Results

The results of this project was a site with many of the basic features found in Reddit. Bloccit taught me the fundamentals of back-end web development in building a basic CRUD app with user authentication. I was introduced to a number of key topics in development, including the MVC architecture, testing, ORM's, CRUD, databases and mailers.    

## Conclusion

Bloccit was the first application I built with Ruby on Rails. I taught me to implement some commonly used functionality in Rails as well as the fundamentals of back-end development.

## Links

[Website](https://bloccit-cp.herokuapp.com/)  &#124;  [Github Repository](https://github.com/ConradPacesa/bloccit)

## Images

### Topics view

![]({{ site.baseurl }}/img/bloccit/bloccit-topics.PNG)

### Topic view

![]({{ site.baseurl }}/img/bloccit/bloccit-topic-view.PNG)

### Post view

![]({{ site.baseurl }}/img/bloccit/bloccit-post-view.PNG)

### New post

![]({{ site.baseurl }}/img/bloccit/bloccit-post.PNG)

### Profile view

![]({{ site.baseurl }}/img/bloccit/bloccit-profile.PNG)
