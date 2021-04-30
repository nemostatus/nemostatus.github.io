---
layout: post
title:      "experimenting with recursion"
date:       2021-04-29 10:27:49 -0400
permalink:  experimenting_with_recursion
---


The definition sitepoint.com gives recursion is "Recursion is a technique for iterating over an operation by having a function call itself repeatedly until it arrives at a result". So the last part of this description hints at that in the function which calls itself is going to use some form of conditional statement. As part of my study of different data structures and algorithms I decided to create a repo https://github.com/nemostatus/recursionPractice In this repo I created one function called countTo() that is nested in an outer function and uses a closure.The outer function holds a variable named count which is equal to 0. In the countTo function a while loop is used to see if count is less than 100 display the current count in a particular div, then increase the count by 1 then recall itself(recursion). Here's how the function looks altogether.

THIS IS AN EDIT MESSAGE: So I was thinking about my examples today and realized that the recursion here really does nothing because the while loop is already taking care of everything. Removing the recursion call still works, however if I were to change the while to an if statement I believe that it will only iterate once,but adding the recursive function call back in with a combo of the if statement makes it work with recursion. I'm going to keep changing my code. Ya I was right... So just ignore the code below as a matter of fact I''ll just add the more necessary recursion at the bottom of this blog

```
  
function outer(){
    count = 0
function countTo(){
    while(count<100){
    document.getElementById("countDisplay").innerHTML += `${count},`
    count++
    countTo() //the function is calling itself which checks condition, if it's true then increase count and recal itself until the condition is met
    }
}
countTo() ////calling itself uneccessarily because the while loop
}
```

Looking at this is confusing. Add another piece of code to see where the outer() function is even used is helpful. Here's the html where this function is used.

```
    <div id = "countDisplay">
        Start the counter :)
    </div>
    <button id= "counterBtn" onclick= "outer()">Counter</button>
```

Here's another example of recursion. Here's some html which shows an input of the number of divs you want to create. This is essentially the same idea as the first function, it's just a bit more dynamic by using form data.

```

    <form onsubmit="create(event)">
        <h1> Create x amount of divs</h1>
        <label>Number of divs created</label>
        <input type="number" id = "num">
        <button id = "createDivs">Create the number of divs selected</button>
    </form>

    <div id = "divDisplay">

    </div>
```

The event handler is the create function which is used when this form is submitted. In the function the value of "num" element is used in a while loop and the code in the while loop creates a div and shows which div was created. Here's the js for that.

```
function create(event){
    event.preventDefault()
    count =0
function inner(){
    
    let num = document.getElementById("num").value
    while(count < num){
    document.getElementById("divDisplay").innerHTML += `<div> Div number ${count+1}.</div>`
    count++
    inner() //calling itself uneccessarily beccause the while loop
}
}
inner()}
```

THE ABOVE CODE WORKS WITHOUT THE RECURSIVE CALL. 
However when using if statement the recursion is necessary. Like this. 

```
function outer(){
    count = 0
function countTo(){
    if(count<100){
    document.getElementById("countDisplay").innerHTML += `${count},`
    count++
     countTo() //needed in order to use recursion to continue this code instead of a while loop
    }
}
countTo() }
```


