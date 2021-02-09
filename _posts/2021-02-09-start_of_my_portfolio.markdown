---
layout: post
title:      "Start of my portfolio "
date:       2021-02-09 22:57:13 +0000
permalink:  start_of_my_portfolio
---


After many mini projects and coding puzzles I've finally decided it was time to start my portfolio. I'm currently working on the first rendition of my portfolio. I figure if I don't like how the project turns out I can always make another rendition. My current approach is unorthodox. It doesn't scream professional, however I'm satisfied with how it's turning out. My approach was to give the portfolio an animated sprite that will use text to speech and a textbox to guide the user through the page. A kind of throwback to that paperclip that used to be on cpu desktops. In a way I'm experimenting and doing what I enjoy. If the portfolio doesn't impress anyone I can lean more toward a professional look and experience. My philosophy going forward is to try to stand out from the other projects. So far I have the text to speech up and running using Web Speech API. Here's the function that takes in message input and makes the cpu talk. 


```
function speech(message){
let synth = window.speechSynthesis;
let voices = synth.getVoices()
 let utterThis = new SpeechSynthesisUtterance(message)
 utterThis.voice = voices[1]
synth.speak(utterThis)
 }
   
```

This function is a mix of information I learned from stackoverflow and mainly mozilla. This function still needs some fixing because I was able to switch the robot voice to another robbot voice but the first click event triggers the voice I don't want. I read this has to do with JS asynchronous nature. With the text to speech covered I now have to build the sprite(I'm not sure how yet but have used a sprite sheet to build an animation), build my project divs which will display an image resembling the project and the name of the project. Once clicked the div will spin and will display a description and github link to the project(if deployed a link to the project itself). I will also put alot more effort into making the ux/ui better for this project. Along with this I want to either beef up past projects or create entirely new projects with my current skillset.

To explain how the above function works I'll break down what's happening. 

1. The speech function takes in a message
2. The synth variable is declared and assigned to window.speechSynthesis. Mozilla describes speechSynthesis as:
"The controller interface for the speech service; this can be used to retrieve information about the synthesis voices available on the device, start and pause speech, and other commands besides." So it's accessing the ability to use 
speech.
4.The voices variable is declared and assigned to synth.getVoices(). Once again the mozilla definition
is: "The getVoices() method of the SpeechSynthesis interface returns a list of SpeechSynthesisVoice objects representing all the available voices on the current device." 
5. Citing mozilla once again, SpeechSynthesisUtterance(message) is: "The SpeechSynthesisUtterance interface of the Web Speech API represents a speech request.' So it takes the input and makes a speech request with said input
6. The next line sets the property voice of the speech request to the voices[1] which is the voice I decided to choose.Similar to Alexa's voice. 
7. Now all together using the speak() method of window.speechSynthesis to now have text to speech in a robot voice.

