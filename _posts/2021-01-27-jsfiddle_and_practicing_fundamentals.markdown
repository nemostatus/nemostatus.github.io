---
layout: post
title:      "JSFiddle and practicing fundamentals"
date:       2021-01-28 01:44:01 +0000
permalink:  jsfiddle_and_practicing_fundamentals
---

Although my github doesn't look like I'm coding too much. I have been active in many other projects and practicing with different coding resources such as JSFiddle, Codewars, Game dev engines, and coding apps. So in order to make my github profile reflect how active I really am I will begin commiting to github everyday and make this a 2021 goal After all perception is reality. 

This week I decided to interact with the breaking bad API to practice some fundamentals in JSFiddle

* Async calls
* USing higher order functions
* iteration / loop
* interacting with object data
* ciick events/listeners to display the data received from the async call

Here's the html code 

```
<button id= "get" onClick="retrieve()">
get data
</button>
<div id = "display">

</div>
```

It's just a button with a handler(found in the js below) and a div used to display the data. The following is the JS.

```
const retrieve = () => {
fetch('https://www.breakingbadapi.com/api/characters')
.then(res => res.json())
.then(data => {
let mapped = data.map(x=> {return{
name: x.name,
job:x.occupation}})
let dis = document.getElementById("display");
for(let el of mapped){
dis.innerHTML += `<ul>
<li>${el.name} -${el.job}</li> 
</ul>`
}
}
)
}
```

So line by line you have an anon function set to the const retrieve. This function makes an async call the the breaking bad api. The endpoint being the characters. Once resolved the objects are turned into and array of objects with only the name and job properties. This array is iterated over then the properties are set to the innerhtml of the display div. The breaking bad api is fun to use if you are currenty looking to understand the fundamentals of js and html. You can use JSFiddle which is an excellent resource to practice your javascript.
