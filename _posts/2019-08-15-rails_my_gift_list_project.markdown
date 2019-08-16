---
layout: post
title:      "Rails "My Gift List" Project"
date:       2019-08-15 18:42:04 -0400
permalink:  rails_my_gift_list_project
---

The name of the rails project that I decided to do is a web application called “My Gift List”.  This web application allows users to create a gift list of their own and the user can purchase an item from another user’s gift list.  The purchase was simulated with a checkbox that was made available for a user to purchase from another user’s gift list.  When the user purchase (checkmark of an item), the item displays to the other receiver of that gifted item on their gift list. 

The process that I took started with planning out the models and their relationships.  The relationships that took place were one-to-many, many-to-one, and many-to-many relationships between a total of 5 models.  The 5 models were the following:

* category - A model for organizing all of the items.
* item - A model for a user to select and add to their gift list.
* list - A model for a user to create multiple lists and organize their gift items.
* list_item - The join model for a user to save and item and an associated list for a user. 
* user - The user model has many lists and items in which it was displayed through a join table called “list-items’.  

The purchaser attribute was added as an alias and foreign key to the join table ‘list_item’ to identify the user that purchased an item as a gift on another user’s gift list. 

My controllers was setup for:

* login in and login out a user
* creating a list and adding items to it
* removing and adding an item from a list
* updating the purchaser for a list_item
* displaying the lists under a user and indicating which user brought an item for them

The forms were setup with validations to make sure that there were unique users and the attributes for the users were not empty.  Nested resources were used for displaying items under categories and lists under users.  

The biggest take away from this project is understanding how the Rails framework is very implicit in nature to save development time.  Also, Rails can make Restful CRUD more easily available to be implemented through its use of routes and implicitly rendering the correct pages based on the controller methods. 





