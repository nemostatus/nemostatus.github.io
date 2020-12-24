---
layout: post
title:      "JS calculator "
date:       2020-12-19 12:20:02 -0500
permalink:  js_calculator
---


So I've finally decided to attempt the classic js project of building a calculator. I usually like using my current knowledge to attempt a project so that's exactly what I did. As expected I ran into some issues that I will troubleshoot this upcoming week. My thought process was to have an input field, the number buttons, operator buttons(+,-,x,/) and the enter button.
I thought, clicking a button should add to the current value of the input field. So clicking 1 would make the input field be 1 and clicking 2 next would give the user 12. It worked I was able to do this for all the numbers. However where I ran into issues was attempting to pass operators as parameters. I didn't know that it wasn't possible. So now I have to start researching the correct way of approaching this project. So stay tuned if you want to follow my attempt this week.

Ok although I said I was going to look at some calculator projects for a reference my stubborn nature told me to try again one more time without other references. I lucked out and had a really good coding session. Everything clicked after I found the eval() javascript function. It evaluates operators and integers according to mathmatical rules(pemdas). So I really only had to think about the flow of the data. I had the main input box which would be filled out with each click of a button on the calculator. Here's what it looks like 

```
function information(number){
document.getElementById("main").value= document.getElementById("main").value + number
}
```

So this function takes in the number from each button like this 

```
onClick = "information(1)"
```

It uses the parameter and passes it into the value of the input field. So whatever the value is plus the new number.I also did this for operators and it works fine. Of course I also have a clear button with an click event that just sets the main input as an empty string(clearing). The calculation function takes the value of the input field uses the eval function and displays that data using a div, setting the outcome ad the innerHTML of that div. So it looks like this, 

```
function calc(){
    let el =document.getElementById("main")
    let display =document.getElementById("display")
display.innerHTML+= eval(el.value)
}
```

So here is what I explained above. It takes the value of the main input box evaluates the equation with eval() and displays that data in the display div. I added this calc function as an event listener when clicking the enter button. 


