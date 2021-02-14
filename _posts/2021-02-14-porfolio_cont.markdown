---
layout: post
title:      "Porfolio cont."
date:       2021-02-14 22:18:41 +0000
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


