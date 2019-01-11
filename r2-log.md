# 100 Days Of Game Dev - Round 2 Log

<a name="toc"></a>
### Table of Contents 
|Day                               |Focus                                      |Day                                 |Focus                                       |
|:--------------------------------:|:-----------------------------------------:|:----------------------------------:|:------------------------------------------:|
|[Day 1](#day-1)    **01/10/19**   | Chapter 2 - State Driven Agent Design     |[Day 2](#day-2)    **01/11/19**     | Global States	         					 |

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
	- Implementing State d
	- Basic State machine

**Thoughts** The book starts with a math and physics primer, that's why we start at Chapter 2. I did some work in the past to try to implement this so I reimported it. Spent most of today's time reading the chapter. From what I understand the State Design Pattern is the concept of defining a state such that it contains all the information it needs to perform its transitions to another state as well as getting a reference to the owner of the state so that when the state is executed it knows which agent to act on. Additionally, states would be derived from a common interface so that each state could be acted upon similarly. 

The book uses the singleton pattern for each state so that there would only ever be one instance of state at any given time. There are some things I dont like too much so far about this pattern. One of them being that each state has to know what state to transition to, why, and when to do so. I can see that getting a bit tricky the more states you add in. It would be a nightmare to implement without a state transition diagram of some sort. 

One of the challenges I face in going through this book is that the book is written in C++ and seems to define some primative types. Types that you would otherwise see provded for you in a game engine. I want to implement these mechanics in a way that they are reusable to me but also follows the book as i know from having peeked ahead that the book will progressively build upon and reuse the objects created from previous chapters. Got a lot to look forward to. 

Tomorrow Global States, or "state blips" as the book puts it.

**Examples**: 

#### Agent Output
![Agent Output](https://raw.githubusercontent.com/kpable/100-days-of-game-dev/master/images/r2/day1/state-driven-agent.gif)

**Link(s) to work**: 
[Github](https://github.com/Kpable/Kpable-Labs/commit/b26e35978a96e356cdd4f2e39caee60f390c9a78#diff-9aedeaf1f77b8642abe528503b8c5de8)

[Table of Contents](#toc)
----------

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