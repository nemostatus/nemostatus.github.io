---
layout: post
title:      "recursion study cont."
date:       2021-05-06 18:08:16 +0000
permalink:  recursion_study_cont
---


The following are some examples I've found from different sources. This will be a shorter blog but it will close out my blogs on recursion. This is from jsTutorials, "A recursive function is a function that calls itself until it doesn’t
A recursive function always has a condition that stops the function from calling itself." So let's create an incorrect use of recursion. Let's create a infinite recursion. 

What happens when no stop condition is created

```
function infinite(){   
infinite()
}

infinite()
```

Put this in developers tools and you will get this.


```
VM116:2 Uncaught RangeError: Maximum call stack size exceeded
    at infinite (<anonymous>:2:1)
    at infinite (<anonymous>:2:1)
    at infinite (<anonymous>:2:1)
    at infinite (<anonymous>:2:1)
    at infinite (<anonymous>:2:1)
    at infinite (<anonymous>:2:1)
    at infinite (<anonymous>:2:1)
    at infinite (<anonymous>:2:1)
    at infinite (<anonymous>:2:1)
    at infinite (<anonymous>:2:1)
```

So since the recursion is infinite the engine will essentially stop it since it's surpassed some limit created by the engine.
Let' s add a condition to fix this.

```
function notInfinite(num){   
console.log(`Number:${num}`) 
if(num>1){
num--
notInfinite(num)}
else{
return
}}

notInfinite(50)
```

Since there is a condtion to be met(is the given input over 1, if so then the input number is now 1 less and a console.log is logged then check the condition again and see if it's still more than 1. If it's not more then essentially end the recursion. 







