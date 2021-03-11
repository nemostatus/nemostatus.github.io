---
layout: post
title:      "Scratch the surface of Binary trees"
date:       2021-03-11 12:02:21 -0500
permalink:  scratching_the_surface_of_binary_trees
---


Hello! So this past week i’ve been trying to learn binary trees. Here’s what I’ve learned so far.I used geeksfogeeks to start learning binary search trees. 

1.There’s a root node of a binary tree
2.The left node of another node has a lesser value of the parent node
3.The right node of another node has a greater value of the parent node


Here’s the code on the page which I followed along with in a gthub repo and added comments as I typed it out. Although the rules of a binary tree seem simple, creating it in code is surprisingly heavy. Here’s the code along with some comments I typed out in order to identify what was going on.

class Node{
    constructor(data){
        this.data = data;
        this.left = null;
        this.right = null
    }
} //breaking down this class
//a node has a data property which will be compared to the other nodes in the class below or bst
//depending on how the node compares to other depends if it will be the left or right branch of
// another node unless a root doesnt exist, then its the root node

class BinarySearchTree{
    constructor(){
        this.root =null
    } //a bst starts with no root node unless added
    insert(data){ // this method takes in data and passes that data into the constructor of node clasee making a new node with data but no branches yet
        let newNode = new Node(data)//the new node
        if(this.root ===null){ //if the binary tree doesn't have a root node yet then make this new node the root node
            this.root === newNode
        }
        else{
            this.insertNode(this.root,newNode) //if the bst has a root node then use the insertnode method to identify where to put this new node
        }} 
        insertNode(node,newNode){
            //conditional to determine where the new node belongs on the bst
            if(newNode.data < node.data){ //the new nodes data is compared to the root node nad if it's val is less than root check if it has a left branch
                if(node.left === null)
                    node.left = newNode //if no left branch then make new node the left branch of root

                else
                    this.insertNode(node.left,newNode) //compare the left branch to the new node using recursion
            }
              else{
                  if(node.right ===null)
                  node.right = newNode //if the new node is more than the left branch and theres no right node then make new node right branch
                  else
                  this.insertNode(node.right,newNode) //compare right branch to new node
              }
        }
        remove(data){
            this.root = removeNode(this.root, data)
        }
        // it recur over the tree to find the 
// data and removes it 
removeNode(node,key){ //so the params are node ===this.root and key===data so removeNode(5,10)
    if(node===null) 
        return null //if the root is null then return null 
         // if data to be delete is less than  
    // roots data then move to left subtree 
    else if(key<node.data){ 
        node.left =this.removeNode(node.left,key)
        return node
    }
        // if data to be delete is greater than  
    // roots data then move to right subtree 
      else if(key>node.data){
        node.right =this.removeNode(node.right,key)
        return node
    }
     // if data is similar to the root's data  
    // then delete this node 
    else{
        if(node.left === null && node.right ===null){
            node = null
            return node
        }
        if(node.left === null){
            node =node.right
            return node
        }
        else if(node.right ===null){
            node= node.left 
            return node
        }
        // Deleting node with two children 
        // minumum node of the right subtree 
        // is stored in aux
        let aux = this.findMinNode(node.right)
        node.data =aux.data
        node.right = this.removeNode(node.right,aux.data)
        return node
    }
}
findMinNode(node){    // if left of a node is null 
    // then it must be minimum node 
if(node.left ===null)
return node
else return this.findMinNode(node.left)
}

getRootNode(){
    return this.root
}

search(node,data){
    if(node ===null)
    return null
}
}
The next week i’m going to attempt to write some tests using jest and create an app.js file so I can also manually test. This week I learned the basic rules and how to convert those rules into code.


