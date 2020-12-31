---
layout: post
title:      "Unity beginner project"
date:       2020-12-31 04:37:58 -0500
permalink:  unity_beginner_project
---


So this past week I had 2 main goals. My first goal was to revisit scraping data with ruby. The other goal was to download unity(a game engine that uses c#) and see if I could create a simple game. Which goal do you think I worked on more this week.... ? Yeah, it was creating the unity game. Although I did find some good resources to practice scraping. I stumbled acrossed this site which is specifcally designed to practice scraping. (https://toscrape.com/), Feel free to copy and paste this into google search if you are hesitant about clicking links. Essentially toscrape.com is a sandbox to practice scraping. I practiced for a few hours seeing how to grab different types of data from the webpage. It's great. However I was just so immersed with creating a unity game that I decided to shelve my scraping practice for another day. 

Knowing absolutely nothing about Unity or c# for that matter I decided to follow a great tutorial series online by a youtube channel named *Brackeys*. I wasn't completely lost since I did create a roblox game in roblox studio and created the  scripts with Lua. I was familiar with pattern of creating and manipulating different objects properties and timed this with different events of the game. So I'll just share some scripts below that Brackeys showed me and try to break it down. One of the things I noticed right away was how similar c# is to javascript so that also added some comfort when creating this project. So below is a script which makes the camera follow behind the player object(which is just a cube).

CAMERA POSITION
```
using UnityEngine;

public class follow : MonoBehaviour
{
    // Start is called before the first frame update
   public Transform player;
   public Vector3 offset;
    // Update is called once per frame
    void Update()
    {
        transform.position = player.position + offset;
    }
}

```

This script is mounted onto the main camera object. It has the postion of the camera(transform.position) set to the current position of the player object plus an offset(the difference of space between the camera and the player). The offset can be set in the engine by adjusting the x,y, and z coordinates(this will determine the space between the camera and player). This script is using update() so it constantly sets the new camera position every frame of the game. The following is the script that reacts to user input on the keyboard which controls the player objects location. 

PLAYER OBJECT MOVEMENT
```
using UnityEngine;

public class movement : MonoBehaviour
{ public Rigidbody rb;
public float sidewaysForce = 500f;
public float forwardForce = 2000f;
    // Start is called before the first frame update
    // void Start()
    // {
    //     rb.AddForce(0,200,500);
    // }

    // Update is called once per frame
    void FixedUpdate()
    {
          rb.AddForce(0,0,forwardForce * Time.deltaTime); //evens out framerate
          if(Input.GetKey("d")){
              rb.AddForce( sidewaysForce * Time.deltaTime,0,0);
          }
             if(Input.GetKey("a")){
              rb.AddForce(-sidewaysForce * Time.deltaTime,0,0);
          }
    }
}
```

Essentially this script is using a condtional event handler that is listened for every frame of the game. The event being the key input and the listener is either moving the cube to the left or to the right. Since it is being listened for every frame holding the d key down will move the cube to the right for every frame it's held down for. This script is very powerful because it gives us the ability to control the player now.  The sideways is also create and set on the unity side, not script side. I do not remember the exact reason why Time.deltaTime is used, here's the first answer Google found. 

"Time. deltaTime allows you to move things not by frame (which would be too fast or too slow depending on your hardware). ... The time in seconds it took to complete the last frame (Read Only). Use this function to make your game frame rate independent"

So this allows the game to run specific to the system it is run on, allowing for a smoother experience. The following script is in charge of detecting if the object is an obstacle and if it's an obstacle disable the players ability to move. 

HIT DETECTION
```

using UnityEngine;

public class collision : MonoBehaviour
{
   public movement move;
  
   void OnCollisionEnter(Collision collisionInfo )
   {
if(collisionInfo.collider.tag =="obstacle"){
move.enabled = false;
}
   }
}

```

public movement move is the movement script mentioned earlier in this blog.  The rest is checking for object the player hits has a tag called 'obstacle'. This tag has to be given to the obstacle object on the unity side. So all together the logic is - if the object the player object hits has a tag named 'obstacle', then the movement script wil be disabled and the player can no longer move. Although I still have alot to learn and get comfortable with I'm very excited to continue this project and learning more about programming and game development. 


