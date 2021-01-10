---
layout: post
title:      "Fun projects this week"
date:       2021-01-10 13:00:00 -0500
permalink:  fun_projects_this_week
---


This last week I've been doing something new almost everyday. I learned alot from both mistakes and various tutorials.
Here is the list of projects that I worked on this past week:

1.  Making a program start upon the startup of my computer(followed a tutorial on  how use a robot voice to greet me when my computer starts, I changed a bit of this. More on this in a bit as this will be the main focus for the blog today.) (howtogeek.com)
2.  Create and train a neural network( Traversy Media) I also built my own networks(didn't quite work but that's the learning process)
3.   Pull different lists from the web, put them into googles sheets, change this data so I can copy and paste into an array. Use this array and the map function to create a  list of json objects (my own thoughts and tutorials)
4 Some more unity game development( Brackeys tutorial)
5.Practicing unit testing

**INTRO**

So the way I came across this we article on having your computer greet you was seeing how some games can be edited using a notepad file. I was having difficulty restarting a computer game called *Undertale* so I could create a fresh file. After a bit of research and some irritation from seeing the same old file I learned that I had to find a certain file of the game, then make it's config file empty. I copied this code before hand in case the game crashed. I rebooted the game and sure enough it worked. The file was empty and I could now start a new game. This got me thinking about how code in notepad had an actual inpact on programs on my cpu. So I went in search for what could be done in notepad and found an article about how you could get your computer to talk to you. I also had the thought. What if I could make a program start when the computer started up. So I'll explain how to start up chrome(or any file) when your computer starts.

**MAKE A PROGRAM START ON CPU STARTUP**

1. Bring up the run box on your cpu(for windows you press windows key and r together)
2. Type **shell:startup** into the run box.
3. This should bring up your startup folder
4. Now that your here you can create a shortcut for the program or script you want to run, then put it here
5. Testing this I know it works Try it out for yourself! Below I will disuss how I created a script from an article from howtogeek.com and changed a bit to make it say different things each time the computer starts. 

**HOW TO BUILD A MOTIVATIONAL BOT **

I followed the tutorial and they describe the language used in this script is VBScript. I'll first show what they created, then show what I changed. 

```
dim speechobject
set speechobject=createobject("sapi.spvoice")
speechobject.speak "The geeks shall inherit the earth"
```

I'm new to VBScript but it looks like the variable speechobject is declared on top then assgined to.. something that makes your computer talk to you. Then when the script is run the voice will say "The geeks shall inherit the earth". So this can be pasted into notepad, saved as a .vbs file then create a shortcut to desktop. If you click it, it will say whatever sentence you want as a robo voice. So I decided to combine these 2 ideas and save this shortcut into my startup folder. So everytime my cpu would start it would say whatever was assigned to the speech.speak property.  That's cool but it would get boring hearing the same old message everytime so I decided to change the code a bit. 

```
Dim Message, Speak, Options,check, ok,max,min
Set Speak=CreateObject("sapi.spvoice")
Options = Array("Hello human", "Today is going to be a good day.","Hello there lets get coding ","you can do it if your computer believes in you believe in yourself "," You are not in the matrix however the matrix made you type this smiley face")
max=4
min=0
Randomize
check =  (Int((max-min+1)*Rnd+min))
ok = Options(check)
Speak.Speak ok

```

So I took a long time trying to get the randomize part of the code work. It was because I was missing the Randomize part, ironic... So like before all of the variables are declared on top of the code, then assigned below.  There's the speak object labeled speak(which has the property of speak). The options variable is an array of hardcoded greetings I came up with. You can put whatever you'd like, song lyrics, anime quotes, whatever. The max and min variables are used to choose which sentence will be selected in the check variable. The ok variable is the random setence. Speak is the object and speak is also the property in charge of saying something. So all together on startup the computer will greet you with a different greeting most of the time. So this just makes me curious of what other more powerful scripts can be executed on startup. Happy coding everyone.














