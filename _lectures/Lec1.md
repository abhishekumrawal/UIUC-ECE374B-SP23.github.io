---
title: Lecture 1 - Course introduction and languages
placeholder: false
back-color: faffff
card-link: LecLink1
# subtitle: And a subtitle
description: This is the first lecture of the course. We'll discuss the course policies and why we model problems as languages.  
people:
  - kani
layout: lecture
# no-link: true  # stops link to page 
deliverydate: 2023-01-17 #last updated date
link-slides: /lecture_slides/lec1.pdf
link-scribbles: /lecture_slides/lec1_scribbles_sp23.pdf
link-recording: https://www.youtube.com/watch?v=Dw6Mp_yalTo
---

Course policies can be found on the website [ecealgo.com](https://ecealgo.com).

#### Big Questions

This course is focused on answering three big questions: 

- Given infinite time, how can we group problems by their "complexity" (Computability-theory)
- Given finite time, but a problem we know is computable, how fast can we solve the problem (Algorithmic design)
- Given a problem whihc is difficult to solve, can we infer how slow/fast we can solve it by comparing it to other known problems (Reductions)

&nbsp;
#### Two types of complexity
&nbsp;

| Computational Complexity      | Algorithmic Complexity |
| -----------                   | -----------            |
| <img src="/img/lectures/Lec1/Chomsky_Hierarchy-REfilled.png" alt="Chomsky Hierachy" style="height: 300px;">  | <img src="/img/lectures/Lec1/Algorithmic_complexity.png" alt="Algorithmic Complexity" style="height: 300px;">       |


&nbsp;
#### Why Languages? 
Problems need to be represented as languages to be comparable. A language is a set of strings and each string represents and *instance* of the problem (a specific set of inputs and their correponding output). For example, the problem of adding two numbers together can be represented by the language: 

**Problem:** Multiplying two integers together               

**Language:** 
$$L_{MULT2} = 
\begin{bmatrix}
  1 \times 1|1, & 1 \times 2|2, & 1 \times 3|3, \ldots\\
  2 \times 1|2, & 2 \times 2|4, & 2 \times 3|6, \ldots \\
  \vdots & \vdots & \vdots \\
  n \times 1|n, & n \times 2|2n, & n \times 3|3n, \ldots \\
\end{bmatrix}$$

&nbsp;
#### Things I forgot to mention
You would think that after talking for 1.25 hours, what else could there be to say. Well my friends, there is so much to know and by extension, just as must to teach! This is what I forgot to mention today. 

###### Group homeworks
Homeworks can be completed in groups of at most **three students** as discussed in the [homework policies](https://ecealgo.com/homeworks.html). Ideally, the way it should work is that each individual in a group looks at all the problems and comes up with some quick notes on possible solutions. Then the group would come together and attempt to reach a consensus on each problem. Finally, the solution writing and presentation would be divvyed up between the members so alleviate some of the presentation burden. However, I personally am conflicted on group work: 

- **Positive:** If done correctly, it can be a powerful way where students learn from and bounce ideas off one-another. That is definitely a good thing. 
- **Negative:** Since this is my sixth time doing this course, I believe about half the groups simply divvy up the problems and don't even look at the problems not assigned to them. I've done a bit of analysis on past semesters where I've had a exam problem that was nearly identical to a homework problem and consistently, theres been about 25-30% of students that clearly have never seen the problem before. 

In summary, I tend to fall of the side of discouraging group work. From what I've seen, the strongest performing individuals are over-represented in the group of students that do the homework solo. Also I have reduced the homework burden compared to past semesters so a single person should be fine doing all the problems themselves. 
But, I won't get rid of group homeworks all together. Like I say a lot, you guys are adults and should know what works best for you. [My job is to encourage behavior that I believe will be optimal for learning, not force it.](https://www.youtube.com/watch?v=QIBMMVJFM4M) 

###### Earlier HW Assignment
One of you made an excellent point after class that if I want to encourage starting homework early, I should post the homework on Friday instead on Monday. The argument is that if I post it on Friday, people usually have free time on the weekend to start right away while if I post on Monday, there are more things going on during the week and a lot of you won't have time to get to it till the next weekend. What a excellent criticism (I mean that sincerely) and it something I hadn't considered. SO I won't promise anything, but the deal is I will do my absolute best to post the homework by Friday midnight. The homework will cover every learned the Tuesday-Friday right before it. THe due date is still the next Monday (so it'll be 10 days between the assignment and submission instead of 7). The one downside is that the next homework will get assigned before the current one is due whihc might be a little emotionally discouraging but the benefit of allowing people to start early right after completing the requisite lectures/labs outweighs that.   

###### DRES
- If you have a DRES accommodation, please email me directly (not sure if sending documents over Piazza is is compliant with EHR policies or not, but why risk it ). Make sure I respond that I've recorded your accommodation! If I don't respond email again.
- Because of the limited staff, DRES students will take the exams at the [TAC](https://www.disability.illinois.edu/academic-accommodations-and-supports/academic-accommodations/testing-accommodations) synchronously with the rest of the class. We'll hammer out the details closer to MT1. 

###### Labs/Discussions are the same thing
Labs and discussions are the same thing. Sorry, I've used both terms interchangeably, I've taught this course so many times with different people, my mind keeps jumping timelines with the exact verbiage.  

&nbsp;
<h4>Additional Resources</h4>
- [Jeff's Textbook - Introduction and History](https://jeffe.cs.illinois.edu/teaching/algorithms/book/00-intro.pdf)
- [Jeff's - Notes on strings](https://jeffe.cs.illinois.edu/teaching/algorithms/models/01-strings.pdf)
- [Sariel's Lecture 1](https://courses.engr.illinois.edu/cs374/fa2020/lec_prerec/) 