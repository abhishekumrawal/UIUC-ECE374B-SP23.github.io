---
title: Lecture 23 - Decidability I
placeholder: false
back-color: fffaff
card-link: LecLink23
# subtitle: And a subtitle
description: Stepping away from algorithms, it is time to ask what problems are not decidable and cannot be solved by a Turing machine. We'll introduced the halting problem.  
people:
layout: lecture
# no-link: true  # stops link to page 
deliverydate: 2023-04-18
link-slides: /materials/lecture_slides/lec23.pdf
link-scribbles: /materials/lecture_slides/lec23_scribbles_sp23.pdf
link-recording: https://mediaspace.illinois.edu/media/t/1_4s9vft47
---

<h4>Decidability</h4>
Decidability usually refers to the concept of whether a problem can be solved algorithmically or not. Specifically, decidability deals with the question of whether there exists an algorithm that can correctly determine whether a given input satisfies a particular property or not.

<br>

<h4>Halting Problem</h4>
The halting problem is a classic example of an undecidable problem in computer science. It asks whether there exists an algorithm that can determine, for any given program and input, whether the program will eventually halt (i.e., stop executing) or run forever.

The halting problem has important implications in theoretical computer science and the foundations of computation. It is a fundamental result that shows that there are certain problems that are inherently undecidable, meaning that there is no algorithm that can solve them for all cases.

<h4>Reduction</h4>
Problem X reduces to problem Y, if given a solution to Y, then it implies a solution for X. Namely, we can solve Y then we can solve X. We will done this by X => Y. This [youtube video](https://www.youtube.com/watch?v=U4yGQp5aCTM) makes it easier to understand how reduction works.

<img src="/img/lectures/Lec23/Reduction.png" alt="Reduction" style="width: 300px;">

<h4>Additional Resources</h4>








