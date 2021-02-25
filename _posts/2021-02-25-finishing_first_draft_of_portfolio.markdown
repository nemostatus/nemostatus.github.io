---
layout: post
title:      "Finishing first draft of portfolio"
date:       2021-02-25 05:15:26 +0000
permalink:  finishing_first_draft_of_portfolio
---


I've noticed that with each project I create, even if the outcome isn't ideal, there are bits and pieces of the application that I'm proud of and that can easily transfer over to other projects I'll create in the future. For instance in the first draft of my porfolio project, I decided to go with a portfolio guide named maxine the cat. I created a div that is responisble for holding an image i created(with an ms paint type program) and drew a cat face that would be used in an "animation". I created this function that alternates between 2 pictures that give the illusion that the cat is talking by switching the div image back and forth. I'll explain more later. Here's the function. 

```
  function animation(input){
     
    let maxine = document.getElementById("maxine")
let arr = input.split(' ')
let ratio = Math.round((arr.length+3)/2 )

if(count < ratio){
  count++
  if(count === ratio){
    count = 0
    return
    }
  else if( count/2%1===0){
      
    maxine.innerHTML = `<img src = "./sprites/cat1.png">`}
else{
 
    maxine.innerHTML = `<img src = "./sprites/cat2.png">`
  }
console.log(count)
}
setTimeout(()=>{animation(input)},500)
}
```

It's funny how in the moment my code makes total sense, now that I'm re reading it I'm relearning what my thought process was. So i'll start from the top. Input is the string that the determines how long the cat should talk(now that I'm re reading I should just use a counter somehow). The ratio variable is the string(now arr) length add 3(this synced up best ) If the count is less than ratio restart count else if count is even or odd make it one picture or the other.  As i said before this snippet of code was more of fixing as I go so It's hard to read right now. However I understand the logic that says if the count is increasing check if the count is an even or odd integer. If its even use 1 pic, if odd use the other pic, this creates a talking animation for the duration of the message.
