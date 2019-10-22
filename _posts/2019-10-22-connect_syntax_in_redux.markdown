---
layout: post
title:      "Connect Syntax in Redux"
date:       2019-10-22 19:38:29 +0000
permalink:  connect_syntax_in_redux
---

If you have ever wondered and have asked yourself while learning Redux what is the connect function syntax doing? Well you  are not alone for I have asked the same thing. I ran into an explanation while watching a Redux Udemy video by Stephen Grider and was happy to have finally see the mystery behind the connect function syntax. The connect function connects to the provider Redux store by returning a function.  Here is a very simple example of a structure that is a function returning a function that’s similar to Redux’s connect function:
```
function connect(){
	return function(){
		return “HELLO PROVIDER!”
	}
}
```
The parent function labeled ‘connect’ returns the function that is also a function but it doesn’t execute that function when calling the ‘connect’ function.  The results would look something like this when executing connect():
```
function() {
	return “HELLO PROVIDER!”
	}
```
One may not necessarily want this as a result but want to return “HELLO PROVIDER!” instead.  There are a couple of ways to execute a function returning a function.  One way is to create a variable and assign it to the executed function like so:
```
let parentFunc = connect();
```
Then call the variable with the parenthesis to invoke the function:
```
parentFunc()
```
The results will return “HELLO PROVIDER!”  

In redux, another syntax that will also return “HELLO PROVIDER!” in the connect function is to simply add another parenthesis like so:
```
connect()()
```
This is a much simpler way than needing to assign it to a variable first to return the inner function’s return statement.  
