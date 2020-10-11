---
layout: post
title:      "Redux, the what, how, and why."
date:       2020-10-11 05:06:04 +0000
permalink:  redux_the_what_how_and_why
---


**THE WHAT** - So I decided to write my technical blog about redux. So what is it? Well the  wikipedia definition is 'Redux is an open-source JavaScript library for managing application state. It is most commonly used with libraries such as React or Angular for building user interfaces. Similar to Facebook's Flux architecture, it was created by Dan Abramov and Andrew Clark.'  In my own words I would describe it as a central hub that data gets dispatched to. A big box of data (the state). Using the useful function mapStateToProps a developer can literally map the current state and assign data to a components properties. Without Redux a developer must pass data in a more complex way, so basically redux is a library that solves this problem by providing a central state.


**THE HOW**-  **The store setup**- To begin, you must install and import alot of different dependencies. Both the createStore and applyMiddleware functions from redux  . The provider which allows us to wrap around our app component which  the store by assigning it to a variable of store to the createStore() function which will make the store available to all components nested in app. The provider component takes a prop of store and assigns it the store created with the createStore() function. Apply middleWare takes in an argument of the Thunk middleware which allows a developer to make fetch calls and dispatch an action to a reducer and return what the developer wants. So this creates the store, provides this store to the application and all components nested in it. 

**The reducer** - Essentially this is the backbone of redux, a reducer is function which takes takes the previous state, an action recieved from dispatch and depending on what 'type' of action determines how the state is affected. This is determined by a switch statement. It checks the action type, then returns whatever state the developer determines. 

**MapStateToProps**-Using connect a developer can connect state to the component using mapstatetoprops function, this will take data from state and allow a developer to assign it to the components property. This is to be defined or marked as NULL.

**MapDispatchToProps**- The second argument for connect mapDispatchToProps allows a developer to give actions to components. This is useful when used with componentDidMount. The component can now have access to an action and used in an event handler or when a component is mounted. 

**THE WHY** - So as stated in the beginning of this blog, redux is a library used to manage state for javascript frameworks. It's used in mainly larger applications. Without a state mangement library, larger scaled applications become increasingly more difficult to manage. It's so useful, I checked my redux dev tools and it looks like  Learn.co uses it!

