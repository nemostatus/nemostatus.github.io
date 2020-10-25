---
layout: post
title:      "Dev log: Day 1 Cat facts"
date:       2020-10-25 04:38:31 -0400
permalink:  dev_log_day_1_cat_facts
---

   If I were to have a new years resolution in 2021 it would be consistent in pursuing my goals. So I figure I'd get a head start on this resolution. Doing something everyday whether it's a good day or a bad day. This dev log will hold me accountable to my programming goals. I want to code something everyday. Whether it be a mini application like the one I will describe below, a strict learning session(exploring my weaknesses and working on them), and showing code snippets. I will try to provide value in these blogs for whoever happens to read them by explaining the code and sharing resources I find along the way. I will make useful bits of information or resources bold.

The past few days I've been using **JSFiddle** and exploring different APIS. I made a simple mini app where you click a button and recieve random cat facts. So first I made it in *JSFiddle* first, then decided to post it on my github. Interestingly enough the code wasn't the hard part since I was able to make it in *JSFiddle*  quickly. The part that I spaced out on was converting it to a github repo. What I mean is in JSFiddle you don't need to let 2 seperate pieces of code(the HTML and JS) know about one another but when creating a repo from some sratch you do. This is just another reminder that in programming, sometimes there is a very simple reason why something doesn't work and they should be checked first.

   So I **used the emmet command ! + enter which creates a barebone html file**. Then I added this line of code in between the 'head' tags so the html file knows about the JS file. 

```
  <script src="index.js"></script>
```

  I know, I know... embarassing but sometimes it's important to realize that simple things like this are very easy to forget.
So without further ado here is the JS code

```

const handle = () => {
fetch('https://cat-fact.herokuapp.com/facts')
.then(resp => resp.json())
.then(data => {  
 for(let cat of data.all){
 document.getElementById("test").innerHTML += `<ul><li>${cat.text}</li></ul>`
 }})
}
```

   **Practice explaining my code**   - So the code above is going to be used as an event handler for the click event of a button in my html file. It is a function using arrow syntax where a fetch call is made to an **API( Application Programming Interface**) which is just a bunch of cat facts in **JSON format(JavaScript Object Notation)**
**W3 schools explains - "JSON is a syntax for storing and exchanging data."** Ok so it's in JSON format so data can be exchanged. **developer.mozilla.org -   The fetch line "returns a promise containing the response object"** The first .then line is where this response object is located. **"To extract the JSON body content from the response, we use the json() method."** Console.logging resp.json() shows

```
Promise {<pending>}
__proto__: Promise
[[PromiseState]]: "fulfilled"
[[PromiseResult]]: Object
all: (269) [{…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, …]
__proto__: Object
```

   Ok so the promise result is an object containing the property of all with a value of 269 cat fact objects. 
Ok so the second .then line is accessing that. Console.logging the data shows ...

```
{all: Array(269)}
all: (269) [{…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, …]
__proto__: Object
```


   So in order to access that array of objects you have to access the property of that object with data.all.
Using a for loop I went over this array and made the innerHTML an unordered list of these objects text. 

**Lessons learned**   
1. Don't overlook the simple things 
2. Console.logging is always useful for knowing what exactly is going on
3. JSFiddle is an excellent resource for quickly creating mini apps
4. I need to practice explaining my code out loud now, knowing how it to get it to work vs why it works are  different


 




