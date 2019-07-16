---
layout: post
title:      "Sinatra Project"
date:       2019-07-16 00:57:06 +0000
permalink:  sinatra_project
---


The simple yet useful sinatra application that I created is called ’Note Saver’.  It is exactly that. It creates, saves, delete,  display and edit notes.  The user can optionally save under a note under a category that the user also can create.  The notes and categories demonstrate restful and crud actions.

I started the project by determining my database tables and models.  The results of the tables are the following:
* 	Users
* 	Notes
* 	Categories

The ‘Notes’ table have the following columns:
* user_id
* category_id
* created_at
* updated_at
* title
* content

The ‘Categories’ table have the following columns:
* user_id
* name

The ‘Users’ table have the following columns:
* username
* email
* password

I created associations in the appropriate models:
*  Users have many notes and many categories.  
*  A note belong to a category and a user
*  Category has many notes and many users

After the associations were made, the restful crud routes were setup.  Sessions were used to determine each user’s unique resources of notes and categories.  Sessions were also made to logout or login a user which are saved in helper methods in the application controller separate from the other controllers (users, notes and categories).  This helps to be able to easily extend in future iterations of the application.

I learned that restful convention in an application is important to setup and maintain for ease of maintaining and extending the functionality.  Also, it helps when working on a team for another coder that is working on existing codebase to quickly identify the routes and crud of an application.  

