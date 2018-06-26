# 100 Days Of Game Dev - Log

<a name="toc"></a>
### Table of Contents 
|Day|Focus|Day|Focus|
|:---:|:-----:|:---:|:-----:|
|[Day 1](#day-1) **06/24/18**|Object Pooling|[Day 2](#day-2) **06/25/18**| Spaceship Behavior |
|[Day 3](#day-3) **06/26/18**|Shmup World Wrap|[Day 4](#day-4) **06/27/18**| TBD |

<!-- ### Day 0: February 30, 2016 (Example 1)
##### (delete me or comment me out)

**Today's Progress**: Fixed CSS, worked on canvas functionality for the app.

**Thoughts:** I really struggled with CSS, but, overall, I feel like I am slowly getting better at it. Canvas is still new for me, but I managed to figure out some basic functionality.

**Link to work:** [Calculator App](http://www.example.com)

### Day 0: February 30, 2016 (Example 2)
##### (delete me or comment me out)

**Today's Progress**: Fixed CSS, worked on canvas functionality for the app.

**Thoughts**: I really struggled with CSS, but, overall, I feel like I am slowly getting better at it. Canvas is still new for me, but I managed to figure out some basic functionality.

**Link(s) to work**: [Calculator App](http://www.example.com)


### Day 1: June 27, Monday

**Today's Progress**: I've gone through many exercises on FreeCodeCamp.

**Thoughts** I've recently started coding, and it's a great feeling when I finally solve an algorithm challenge after a lot of attempts and hours spent.

**Link(s) to work**
1. [Find the Longest Word in a String](https://www.freecodecamp.com/challenges/find-the-longest-word-in-a-string)
2. [Title Case a Sentence](https://www.freecodecamp.com/challenges/title-case-a-sentence)
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

#### Also my lander curiousity
![Lander behavior Example](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/day3-world-wrap/lander.gif) 


**Link(s) to work**:
- [Github (Spaceship)](https://github.com/Kpable/Kpable-Labs/tree/misc/spaceship-behavior/Assets/Misc/Spaceship%20Behavior)
- [Github (Lander)](https://github.com/Kpable/Kpable-Labs/tree/misc/spaceship-behavior/Assets/Misc/Lander%20Behavior)

[Table of Contents](#toc)
----------
