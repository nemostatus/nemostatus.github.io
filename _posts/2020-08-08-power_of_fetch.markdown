---
layout: post
title:      "Power of fetch"
date:       2020-08-08 15:29:10 +0000
permalink:  power_of_fetch
---


Throughout my project, I learned just how powerful the fetch() method is. My application has a total of 8 fetch requests. 3 of those fetch calls used a GET request, 2 were POST requests, 1 DELETE request and 1 PUT request. I''ll explain  the trickier GET fetch call hoping it helps anyone who reads this. So in my application my associations was a Challenge has_many Attempts and an Attempt belongs_to a Challenge. I originally made a fetch to this endpoint

```
const  BASE_URL. =  "http://127.0.0.1:3000"
fetch(`${BASE_URL}/attempts') - original endpoint
```

Thinking about it I realized that I didn't just want to get all the attempts. I wanted to get the attempts belong to that challenge. So I knew before I could make the fetch request to that nested route it would need to exist. So I configured the the backend.First, I add this to my routes.rb file 

```
resources :challenges do
  resources :attempts
  end
	
	new route - 	/challenges/:challenge_id/attempts
```

That allowed me to now make a fetch request to the new endpoint of the attempts belong to whatever challenge I wanted.However I had to change the index method in the backend for attempts to reflect this new change.

```
 @challenge = Challenge.find(params[:challenge_id])
    @attempts = @challenge.attempts
    render json: @attempts
		
		instead of @attempts = Attempt.all
```

So now that the backend for the nested resource is configured, let's go over the fetch call itself. 

```
function fetchAttempts() {
  fetch(`${BASE_URL}/challenges/${event.target.dataset.id}/attempts`)
    .then((resp) => resp.json())
    .then((attempts) => {
      for (const attempt of attempts) {
        let a = new Attempt(
          attempt.id,
          attempt.name,
          attempt.deadline,
          attempt.notes,
          attempt.complete,
          attempt.challenge_id
        );
        a.renderAttempts();
      }
    });
}
```

Ok so breaking this block of code down.
1. Using the fetch() method to make a GET request to the localhost endpoint that uses the id from the challenge that was clicked on, the event.target.dataset.id carries over an id from the click event which has the challenge.id set in the dataset of the button
2. Then returns a promise containing a response in json format then  returns the data as  javascript objects
3. Then the array of javascript objects are iterated over and creates a new attempt using the attributes of each javascript object
4. Using a class method renderAttempts() then which takes the instance of attempt and is then displayed on screen

So this is alot done with a relatively small amount of code and this is only one thing the fetch() method can do. 

