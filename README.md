# PikesRules

_Reference_: https://twitter.com/rob_pike/status/998681790037442561?lang=en  
_Reference_: http://doc.cat-v.org/bell_labs/pikestyle

# preface
From Pike's official twitter account:
> People keep quoting my '5 Rules of Programming'. Actually there were 
(and still are) 6 rules.

> Plus they need proper context. The original version was a handout 
(we used paper for things back then) for a graduate operating systems 
course at Princeton in 1987. The rules are the gist of the section on 
complexity.

> Since then, there have appeared many corrupted version of those notes, 
with bad formatting or punctuation or what have you.

> The best copy I can find on line is 
http://doc.cat-v.org/bell_labs/pikestyle. 
Most of the other versions have errors.

# rules
Most programs are too complicated - that is, more complex than they need 
to be to solve their problems efficiently. Why? Mostly it's because of 
bad design, but I will skip that issue here because it's a big one. 
But programs are often complicated at the microscopic level, and that 
is something I can address here.

* **Rule 1.** You can't tell where a program is going to spend its time. 
Bottlenecks occur in surprising places, so don't try to second guess 
and put in a speed hack until you've proven that's where the bottleneck is.

* **Rule 2.** Measure.  Don't tune for speed until you've measured, and even 
then don't unless one part of the code overwhelms the rest.

* **Rule 3.** Fancy algorithms are slow when n is small, and n is usually small. 
Fancy algorithms have big constants. Until you know that n is frequently 
going to be big, don't get fancy. (Even if n does get big, use Rule 2 first.)   For example, binary trees are always faster than splay trees for workaday problems.

* **Rule 4.** Fancy algorithms are buggier than simple ones, and they're much 
harder to implement. Use simple algorithms as well as simple data 
structures.

    The following data structures are a complete list for almost all practical 
    programs:
    
    * array 
    * linked list 
    * hash table 
    * binary tree
    
    Of course, you must also be prepared to collect these into compound data 
    structures. For instance, a symbol table might be implemented as a 
    hash table containing linked lists of arrays of characters.

* **Rule 5.**  Data dominates.  If you've chosen the right data structures and 
organized things well, the algorithms will almost always be self-evident.
Data structures, not algorithms, are central to programming. 
(See The Mythical Man-Month: Essays on Software Engineering by 
F. P. Brooks, page 102.)

* **Rule 6.** There is no Rule 6.
