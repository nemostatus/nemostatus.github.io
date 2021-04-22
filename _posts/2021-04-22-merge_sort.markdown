---
layout: post
title:      "Merge Sort"
date:       2021-04-22 13:58:50 +0000
permalink:  merge_sort
---

A fun algorithm to attempt is the merge sort algorithm. The goal is to break an array in half and continue this until each element in that array is it's own array, then sort them and eventually return a newly sorted array so it should be like this.\

```//[1,4,2,8,345]
//[1,4,2] [8,245]
//[1,4] [2] [8] [345]
//[1][4][2][8][345]
//split the whole array into individual arrays
//compare and sort
//[1,4] [2,8] [345]
//[1,2,4,8] [345]
//[1,2,4,8,345]

```

The first line is th original array which is usually unsorted. Then as discussed it's broken down and the compared to eachother and the final result should be the sorted array. Here's the code for the merge sort algorithm.

```
const merge = (leftArr, rightArr) =>{
//comparison fn
const output =[];
let leftIndex = 0;
let rightIndex = 0;
while(leftIndex < leftArr.length && rightIndex < rightArr.length){
    const leftEl = leftArr[leftIndex]
    const rightEl =rightArr[rightIndex]
if(leftEl < rightEl){
    output.push(leftEl);
    leftIndex++;}
    else{
        output.push(rightEl);
        rightIndex++;
    }
}
return [...output, ...leftArr.slice(leftIndex), ...rightArr.slice(rightIndex)] //returns sorted arr using shallow copies
} //helper fn, when popping into output increment indices


const mergeSort = array =>{
    if(array.length <= 1 ){
    //edge case for recursive fn
    return array;
} //exits when this happens
    const middleIndex = Math.floor(array.length /2);
    const leftArr = array.slice(0, middleIndex);
    const rightArr = array.slice(middleIndex);
    return merge(
        mergeSort(leftArr),
        mergeSort(rightArr) //recursing mergeSort until theres one element the 2 arguments in the merge fn 
    ) 
 
}
console.log(mergeSort([1,4,2,8,3432424,54543,546546,23123,43454,565,676,86757657]))
```



This is alot to take in but I learned alot just following along with a code along and attempting it.  The mergeSort function begins by establishing a condition that needs to be met in order to escape the recursion(since the function is recursed at the bottom of the functions code). The condition is if the array is less than 1 or eaual to 1 return the array. Then some variables are assigned. In order to divide the original array in half over and over the middle index of the array is necessary. This can be found by dividing the array in half and rounding down with Math.floor(). Then use this variable to get the left array by using array.slice(). Slice works like this .slice([startIndex,endIndex]). So by starting at 0(beginning of array) and using the middle index as the end index you can get the left side of the array and with middle as the start and not establishing an end index makes the index the end of the array.  Ok so now that we have the left and right array we can pass them into a helper function as parameters.

This helper function breaks down and merges to together the smaller arrays, in the end a sorted array is returned. It compares the left element to the right element and using some condtionals pushes the smaller number into the output array and keeps doing this until a final sorted array can be returned by using the spread operator to combine all the shallow arrays
