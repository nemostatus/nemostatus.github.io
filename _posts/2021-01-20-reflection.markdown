---
layout: post
title:      "Reflection"
date:       2021-01-20 20:12:38 +0000
permalink:  reflection
---


This week hasn't been the most action packed week in terms of coding but rather coding in codewars and reflecting on my programming journey and how I can best continue learning now that I'm done with FlatIron S.E. curriculum. I've been practicing in codewars, reading different programming articles, following different coding tutorials, and creating some of my own mini projects such as pokemon battle app, secret message app, and trying out my own popular baby name classifier with brain.js(didn't turn out the way I wanted) and a couple of games using roblox studio and unity game engine. 
Although these projects are fun I realize I need to return to practice my technical skills more rigorously. Codewars has helped me tremendously in solving various code puzzles but recently I learned some important lessons such as :

* Limiting global scope variables
* Use closures when possible
* The difference between variables by reference and variable by value

This made me pause and reflect on my current skills and reflect on my current coding practices and how I can improve. 
Here's what I have so far:

1. Read the best practices section in  codewars
2. Practice writing tests for my code
3. Think about if my code is DRY and there's any possible way to refactor it

Here are some code snippets of examples of writing tests for your code(using the Jest library)

```

function concatenated(word, secondword){
return word.concat(" ", secondword)
}

module.exports = concatenated
```

So the function above will take into 2 words, take the first word then concatenate (with a space in between) with the secondword. Here's an example

```
concatenated("pb","j")
// this is what is returned "pb j"
```

Ok, so this is a very simple example however the more complex code becomes the more important tests become. Here's a snippet of how to use the Jest library to make sure the function returns what you expect. 


```

const concatenated = require('./concat')

test('This should add on the word chosen', ()=>{
    expect(concatenated("word","plus")).toEqual("word plus")
})
```

Ok so the code above is a test using the jest library. The good thing about the test is that it reads very easily. It has a function named test that takes in 2 parameters, the first parameter is a description of what you expect the concatenated function should return. Then the second parameter is an anonymous function that says expect concatenated function that takes in certain data to equal "word plus".



