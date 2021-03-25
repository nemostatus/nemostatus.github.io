---
layout: post
title:      "Learn about stacks"
date:       2021-03-25 05:01:23 +0000
permalink:  learn_about_stacks
---

A stack is a data type that is essentially an array. However the main difference between an array and a stack has to do with the fact that a stack focuses on the last element of the data strcuture. It has 2 main methods which are push(adding an element to the end of the structure). The second method is pop which not only removes the last element but returns the last element. If you are familiar with arrays you will realize that js has built in array methods(push and pop). Since coding seems like magic but never is let's understand why these built in methods work. Let's start by defining the stack class and what properties it should have.

```
class Stack{
constructor(){
    this.items = []
    this.count = 0
}}
```

Here's the stack class which has an items property(set to empty array). Also there's a count property which will help identify which element in the array we want to work with.Let's start with the push method.  So the goal of the method is to
1. Take in data as an argument
2. Add this new data to the end of the array or items property
3. Increase the count property since a new element was added

Altogether the push method looks like this

```
push(element){
    this.items[this.count] = element
    console.log(`${element} added to ${this.count}`)
    this.count+=1
    return this.count - 1
}

```

Ok now that the push method is created, what should the pop method accomplish

1. If there's no element to pop or remove then return undefined
2. Identify the last element in the array
3. Decrease count
4. return the last element that was just deleted

Altogether the pop method looks like this

```
pop(){
    if(this.count ===0) return undefined
   let deleteItem = this.items[this.count-1]
   this.count -=1
   console.log(`${deleteItem} removed`)
   return deleteItem
}
```

So these are the 2 main methods of a stack. There are other methods that can be created such as 

1. peek(), Goal: Returns last element in stack(without removing it like pop())
2. isEmpty(), Goal: Checks if the stack is empty
3. size(), Goal: Returns size of stack
4. print(), Goal: Prints out the elements in a stack
5. clear(), Goal: Sets the items to an empty array and the count back to 0

A youtuber named "Traversy Media" has a great video on stacks if you want to learn in more detail about stacks.




