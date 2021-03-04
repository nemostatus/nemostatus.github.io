---
layout: post
title:      "Journey into data structures and algorithms(linked lists)"
date:       2021-03-04 14:27:14 +0000
permalink:  journey_into_data_structures_and_algorithms_linked_lists
---


Although I haven't had a technical interview yet, I want to ensure I can be prepared for the most common questions that interviewers may ask. After some research I saw a video from a youtuber named * web dev simplified* on youtube and he has a great video named "before your next interview, watch this" . In this video he goes over 10 different data-structures and algorithms. Here is the list of data strcutures and algorithms he mentioned in his video.

1. Linked Lists
2. Binary Tree
3. Stack and Queue
4. Merge/Sort
5. Dictionary/Map
6. Graph
7. Binary Search
8. Breadth/Depth first search
9. Recursion
10. Big O Notation

This past week I followed along with the * web dev simplified* instrructional video on linked lists. Although I still dont have a full understanding on them yet here's what I learned from his video.

1. Unit Testing
2. Pros and Cons of linked lists
3. The difference between linked lists and arrays

1. UNIT TESTING
The package needed to begin unit testing is called jest. To install this package you must first have a pckage.json
file so run npm init in your terminal. This will generate a package.json file for you. Now to begin using jest you have to run  npm i --save-dev jest which will create a package in your package.json file so you can create test files and check to see if a certain input creates a certain output. In order to run a test a test file has to be created, so to let's say there's a file named linkedLists.js that has my linked list class and certain methods that I want to test I would create a file named linkedLists.test.js. In this file I would import the file I want to test, so 

```
const LinkedLists = require('./linkedLists')

```

This imports the file so different methods can be tested from that file. The following code snippet is a one test in the test file that willl test that a specific method named insertAtHead is working the way it supposed to. 

```
describe('#insertAtHead', ()=>{
    test('it adds element to start of list',()=>{
        const li = new LinkedLists()
        li.insertAtHead(10)
        const oldHead = li.head
li.insertAtHead(20)
expect(li.head.value).toBe(20)
expect(li.head.next).toBe(oldHead)
expect(li.length).toBe(2)
    })
})
```
The test takes in the name of the test, '#insertAtHead' then a  function containing the test function named 'test()'. This function takes in the description of the function and finally the second parameter contains the actual input and output. So li is assigned to the LinkedLists class. This class contains a method named insertAtHead(). It's testing that putting an input of 10 actually makes the head of the linked list 10. The beginning of a linked list is called the head and in a linked list each node has a value and reference to the next node. So since the new head is now 10, the value of the  node is 10 and it's next attribute is the previous head. Like I said before I'm new to linked lists and there's so much to cover that I'll just describe a small part of linked lists. 

First off there's 3 different types of linked lists. 
1.Singly
2.Doubly
3.Circular

The difference between these types is the reference of each node. Singly has a reference to the next in the list. Doubly has a reference to the next and previous node. A circular list loops back to the head while singly lists dont.

Here's a look at the linkedLists class. 

```
class LinkedLists{

    constructor(){
        this.head = null //we dont have first yet so null
        this.length = 0 //starts of as 0
    } //creates an object with a head prop and a lnegth prop initializing them to 0 or null
    insertAtHead(data){ //insert at head is used in the from vals helper method
 const newNode = new LinkedListNode(data, this.head)
 this.head = newNode 
 this.length++
    } //inserts into beginning of list

    getByIndex(index){
        if(index< 0||index>=this.length)  return null
        let current = this.head
        
        for(let i = 0;i< index;i++){
            current =current.next
        }
    return current}

    print(){
        let output = ''
        let current = this.head
        while(current){
            output = `${output}${ current.value} ->`
            current = current.next
        }
        console.log(`${output}null`)
    }
}



class LinkedListNode{
constructor(value, next){
    this.value = value //value of node
    this.next = next //next linkedlist node
}
}

LinkedLists.fromValues= function(...values){ //helper method taking in a list like 1,2
    const li = new LinkedLists()
    for(let i = values.length - 1; i >=0;i--){
        li.insertAtHead(values[i])
    }
    return li
} //this is a helper function so test can be ran without depending on other tested methods
//each node in linked list
module.exports = LinkedLists
//so we can access in test file
```

There's a lot to linked lists so why wouldn't I just use an array to store the data. Well the pro is that if a feature only needs to manipulate the first element or head then a linked list is faster and improves performance. The con obviously is that it takes time to setup.
