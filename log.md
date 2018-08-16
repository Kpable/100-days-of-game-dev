# 100 Days Of Game Dev - Round 1 Log

<a name="toc"></a>
### Table of Contents 
|Day                               |Focus                                   |Day                                 |Focus                                 |
|:--------------------------------:|:--------------------------------------:|:----------------------------------:|:------------------------------------:|
|[Day 1](#day-1)    **06/24/18**   | Object Pooling                         |[Day 2](#day-2)    **06/25/18**     | Spaceship Behavior                   |
|[Day 3](#day-3)    **06/26/18**   | Shmup World Wrap                       |[Day 4](#day-4)    **06/27/18**     | Shmup Weapons                        |
|[Day 5](#day-5)    **06/28/18**   | Health on Meteors                      |[Day 6](#day-6)    **06/29/18**     | Environmental Hazard - Splitter      |
|[Day 7](#day-7)    **06/30/18**   | Weapons Refactoring                    |[Day 8](#day-8)    **07/01/18**     | Paralax Backgrounds                  |
|[Day 9](#day-9)    **07/02/18**   | Shmup Power Ups                        |[Day 10](#day-10)  **07/03/18**     | Spiral Gun Spawning                  |
|[Day 11](#day-11)  **07/04/18**   | Bullet Reflection                      |[Day 12](#day-12)  **07/05/18**     | Steering Behavior - Seek             |
|[Day 13](#day-13)  **07/06/18**   | Steering Behavior - Arrive             |[Day 14](#day-14)  **07/07/18**     | Steering Behavior - Flee             |
|[Day 15](#day-15)  **07/08/18**   | Steering Behavior - Evade              |[Day 16](#day-16)  **07/09/18**     | Steering Behavior - Wander           |
|[Day 17](#day-17)  **07/10/18**   | Steering Behavior - Obstacle Avoidance |[Day ?](#day-18)   **08/02/18**     | End                                  |

<!-- 
|[Day 19](#day-19)  **07/12/18**   | Steering Behavior - Pursuit            |[Day 20](#day-20)  **07/13/18**     | Steering Behavior - Hide             |
|[Day 21](#day-21)  **07/14/18**   | Steering Behavior - Path Following     |[Day 22](#day-22)  **07/15/18**     | World Wrap 3D                        |
|[Day 23](#day-23)  **07/16/18**   | TBD                                    |[Day 24](#day-24)  **07/17/18**     | TBD                                  |
|[Day 25](#day-25)  **07/18/18**   | TBD                                    |[Day 26](#day-26)  **07/19/18**     | TBD                                  |
|[Day 27](#day-27)  **07/20/18**   | TBD                                    |[Day 28](#day-28)  **07/21/18**     | TBD                                  |
|[Day 29](#day-29)  **07/22/18**   | TBD                                    |[Day 30](#day-30)  **07/23/18**     | TBD                                  |
 -->
<!-- 
### Day 0: June 23, 2018 

Because arrays start at 0

[Table of Contents](#toc)
-->

----------
<a name="day-1"></a>
### Day 1: June 24, 2018 

**Today's Focus**: Learn and implement object pooling.

**Details**:
  - Went through brackeys tutorial on [Object Pooling](https://www.youtube.com/watch?v=tdSmKaJvCoA).
  - Looking at other resources to see other implementations to improve usability. 
  - Did a little clean up in the hierarchy to make pools manageable

**Thoughts** I've always been curious, never really had a need to implement them. I worked on a shmup for a [Ludem Dare 41](https://github.com/Kpable/Dimensional-Rift-Escape) and I think this would be good to implement in that for when I continue work on it. All those bullets flying around. Plus I think I recall back when I played a MegaMan game, where I could only shoot 3-4 bullets before the first bullet I shot vanished to be the new bullet I fired. 

**Examples**: 

#### A bunch of squares and circles being spawned
![Day 1 Example](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day1-object-pools/object-pooling-2.gif)

#### Hierarchy cleanup
![Day 1 Example](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day1-object-pools/parenting.gif)

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/object-pools/Assets/Misc/Object%20Pools)

[Table of Contents](#toc)
----------
<a name="day-2"></a>
### Day 2: June 25, 2018 

**Today's Focus**: Spaceship behavior

**Details**:
  - Taking a look at the mechanics around 2D spaceship behaviors
  - Looked at implementation without using the RigidBody2D component
  - Looked at implementation using the RigidBody2D component
  - Still curious about implementation without the built in physics, but went with the built in physics for now. 

**Thoughts** So that shmup I mentioned yesterday, [Ludem Dare 41](https://github.com/Kpable/Dimensional-Rift-Escape), I threw together some quick and dirty ship movement modified from some tutorial that I had seen some time ago. It's for this reason, and the fact that I have an outstanding task from Jan. 2016 to complete a 10 game beginner developer challenge which including cloning asteroids, is why I'm taking a closer look at this. 

**Examples**: 

#### Movement without a RigidBody2D
![Spaceship behavior Example](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day2-spaceship-behavior/spaceship-behavior.gif) 

#### Movement with a RigidBody2D
![Spaceship behavior RigidBody2D Example](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day2-spaceship-behavior/spaceship-behavior-rigidbody2d.gif) 

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/spaceship-behavior/Assets/Misc/Spaceship%20Behavior)

[Table of Contents](#toc)
----------
<a name="day-3"></a>
### Day 3: June 26, 2018 

**Today's Focus**: Get Spaceship to World Wrap All Pretty Like

**Details**:
  - Shift ship position to wrap around defined world bounds. 
  - Simulate the sprite being sliced at edge of screen and appearing on other end of screen.
  - Got distracted for a bit and wondered if I can quickly tweak the Spaceship behavior to act as a lander. 


**Thoughts** I want to get the world wrap set up so that its not a sudden jump. I remembered reading an article, watching a video, and/or reading some design secrets in which instead of performing some fancy math and rendering magic, the appearance of the ship being sliced as it goes off screen and the other half showing up in the wrapped other side was done by creating ghost copies of the sprite that always follow the player's rotation and relative position. I don't know how this is going to work once more object need that "ghost" effect but we'll find out right. 

**Examples**: 

#### Sprite split effect I was looking for 
![World Wrap "Ghosting" Example](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day3-world-wrap/ship-split.gif) 

#### Behind the scenes in the editor
![World Wrap "Ghosting" In Editor](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day3-world-wrap/ship-split-editor.gif) 

#### Also my lander ~~distraction~~ curiousity
![Lander behavior Example](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day3-world-wrap/lander.gif) 


**Link(s) to work**:
- [Github (Spaceship)](https://github.com/Kpable/Kpable-Labs/tree/misc/spaceship-behavior/Assets/Misc/Spaceship%20Behavior)
- [Github (Lander)](https://github.com/Kpable/Kpable-Labs/tree/misc/spaceship-behavior/Assets/Misc/Lander%20Behavior)

[Table of Contents](#toc)
----------
<a name="day-4"></a>
### Day 4: June 27, 2018 

**Today's Focus**: Shmup Weapons systems 

**Details**:
  - Imported weapons implementation from older tutorial. Not final but good enough to get a handle on how to implement weapons system. 
  - Updated projectiles to utilize previously done object pooling. 
  - Ensuring projectiles share rotation on ship when firing. 


**Thoughts** I remembered a tutorial I completed a while ago in which a similar weapons system was implemented. That implementation didn't utilize object pools and was more of the strafe left and right kind of shmup but I liked how the weapon details were defined in one place and it was retrieved when setting the projectile type. 

**Examples**: 

#### Single shot blaster weapon
![Single shot blaster Example](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day4-shmup-weapons/firing-blaster.gif) 

#### Spread shot blaster weapon
![Spread shot blaster Example](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day4-shmup-weapons/firing-spread.gif) 


**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/shmup-weapons/Assets/Misc/Shmup%20Weapons)

[Table of Contents](#toc)
----------
<a name="day-5"></a>
### Day 5: June 28, 2018 

**Today's Focus**: Health and Destroying objects

**Details**:
  - Stopped projectiles from colliding with each other 
  - Processed projectiles impacting another object with health
  - Reduced that object's health by damage dealt by projectile
  - Destroy the object when health reaches zero

**Thoughts** Kinda cheated a bit here since health is something I've coded and used before so not a new thing to look at but I'm doing this to see how these different shmup components need to interact with one another so I went with it. The more I use it, the more I get to find areas of improvement for it. This is all leading to something.. 

**Examples**: 

#### Meteor Running out of health
![Meteor running out of health](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day5-health/destroying-meteor.gif) 


**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/shmup-weapons/Assets/Misc/Shmup%20Weapons)

[Table of Contents](#toc)
----------
<a name="day-6"></a>
### Day 6: June 29, 2018 

**Today's Focus**: Splitter Behavior (Environmental Hazard)

**Details**:
  - Have meteor split into smaller copies of itself
  - Pass splitting information onto smaller copies. 
  - Pooled Meteors since splitting them makes a lot. 

**Thoughts** So I dub these kinds of behaviors environmental hazards because in looking at some common themes among platformers and some other types of games, there's often an enemy that when you do enough damage to kill it, it splits off into smaller weaker versions of itself that do the same thing until you've killed enough. Like the blob creatures from Ori and the Blind Forest, giant manta may from Super Mario Sunshine, Some Goombas in Mario, etc.  There are others I want to look at like crawlers, spine shooters (always shoot like 3-5 needles), droppers (hang from the ceiling until you pass under them) etc. This one is just currently applicable. 

**Examples**: 

#### Meteor Splitting up
![Meteor Splitting up](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day6-splitter-behavior/meteor-splitting.gif) 

#### Splitting Parameters
![Splitting Paramters](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day6-splitter-behavior/split-params.gif) 

#### Passing the Params Along
![Passing Parameters](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day6-splitter-behavior/split-function.gif) 

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/shmup-weapons/Assets/Misc/Shmup%20Weapons)

[Table of Contents](#toc)
----------
<a name="day-7"></a>
### Day 7: June 30 2018 

**Today's Focus**: Weapons refactoring

**Details**:
  - Changed the origin of projectiles to around the ship

**Thoughts** Wanted to refactor how the weapons work. Previously the I imported it from a tutorial but I want to add some more versatility. The plan is to have the gun objects circle around the ship depending on the weapon type. 

**Examples**: 

#### Spread Wepons Originating from Surrounding Objects
![Spread Weapons](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day7-weapons-refactoring/weapons-refactored.gif) 

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/shmup-weapons/Assets/Misc/Shmup%20Weapons)

[Table of Contents](#toc)
----------
<a name="day-8"></a>
### Day 8: July 1, 2018 

**Today's Focus**: Parallax Backgrounds

**Details**:
  - Modified parallax implementation from a tutorial to work
  - Stardust and stars move with respect to target object, in this case a ship. 

**Thoughts** I completed a tutorial a while back that incorporated a parallax effect. I had to massage it a bit to get it to work right but it looks good. Theres still some work left to do to get it to work a bit nicer, but for the interim its a good start. 

**Examples**: 

#### Parallax Effect
![Parallax Effect](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day8-parallax-backgrounds/parallax.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/parallax/Assets/Misc/Parallax)

[Table of Contents](#toc)
----------
<a name="day-9"></a>
### Day 9: July 2, 2018 

**Today's Focus**: Shmup Power Ups  

**Details**:
  - Incorporated power up 
  - Change weapons when the ship collides with it. 

**Thoughts** These are a must of any given shmup. I had to incorporate a power-up to allow the ship to change weapons. Next step for this would be to be able to set a power-ups type so that enemies can spawn power-ups on death. 

**Examples**: 

#### Ship hitting power ups
![Power ups in effect](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day9-power-ups/power-ups.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/develop/Assets/Misc/Power%20Ups)

[Table of Contents](#toc)
---------- 
<a name="day-10"></a>
### Day 10: July 3, 2018 

**Today's Focus**: Weapon Redux - Spiral Guns

**Details**:
  - Looked into how to spawn guns around the ship
  - Had some fun with angles

**Thoughts** I was having some issues with getting the projectiles to spawn from different gun locations. I also wanted to upgrade it from manually defined positions (which I would like but not right now) to just around the ship depending on the number. Right now I was only thinking with regard to single shot and triple shot but the possibilities... 

**Examples**: 

#### Changing Number of Guns
![Spiral Gun Spawning](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day10-spiral-guns/gun-spawning.gif)  

#### Fun with Angles
![Spiral Gun Spawning Code](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day10-spiral-guns/angle-code.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/develop/Assets/Misc/Shmup%20Weapons)

[Table of Contents](#toc)
----------
<a name="day-11"></a>
### Day 11: July 4, 2018 

**Today's Focus**: Bullet Reflection

**Details**:
  - Reflect bullets of surfaces
  - Set Fixed reflection for now

**Thoughts** There was this Dexter's Laser Lab flash game many years ago I had a blast with (ha! laser blast! punSkills++;). It was a puzzle game where you had orient some mirrors so that when the laser fired it would hit all the balloons in the level. It was fun and I have seen that mechanic show up again in other games as well. Such as Zeldas in which a dungeon required the reflection of light, most recently in Song of the Deep in which some reflective shells needed to be rotated to trigger doors or switches. I wanted to look at how that could be incorporated. For now though, i got some fixed reflection going so that bullets will bounce in the direction the reflective object states. Next step, doing it dynamically with raycasts and line renderer. 

**Examples**: 

#### Fixed Bullet Reflection
![Bullets bouncing off surfaces](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day11-lasers/fixed-reflection.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/lasers/Assets/Misc/Lasers)

[Table of Contents](#toc)
----------
<a name="day-12"></a>
### Day 12: July 5, 2018 

**Today's Focus**: Steering Behaviors - Seek

**Details**:
  - Created a Vehicle object
  - Applied Seek Behavior
  - Made Space Invader for fun

**Thoughts** AI is a big interest to me but I have yet to really dive into learning some concepts. Steering Behaviors are a good place to start I think. A lot of this i've looked at briefly in the past and even created a Unity implementation of the code written in [Programming Game AI by Example](https://www.amazon.com/Programming-Example-Wordware-Developers-Library/dp/1556220782). I never fully got a grasp of all of the concept and eventually moved on to other topics of interest but this is something (like everything that I've previously committed to) that I don't want to give up on. This will be a good way to take a real good look at these behaviors and learn what's going on with them. I'm using [The Coding Train](https://www.youtube.com/watch?v=4hA7G3gup-4) as reference as well. 

**Examples**: 

#### Seek Behavior
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
---------- 
<a name="day-13"></a>
### Day 13: July 6, 2018 

**Today's Focus**: Steering Behaviors - Arrive

**Details**:
  - Implement Arrive behavior
  - Learned delta time with these behaviors doesn't need to be directly applied as each frame will update all needed values
  - Learned difference between clamp and multiply
  - Learned obvious in hindsight lessons

**Thoughts** I put a lot of "learned" in the details because I spent a lot of time debugging this bevaior for 3 reasons. The first, arrive should you know arrive and that wasn't what I was seeing. This was because I was multiplying Time.deltaTime to the acceleration unecesesarily. It was giving me odd behavior. Second, I inteded to clamp the steering force to the max force of the vehicle but while my mind thought, "hmm this is clamping", what the code rightly saw was "hmm this steering force will be multiplied to max, got it". Once that finally stood out, problem three was a silly one. I had left seek behavior active when I was testing arrive. This resulted in arrive behavior with a giggle once it arrived as seek would always move past the mark and return. Seek has no chill and will always move at max force. 

**Examples**: 

#### Arrive Behavior
![Arrive Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day13-sb-arrive/arrive.gif)  

#### Wiggles
![Arrive and Seek Behavior = Wiggles](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day13-sb-arrive/wiggles.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
---------- 
<a name="day-14"></a>
### Day 14: July 7, 2018 

**Today's Focus**: Steering Behaviors - Flee

**Details**:
  - Implemented Flee 
  - Played a bit with Weighting the steering force

**Thoughts** My initial thought was that the Flee behavior is just Seek in the opposite direction and to an extent that is true. But continuing to use [The Coding Train](https://www.youtube.com/watch?v=4hA7G3gup-4) as a refence, additional possibilities for the behaviors came to my attention such as only fleeing if target is within a certain range and applying a weight to a calculated steering force to alter its effect disctinctly from the other behaviors. Also brings to mind the possiblity of maintaining a list of behaviors the steering would process with a given type, target, and weight. Oh the possibilities..

**Examples**: 

#### Flee Behavior
![Flee Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day14-sb-flee/flee.gif)  
#### Flee 2x Faster
![Weighted Flee Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day14-sb-flee/flee2.gif) 

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
---------- 
<a name="day-15"></a>
### Day 15: July 8, 2018 

**Today's Focus**: Steering Behaviors - Evade

**Details**:
  - Implemented Evade
  - Added walls in which all agents flee from
  - Combined Arrive and Flee behaviors on the Invader

**Thoughts** I had a bit of trouble with this one but the theory behind the behavior is pretty straight forward, evade the target vehicle by fleeing the predicted position given their velocity and position. Theres a bug in which the velocity of the evading vehicle isn't reset. After all, I'm grabbing only the steering force and applying it to the acceleration. That force goes to zero if the evade target leaves the range so the velocity doesnt change. I will have to come back to this but for now I'm satisfied 

**Examples**: 

#### Evade Behavior
![Evade Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day15-sb-evade/evade.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
---------- 
<a name="day-16"></a>
### Day 16: July 9, 2018 

**Today's Focus**: Steering Behaviors - Wander

**Details**:
  - Implemented wander
  - Struggled a lot
  - Wrote a bunch of debug to see what was going on with the values. 

**Thoughts** This behavior took me several days to work out. There were a lot of small difficulties that arose and then some required tweaking of parameters. First was with my random vectors, they always returned zero because of course i was using Random.Range of type int and not float. Next, was the target point wasnt translating with the vehicle position. There was more that required me to write debug code to visualize what was going on with the vector values. Got some gizmo drawing in. This made me consider adding a visualizer to the steering behaviors. Maybe a project for a later time. After 

**Examples**: 

#### Wander Behavior
![Wander Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day16-sb-wander/wander.gif)  

#### Wander Behavior Gizmos
![Wander Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day16-sb-wander/wander-editor.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
---------- 
<a name="day-17"></a>
### Day 17: July 10, 2018 

**Today's Focus**: Steering Behaviors - Obstacle Avoidance

**Details**:
  - Implemented basic obstacle avoidance
  - only implemeted in 2D. 

**Thoughts** Still working with [Programming Game AI by Example](https://www.amazon.com/Programming-Example-Wordware-Developers-Library/dp/1556220782) for this one and although the concepts make sense, Implmenting them in unity from a c++ system the book describes is proving interesting as there are already helper functions to accomplish the tasks the book performs. I appreciate the long way approach though, good to know what all thoses helpers are doing. 

**Examples**: 

#### Obstacle Avoidance
![Obstacle Avoidance Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day17-sb-obstacle-avoidance/avoidance.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
---------- 

<a name="day-18"></a>
### Day ?: August 2, 2018 

End. 

So I failed to keep at this consistently. I found it hard to carve out a half hour to an hour a day to focus on my own game dev. I did try to complete this challenge while working on a seperate game with a few friends. My game dev time went towards that project more than it did my pursuit of my topics of interests. 

**Lessons Learned** 

I needed to find an alternative way to determine progress on a particular subject. During this run I only considered the topic covered once it was fully implemented, tested, and presentable. I feel that was a mistake and deviated from my initial challenge. I mistook my goal to **work towards** understanding and playing around with a particular topic each day for *completely understand* a topic of interest each day. Huge mistake. I forgot the whole point of me doing this was to learn about the topics I grew curious about over the years. Once it became about needing something completed presentable after 30 minutes to an hour, it started to feel impossible, then the days started to pile up as I worked though bugs and other issues. I need a new perspective on what I deem as "presentable". 

So what next

I failed this challenge and it was a blow. I've taken on a number of game dev challenges of the majoritory ended in failure and the weight of those failures do pile on after a while. As discouraging as those failures are, I really enjoy game dev. So I will continue. This is only Round 1 of the 100 days of dev challenge. There's still plenty more I am curious about. So I will regroup, get organized, ease up on myself, rethink some things and carry on. 

See you in Round 2!


[Table of Contents](#toc)
---------- 
<!--
<a name="day-18"></a>
### Day 18: July 11, 2018 

**Today's Focus**: Steering Behaviors - Wall Avoidance

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Wall Avoidance
![Wall Avoidance Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
---------- 
<a name="day-19"></a>
### Day 19: July 12, 2018 

**Today's Focus**: Steering Behaviors - Pursuit

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Pursuit Behavior
![Pursuit Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
---------- 
<a name="day-20"></a>
### Day 20: July 13, 2018 

**Today's Focus**: Steering Behaviors - Hide

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-21"></a>
### Day 21: July 14, 2018 

**Today's Focus**: Steering Behaviors - Path Following

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-22"></a>
### Day 22: July 15, 2018 

**Today's Focus**: World Wrap 3D

**Details**:
  - Took the previously implemented world wrap and expanded it to support a 3d cube world

**Thoughts** This came to mind while working on the [wander steeing behavior](#day-16) when I set some agents to go off an wander and they quickly when off screen. It seemed like a good idea to implement this world wrap for 3d considerations.  

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-23"></a>
### Day 23: July 16, 2018 

**Today's Focus**: TBD

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-24"></a>
### Day 24: July 17, 2018 

**Today's Focus**: TBD

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-25"></a>
### Day 25: July 18, 2018 

**Today's Focus**: TBD

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-26"></a>
### Day 26: July 19, 2018 

**Today's Focus**: TBD

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-27"></a>
### Day 27: July 20, 2018 

**Today's Focus**: TBD

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-28"></a>
### Day 28: July 21, 2018 

**Today's Focus**: TBD

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-29"></a>
### Day 29: July 22, 2018 

**Today's Focus**: TBD

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
<a name="day-30"></a>
### Day 30: July 23, 2018 

**Today's Focus**: TBD

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Seek Behavior](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day12-sb-seek/seek.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/steering-behavior/Assets/Misc/Steering%20Behaviors)

[Table of Contents](#toc)
----------
-->