---
layout: default
title: Learning new libraries
excerpt: I work on my aster chart generator, working with Node, PostgreSQL, and running my code on Heroku all for the first time.
---
Learning a new library can often be challenging, especially if it is not very well documented. When I first started with [D3](http://d3js.org/), I had no idea what I was doing. In order to get started, I tried to find a good tutorial for what I wanted to do, but it was to no avail. I finally managed to find someone who had done something like what I wanted to do in D3, so with permission, I borrowed his code. Borrowing code is a good way to help you dive into a new library, as it gives you a working backbone that you can modify, instead of dealing with the overwhelming process of figuring out the library from start to finish. Now that I have worked with this code a little bit, I think I understand how it works, but I am still a little bit uncertain about specific aspects (such as how to load data from an array of JSONs). It may be challenging enough to try out one library for the first time, but for this project, I also need to use [Nodejs](http://nodejs.org/), a platform for "easily building fast, scalable network applications." This is the first project where I have needed to use a server, so I also had to learn a platform for that (nodejs). My project is hosted on Heroku, which fortunately, has a brief tutorial on how to launch a node application on their site. I copied their sample code, and managed to get "Hello, world!" to be displayed at my URL. Since then, I have successfully modified the code so that it will load my aster chart at the URL, but the aster chart is still taking data from my .CSV file instead of a database. 

At this point, I started working on learning PostgreSQL, as it is a database service that I can host on Heroku without needing to give away a credit card (otherwise, I would still be using Mongodb). After some messing around and reading a lot of [W3 Schools](http://www.w3schools.com/), I managed to insert data into my database. Next, I had to learn the [pg](https://github.com/brianc/node-postgres) library so that I could run a query to the database from my server. In order to figure out pg, I once again looked at sample code, copied it, and edited it to fit my needs. Eventually, I got it such that I ran a query to the database to get all the data associated with a specific user, and could print the result. After this, the next step was to get the server and client to talk. I decided that the server should create the client, which would then send the server a user name. The user name would in turn be queried, and then the server would give the client the resulting data. Upon receiving data for its user, the client would create an aster chart using it. So far, I have started coding this using [socket.io](http://socket.io/), from which I borrowed a lot of their code for a simple chartroom, which I plan to implement my own version of at some point. 

This code is currently not working, but when it is, I will be able to see if I correctly modified my D3 code to work with an array of JSONs, and if it does, this project will almost be done. Learning libraries can be a very tedious thing. I have spent hours browsing through poorly documented APIs, trying to find the correct command to use in order to do what I want. Sometimes, I will be able to find the command, but without a sample implementation, I am not sure how to use it. Borrowing code from others can save yourself hours and headaches, but if it is a substantial amount of code, it is a good idea to ask them for permission first. After finishing this project, I plan on moving back to something more algorithm related, such as code that uses machine learning to tell the difference between images of capital As and capital Bs.