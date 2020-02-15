---
layout: post
title:      "My Pokemon CLI "
date:       2020-02-15 11:05:14 +0000
permalink:  my_pokemon_cli
---


   Hello there! Over the past two weeks after many error messages and energy drinks later I created a Pokemon CLI for my first Flatiron project. In this blog post I want to share a brief explanation of what my CLI can do, how my code works, what my personal process was, and finally what lessons I took away from this experience.
	 
	 If you have the chance to interact with my CLI you will have access to a miniature pokedex. For the readers unfamiliar a pokedex is a device in the fictional world of Pokemon! Pokemon stands for pocket monster and the pokedex allows the user to choose a monster and after one is selected the user has the option to choose which attribute they would like to learn about that particular Pokemon. I have detailed the route the user will take in Fig. A
	 
	 Fig. A 
	 
```
                                                                        |--- moves--- lists multiple moves of selected pokemon
                                                                        |--- types - lists a pokemon types                                                          |--pokemon  list-loop
                                                                        |--- base xp -- lists xp gained when this pokemon is defeated--|
pokedex - pokemon list- choice ----|--- weight --- weight measured in hectograms                                |--exit-end  
exit -end                                                      |--- height -- height measured in decimeters
                                                                        |--- abilities -- lists all abilities of pokemon
```  

  The architecture of my code consists of setting up everything needed: creating a git repo, bundle gem pokemon_cli, first commit, creating a executable file, and setting up the enviornment for the cli. Then once everything was set up I created three classes: an API class in charge of bringing in external data(from PokeAPI) and instantiating new objects with the data, a Pokemon class in charge of storing data and gives my program the ability to create objects(with intitialize method and mass assignment) and finally a CLI class in charge of creating the experience with the user and gives the user options as detailed in Fig. A
	
	This was definitely a huge learning experience for me. My first way of approaching my project wasn't working. I thought as long as I put in the time and worked hard that I could finish without a hitch. I was mistaken. I was creating my own loop of error messages and I knew that couldn't continue working the way I was. I knew in order to break this loop I had to change my approach so I slowed down a bit, took more breaks. Instead of focusing on the quantity of my thoughts I started focusing on the quality. I thought to myself, "just follow the data". So I took out a piece of paper and drew a diagram so it made more sense in my head of what was going on. Taking the theoretical and making it more understandable. I focused on how the data was pulled in, instantiated into objects, stored, manipulated and finally controlled with conditional statements. I do understand I have much more to learn however.
	
	Overall this experience has been a rollercoaster but after all the late nights and error messages  I finally broke the loop and finished my project. Thank you for taking the time to read this and enjoy your day.

	 
	 