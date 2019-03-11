---
layout: project
type: project
image: images/garbage_collector.png
title: Junior Scheme Project
permalink: projects/junior-scheme-project
# All dates must be YYYY-MM-DD format!
date: 2018-05-04
labels:
  - C++
  - Scheme
  - CLion
  - Git/GitHub
summary: A partially-compliant R7RS Scheme interpreter called “Shaka Scheme” written in C++.
---

<div class="ui small rounded images">
  <img class="ui image" src="../images/Screen Shot 2018-05-02 at 8.01.29 AM.jpg">
  <img class="ui image" src="../images/Screen Shot 2018-05-02 at 8.01.50 AM.jpg">
  <img class="ui large image" src="../images/Screen Shot 2018-05-02 at 8.02.22 AM.jpg">
</div>

This project was designed on the CLion IDE in C++, and was the continuation of Austin Tasato’s Shaka Scheme project which had been running for two semesters prior to my contribution. Shaka Scheme is currently a partially-compliant R7RS Scheme implementation, with the goal of creating a clean implementation of R7RS-small Scheme using modern C++ and OOP design idioms and features. In addition, the structure of the project should be readable for novice/intermediate C++ programmers. Since the project strives to create a standalone distribution of Scheme that is relatively light and portable, the design choices tend away from using larger libraries such as Boost within the implementation.

As for my contribution to the project, I was tasked within the core systems team to design a garbage collector for memory management by implementing the mark-and-sweep algorithm. In many main stream programming languages, like Java, there is what is called a garbage collector which periodically checks the VM (virtual machine) of any unused variables in memory. It then deletes it from the system to further preserve memory. The mark-and-sweep algorithm itself is quite elegant as it traverses the entire Scheme environment marking existing variables in memory. It then sweeps or deletes all unused variables. Though the definition above is extremely generalized, my team and I were able to successfully implement the garbage collector algorithm in a heap-based model of Scheme by re-aliasing the `NodePtr` that holds all allocated memory. By creating a GCNode wrapping over a GCData (heap allocated memory used for the “sweep” portion of the algorithm), it then wrapped over the allocated data. From there, all newly allocated data was created on the heap as GCData objects and put into a GCList. The `mark()` phase then traversed all five of the registers in the heap virtual machine (accumulator, expression, environment, call frame, and value rib) placing a mark on all declared variables and values in those respective registers. From there, the `sweep()` phase traversed the GCList and deleted all unmarked GCData objects while unmarking previously marked GCData objects in the GCList for the next cycle of mark-and-sweep.

The Shaka Scheme project consisted of two individual teams: Libraries and Core Systems. As previously mentioned above, I was part of the Core Systems team, which consisted of a leader/mentor and two other members including myself. Besides Austin Tasato being the head of the entire project, my direct leader/mentor of the Core Systems team was Billy Troy Wooton. My partner was Kirsten Takanishi. Pertaining to the implementation of the garbage collector (GC for short), my specific contribution included the implementation of the GCList .hpp and .cpp files which held a linked-list of GCData objects. The class methods consisted of a check to the size of the list, a method to add GCData objects to the list, and a method to implement the sweep functionality. I also designed the GC class .hpp and .cpp files which held the `create_data()` method. This method took in a `const` reference to a data object as an input parameter, then dynamically allocated a “new” GCData object over that data object. From there, it added that GCData object to the GCList, returning the GCData object. The GC class also made the GCList private and allowed to get the size of the list as well as invoke the sweep method within the GC class. My last task of the project was to complete the mark implementation, which as previously mentioned marked everything in the five registers of the heap virtual machine. I wrote the method for marking the environment register (`mark_environment()`). The implementation was simple as it consisted of using an iterator through the environment map to call a function, `mark_node()` on all variables and values. Since this was a fairly short task, I assisted my partner, Kirsten, in her completion of the mark implementation by helping her write `mark_accumulator()`, `mark_expression()`, and `mark_value_rib()`. In addition to my tasks consisting of writing .hpp and .cpp files for GC classes and functions, I also wrote individual unit-test .cpp files to test the functionality of all my methods and functions.

This project was extremely helpful in improving my OOP skills in C++. Though it did not cover much Scheme syntax nor language use, it was a nice introduction to the Scheme language. I personally enjoyed working on the garbage collector implementation, especially since I had direct mentorship from my core systems leader, Troy. He was very patient in helping me understand all necessary C++ concepts. The first image at the top is the directory holding all necessary .hpp and .cpp files for the GC, the second image shows the directory holding all the unit-test files we wrote, and the title image shows our completed GC design within main.cpp of Shaka Scheme.


Source: <a href="https://github.com/uhmanoa-transpiler-project/shaka-scheme"><i class="large github icon "></i>uhmanoa-transpiler-project/shaka-scheme</a>
