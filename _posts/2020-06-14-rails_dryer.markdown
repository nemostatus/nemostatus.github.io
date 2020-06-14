---
layout: post
title:      "Rails DRYer"
date:       2020-06-14 07:49:55 -0400
permalink:  rails_dryer
---

**THE WHAT**
  So far in my developer journey have learned alot of different concepts. However there is one concept that has been REPEATED over again and regarded as highly important. Ironically that's the concept of keeping your code DRY. An acronym standing for don't repeat yourself. While developing my rails app I saved that for the end because it sounded overwhelming! However with the help of using before action methods and partials I was ble to remove most of my repeated code. I am no expert in keeping my code DRY yet but after learning more about why it's important I want to make it a concept I keep in mind while developing.
	
	**THE WHY**
Watching some instructional videos on keeping my rails app DRY I learned that using methods to keep code DRY make the application more maintainable. For example in my app I have this code for my navigation bar.



```

<%= link_to "Creat New vehicle", new_user_vehicle_path(current_user.id)  %>
<%=link_to "All Vehicles", all_path %> 
<%=link_to "Your reviews", user_reviews_url(current_user.id) %> 
<%=link_to "Your vehicles", '/vehicles'%>
<%= link_to "Homepage", user_path(current_user.id), method: :get%>
<%= button_to "Logout", '/logout', method: :delete%>

```



Let's say I just copied and pasted it into multiple different files but i wanted to delete one of these links and add another.So I would have to go back to each page and copy and paste the newly and edited code. Copy and paste is useful but it isn't the answer. It wouldn't be so bad to do on a smaller scale but I can imagine how time consuming it would be to change every file that a repeated snippet of code is.
	

**THE HOW**

In order to make the application more efficient you use partials. First created a folder in my views folder named shared. Then in that folder I created a file named  _nav.html.erb.  In this file I added the snippet of code above. So instead of copy and pasting the snippet I can now just copy and paste this line of code
		 
```
<%=render "shared/nav"%>

```

  Now if I wanted to change the code I wouldn't have to change anything else but what's inside of the shared/nav file. 
Only having to make a change once. All  other files containing <%=render "shared/nav"%> would now have the edited code. Very cool.Another way to make your application more DRY is by using methods in your controller. For instance in my reviews controller I have a few instances where I use these lines of code so i decided to put them in methods in my controller.
		 
		 
 ```def find_vehicle
  @vehicle= Vehicle.find(params[:vehicle_id])
  end```

	
Now everytime I want to use them I just put this line on the top of the controller ensuring that the methods will be called before the other code in the method
	
```before_action :find_vehicle, only: [:edit, :update]
  before_action :find_review, only: [:edit, :update]```
	
Overall this project had been intense but I learned alot and hopefully this helps anyone out there who may need a starting point on keeping code DRY and why it's important. I just want to REPEAT that I am in no way an expert but I do see the importance of keeping code ADAP. 
	 
