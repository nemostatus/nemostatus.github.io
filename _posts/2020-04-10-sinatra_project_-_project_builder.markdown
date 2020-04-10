---
layout: post
title:      "Sinatra project - 'project builder'"
date:       2020-04-10 11:01:09 +0000
permalink:  sinatra_project_-_project_builder
---

The project:   I've noticed a pattern when it's time to go into project mode. I usually have many project ideas and I don't know which why to go with and why. So ironically for this project I decided to build a web application that allows a student to create a project idea, read(or view) that project, update that project and if they find they don't want to follow that project anymore they can delete it. I decided to create a rating system that will allow the user to view which project may be the better option based on passion,  knowledge and time restraints. However I believe only the creator decides how great an idea becomes. I just hope my app can be helpful for anyone that may need it.

The process: 

RAKE AND DB:So this has been an eventful couple of weeks. Just when I thought my project was near completion I learned that there was so much more to be done. So I'll just start from the beginning. I started by creating my database.
I created 2 migrations with Rake. One to create a users table made up of with an email, username, and password_digest(used along with the bcrypt gem in order to salt the users password). I also created a projects table made up of name,project_type,comfort,passion,deadline,description, rating, and timestamps. I then typed rake db:migrate which created my database.

MODELS: I then created my 2 models which inherited from ActiveRecord::Base . The project model had 2 macros. One validates_prescence_of which validated that the user was inputing data into the new project form and also a second macro named belongs_to :user. The User model has 3 macros. The first being has_secure_password, the second validates_prescence of and validates_uniqueness_of. 

ROUTES: So throughout my app i used routes to create the flow. In the user controller i created routes which allowed a user to signup, login(create session), and logout. In my projects controller the user has the get /project/new form which allows a user to create a new project. This data gets passed to the post '/projects' route which then uses the data filled out in the form to create a new project set to an instance variable. The user_id is set to the session[user_id] which is established as the users id in the user controller. I also created a route,  get '/projects/:id'  which finds the project instance based on id. I created a conditional statement.

  if @project.user_id == current_user.id
	
	This is important because if a conditional isn't used to check if the current user has access to that particular id then any user could change any project instance or even delete it which is bad. However if the user does have access I redirected the user to the show page so they can read that instance.
	
	I also created a patch route which allows the user to find the project instance in db by id then update the values of the attributes as they like. I finally allowed the user to delete each instance and all instances. My favorite route is the index route which allows the user to view all of their projects which are ordered alphabetically and order from best to worst based on rating.
	
	Overall this project has taught me alot about how much work goes into building applications and how much testing is needed to see if the application works. I understand just how difficult ensuring site security can be and how certain gems like bcrypt can make that task alot easier.
