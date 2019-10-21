---
layout: post
title:      "ComponentDidUpdate in my react project"
date:       2019-10-21 01:40:09 +0000
permalink:  componentdidupdate_in_my_react_project
---

For my project, I was faced the challenge of loading data of a user that has already persisted to the database.  When a user enters a timestamp and submit it over to the database, the timestamp displays unless the user refreshes the page in which the timestamp stops displaying.  Also, the user may have entered other timestamps for other days so those times aren’t displaying either.  This is where ‘componentDidUpdate’ and ‘componentDidMount’ comes in handy. 

The ‘componentDidUpdate’ lifecycle method is used for after all of the individual time blocks are loaded to check to see if the user already have times saved in the database.  The ‘prevProps’ parameter is used to compare against the previous props with the current props upon every component update.  If they are different, then all of the user timestamps will display from the current props.  The ‘componentDidUpdate’ only handle when the props update.  

The code that displays all of the user’s timestamps only executes in componentDidUpdate method which doesn’t cover use cases for when a user logs off then logs back in and upon the component’s first render.  This is where componentDidMount comes in to cover that situation.  Therefore, the code is not only executed  on first render but all subsequent component re-renders while componentDidUpdate checks for changed props.  Using these two lifecycle methods together  has helped to form a reliable solution for the display of persisted user data.
