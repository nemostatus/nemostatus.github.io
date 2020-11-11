---
layout: post
title:      "Dev log: Week 2 Codewars frenzy"
date:       2020-11-11 03:16:37 +0000
permalink:  dev_log_week_2_codewars_frenzy
---


Last week  I've been addicted to solving puzzles on codewars.com.  I can't remember one specific problem off the top of my head but I the pattern has been like this

1.  Use comments to pseudocode (creating a hypothesis of how the problem might be solved)
2.  Attempt that set of pseudocode and run in to an unexpected issue 
3.  Put console.log() everwhere and try to find data by using labels next to the log so I know what data it is
4.  Look at data and see where I can fix the code 
5. Repeat until problem is solved 

Here is one example from a funny problem called 'Jaden Casing Strings'.. The problem wants you to create a function which takes in a string and capitalize the first character of each word. So to start pseudocoding I know I'll need to split this string into an array so I can manipulate the data. Then assign that array to a variable. This array looks like this.

```
 ["hello", "there", "person"]
```

Now that there's an array, the data manipulation can happen, Since I want to change each element I decided to use .map() method which takes the original array, manipulates each element in some way and returns a new array.

```
  let answer=array.map(x=> {
return x.charAt(0).toUpperCase()+ x.substring(1)
  })
```
This returns ["Hello", "There", "Person"]
Breaking it down x is each element in the original array. CharAt() is a method that returns a character from a specified index(in this case 0 is the first letter of each word. The toUpperCase() method capitalizes this letter. This alone doesn't work  because if it ended there it would just return

```
["H","T","P"]
```

To return the last part of the word the substring() method is required and this works by selecting the start index and end index of each word. Since there's no end index in the code it just goes off the second element or index '1' of each word and returns the rest of the word.The last line is just rejoining this new array back into a string

```
function JadenCase(string) {
 
  let array = string.split(" ")
  let answer=array.map(x=> {
return x.charAt(0).toUpperCase()+ x.substring(1)
  })
return answer.join(" ")
};
```

All together this function takes in any string and returns every word in the string capitalized. This was one of the easier puzzles of last week but the thought process was still the same. 




