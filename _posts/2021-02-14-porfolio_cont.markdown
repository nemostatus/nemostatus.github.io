---
layout: post
title:      "Porfolio cont."
date:       2021-02-14 17:18:42 -0500
permalink:  porfolio_cont
---


So now that I have the dynamic message box built as well as the dropdown nav list that responds with text to speech, I decided to build out the main part of the portfolio. The list of projects I've built as well as the github links to those projects. I might need to rebuild this if I can't figure it out. I'm building it to where there's one main div listing all of the projects. Clicking on a specific project will flip the div and reveal the information of the project on the back of the div. I figured out how to do this when hovering over the div but still need to make this event a click event and have the event change the info on the back of the div dynamically. Here's the beginning of the div along with some css that flips the div when hovered. 

THE FRONT OF THE DIV

```
 <div id="projectDiv" class="projectDiv">
<h1><u>Projects</u></h1>

<div id = "sinatra" class = "turn">Sinatra</div>
<div id = "ruby" class = "turn">Ruby on Rails </div>
<div id = "js" class = "turn">Javascript</div>
<div id = "react" class = "turn">React</div>


    </div>
```

HOVER CSS

```
  .card:hover{
          transform: rotateY(180deg);
        }
```

As mentioned before this rotates the div but only when hovered over. I need to make this a click event.
So to keep it simple for now, I decided to follow the simple click event for each project. I created a function that takes in the event, gets the id attributed from the event,target and uses a switch case statement to determine the innerhtml of the card. Here's what it looks like in code

```
 function check(event){
     let card = document.getElementById("card")
    

     let id= event.target.getAttribute('id')
     switch(id){
       case "sinatra":
         card.innerHTML = `this is my sinatra app description<br>
         <button id ="restart" onclick = "restart()"> Projects </button>`
         speech("sinatra")
         break;
         case "ruby":
          card.innerHTML = `this is my ruby app description <br>
          <button id ="restart" onclick = "restart()"> Projects </button>`
          speech("ruby")
          break;
          case "js":
            card.innerHTML = `this is my js app description <br>
            <button id ="restart" onclick = "restart()"> Projects </button>`
            speech("javascript")
            break;
            case "react":
              card.innerHTML = `this is my react app description <br>
              <button id ="restart" onclick = "restart()"> Projects </button>`
              speech("react")
              break;
     }}

```

The restart function  set to handle the click event just resets the card html. This is what it looks like 

```
   function restart(){
      let card = document.getElementById("card")
      card.innerHTML = `<div id="projectFrontDiv" class="projectFrontDiv">
      <h1><u>Projects</u></h1>
      <div id="sinatra" class="turn" onclick = "check(event)">Sinatra</div>
      <div id="ruby" class="turn" onclick = "check(event)">Ruby on Rails</div>
      <div id="js" class="turn" onclick = "check(event)">Javascript</div>
      <div id="react" class="turn" onclick = "check(event)">React</div>
    </div>`
    }
```

Now what's left to do is create an animation for maxine that will "talk". This is going to be challenging but very rewarding. I need to learn how to create the sprite sheet, animate the talking motion when she talks and stop when she stops talking. It may fail and I'll need to change something about the animation but this is going to be the most exciting part of building out my portfolio.

