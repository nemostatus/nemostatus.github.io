---
layout: post
title:      "web scraping and google sheets"
date:       2021-01-05 23:37:44 +0000
permalink:  web_scraping_and_google_sheets
---


So this past few days I've been refreshing my scraping skills since I've always enjoyed the concept. Scraping show cases the power of programming very well. I decided to use a scraping sandbox [https://books.toscrape.com/](http://). It is a fake online book store. I was able to grab the book titles,prices, although I'm struggling to get the star ratings. Now that I had this data, I wanted to store it somewhere in a database so I was going to create a rails project but my text editor was having some issues with rails so after trying to troubleshoot for a bit I thought that rails may not be the only way. This thought led me to many instructional videos of how to store scraping data in different ways. So I learned something very powerful from one of these videos.

I learned that I could get data from lists and tables on a webpage with a function named importhtml(). I watched a video from a youtuber named *dataslice* He explained that going to the function bar of googlesheets (fx) and putting the function below will scrape website data.

```
=importhtml("the url you are scraping from", "table or lists", the number of table or list on page)
```

So this function takes in 3 parameters. The first is the url the data is being pulled from. The second is detaling what element it is. Is it a table or a list? Then the last parameter is the number list or table it is on the page. To find this dataslice provided some code that can be used in the developer tools console to all lists or tables depending on what element you look for using query selector. The code can be found on dataslices youtube video "web scrape in google sheets..." but I'll also post it below with the following example. So still using the books.toscrape.com I'll find all lists on that page by using this code.

```
var i = 1; [].forEach.call(document.querySelectorAll('ul,ol'), function(x) { console.log(i++, x); });
```

This is console.logging all  lists plus the most important part being the id of the list on the page. Using the select an element button in developers tools and hovering over the element will reveal what data we want. So wanting to get the title of each book and their prices I hovered over each list and found out was list number 4. So all together to get this data here's the code

```
=importhtml("https://books.toscrape.com/","list",4)
```

Again this goes in the function bar of google sheets, the parameters are the url first, whether it's a list or table element, and then after identifying which table or list is which you put that number in as the last parameter of that function and now google sheets populates with the data from list number 4 from books.toscrape.com. 
