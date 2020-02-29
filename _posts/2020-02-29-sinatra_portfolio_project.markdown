---
layout: post
title:      "Sinatra Portfolio Project"
date:       2020-02-29 21:23:06 +0000
permalink:  sinatra_portfolio_project
---


For my second project, I built a Sinatra app. I wanted it to be something anyone might have a use for, so I went with making a budget app. The app allows the user to create new monthly expenses and input the costs for said expenses.

In order to make sure users can only view, edit, and destroy expenses associated with their own account, I used bcrypt with active-record to ensure users have secure passwords, as well as a unique email address associated with their accounts. Users first must sign up by entering their name, email address, and creating a password. The email address must not already be in use to avoid complications. Users can then use their unique email address and password to log in, where they are taken to their account's Home Page and shown a navigation bar at the top of the web page. The nav bar gives the user the option to create new expenses, view all their expenses, visit the home page, or log out.

**Getting Started**

To begin, I used the Corneal gem to create the the files and folders required for most of my project, as well as give it a simple layout. With that out of the way, it was time to create the schema and seed in some data. 

**MVC**

The app as a whole is fairly simple. For models, it only has users and expenses, the users have many expenses, and the expenses belong to users. 

In the Views folder, I created additional folders for expenses and users, as well as files for the general layout, a login view, a signup view, and the welcome view that a user will see upon visiting the home page. In the expenses folder, I have an index view for displaying all expenses created by the given user, a show page to view individual expenses, an edit view to actually edit them, and a new view to create new expenses. In the user folder I only have a show view, which represents the user's home page. 

As for controllers, I only have three - a users controller, an expenses controller, and the application controller. Thanks to Rack::MethodOverride I was able to run the application controller that inherits from ActiveRecord::Base and use the other two controllers that inherit from ApplicationController in order to also give them the full functionality of Active Record.

My application controller is where I enabled sessions in order to keep track of users, and registered Sinatra::Flash so users could see messages or errors upon giving an input to the system. The flash messages are particularly important to make sure users are aware they did something wrong and their input was not accepted. This controller is also where I put the majority of my helper methods.

The expenses controller is where I put everything that has anything to do with an expense's CRUD functionality. This controllers contains everything that lets users create, read, update, and destroy their expenses. 

The users controller is where I put everything regarding the user. This holds all of the code allowing users to create new accounts or login, as well as log out by clearing their session. This controller is also where we include the code to actually log the user in to their account, in which we find the given user by their params[:email], assigning them to a variable (@user in this case), then we authenticate the user by checking their password. If they are authenticated, we set 'session[:user_id] = @user.id' to log them in! If something goes wrong here, the user is redirected to the login page and given a flash message indicating that something went wrong.

**Stretch Goals**

Other than cleaning up the formatting (that I left alone after the Corneal gem helped me so much), my main stretch goal is to create a way for users to see the total of all of their monthly expenses. As of right now, I have each expense showing up with their cost as a string on the index page, in order to insert commas into costs that are more than $999.99. At some point in the future I would like to store the costs as they are created separately in order to add them up and display the grand total at the bottom of the index page so that a user may see how much they will have spent by the end of the month in order to appropriately manage their budget.

