---
layout: post
title:      "My Pokemon CLI "
date:       2020-02-15 06:05:15 -0500
permalink:  my_pokemon_cli
---


   Hello there! Over the past two weeks after many error messages and energy drinks later I created a Pokemon CLI for my first Flatiron project. In this blog post I want to share a brief explanation of what my CLI  can do, how my code works, what my personal process was, and finally what lessons I took away from this experience.
	 
   If you have the chance to interact with my CLI  you will have access to a miniature pokedex. For the readers unfamiliar a pokedex is a device in the fictional world of Pokemon! Pokemon stands for pocket monster and the pokedex allows the user to choose a monster and after one is selected the user has the option to choose which attribute they would like to learn about that particular Pokemon. 
	 
  I started my project by setting up everything I needed: creating a git repo, bundle gem  pokemon_cli, first commit, creating a executable file, and setting up the enviornment for the CLI. Then once everything was set up I created three classes: an API class in charge of bringing in external data(from the PokeAPI). The API class was incredibly challenging for me because the PokeAPI is tricky. I thought it would be extremely easy just using the rest-client gem to get the raw data and json to parse but unfortunately after I did that I could only get 2 elements from the pokemon, it's name and the url of the pokemon.Since I don't have the most experience with API's I began to worry because my CLI would only show the name of the pokemon which isn't very interesting. So I got creative and created a second API call which would plug in the pokemon url into the call and get that information back. This was a dead end because there was no 'results' key to use when parsing. There were many seperate keywords. So I was really lost for a while. I decided to keep adapting and eventually came up with the idea of a second api method which would not only plug the pokemons name but based on user input it would also plug in a stat keyword into the JSON parse line. This finally gave me access to more than just the name.The user could now learn about any pokemon and any stat about them. I'm not sure if this is common practice but I do want to learn the proper way to extract data. I also created a Pokemon class in charge of storing data and gives my program the ability to create objects(with intitialize method and mass assignment) and finally a CLI class in charge of creating the experience with the user and gives the user options.
	
  This was definitely a huge learning experience for me. My first way of approaching my project wasn't working. I thought as long as I put in the time and worked hard that I could finish without a hitch. I was mistaken. I was creating my own loop of error messages and I knew that couldn't continue working the way I was. I knew in order to break this loop I had to change my approach so I slowed down a bit, took more breaks. Instead of focusing on the quantity of my thoughts I started focusing on the quality. I thought to myself, "just follow the data". So I took out a piece of paper and drew a diagram so it made more sense in my head of what was going on. Taking the theoretical and making it more understandable. I focused on how the data was pulled in, instantiated into objects, stored, manipulated and finally controlled with conditional statements. However I do understand I have much more to learn.
	
  Overall this experience has been a rollercoaster but after all the late nights and error messages  I finally finished my project. Thank you for taking the time to read this and enjoy your day.

	 
	 
