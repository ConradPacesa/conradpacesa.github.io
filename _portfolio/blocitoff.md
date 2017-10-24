---
layout: post
title: Blocitoff
thumbnail-path: "img/blocitoff/blocitoff-landing.PNG"
short-description: Blocitoff is a self-destructing to-do list app.

---

{:.center}
![]({{ site.baseurl }}/img/blocitoff/blocitoff-landing.PNG)

## Summary

Blocitoff is a self-destructing to-do list, built as my capstone project at Bloc. I used Ruby on Rails 5 to build an API on for the back-end, as well as an Angular 4 app to consume the API for the front-end.

## Explanation

The goal of the capstone project at Bloc is to put everything I learned in my previous projects to work, as well as push myself to work with new technologies I wasn't familiar with. As part of this project, I wanted to learn new technologies as well as build a modern web app with the latest technologies. I used Ruby on Rails 5 to build a RESTful API on the for the back-end, along with [Docker](https://www.docker.com/) for containerization. I built an Angular 4 app, written in Typescript, which consumes the Ruby on Rails API that I built for the back-end.

## Problem

Blocitoff required user authentication and authorization in order to be able to create to-do list items. I had previously used [Devise](https://github.com/plataformatec/devise) for authentication, but would need to make some modifications in order to use it in an API. To-do items needed to expire in 7 days if they weren't completed, so I needed some automated check to delete incomplete items older than 7 days. My plan was to build my front-end and back-end as two separate apps, with the front-end hosted on [Firebase](https://firebase.google.com/) and the back-end hosted on [Heroku](https://www.heroku.com/), this design required me to enable cross origin resource sharing in my API.

In my previous Rails applications, I used cloud-based IDE's and virtual machines running a Linux OS, in order to be able to work with Rails on a Windows based machine. I wanted a more efficient way to develop and test my Rails app locally, rather than having to open up a virtual machine, or cloud based IDE in order to work.

## Solution

In order to implement authentication in my API, I decided to use a token-based authentication. I started with Devise for user registrations, and user sessions, as well as their email confirmation functionality. I used [Simple Token Authorization](https://github.com/gonzalo-bulnes/simple_token_authentication), which is a package that works with Devise to provide token-based authentication and authorization for API's. Simple Token Authorization generates a token for each user and requires the users email and token to be passed into the headers with each HTTP request.

In order to facilitate cross origin resource sharing between the front-end and back-end of my app, I included the [Rack CORS Middleware](https://github.com/cyu/rack-cors) in my Rails API. This middleware allows me permit specific domains and their methods for making HTTP requests.

I used Docker to containerize my application. This allowed me to edit my app in a text editor within Windows, and run/test the application inside a container on my machine. Using Docker allows me to specify the configuration inside a file, and Docker takes care of building up the application. This had significantly improved my workflow, making setting up a new Rails app fast and easy.

## Results

The resulting application was a fast single page app which I had built from end to end using Rails and Angular. I used the latest techniques in web development, by using a back-end API, written for a front-end app, built with a modern JavaScript framework. I learned to use several new tools in the process, including Docker to containerize my apps.

## Conclusion

Blocitoff taught me to build an app from start to finish. I also added a new tool to my tool belt with Docker. Docker has significantly improved my workflow and sped up my process of building new apps.

## Links

[Website](https://blocitoff-bed7d.firebaseapp.com)  &#124;  [Github Repository (front end)](https://github.com/ConradPacesa/blocitoff) &#124;  [Github Repository (back end)](https://github.com/ConradPacesa/blocitoff-api)

## Images

### Sign up page

![]({{ site.baseurl }}/img/blocitoff/blocitoff-sign-up.PNG)

### To-do list

![]({{ site.baseurl }}/img/blocitoff/blocitoff-todo.PNG)

### Complete items

![]({{ site.baseurl }}/img/blocitoff/blocitoff-complete.PNG)
