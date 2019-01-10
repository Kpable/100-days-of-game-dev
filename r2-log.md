# 100 Days Of Game Dev - Round 2 Log

<a name="toc"></a>
### Table of Contents 
|Day                               |Focus                                      |Day                                 |Focus                                       |
|:--------------------------------:|:-----------------------------------------:|:----------------------------------:|:------------------------------------------:|
|[Day 1](#day-1)    **09/16/18**   | Chapter 2 - State Driven Agent Design     |[Day 2](#day-2)    **09/17/18**     | 					TBD  				     |

### Day 0: January 09, 2019 

With a new perspective on this, I'm excited to give this another try. I will be working through some AI programming by following the book, [Programming Game AI by Example](https://www.amazon.com/Programming-Example-Wordware-Developers-Library/dp/1556220782). After that, who knows. Theres a lot of game dev I am interested in.

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