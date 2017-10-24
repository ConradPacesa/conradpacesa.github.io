---
layout: post
title: Blocipedia
thumbnail-path: "img/blocipedia/blocipedia-landing.PNG"
short-description: Blocipedia is a wiki for with support for Markdown.

---

{:.center}
![]({{ site.baseurl }}/img/blocipedia/blocipedia-landing.PNG)

## Summary

Blocipedia is a wiki app, for creating articles which support Markdown format. Blocipedia was built with Ruby on Rails as part of the Bloc curriculum to further my understanding of Ruby on Rails and back-end web development.   

## Explanation

I built Blocipedia as the second project of the back-end portion of the Bloc curriculum. Similar to Bloccit, Blocipedia implemented authentication and authorization as part of a CRUD app. It also required additional functionality in the form of support for payments as well as support for Markdown syntax. Since this was my second project in the back-end portion of Bloc, I was expected to be far more self-sufficient.

## Problem

Blocipedia required users and authorization to be implemented. Three user types were required for this project: free, premium and admin. Free users are able to create and edit and delete public Wikis. Premium users have the same functionality as free users with the additional benefit of being able to create private wikis. Admin users are able to create, view edit and delete all wikis, public or private. An additional users feature required is the ability for users to confirm their email upon sign up, and reset their password if they forgot it.

## Solution

I used the [Devise](https://github.com/plataformatec/devise) Ruby gem to implement the user registrations feature. Devise provides a registrations and sessions controller for user sign up and sign in. Devise also includes support for password recovery and email confirmation. I used the Devise mailer along with [Sendgrid](https://devcenter.heroku.com/articles/sendgrid) for email confirmation and password rest functionality. I used [Pundit](https://github.com/elabs/pundit) to provide authorization functionality in my application, and restrict users abilities based on their role. In order to provide premium accounts, I needed some way to accept credit card payments securely. I used [Stripe](https://stripe.com/ca) for secure credit card transactions, allowing users to upgrade their account from free to paid.

To provide Markdown support in the app I used [Redcarpet](https://github.com/vmg/redcarpet), a Ruby library for processing Markdown to be displayed in the browser. As an additional feature, I wanted to provided users with a live preview of their formatted Markdown as they typed. For this, I used [Showdown](https://github.com/showdownjs/showdown), a JavaScript library for converting Markdown to HTML.

## Results

The resulting wiki app allows users to sign up, create, edit and delete wikis, upgrade their account to premium and include collaborators in their wikis. After implementing everything from scratch in Bloccit, I relied more heavily on third-party libraries in Blocipedia. This allowed me to speed up development of commonly implemented features, as well as build upon and customize those features for my application. I learned how to use common libraries like Devise and Stripe.

## Conclusion

Blocipedia further reinforced my knowledge of back-end development in addition to introducing me to several commonly used libraries to speed up development. Though these libraries sped development up quite a bit, they added an additional layer of complexity for debugging, with additional codebases and documentation to work through.

## Links

[Website](https://dry-wave-90624.herokuapp.com/)  &#124;  [Github Repository](https://github.com/ConradPacesa/blocipedia)

## Images

### Markdown previewer

![]({{ site.baseurl }}/img/blocipedia/blocipedia-markdown.PNG)

### Account upgrade

![]({{ site.baseurl }}/img/blocipedia/blocipedia-upgrade.PNG)

### Edit account

![]({{ site.baseurl }}/img/blocipedia/blocipedia-edit-account.PNG)
