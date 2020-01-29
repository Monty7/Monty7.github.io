---
layout: post
title:      "prevState in React conundrum"
date:       2020-01-29 17:06:40 +0000
permalink:  prevstate_in_react_conundrum
---


I was introduced to ‘prevState’, when I first started learning React. I also learned about working with state and how to use ’setState’ to change state.  I knew how to use ‘prevState’ but never understood why I had to use it with a function.   I mostly got confused with understanding prevState’s value.  Of course it is the previous state but what does that mean exactly.  I searched through Google to get different explanations and I was still confused because of the choice of words that they used to explain the current state such as ‘this.state.count’ as the current state.  Hmm, if current state is ‘this.state.count’ then what is prevState?  I thought ‘prevState’ represented the current state. If so, why not label the parameter ‘currentState’ instead of ‘prevState’.  So, I decided to try to put two and two together to understand what the value of prevState represent in a way that I understood it and verifying it through console logs.   Lets  go with the following example:
```
increase() {
        this.setState(prevState => {
            return {
                count: prevState.count + 1
            }
        })
    }
	```
We simply want to increase the count by one. Let’s imagine that ‘this.state.count’ value in a class component is rendered onto the screen with a button to change the state with the ‘increase’ method. I truly discovered that yes, ‘prevState’ represents the current state but before the state will change which is in the context of the ’setState’ method.  We may have something like this for the state:
```
state = {
	count: 0
}
```
prevState’s value is currently 0.  setState will return ‘count: prevState.count + 1’ to change the this.state.count value. 

One may ask, why use ‘prevState’ at all and code the changed state like the following:
```
this.setState({count: count + 1})
```
The reason to not do this is because of the asynchronous behavior of the setState method in React.  Coding without using the ‘prevState’ in a function may render inaccurate results especially if you are changing more than one state.  See the React documentation for more explanation on this asynchronous behavior with [setState batch processing](https://reactjs.org/docs/state-and-lifecycle.html).

All in all, the take away and confirmation that I came to is that something such as ‘this.state.count’ is essentially the value of ’prevState’ BEFORE it has been changed within the context of setState and also can be used in other methods such as lifecycle method ‘componentDidUpdate’ in which one could pass two parameters.  The first parameter is ‘prevProps’ and the second is ‘prevState’.  The concept of using ‘prevState’ to represent the current state before it is changed applies here as well.  
