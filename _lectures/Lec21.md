---
title: Lecture 21 - NP-complete problems and reductions I
placeholder: false
back-color: fffaff
card-link: LecLink21
# subtitle: And a subtitle
description: We now delve into the hard (NP-hard) problems and investigate how to prove if a specific problem is NP, NP-hard, etc.
people:
  - nicholas
layout: lecture
# no-link: true  # stops link to page 
deliverydate: 2023-04-11
link-slides: /materials/lecture_slides/lec21.pdf
link-scribbles: /materials/lecture_slides/lec21_scribbles_sp23.pdf
link-recording: https://mediaspace.illinois.edu/media/t/1_1bnz6ltr
---

### SAT
#### **Defnition**:
For a set of boolean variables $x_1,x_2,...,x_n$
- A literal is either $x_i$ or $\neg x_i$
- A clause isa disjunction of literals

(i.e. $x_3 \lor \neg x_7 \lor x_8$)
- Conjunctive normal form (CNF) is a conjunction of causes 

(i.e. $(x_1 \lor x_4) \land (x_3 \lor \neg x_7 \lor x_8) \land x_5$)
- 3CNF is a CNF formula where each clause has *exactly* 3 literals

#### **Problem: SAT**
For a given CNF (3CNF for 3SAT) formula $\phi$, is there a truth assignment of the variables such that $\phi$ evaluates to true? 

Example: 
- $(x_1 \lor x_4) \land (x_3 \lor \neg x_7 \lor x_8) \land x_5$ evaluates to true when every variable is set to true.
- $(x_1 \lor x_4) \land x_5 \land \neg x_5$ cannot evaluate to true because either $x_5$ or $\neg x_5$ will be false.

#### **Reducing SAT to 3SAT:**
To reduce from an instance of SAT to an instance of 3SAT all clauses must be made to have exactly 3 literals. To do this dummy variables are introduced such that the original formula is satisfiable if and only if the formula with the dummy variables is satisfiable. To do so short clauses are padded with dummy variables to have 3 literals, long clauses are broken apart using dummy variables to get 3 literals.
Proof in Prof. Har-Peled's lectures

### Complexity Classes

<img src="/img/lectures/Lec13/lec13_fibo.png" alt="Fibonacci" style="width: 700px;">

#### **Types of Algorithmic Problems**:
- Decision Problems: Is the input a YES or a NO

    example: Given a graph $G$, for nodes $s,t$ is there a path from $s$ to $t$ in $G$.
- Search Problems: Find a solution if the input is a YES

    example: Given a graph $G$, for nodes $s,t$ find a path from $s$ to $t$ in $G$.
- Optimization Probelm: Find the best solution if the input is a YES

    example: Given a graph $G$, for nodes $s,t$ find the shortest path from $s$ to $t$ in $G$.

#### **Analysis of Algorithmic Problems**:
- Does the algorithm correctly solve the problem.
- What is the asymptotic worst-case running time of the algorithm.
- What is the asymptotic worst-case space used by the algorithm.

An algorthim has an asymptotic running time of $O(f(n))$ if for every input of size $n$ the algorithm terminates after $O(f(n))$ promitive steps.

### Reductions
A reduction from problem $A$ to problem $B$ is formatting problem $A$ in terms of problem $B$. The algorithm for $A$ uses the algorithm for $B$ as a black box.

example: Given an array $A$ of n integers, are there any duplicates in $A$.

Solving directly by comparing every element to every other element takes $O(n^2)$ running time. If we sort the array first then elements only need to be compared to adjacent elements which takes total $O(n log(n))$ running time. This is a reduction of the duplicate elements problem into the sorting problem when we use the sorting algorithm as a black box.

#### **Types of Reductions**:
Given 2 problems $C$ and $D$ where problem $C$ reduces to problem $D$
- Positive Direction: Constructing an algorithm for $C$ implies a constrution of an  algorithm for $D$. 
- Negative Direction: If the reduction from problem $C$ to problem $D$ **is** "efficient". Assuming there **is no** "efficient" alogrithm for $C$ implies there **is no** "efficient" algorithm for $D$


### Recursions
A recursion is a special case of reduction where the problem is reduced to a "smaller" instance of itself.

example: Tower of Hanoi, moving a tower of size $n$ from peg $0$ to peg $2$.

The problem can be generalized to move a tower of size $m$ from peg $x$ to peg $y$. Then the problem of moving a tower of size $n$ from peg 0 to peg 2 can be viewed as moving a tower of size $n-1$ from peg 0 to peg 1, then moving the bottom disk to peg 2, and finally moving the tower of size $n-1$ from peg 1 to peg 2. Therefore a general algorithm that moves a tower of size $m$ from peg $x$ to peg $y$ can be recursively implemented as the ordering/ labeling of the pegs does not impact the problem.

#### **Running Time Analysis**:
- Recursion Tree: A recurrence relation can be viewed as tree which splits at a node based on the integer constant that multiplies the recurrent function. Then the running time can be computed by looking at the running time contributed by each layer in the tree.

example: $T(n) = 2T(n/2)+cn$ split into 2 after each node but the running time contributed by each split is $cn/2$. This results in a constant amount of work done at each level. The total running time is the sum of the running times for each level. Because $n$ divides by 2 each time, there are $log(n)$ levels. This results in a total running time of $O(nlog(n))$.

<img src="/img/lectures/Lec10/lec10_fig1.PNG" alt="Example3" style="height: 150px;">

- Expanding the Recurrence: Expanding the recurrence is done by replacing the recurrent function on the right side of the equation the right hand side of the equation for the smaller case.

example: $T(n) = 2T(n/2) + cn$ can be rewritten as $T(n) = 2(2T(n/4)+cn/2)+cn = 4T(n/4)+cn+cn$. This replacement can occur $log(n)$ times because $n$ divides by 2 each time. Every time the replacement occurs an extra $cn$ is added. This means the eventual expansion will be $T(n) = cn+...cn = cnlog(n)$ which has a running time of $O(nlog(n))$.



<h4> Reductions example </h4>

Your very own, Mr. Kevin Lim, did an animation of a classic 374 reduction:

<iframe width="560" height="315" src="https://www.youtube.com/embed/aWWXXwp1Ya8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


<h4>Additional Resources</h4>
















