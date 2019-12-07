---
layout: post
title:      "Ghibli CLI Gem Project"
date:       2019-12-07 18:04:43 -0500
permalink:  ghibli_cli_gem_project
---


My first real coding project had me feeling overwhelmed, but despite a major move and working overtime, I managed to make it out alive with the help of the resources provided by Flatiron School and my instructor.

### What does it do?

My project extracts data from the Studio Ghibli API and displays it to the user. The user tells the program which film by Studio Ghibli they would like to view more about, and it pulls up the title, director, producer, release date, Rotten Tomato score, and a short description of the film. This is a must-have for any Studio Ghibli lovers out there who are looking for their next film to watch!

### The process

I built my project using Ruby. I knew what I needed to do for the project, but figuring out how to do it proved to be difficult. The hardest part for me was not having tests to guide the process. Because of this, I felt lost for much of the project until near the end when it all came together.

My project consists of three main classes that interact with each other - the CLI class that the user interacts with, the API class that extracts data from the API, and the Films class that creates instances of all Studio Ghibli Films and provides the information for them. Much of the setup for the project was fairly straightforward, as we were provided instructional videos which clearly outlined how to set up the environment and gemspec files, so I didn't have too much trouble with that.

The real trouble came when I started building out my classes. Creating the menu and loops for the interface was the easy part, and creating the Films class to instantiate and store objects into an array was nothing I hadn’t done before. Creating the API class, however, was completely new and scary to me. I didn’t know where to begin, and to make matters worse I had avoided using ‘Pry’ as much as possible up until this point so I was not as familiar with it as I should have been. I now understand how valuable ‘Pry’ is!

Once I got my API class extracting the data and storing it in variables, through much trial, error, and frustration, I was able to call on my Films class to use those variables as parameters. From here all I had to do was finish my CLI class. I only needed to iterate through my Films array, now filled with instances of films, to show the titles for the user to select and take in their input to give out information on the selected film!

### Conclusion

There are still some things I would like to tweak on my project in the future. Specifically I would like to go through and make the interface neater and more organized to make it easier to use. I may also spice up the README a bit in the future with a relevant image or two. Overall, I'm glad to finally be done with myfirst project and pleased with how it turned out, and I look forward to learning more.
