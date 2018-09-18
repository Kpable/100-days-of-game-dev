# 100 Days Of Game Dev - Round 2 Log

<a name="toc"></a>
### Table of Contents 
|Day                               |Focus                                   |Day                                 |Focus                                       |
|:--------------------------------:|:--------------------------------------:|:----------------------------------:|:------------------------------------------:|
|[Day 1](#day-1)    **09/16/18**   | 100 Days Log Generator                 |[Day 2](#day-2)    **09/17/18**     | 100 Days Log Generator - Dynamic Additions |

<!-- 
|[Day 3](#day-3)    **08/20/18**   | Shmup World Wrap                       |[Day 4](#day-4)    **08/21/18**     | Shmup Weapons                              |
|[Day 5](#day-5)    **08/22/18**   | Health on Meteors                      |[Day 6](#day-6)    **08/23/18**     | Environmental Hazard - Splitter            |
|[Day 7](#day-7)    **08/24/18**   | Weapons Refactoring                    |[Day 8](#day-8)    **08/25/18**     | Paralax Backgrounds                        |
|[Day 9](#day-9)    **08/26/18**   | Shmup Power Ups                        |[Day 10](#day-10)  **08/27/18**     | Spiral Gun Spawning                        |
|[Day 11](#day-11)  **08/28/18**   | Bullet Reflection                      |[Day 12](#day-12)  **08/29/18**     | Steering Behavior - Seek                   |
|[Day 13](#day-13)  **08/30/18**   | Steering Behavior - Arrive             |[Day 14](#day-14)  **08/31/18**     | Steering Behavior - Flee                   |
|[Day 15](#day-15)  **09/01/18**   | Steering Behavior - Evade              |[Day 16](#day-16)  **09/02/18**     | Steering Behavior - Wander                 |
|[Day 17](#day-17)  **09/03/18**   | Steering Behavior - Obstacle Avoidance |[Day ?](#day-18)   **09/04/18**     | End                                        |
 
 |[Day 19](#day-19)  **07/12/18**   | Steering Behavior - Pursuit            |[Day 20](#day-20)  **07/13/18**     | Steering Behavior - Hide                  |
 |[Day 21](#day-21)  **07/14/18**   | Steering Behavior - Path Following     |[Day 22](#day-22)  **07/15/18**     | World Wrap 3D                             |
 |[Day 23](#day-23)  **07/16/18**   | TBD                                    |[Day 24](#day-24)  **07/17/18**     | TBD                                       |
 |[Day 25](#day-25)  **07/18/18**   | TBD                                    |[Day 26](#day-26)  **07/19/18**     | TBD                                       |
 |[Day 27](#day-27)  **07/20/18**   | TBD                                    |[Day 28](#day-28)  **07/21/18**     | TBD                                       |
|[Day 29](#day-29)  **07/22/18**   | TBD                                    |[Day 30](#day-30)  **07/23/18**     | TBD                                        |
 -->

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

**Today's Focus**: Make the elements and links of the form dynamically add or remove

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