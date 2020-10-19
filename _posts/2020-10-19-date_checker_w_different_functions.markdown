---
layout: post
title:      "Date checker w/ different functions."
date:       2020-10-19 17:18:24 +0000
permalink:  date_checker_w_different_functions
---

Similar to most things in programming there are usually multiple ways of accomplishing the same task. 
In a way that's  good but just because a way works one time doesn't mean that it will work or be the most efficient in all cases. This is true with javascript functions. So before going on let's define what a function is ? 

Well they are bits of code that can be created to 'do something'(declared) and called as many times as the developer wants  (invoked). If a function belongs to a class object, the function is now a method. A function can take in multiple parameters, even other functions. The functions being used as arguments are called callback functions. Since there is alot to talk about for functions I'm going to narrow down the scope of functions to 

1. The functions keyword 
2. Anonymous Functions 
3. Arrow functions 
4. The difference between implicit and explicit functions 
5. Closures 


**The function keyword**- So to demonstrate one way of creating a function let's begin by using the function keyword. Let's build a date checker function with the *function* keyword. 

```
function explicitCurrentDate(){
return new Date()}

```

So breaking this function down piece by piece, it starts with the function keyword which declares the rest of the code as a function object. The 'explicitCurrentDate()' is declaring the name of the function. Since it doesn't currently need any input there are no parameters . The curly brackets which have the *explicit* syntax (meaning the programmer has to type out the return keyword itself and is not done by the JS engine, more on this later) is returning a new date object. This function can be invoked by typing explicitCurrentDate(). Trying to declare this function without the function keyword doesn't work and will render the error. 

```
Uncaught SyntaxError: Unexpected token '{'
```

Trying to declare this function without the *return* keyword returns *undefined * when invoked.

So in this syntax a few things are required. The *function* keyword, the *return* keyword and the curly brackets. The programmer has to type all of this out for it to work. Using ES6 arrow functions allows the programmer to type less code and the code can be created implicitly(done by the JS engine without the programmer telling it to do so)

**Arrow functions** -  Using arrow functions allows the programmer to now create the function implicitly. So what does implicit   mean exactly. Think of it as implicit as less code written by programmer and more code written by the engine because the engine knows to create the function object without explicitly typing out *function* and knows to return a value without the  *return* keyword. Below is the same date function but using arrow function syntax the explicit way


*EXPLICIT*
```
const explicitArrowCurrentDate = () => {
return new Date()
}
```

*IMPLICIT*

```
const implicitArrowCurrentDate = () => 
 new Date()
```

So what's the difference between this syntax and the first function, well using arrow functions no longer require the function keyword. Also the return keyword isn't needed, nor are the curly brackets. The implicit syntax can also be typed out using parenthesis wrapped around new Date(). The parenthesis are useful when returning an object with curly braces, like so {name: 'matt'} and you don't want the engine to confuse the objects curly braces for explicit syntax.  Arrow functions are considered anonymous.

**Anonymous function** - Anonymous functions are really useful when using the function itself will only be used once in a program. So let's say we wanted to create a program that checked the date every day( that program makes sense right?)

```
setInterval( () =>
console.log(new Date()), 86,400,000)
```

So the above code is using the window method setInterval, passing in the *anonymous* function and because all we want to do in this program is check the date everyday we don't need to invoke this code anywhere else so there's no point in giving it a name. So breaking down the code above again we are using the window method setInterval, passing in the anonymous arror function which is also using implicit syntax. In the second parameter we are saying invoke the anonymous function every day or .... 86,400,000 milliseconds.  

**Closures** - Ok, what is a closure?  The MDN docs say *A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function*  Ok before I continue I'm going to not only read some examples but also create some for myself so I can get a better understanding. I'll be right back... I'm back. Here's an example I created inspired from the MDN example. I'll breakdown whats going on and prove it's a closure using console.dir()

```
function outerFunction(){
let date = new Date();
function displayDate(){
alert(date);
}
return displayDate
}

let finalFunction = outerFunction()
finalFunction()
```

Ok so if you're familiar with JS scope rules you know that variables defined outside of functions are still accessible to inner functions but any variable defined inside a function isn't accessible outside from outside the function.(Lexical Scoping)  So closure is based off this scoping rule. Citing the MDN docs once again. *“A closure is a special kind of object that combines two things: a function, and the environment in which that function was created.* Ok so after replacing finalFunction() on the last line with console.dir(finalFunction) we can get a good look of the function and it's scope. Running the code now, in the console I get

```
[[Scopes]]: Scopes[3]
0: Closure (outerFunction)
date: Mon Oct 19 2020 06:25:34 GMT-0700 (Pacific Daylight Time) {}
1: Script {I18n: {…}, EditorUISettings: {…}, choicesScript: script, GroupsPicker: ƒ, Common: ƒ, …}
2: Global {0: global, window: Window, self: Window, document: document, name: "", location: Location, …}

```

This is the scope of the function and proof that the function demonstrates the idea of closure because it's right there after checking the scope. Expanding the closure scope gives us the date which is the variable defined outside of the inner function but inside the outer function. Ok so let's continue this exploration of closure. After adding the same date variable right before alert, like so

```

function outerFunction(){
let date = new Date();
function displayDate(){
let date = new Date();
alert(date);
}
return displayDate
}

let finalFunction = outerFunction()
console.dir(finalFunction)
```

Then console.dir() reveals that there's no longer a closure because in javascript the engine goes out of scope only if it needs to which it doesn't here and that's why it doesn't have a closure scope. Setting the outerfunction() to a variable is also key because just console.dir( outerFunction()) says the closure doesn't exist.  So that means in order for it to be a closurethe outer function needs to be assigned to a variable. If you try invoking outerFunction it just returns the displayDate() function as a whole not the action itself. 

```
outerFunction()
ƒ displayDate(){
alert(date);
}
```

So the variable finalFunction is just a record of the outerFunction() which maintains a reference to the scope. To quote Douglas Crockford(computer programer) - *Closure means that an inner function always has access to the vars and parameters of its outer function, even after the outer function has returned.* . Ok so now what? Now we know the syntax of a closure, what it is and how to check if it's a closure but what's the point. Why would a programmer need to know all of these rules of a closure?
1.  Developing a function factory using closures -MDN Docs
2.  Emulating private methods. - MDN Docs
3.  Data encapsulation






