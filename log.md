# 100 Days Of Game Dev - Log

<a name="toc"></a>
### Table of Contents 
|Day|Focus|Day|Focus|
|:---:|:-----:|:---:|:-----:|
|[Day 1](#day-1) **06/24/18**| Object Pooling |[Day 2](#day-2) **06/25/18**| Spaceship Behavior |
|[Day 3](#day-3) **06/26/18**| Shmup World Wrap |[Day 4](#day-4) **06/27/18**| Shmup Weapons |
|[Day 5](#day-5) **06/28/18**| Health on Meteors |[Day 6](#day-6) **06/29/18**| Environmental Hazard - Splitter |
|[Day 7](#day-7) **06/30/18**| Weapons Refactoring |[Day 8](#day-8) **07/01/18**| Paralax Backgrounds |
|[Day 9](#day-9) **07/02/18**| TBD |[Day 10](#day-10) **07/03/18**| TBD |

<!-- 
### Day 0: June 23, 2018 

<a name="day-2"></a>
### Day 2: June 25, 2018 

**Today's Focus**: Spaceship behavior

**Details**:
  - Taking a look at the mechanics around 2D spaceship behaviors

**Thoughts** 

**Examples**: 


**Link(s) to work**: 

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

**Thoughts** Wanted to refactor how the weapons work. Previously the i imported it from a tutorial but i want to add some more versatility. The plan is to have the gun objects circle around the ship depending on the weapon type. 

**Examples**: 

#### Meteor Splitting up
![Meteor Splitting up](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day7-weapons-refactoring/weapons-refactored.gif) 

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/shmup-weapons/Assets/Misc/Shmup%20Weapons)

[Table of Contents](#toc)
----------
<a name="day-8"></a>
### Day 8: July 1, 2018 

**Today's Focus**: 

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Meteor Splitting up](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day6-splitter-behavior/meteor-splitting.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/shmup-weapons/Assets/Misc/Shmup%20Weapons)

[Table of Contents](#toc)
----------


<a name="day-9"></a>
### Day 9: July 2, 2018 

**Today's Focus**: 

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Meteor Splitting up](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day6-splitter-behavior/meteor-splitting.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/shmup-weapons/Assets/Misc/Shmup%20Weapons)

[Table of Contents](#toc)
---------- 
<!-- 
<a name="day-10"></a>
### Day 10: July 1, 2018 

**Today's Focus**: 

**Details**:
  - 

**Thoughts** 

**Examples**: 

#### Meteor Splitting up
![Meteor Splitting up](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day6-splitter-behavior/meteor-splitting.gif)  

**Link(s) to work**: [Github](https://github.com/Kpable/Kpable-Labs/tree/misc/shmup-weapons/Assets/Misc/Shmup%20Weapons)

[Table of Contents](#toc)
----------

-->