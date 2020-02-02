---
layout: post
title:      "Array manipulation."
date:       2020-02-02 13:26:19 -0500
permalink:  array_manipulation
---


The concept of arrays was easy to learn at first. I just thought of them as a list of items seperated by commas, encased in square brackets and to be organized assign the list to a variable name that makes sense. However when it came to manipulating where the elements of the array were located is when I started to struggle. Since an array can be manipulated in a variety of arrays via methods and iterators I was confused and had trouble remembering which method did what to an array. However with time I slowly started remembering more array methods.  

For example, the array below is a cereal array that stores everything needed to make breakfast( or my dinner).

```
cereal_array = ["bowl","milk","spoon","cereal","spider"]
```

AH! That last item is really disturbing! However something even more disturbing is the fact that I accidentally poured my milk into the bowl before the cereal was in there. I think that I should switch the location of the milk and cereal elements so I should do the following,

```
cereal_array[1],cereal_array[3] = cereal_array[3],cereal_array[1] 
cereal_array 
```

So the code above will give me

```
["bowl", "cereal", "spoon", "milk", "spider"]
```

Unfortunately it's time to close the spider spa so it will have to be popped away using.. well the pop method.

```
cereal_array.pop
cereal_array
```

Finally I have a nice bowl of cereal leaving only the items I want in it and in the order I want as well. This is just one of many examples of array manipulation and don't even get me started on iteration... Oh ok I'll show you an example of how to manipulate an array using iteration. Using the original instance of the cereal array iterate over the array, grabbing each item and using a case statement to control how the data is manipulated, returning a whole new array.

```
cereal_array = ["bowl","milk","spoon","cereal","spider"]
cereal_array.map{|item|case item 
when "bowl"
 "shiny bowl"
when "milk"
"delicious milk"
when "spoon"
"fancy spoon"
when "cereal"
"the best cereal"
when "spider"
"Get out of my bowl spider!"
end 
}
```

The code above will return 

```
 ["shiny bowl", "delicious milk", "fancy spoon", "the best cereal", "get out of my bowl spider"]```
 
 Totally worth all of that iteration. Thank you for reading.
 









