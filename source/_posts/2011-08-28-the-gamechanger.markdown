---
layout: post
title: "The Gamechanger"
date: 2011-08-28 22:14
comments: true
categories: [Games, Pressure, Student]
---
## "You can't die?" ##
"Well no, I didn't get to implement that logic," 
I replied to our game design professor.
He frowned, and prodded me again, 
   >"What about the multiplayer functionality?"

"Well...," he immediately frowned again and I stammered, "The code is there to do multiplayer but
I haven't been able to finish it yet." At this point in time, Ryan, Mike, and myself were roughly 45 minutes out from presenting our final project
for a game design class to a roughly 100 people. 


The game was a top down space shooter. Beginning in the fall, the class aimed to teach
students how to craft a game using the Microsoft XNA framework with a capstone presentation and playable game. From the start, we wanted a multiplayer game.
We also wanted some sort of physics mechanic. We had grand visions... this was going to be a fantastic game.
{%img http://thesecondcoming.googlecode.com/svn/trunk/data/textures/Umbrarak.png %}

<!--more-->
Early on in the semester, we were doing well. We had adopted a game engine for XNA. Mike was hard at work on the sprites and audio. At the first milestone,
we were the only team that even had a moveable player sprite!

I recall laughing at the other teams. They were crashing. I had built a level editor. They had no artwork. We had a *soundtrack*.

At the second milestone, a month before finals, the other teams had caught up. I was still confident. Ryan had finished the AI for enemies. Mike's artwork was fantastic.
I had built a few levels with my editor and you could play through them and kill the bosses.

{% img http://thesecondcoming.googlecode.com/svn/trunk/data/textures/chromothanim.png "The Chromoth Boss" %}

The night before the presentation, I stayed up coding furiously trying to polish and implement all of the features we had promised. Birds were chirping, I had to call it quits.
All during classes the next day, I was sweating lead. I had left the code in a state that would build and run successfully, but a *lot* of our design was missing. Finally, out of class
I met up with my teamates. We got to work, tweaking this and that. We happily fired up our game for our professor to gut-check before the presentation.

> "How do I know if I've won or not?"

*Dang!* We started typing feverishly. It all came together in one method.


``` csharp
      void _checkLevel();
```


This method was located in "SinglePlayerLevel.cs" yet this was a multiplayer game. I never got around to refactoring. Just to be clear, I added a comment at the top:

> "Set up all of the objects for the level. Very Important!"

Ignoring the naming convention of the method signature, you'll find this method performs the following:

* Checks if a player is dead
* Counts down to determine if they need to respawn 
* If the other player is still alive it respawns the dead player. 
* If both players are dead it proceeds to the "Game Over" screen (ahem... screen 5 hardcoded)
* Finally if the last boss is dead (null) and we're on the last level.. display the winning screen.

You can see below just how poorly written it was. Overall, the entire game was *poorly* written and I'm glad _My_C0dE="My Hell".  But, we delivered *something* and that felt great. 

Since this is the first post, we welcome all forms of criticism. Comment, fork, and contribute. Share your hellish stories.

{%gist 1177756 %}
