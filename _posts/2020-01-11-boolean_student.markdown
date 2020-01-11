---
layout: post
title:      "Boolean student"
date:       2020-01-11 10:36:37 -0500
permalink:  boolean_student
---


   If i were to teach someone who never heard of a boolean before, I would start by telling them that a boolean in the Ruby language is just a value of either true or false. The concept of a boolean is represented as either a truthy value or falsy value with the truthy being returned as true and falsy being returned as false or nil.
	 
   Following the explanation I would give the boolean student the most simple example I could think of. I would ask them to type in an ide 1==5 and then have them run it to see the ide return the value of false. I would explain that Ruby is checking to see if 1 is equal to 5 and since it doesn't the ide returned false. So now that leaves the student with the profound truth that 1==1. I would explain that the true value is the only truthy in the boolean data type.
	
The boolean student will probably be asking me, So? I already knew that 1 is equal to 1." Agreeing with the student, I would explain that the boolean data type is what will give us freedom in programming. I would explain how we can imagine ourselves walking down a path step by step(line by line) creating doors(conditional statements, in this case if key == and also creating the keys to open the newly created door("Alakazam!!)now that we created this door if a traveler passing by(user of program) has the a key("Abracadabra.") they cannot open our newly created door and see behind it(the executable code- "Open sesame!!") .However since we created 1 more door(using elsif) our traveler keeps going in order to check if the key he has works and since his key ="abracadabra" then "abracadabra"=="abracadabra"(true value) which allows our traveler(user) to open the door and see what's inside(the executable code- "less enthusiastic open sesame"). I would explain how the keyword else in and if-else path is the end of the path that either has a door that takes all keys that didn't open the previous doors or a complete dead end(nil) if no destination(executable code) is provided.
  ```
def magic_door(key)
if key == "Alakazam!!"
 "Open sesame!!"
 elsif key == "abracadabra"
 "less enthusiastic open sesame"
else 
 "open something something ehh... not in the mood today"
end 
end
magic_door("abracadabra")
```
I would explain how the path is a metaphor for how booleans allow programmers to have flow control and the outcome is unique depending on the value provided. Overwhelmed the boolean student says "oh ya,well... I still know that 1 is equal to 1!" I would  say "ok and how can we work with that boolean and create a conditional statement. We know that 1 is equal to 1 so we can double check via Ruby with a condtional statement." The student types the following condtional statement after I put the question 
```
def does_1_equal_1?
puts "Does 1 equal 1 based on human agreement??"
if 1==1
 "yes"
end
end
does_1_equal_1?
```
  The student is amazed and says "I knew it! Thats awesome! I think I'm starting to get flow control a little bit." I would then explain to him the basic rules of booleans and that booleans use more than the == operator to check for true and false. I would provide him with this list of operators(!-represents "not", &&-represents "and', ||-represents "or") I would explain how true && true returns true but true && false returns false however false||true returns true. I would use another metaphor for this and explain imagine false as a spider and true as a butterfly. Put the butterfly && spider together and only the spider remains. However if you had the choice between either the butterfly||spider , only the butterfly remains. I would then complete the lesson by listing off the remaining boolean operators(!=,>,<,>=,<=)I would close off my lesson by stating that there many ways to use a boolean data type via multiple types of conditional statements but fundamentally a booleans purpose in programming is to make comparisons and control the flow of the program. 
```
def to_read_or_not_to_read(status="unread")
if status == "unread"
":("
else
":), thank you for reading."
end
end 
to_read_or_not_to_read()
```

