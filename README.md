grid-world-scheme
=================

Final project for AP Computer Science.

##Summary
For my final AP Computer Science project sophomore year, I decided to implement Grid World in [Scheme][1], and specifically, [Racket][2] (previously known as PLT Scheme). Along the way, I built parts of Java's most common data abstractions (String, ArrayList, 2d arrays, HashMap). I also developed a testing suite with various types of unit tests.

##What is Grid World?
For those that don't know, Grid World is a Java [case study][3] provided by CollegeBoard. To put it in their own words:    

	The GridWorld Case Study provides a graphical environment where visual
	objects inhabit and interact in a two-dimensional grid. In this case
	study, you will design and create “actor” objects, add them to a grid, and
	determine whether the actors behave according to their specifications. A
	graphical user interface (GUI) is provided that displays the grid and the
	actors. In addition, the GUI has a facility for adding actors to the grid
	and for invoking methods on them.                                          
	
To put it simply, GridWorld is a case study that is meant to help CS students learn about data abstraction, inheritance, and other object oriented programming concepts. It is akin to [cellular automata][4] (widely popularized by [Conway's Game of Life][5]). The Java packaged is composed an **Actor** class, **Grid** class, and **Location** class, among others. An **Actor** can be added to a **Grid** (2d array) at a certain **Location** ( (x, y) coordinate pair). These **Actor**s can move around to other locations each time their act() method is called (i.e. each time a frame occurs). They can rotate, change colors, and interact with other **Actor**s in the **Grid**. 

The simulation is displayed in a Java applet (as seen below).

![College Board's GridWorld Java applet](http://www.horstmann.com/gridworld/part1-constructors.png)                                               

To see the full abstraction, go take a look at the [Java docs][6]. You can also download the code from [College Board][3]. 

##Result
          
Here is what it looks like when the my code is run...

![GridWorld in Scheme](https://github.com/drewbent/grid-world-scheme/raw/master/images/screenshots/screenshot1.png)
![GridWorld in Scheme](https://github.com/drewbent/grid-world-scheme/raw/master/images/screenshots/screenshot2.png)

##Motivation
I'd been exposed to the case study in my class and had also become familiar with it as it's included in the AP test. At the same time, my class had spent the first semester working with Scheme. (My teacher, [Mr. Paley][7], had previously taught at Berkeley and had brought over some of the awesome Scheme curriculum ([SICP][8]) to our high school.)     

Scheme is a fun language to work with. It can be tedious at times and things that could be implemented in Java in seconds might take longer. It is not object-oriented and assignment is usually [discouraged][9]. However, Scheme can still be a powerful language. Object oriented programming paradigms can still be used (e.g. dispatch) and assignment is possible if necessary (e.g. set!).

As a challenge, I decided to see if I could recreate GridWorld in Scheme. I wanted to get things as close to the actual thing as possible. That meant having the same abstractions, same method/class/parameter names, and more. It also meant that I first had to implement all of Java's built-in features that had been utilized in Grid World. For the most part, the code was written in the order you see it in the file. I started by coding things like ArrayList and then moved up the abstraction to 2d arrays, Grid, and ActorWorld.

##Code
###Naming
All of the original Java names were converted from **camelCase** to **not-camel-case-but-rather-hyphens**

Let's take GridWorld's **Location** class as an example.   

	JAVA						    SCHEME
	----------------------------------------------------------------
   	loc = new Location(r, c);		(define loc (new-location r c))
	loc.getRow();					(loc 'get-row)               
	
###Graphics and Animation
For the most part, data and graphics are separated in the program.

[1]: http://en.wikipedia.org/wiki/Scheme_(programming_language) "Scheme"
[2]: http://racket-lang.org/ "Racket"      
[3]: http://apcentral.collegeboard.com/apc/public/courses/teachers_corner/151155.html "Grid World"          
[4]: http://en.wikipedia.org/wiki/Cellular_automaton "Cellular Automata"
[5]: http://en.wikipedia.org/wiki/Conway's_Game_of_Life "Conway's Game of Life"                      
[6]: http://www.horstmann.com/gridworld/javadoc/overview-summary.html "GridWorld Java Docs"
[7]: http://www.paleyontology.com "Mr. Paley's website"
[8]: http://mitpress.mit.edu/sicp/full-text/book/book.html "The greatest book of all time"                                                  
[9]: http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-20.html#%_sec_3.1.3 "The Costs of Introducing Assignment"    
[10]: http://docs.racket-lang.org/teachpack/2htdpuniverse.html "universe.rkt"           
[11]: http://docs.racket-lang.org/teachpack/2htdpimage.html "image.ss"
[12]: http://docs.racket-lang.org/teachpack/draw.html "draw.ss"