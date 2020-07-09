---
layout: post
title:      "MY JS-RAILS PROJECT JOURNEY"
date:       2020-07-09 12:23:29 -0400
permalink:  my_js-rails_project_journey
---



### Before I actually start my project:

After reading the project requirements, the very first thing I do is go through most of the demo projects and get some ideas about the kinds of applications we can build. Then I make a list of the possible topics that I see as possibilities for an application. I write out models, attributes and relationships between the models. I compare them and think about which idea best meets the project requirements. During this process I also ask for the opinions of my fellow students and cohort lead about which of the ideas is a better option in their opinion. It helps me to decide how to narrow down the list of possibilities. After that I design a layout template on figma or photoshop and once I've created my roadmap, I get started on building the project.

### Why I chose this topic:

The name that I chose for my JavaScript and Rails project's is "POSITIVE QUOTES". I chose this topic because of the current climate in the world, let alone our own country. I feel as though there is a lot of negativity spiraling around and we really need to try to stay positive and strong. 

### User Experience: 

I built out a seeds file in my rails api backend with a few categories that have multiple quotes each to be readily available for the user to draw inspiration from. Upon clicking a category it displays all of the respective quotes. After a user picks the category they like and has read the quotes, if they're feeling inspired they can create their own quotes as well. Users don't need an account to use this application, so it's simple, easy and safe to use.

### During project:

The first thing I did was set up a frontend and backend repository where unknowingly I end up with an embedded repo. At first I thought that's how it was supposed to be because a lot of my fellow students had their repositories set up the same way and I started working on my project. About 25 commits in, out of curiosity I asked my cohort lead if an embedded repo is normal To which she replied, "it's not." That was my first  obstacle and it ended up being a very involved task to resolve that issue. However I fixed it with the help of a cohort lead and another student who went through the same issue. However I lost all my commit history in the process and started again with zero commits. On the positive side though, all of the code I had written was able to be saved. I was worried about not having enough commits because of that issue but I was still able to make more than 50 commits before being finished with the project. To anyone who is setting up Rails and JavaScript project repository here is a resource that you can utilize so that you, hopefully, won't face same issue:

[https://www.youtube.com/watch?v=pfLN73eELNw&feature=youtu.be
](http://)
Another struggle I went through was separation of concerns. That was actually a surprising factor for me because until the project requirement lesson, I did not see anywhere in the curriculum where we did separation of concerns in a lab or lesson in the JavaScript module. All JavaScript code we were writing was in one file, the index.js file, and I thought that's how the project was to be structured as well.
After going through some video resources regarding separation of concerns, finally I learned how it works and how to structure the code. Separation of concerns itself is not a new concept to me because in my Rails project, and in line with the Rails way, separation of concerns is a must follow convention but when it comes to JavaScript it was a bit of a struggle. So I have an Adapter folder where I have a file called api_service.js, which takes care of all of the  fetch requests to the backend Rails API. Then I have component folder where I have category.js and quote.js which represent the two models from the backend: these two JavaScript files set up the JavaScript classes and create instances of that class. I also have an index.js file where I have functions which I am calling in DOMContendLoaded event listener attached to the document. All the css styling lives inside a style.css file and finally in my index.html file I have an html template which will be displayed in the browser. I connected all other JavaScript files and folders here through script tags and made sure index.js is the last tag since the index.js file coordinates code from all of the other JavaScript files.

### The Technical and Requirements Checklist:

[x] The application must be an HTML, CSS, and JavaScript frontend with a Rails API backend. All interactions between the client and the server must be handled asynchronously (AJAX) and use JSON as the communication format.
[x] The JavaScript application must use Object Oriented JavaScript (classes) to encapsulate related data  and behavior.
[x] The domain model served by the Rails backend must include a resource with at least one has_many relationship. For example, if you were building an Instagram clone, you might display a list of photos with associated comments.
[x] The backend and frontend must collaborate to demonstrate Client-Server Communication. Your application should have at least 3 AJAX calls, covering at least 2 of Create, Read, Update, and Delete (CRUD). Your client-side JavaScript code must use fetch with the appropriate HTTP verb, and your Rails API should use RESTful conventions.

### Overall about this project:

JavaScript is definitely not as easy to use compared to other languages, for me, but it was really fun to learn all the new things I could do with JavaScript. Building my own api and using fetch requests to it from the frontend using JSON, manipulating the Document Object Model (DOM) and using object oriented JavaScript was great fun. Going through backend and frontend together was a bit of a struggle but i am really happy that now I can build both frontend and backend applications and have them communicate with each other. This is what it means to be a full stack developer - I'm on my way!

Thank you and see you in next blog..


