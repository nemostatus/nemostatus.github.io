---
layout: post
title:      "Practice turned to fun project"
date:       2021-02-03 11:33:31 +0000
permalink:  practice_turned_to_fun_project
---


This past week I've signed up for leetcode, completed a few puzzles on there and created a repo to practice my click events and condtional statements and trying to brush up on my css skills and make my future apps look good. I decided to go forward with a fun project of interacting with a prompt and using click events and conditionals to make the outcome different for the user. I ended up building a pet care simulator. Where you can choose your pet, then name it, then care for it by clicking on the feed and water buttons.  This is just one of my many mini projects that are done for fun and to refresh on the basics. So here's how the code works. 

```
  <div id=selectPet>
        <h1>Which pet would you like to have?</h1>
        <button id = "bird" onclick = "birdPic()">Bird</button>
        <button id = "dog" onclick = "dogPic()">Dog</button>
        <button id = "cat" onclick = "catPic()">Cat</button>
    </div>
```

The code snippet above is just three buttons that have click events attached. Here's how the event works

```
function dogPic(){
    document.getElementById("virtualPet").innerHTML =
    `<h1>Hey there, here is your pet, what will you name it?</h1>
    <div id = "title"> </div>
    <div id= "pic"><img src= "https://images.pexels.com/photos/2820134/pexels-photo-2820134.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500" width="200"></div>
    <form onSubmit ="giveName(event)" id="form">
        <label>Name:</label>
        <input id="name" type = "text">
        <input type ="submit">
    </form>`
    document.getElementById("feedSys").innerHTML =`
    <button id="feed"  onclick ="feedCat()">Feed</button>
    <button id="water" onclick = "waterCat()">Give Water</button>
    <div id = "watered"></div>
    <div id = "fed"></div>`
     feedCount= 0
      waterCount = 0
}
```

This functions does a few things. It first sets the pet picture to a dog picture, reveals a form that will take in the input and assign the pet's name once submitted. It also will display a couple of buttons that have a feed and water button. These click events just increase a variable then use a condtional to compare how many times the pet has been fed, if fed too much the virtual pet will be "gone". Here's the code for that. 

```
function feedCat(){
    feedCount++
    if(feedCount ===1){
        document.getElementById("fed").innerHTML = `<h3>Thank you for feeding me :)<h3>`
    }
    else if(feedCount ===2){
        document.getElementById("fed").innerHTML = `<h3>Thank you I'm getting quite full now :/<h3>`
    }
    else if(feedCount ===3){
        document.getElementById("fed").innerHTML = `<h3>I'm like a fish, if you keep feeding me, I will eat, be careful :(<h3>`
    }
    else if(feedCount === 4){
        document.getElementById("pic").innerHTML = `<img src=  "https://cdn.pixabay.com/photo/2017/02/18/18/09/skull-and-crossbones-2077840_960_720.jpg" width="200">`
        document.getElementById("title").innerHTML = `<h2>RIP<h2>`
        document.getElementById("fed").innerHTML = `<h1>I told you.<h1>
       `
        document.getElementById("watered").remove()
        document.getElementById("feed").remove()
        document.getElementById("water").remove()
        document.getElementById("form").remove()
    }
}
```



