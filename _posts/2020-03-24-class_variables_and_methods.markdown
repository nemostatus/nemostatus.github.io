---
layout: post
title:      "Class variables and methods"
date:       2020-03-24 11:47:41 +0000
permalink:  class_variables_and_methods
---


I learned a difficult lesson building my first project. After days of typing line after line I had finally built a CLI I was proud of. It worked. There was no way to break the CLI. I was going to pass for sure right? Unfortunately I learned a lesson I can now carry forward into my future projects.  I failed. What I did was use class variables to store all of my information that I got from the PokeAPI. I now understand after building two different versions of my project that using instance variables and class variables correctly allowed me to build the project with significantly less lines of code. I didn't have to clear the class variables and have the user re-input the information they wanted. Looking back my code was honestly a mess and I'm glad that I was instructed to build the correct way . I struggled so much more when using class variables to store all information gathered from the API.

So if you're just learning class variables and methods I would say use them carefully and only to store objects that have attributes not using class variables to storethe hash of data. The most common class variable you'll use is the @@all class variable. This class variable is used to store all objects of your class in. So the variable is an empty array and using the initialize method you can push all instance of the class into the class variable @@all using @@all << self. So this line of code in the initialize means that once an object is created in the class it will be pushed into the class variable @@all. So once that is done in the initialize method it will store that object in the variable. In order to be able to call on the class variable a class method must be created  named self.all.So what does that mean? Self is whatever your class name is. So if my class name is Pokemon then when I call on the class method later on it will be named Pokemon.all. So whatever pokemon have been stored in my variable are now being read. So below is just a snippet of what I'm talking about.

```
class Pokemon 

attr_accessor :name

@@all = []

def initialize (name)
@name = name 
@@all << self 
end 
 
 def self.all 
 @@all 
 end 
 
 end 
```

So when the object is created, it is stored and able to called later. The code snippet below will create two objects and then the class variable is called.

```
pika = Pokemon.new("pikachu")
 char = Pokemon.new("charizard")
 Pokemon.all
```
This will give me

```
[#<Pokemon:0x000055e59ef1fb60 @name="pikachu">, #<Pokemon:0x000055e59ef1fb10 @name="charizard">]

```

So the class variable now has the object id and the name attribute of each pokemon object. This is the correct way to use class variables. It is organized,will allow the developer to call on the data stored and will be less buggy when building anything in OOP.
