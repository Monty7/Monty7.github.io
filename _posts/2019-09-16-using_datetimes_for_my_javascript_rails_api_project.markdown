---
layout: post
title:      "Using DateTimes for my JavaScript Rails API project"
date:       2019-09-17 01:05:24 +0000
permalink:  using_datetimes_for_my_javascript_rails_api_project
---


I decided to work with dates and time objects in Ruby and Javascript while creating an app in which a user can calculate their time in a span of a month when they have entered a clock in and a clock out time.  Date and Times can be tricky to work with, especially if the date  or time format is automatically formulated.  This issue has made me find creative ways to utilize the date and time from Ruby and JavaScript when the format is not that friendly to work with to get the results necessary.  I had my work around the limitations to accomplish the results I needed.  

For instance, my input type in the HTML were of time type.  Once the ‘clock in’ and ‘clock out’ times go through the params in the create method of my rails controller, I reconstructed the time for the database to accept it in the dateTime format:
```
		   date = "#{params[:date_of_times]}"
                    clock_in = "#{params[:clock_in]} #{date}" #constructing dateTime
                    clock_out = "#{params[:clock_out]} #{date}" #constructing dateTime
                    times = user.user_times.create(clock_in: clock_in, clock_out: clock_out, date_of_times: params[:date_of_times])
```

To retrieve the ‘clock in’ and ‘clock out’ times from the database, I had to grab the date, and times only.  To do that, I used Javascript’s sliced method to get only the characters that reflected the date and times:
```
data.user_times.clock_in.slice(11, 16) # Used for times
data.user_times.clock_out.slice(11, 16) # Used for times 
```

Once I was able to slice the times from the database response, I looped over every date container in the HTML to assign the time values.  

The trickiest part of working with times were calculating the times.  I had to make sure that the times were in a certain format by working with Javascript’s Date object.  I thought that `Date.parse()` would obviously be the clear choice, but to only realize that parse refers to the date format which was very limited and didn’t have the options for me to parse the time only.  Therefore I had to use a combination of splicing the data times from the database and calculating using ``` new Date(0, 0, 0, clockIn[0], clockout[1], 0); ```  The first three zeros represents the dates in which I am disregarding since I only want to calculate based on time.  The ‘clockin[0]’ represents the hour from the database and ‘clocking[1] represents the minutes from the database.  When subtracting the ‘clock in’ from the ‘clock out’ using the ‘new Date’, the results were in seconds in which was converted to hours and minutes to be displayed for total of hours.  

I learned that the Javascript Date object might have it’s rough quirks but once there is an understanding of it’s limitations, with a good work-around, the Date object can be used to your advantage. 

