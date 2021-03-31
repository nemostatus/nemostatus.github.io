---
layout: post
title:      "Learn about Queues"
date:       2021-03-31 17:19:08 +0000
permalink:  learn_about_queues
---


If you are familiar with a stack data structure you know the rules are LILO(last in last out). Meaning in a stack whatever element comes in gets put at the end of the array(push) and the last element is what gets removed first(pop). For a queue data structure the first element gets removed first so either LIFO(last in first out) or FIFO(first in first out). Here's a code snippet that demostrates how a queue data structure works.

```
function queue(){
    let collection = []
    this.print = () => {
        console.log(collection)
    }
    this.enqueue = element => {
        collection.push(element) //add to end of collection, if i want to add to beginning i would use unshift
    }
    this.dequeue = () => {
       return collection.shift() //removes element from beginning unlike stack which remove from end so
        //queue - fifo first in first out
        //stack - lifo last in first out
    }
    this.front = () => {
      console.log(collection[0] + " is the first element" )
    }
    this.size = () => {
        return collection.length
    }
    this.isEmpty = () => {
        return collection.length === 0 ? console.log("IS EMPTY"): console.log("IS NOT EMPTY")
    }
    this.clear = () => {
    collection = []
    }
  
}
```

Here is a data structure that has a LIFO(last in first out) structure.  If you wanted a FIFO(first in first out) structure in the helpre method enqueue you would change collection.push(element) to collection.unshift(element). Ok so section by section there is a function named queue with alot of helper functions. To start of with this function has a variable named collection set to an empty array. If this was a class it would be the property of queue. Here's a breakdown of the helper functions.

1. Print - This function logs the queue.
2. Enqueue-This function adds an element to the end of collection
3. Dequeue-Removes element from the beginning(main difference between a queue and a stack
4. Front-Logs first element of collection
5. Size - returns length of collection
6. IsEmpty - Logs if the collection is empty or not
7. Clear - resets collection

The following code snippet is an example of these methods on a new queue instance.

```
let q = new queue //instance of queue
q.enqueue(100) // adding to the end of empty array, so first element
q.front() //logging the first element
q.enqueue(1000) //adding to the end of array
q.front()//100 is the first element
q.dequeue()//remove from the front so now 1000 is the first and only element
q.front() //1000
q.print()
```


