# 100 Days Of Game Dev - Round 2 Log

<a name="toc"></a>
### Table of Contents 
|Day                               |Focus                                      |Day                                 |Focus                                       |
|:--------------------------------:|:-----------------------------------------:|:----------------------------------:|:------------------------------------------:|
|[Day 1](#day-1)    **01/10/19**   | Chapter 2 - State Driven Agent Design     |[Day 2](#day-2)    **01/11/19**     | Global States	         					           |
|[Day 3](#day-3)    **01/12/19**   | Telegrams                                 |[Day 4](#day-4)    **01/13/19**     | Message Dispatching                        |
|[Day 5](#day-5)    **01/14/19**   | Steering Behaviors Revisited              |[Day 6](#day-6)    **01/15/19**     | Moving Agents                              |
|[Day 7](#day-7)    **01/16/19**   | TBD          							               |[Day 8](#day-8)    **01/17/19**     | TBD                	         			         |

### Day 0: January 09, 2019 

With a new perspective on this, I'm excited to give this another try. I will be working through some AI programming by following the book, [Programming Game AI by Example](https://www.amazon.com/Programming-Example-Wordware-Developers-Library/dp/1556220782). It will be an interesteing challenge as the book shows its examples in C++ and does not appear to have an engine which provides some of the basic toolsets like collision detection and definition. 

After that, three years ago when, a couple months into my game development journey I found a development challenge. The challege is a 10 game challenge each with progressively more difficult game play to learn with. Although I started this challenge 3 year ago, I dont give up. So I will revisit it and attempt to complete it. 

So to summarize, goals for the next 100 days: 
- Working through the book [Programming Game AI by Example](https://www.amazon.com/Programming-Example-Wordware-Developers-Library/dp/1556220782)
- 10 Game Challenge
  - Pong
  - Snake
  - Breakout
  - Missle Command
  - Space Invaders
  - Asteroids
  - Tetris
  - Pacman
  - Ikari Warriors 
  - Super Mario Bros

Let's see how this goes!

[Table of Contents](#toc)

----------
<a name="day-1"></a>
### Day 1: Chapter 2 - State Driven Agent Design
#### January 10, 2019 

**Today's Focus**: State Driven Design. 

**Details**:
	- Implemented state driven design
	- Implemented basic State machine

**Thoughts** 

The book starts with a math and physics primer, that's why we start at Chapter 2. I did some work in the past to try to implement this so I reimported it. Spent most of today's time reading the chapter. From what I understand the State Design Pattern is the concept of defining a state such that it contains all the information it needs to perform its transitions to another state as well as getting a reference to the owner of the state so that when the state is executed it knows which agent to act on. Additionally, states would be derived from a common interface so that each state could be acted upon similarly. 

The book uses the singleton pattern for each state so that there would only ever be one instance of state at any given time. There are some things I dont like too much so far about this pattern. One of them being that each state has to know what state to transition to, why, and when to do so. I can see that getting a bit tricky the more states you add in. It would be a nightmare to implement without a state transition diagram of some sort. 

One of the challenges I face in going through this book is that the book is written in C++ and seems to define some primative types. Types that you would otherwise see provded for you in a game engine. I want to implement these mechanics in a way that they are reusable to me but also follows the book as i know from having peeked ahead that the book will progressively build upon and reuse the objects created from previous chapters. Got a lot to look forward to. 

Tomorrow Global States, or "state blips" as the book puts it.

#### Agent Output
![Agent Output](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/r2/day1/state-driven-agent.gif)

**Link(s) to work**: 
[Github](https://github.com/Kpable/Kpable-Labs/commit/b26e35978a96e356cdd4f2e39caee60f390c9a78)

[Table of Contents](#toc)

----------
<a name="day-2"></a>
### Day 2: Global State Definition
#### January 11, 2019 

**Today's Focus**: Global State Design. 

**Details**:
	- Implemented a global state
	- implemented a second agent
	- Templatized a singleton state

**Thoughts** 

This took a little longer to implement than I would've hoped. Reading through the chapter the concept was pretty simple to understand. A global state is a state in which can be triggered at any time and then reverts to the previous state when it's done. It's a lot like the "Any State" box in Unity's animator which essentially acts as a giant state machine. I did some tracing through the example source to find that the global state was being called at all times in the state machine. Which in hindsight, duh thats what would happen. But again i am translating C++ environment to C# Unity environment and of course my own coding style. Which i'm finding to be a hugely beneficial learning tool as i now have to fully understand the original implementation and think through how to translate it. 

Once i figured it out i had some fun with it. My new pet robot has a 1 in 10 chance to compute life in its spare time. 


#### Global State Output
![Agent Output](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/r2/day2/global-state.gif)

#### Text Output
```
Soft_Eng: Writing some code, making some bugs, fixing some bugs
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Writing some code, making some bugs, fixing some bugs
Soft_Eng: Gotta step out and take a break
Soft_Eng: Gonna log my hours so far
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Logging my hours so far. Total Hours: 12
Soft_Eng: A good day's work, time to head home
Soft_Eng: Alright, enough logging
Soft_Eng: Gotta go home
Pet_Robot: I am a robot, are you amused master?
Pet_Robot: I... am.. a... Robot?
Soft_Eng: So tired must sleep
Pet_Robot: I am a robot, are you amused master?
Pet_Robot: What does it mean to be a Robot?
Pet_Robot: SpawnThread(ComputateLife);
Soft_Eng: So tired must sleep
```
**Link(s) to work**: 
[Github](https://github.com/Kpable/Kpable-Labs/commit/5e0e26594f010a4d4f9a60b3fd71c182b838fbc6)

[Table of Contents](#toc)

----------
<a name="day-3"></a>
### Day 3: Global State Definition
#### January 12, 2019 

**Today's Focus**: Telegrams

**Details**:
  - Implemented telegram structure
  - Beginnings of integrating a message dispatcher


**Thoughts** 
Unfortunately not much to show today. I didnt get a chance to fully implement the message passing between my two agents. Did get the inital classes written up. 

In addition to reading the chapter, i spend time comtemplating how i'd implement the telegram sending through the system. Its easy to just implement it the same way. I'm curious to how i would do it in unity with my current knowledge. I'm thinking about how this could be implemented using scriptable objects. While at the same time too much deviation may cause future problems when the book reuses previous implementations. 


**Link(s) to work**: 
[Github](https://github.com/Kpable/Kpable-Labs/commit/71cdc0d66614f4e4c5a998b6474cdedd7f1d6f8a)

[Table of Contents](#toc)

----------
<a name="day-4"></a>
### Day 4: Message Dispatching
#### January 13, 2019 

**Today's Focus**: Message Dispatching

**Details**:
  - Implemented message dispatching
  - Got the two agenst to send messages to one another


**Thoughts** 
I like the ease of which setting up the templatized state/singleton state helped with creating new states  quickly, There were several times i had to add a few new stats and it was no problem at all. Of course the problem of not having a diagram for my example would make things worse the more i add but it wasnt too bad since i'm still dealing with single digit number of states. 

The dispatching wasnt too hard to implement just a matter of making sure the message handling is plumbed through correctly. 

I would really like to be able to include the debug for when messages are dispatched and queued. Perhaps i will do that tomorrow. 

In any case, that is the end of Chapter 2. 

What i've learned from this chapter:
 - Finite state machines
 - State driven design
 - Autonomous Agents
 - Telgram Structure
 - Message Dispatching


**Link(s) to work**: 
[Github](https://github.com/Kpable/Kpable-Labs/commit/a6edfe86268bb4aaffb06d4ef278086f6958db33)
[Full Text Output](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/r2/day4/fsm-output.txt)

#### Tail End of Text Output
```
Soft_Eng: Thats a good quick gaming session, time to go back to work
Soft_Eng: Leaving Home
Soft_Eng: Going To Work
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Writing some code, making some bugs, fixing some bugs
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Writing some code, making some bugs, fixing some bugs
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Writing some code, making some bugs, fixing some bugs
Soft_Eng: Gotta step out and take a break
Soft_Eng: Gonna log my hours so far
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Logging my hours so far. Total Hours: 39
Soft_Eng: A good day's work, time to head home
Soft_Eng: Alright, enough logging
Soft_Eng: Gotta go home
Pet_Robot: I... am.. a... Robot?
Pet_Robot: What does it mean to be a Robot?
Pet_Robot: SpawnThread(ComputateLife);
Soft_Eng: So tired must sleep
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: So tired must sleep
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: So tired must sleep
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Thats a good quick gaming session, time to go back to work
Soft_Eng: Leaving Home
Soft_Eng: Going To Work
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Writing some code, making some bugs, fixing some bugs
Pet_Robot: I... am.. a... Robot?
Pet_Robot: What does it mean to be a Robot?
Pet_Robot: SpawnThread(ComputateLife);
Soft_Eng: Writing some code, making some bugs, fixing some bugs
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Writing some code, making some bugs, fixing some bugs
Soft_Eng: Gotta step out and take a break
Soft_Eng: Gonna log my hours so far
Pet_Robot: I am a robot, are you amused master?
Soft_Eng: Logging my hours so far. Total Hours: 42
Soft_Eng: A week's work, time for the weekend!
Soft_Eng: Alright, enough logging
Soft_Eng: It's the weekend now Ekko, time to sleep buddy
Pet_Robot: Very well Human Companion.
Pet_Robot: Entering Standby Mode
```

[Table of Contents](#toc)

----------
<a name="day-5"></a>
### Day 5: Steering Behaviors
#### January 14, 2019 

**Today's Focus**: Steering Behaviors Revisited

**Details**:
  - Imported work done with R1

**Thoughts** 
Chapter 3, My old friend. This chapter is steering behaviors and the one that caused me to stop the first round of 100 days. I explain why in the last day of the r1 log so I wont repeat myself here. 

I've actually used some of that work before in attempting to convert the system to usage in a ScriptableObject fashion in allowing myself to define different Arrive behaviors for examples with different parameters and be able to hot swap them as needed. 

Thats kind of the foundation I am working on. Its late today and i'm tired though so i dont have much more than the import done. Nothing pretty to look at today. 

[Table of Contents](#toc)

----------
<a name="day-6"></a>
### Day 6: Moving Agents
#### January 15, 2019 

**Today's Focus**: Vehicle Object

**Details**:
  - Worked on moving entity hierarchy used in steering calculation
  

**Thoughts** 

There are several challenges i'm presented to here, some of which i've mentioned before but here int this chapter its most prominent. That is my coversion into Unity from the book's implementation. A lot of the definitions being made such as, bounding radius, position, mass, velocity, etc., are defined in components such as Transform and Rigidbody. As well as needing to have some of the functionality to inherit from MonoBehaviour. 

Already thats a problem as i cannot new up a MonoBehavior derived script and i cant act on the components of a MonoBehaviour without some extra linking of components to non MonoBehaviour classes. Not ideal. 

Admittedly, i am adding more to my struggles as i just realized i have been trying to mimic a 2D implementation on a 3D agent. Unfortunately just now occured to me. I'm still planning to work with 3D objects because i hope to translate all this to 3d some day but i figure i'll start with 2D and just rotate the world orientation so that. 

Unfortunately this looks like it'll require more reading and redesigning on my part but i'll make it work. Not much to look at but i got the Arrive Scriptable Object steering behaviour to run. 


#### Agent Moving via Arrive behavior
![Agent Output](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/r2/day6/arrive.gif)

**Link(s) to work**: 
[Github](https://github.com/Kpable/Kpable-Labs/commit/9be48bb7ab6a912bed8217f914ea7bd0ed74c408)


[Table of Contents](#toc)

----------
<a name="day-7"></a>
### Day 7: Obsticle and Wall Avoidance
#### January 16, 2019 

**Today's Focus**: Obsticle and Wall Avoidance

**Details**:
  - Reading through obsticle and wall avoidance

**Thoughts** 
I decided to read through the chapter fully before starting to implment one behavior at a time as i did last time. I found some difficulties in doing that and in reading through this time it seems that was the authors intent. 

The obsticle avoidance implmentation i will likely change as i dont liek the concept of having any given vehicle track every obticle in the game world. A possibile alternative i think of now is maintaining a trigger or scanning in a radius to only get a subset of the world's obsticles. 

Wall avoidance which is similarly implemented by passing all the walls in the game world for the vehicle to iterate through to check for intersections with the some feelers of defined length. I figure i can produce the same result with some raycasting in front of the vehicle. I dont know, we'll se how that works. 

[Table of Contents](#toc)
----------
<a name="day-8"></a>
### Day 8: Group behaviors
#### January 17, 2019 

**Today's Focus**: Group behaviors

**Details**:
  - Reading through the chapter and different behaviors
  - Introduction to group behaviors

**Thoughts** 
There isn't anything to show for today either  as i spent my time today reading more of the chapter to better understand the individual behaviors and the implementation. Good thing i did too since it seems the implementation of the code does not have good examples for one behavior at a time but all of them together, toggled using some flags. 

It also includes the group behaviors of cohesion, alignment, and seperation which introduces the vehicles to their neighbors. I noticed a section on spacial partitioning but i will stop before then and take a look at how to implement all of the behaviors with toggle flags and summing functions. The group behaviors sounds akin to an example i read through years ago with boids. 

[Table of Contents](#toc)
----------
<a name="day-9"></a>
### Day 9: Summing Functions
#### January 18, 2019 

**Today's Focus**: Summing Functions

**Details**:
  - Sadness, lost some work

**Thoughts** 
I was going through implementing all the steering behaviors with toggle flags and wieghts as well as summing functions of weighted, prioritized and dithered but when i finished up for the day and went to commit i accidentally reverted and lost everything. So much sadness. 

Good thing is i managed to save the bulk of the changes thanks to the delay of Visual Studio refreshing the project when its been modified externally. I was able to copy all my current work and attempt to recreate it. 
Needless to say i rage quit for the day. I'll pick this back up tomorrow. 


**Link(s) to work**: 
[Github](https://github.com/Kpable/KLib/commit/f6d70434726211ca9b604a68133f87d56edae537)

[Table of Contents](#toc)

----------
<a name="day-10"></a>







<!-- 
<a name="toc"></a>
### Table of Contents 
|Day                               |Focus                                      |Day                                 |Focus                                       |
|:--------------------------------:|:-----------------------------------------:|:----------------------------------:|:------------------------------------------:|
|[Day 1](#day-1)    **09/16/18**   | 100 Days Log Generator                    |[Day 2](#day-2)    **09/17/18**     | 100 Days Log Generator - Dynamic Additions |
|[Day 1](#day-1)    **09/18/18**   | 100 Days Log Generator - Dynamic Removals |[Day 2](#day-2)    **09/19/18**     | TBD                                        |

### Day 0: August 18, 2018 

With a new perspective on this, I'm excited to give this another try. I will be working through some AI programming by following the book, [Programming Game AI by Example](https://www.amazon.com/Programming-Example-Wordware-Developers-Library/dp/1556220782). After that, who knows. Theres a lot of game dev I am interested in.

[Table of Contents](#toc)

----------
<a name="day-1"></a>
### Day 1: Log Generator
#### September 16, 2018 

**Today's Focus**: Create a form that would populate the logs for each day. 

**Details**:
	- Created a good looking form

**Thoughts** My initial go at the 100 days of game development, one of the most tiresome parts were the copying and pasting to enter a new log. Not that it takes more than 5 minutes but if i can make it easier and faster to put in the entries for this, why not! I got the form more or less put together, all thats left is to make it actually generate the markdown. 

**Examples**: 

#### Front End Form
![Front End Form](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/r2/day1/log-form.png)

**Link(s) to work**: 
[Github](https://raw.githubusercontent.com/Kpable/kpable.github.io/4b596e0ae8df5ad8ce3b844e47bdf751c75ad701/100daysform.md)
[Form](https://kpable.github.io/100daysform)

[Table of Contents](#toc)
----------
<a name="day-2"></a>
### Day 2: Log Generator - Dynamic Additions
#### September 17, 2018 

**Today's Focus**: Make the elements and links of the form dynamically add 

**Details**:
	- Added some jQuery to add a new element group to the list

**Thoughts** It's been a long while since I wrote any jQuery but figured it would be a quick way to add some on click events and find and clone DOM elements. I didn't get very far since I spent a lot of the short time i spent today just figuring out jQuery syntax and making the javascript work within the context of the Jekyll site. Don't know why but I had to put the script resource along with the others as opposed to the file I was working in. Anyways, lots of cobwebs on my web dev scripting. 

**Examples**: 

#### New Added Entries
![New Added Entries](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/r2/day2/new-additions.png)

**Link(s) to work**: 
[Github](https://github.com/Kpable/kpable.github.io/commit/2aa811ddfac3072111cc20c5649ecaf6d1657586)
[Form](https://kpable.github.io/100daysform)

[Table of Contents](#toc)
----------
<a name="day-3"></a>
### Day 3: Log Generator - Dynamic Removals
#### September 18, 2018 

**Today's Focus**: Make the elements and links of the form dynamically remove

**Details**:
	- Added some jQuery to remove an new element group from the list

**Thoughts** Another quick progress report. I ran into an issue with identifying the elements as I initially am selecting the elements by id but that should be unique. It adds some complexity in removing the elements but i'm thinking it doesnt have to be perfect for now, just has to do the job of generating the log. In the end, i'm hoping it's just a series of string replacements. I started work on testing out the generation but ran out of time. 

**Examples**: 

#### Basic jQuery
~~~~
$("#new-example-button").click(function(){
    numElements += 1;
    var clone = $("#example-group").clone(true);
    clone.attr("id", "example-group" + numElements);
    $(this).parent().before(clone);
});

$(".fa-minus").click(function(){
	$(this).parents("#example-group").remove(); 
	$(this).parents("#link-group").remove();
});

$("#new-link-button").click(function(){
    numLinkElements += 1;
    var clone = $("#link-group").clone(true);
    clone.attr("id", "link-group" + numLinkElements);
    $(this).parent().before(clone);
});

$("#generate").click(function(){
	alert("generate");
	var dayNumber = $("#day-number").text();
	var title = $("#title").text();
	var date = $("#date").text();
	var thoughts = $("#thoughts").text();
});
~~~~


**Link(s) to work**: 
[Github](https://github.com/Kpable/kpable.github.io/commit/1688333dab19bf8de327575cbfeb2d6cc81fa677)
[Form](https://kpable.github.io/100daysform)

[Table of Contents](#toc)
----------

-->