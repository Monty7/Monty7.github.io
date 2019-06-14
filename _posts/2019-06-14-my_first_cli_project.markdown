---
layout: post
title:      "My first CLI project"
date:       2019-06-14 18:26:38 +0000
permalink:  my_first_cli_project
---


The functionality of my project is about displaying recipes for a user to be able to save recipes into their own recipe box. The user would be able to view the link to the recipe for viewing the ingredients and directions on how to prepare the recipe.  

My process was to first understand on a high level step-by-step what my application should do as a guide.  I accomplished that by writing out the following steps:

1. Welcome the user
2. Display a list of recipes for user to choose
3. The user choose a recipe
4. The user adds that chosen recipe to his/her recipe box collection
5. The user selects a recipe from their own recipe box collection to view details of how to prepare the recipe.
6. Provide the user to be able to have a choice to exit, go back to list all recipes, or view their recipe box.

After I wrote out the basic functionality of the CLI application, I began stubbing out my classes and methods.  I started out creating a class for the scraper and then the CLI class for the application to run.  When I started to flesh out my methods inside my classes, I only created based on only getting the application to work.  I did run into some issues with my object relationships but I refactored my methods as deemed necessary.  For instance, as I was building my methods, I was creating methods that were user interactive, therefore, I moved those methods over to my CLI class since that is where user interaction will occur.  I also realized that I needed another class for creating and saving new recipes for my CLI to be able to efficiently pull from.  Once I made those changes, it assisted my code to interact with my Scraper and CLI classes.  

Once I felt comfortable with my CLI functionality, I went back to check for code situations that I could refactor to clean up indentation to include replacing a group of code in which I could DRY up with using one method.  I plan to iterate the CLI to add more functionality for the user to be able to list the details inside the application instead of opening a link to the page where they can view the details.  

This project was a great learning experience in ways that helped me to solidify concepts.  It also gave me an opportunity to tie in concepts that I learned thus far and how it behaves live which helped deepened my understanding of how to write code.
