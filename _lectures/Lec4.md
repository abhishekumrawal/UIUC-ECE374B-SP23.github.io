---
title: Lecture 4 - Non-deterministic finite automata (NFAs)
placeholder: false
back-color: faffff
card-link: LecLink4
# subtitle: And a subtitle
description: Introduction to non-determinism. We'll talk about how it applies to automata and formalize NFA concepts/definitions.
people:
layout: lecture
# no-link: true  # stops link to page 
deliverydate: 2023-01-26
link-slides: /materials/lecture_slides/lec4.pdf
link-scribbles: /materials/lecture_slides/lec4_scribbles_sp23.pdf
link-recording: https://mediaspace.illinois.edu/media/t/1_jrvgweav/282723252
---

<style>
  table{
    border-collapse:separate;
    border-spacing: 50px;
  }
</style>

<h4>Nondeterministic Finite Automaton(NFA)</h4>

An NFA is a finite-state automaton that can non-deterministically transition between states.
Unlike a DFA, an NFA can:

1. Transition without taking an input symbol, which is called **$\epsilon$-transition**.
2. Have multiple transitions for the given source state and the input symbol.

Due to the properties described above, there can be multiple possible ways of transitioning between states given a single input string. 
If there exists a way to transition from the start state to an accepting state, then the NFA accepts the input string. 
Consider the following example of an NFA.

<img src="/img/lectures/Lec4/lec4_nfa.png" alt="Example NFA" style="height: 300px;">

Suppose the NFA received $1$ as an input string. There exists a transition from $a$ directly to the accepting state $d$, so the NFA accepts the input $1$. 
For an input $0$, there is a transition leading to $d$, by taking the $\epsilon$-transition to $b$ and then to $d$. 
For an input $10$, the NFA can reach $d$ through the state $c$. Therefore, the NFA accepts three strings, $0$, $1$, and $10$. 

<h4>Formal Definition of NFA</h4>

Formal definition of NFA is similar to that of DFA, except for the transition function. 
An NFA $N$ is a 5-tuple $N=(\Sigma, Q, \delta, s, A)$, which are input alphabet, states, transition function, start state, and accepting states, respectively.
However, unlike DFA, the transition function $\delta:Q\times \Sigma \rightarrow 2^Q$ is a function that maps the pairs of a state and an input symbol to the **power set** of $Q$.
This is because there can be multiple possible transitions for the given source state and the input symbol, each leading to a different state. 
The transition function of the example NFA above can be formally described as the following.

$$\delta(a, \epsilon)= \{ b \}$$

$$\delta(a, 1)=\{c, d\}$$

$$\delta(c, 0)=\{d\}$$

$$\delta(b, 0)=\{d\}$$

Note that not every (state, input symbol) pairs appear in the above definition. The missing pairs are implicitly mapped to the empty set $\emptyset$.

<h4>Closure properties of Regular Languages</h4>

An arbitrary NFA can be transformed to have a single accepting state as appears in the following figure. 

<img src="/img/lectures/Lec4/singleaccept.png" alt="Transforming an NFA to have a single accepting state" style="width: 500px;">

The closure properties of regular languages under union, concatenation, and Kleene Star can be proved using the transformed NFAs. 
The following figures show how the union, concatenation, Kleene star of regular languages can be constructed, given NFAs with a single accepting state for the languages. 

<table border='0'> 
  <tr>
    <td> <b>Union</b> </td>
    <td> <b>Concatenation</b> </td>
    <td> <b>Kleene Star</b> </td>
  </tr>
  <tr>
    <td>
      <img src="/img/lectures/Lec4/union.png" alt="Union" style="width: 300px;">
    </td>
    <td>
      <img src="/img/lectures/Lec4/concat.png" alt="Concatenation" style="width: 300px;">
    </td>  
    <td>
      <img src="/img/lectures/Lec4/kleene.png" alt="Kleene star" style="width: 300px;">
    </td>  
  </tr>
</table>







Since the NFAs for the operations could be constructed, we conclude that the resulting languages are regular, and therefore the class of all regular languages is closed under the three operations. 
Note that the NFAs after applying the operations in the figures also have a single accepting state. Therefore, any combinations of unions, concatenations, and Kleene stars can be represented by recursively applying the construction method. 

<h4>Terms and concepts</h4>

<h5>Power Set</h5>


The **power set** of a set $S$, often denoted as $2^S$, is a set of all subsets of $S$. 
For example, if $S=\\{0, 1 \\}$, then $2^S=\\{\emptyset, \\{0\\}, \\{1\\}, \\{0,1\\} \\}$.

<h5> $\epsilon$-Transition </h5>


An **$\epsilon$-transition** is a transition of an NFA that does not consume an input symbol.
If there is an outgoing$\epsilon$-transition from the current state of an NFA, then the NFA can choose to either take the $\epsilon$-transition or not.

An **$\epsilon$-reach** of a state $q \in Q$ is a set of all states that can be reached from $q$ without reading in an input symbol. 
In the example NFA, the $\epsilon$-reach of the state $a$ is $\\{a, b\\}$. Note that $\epsilon$-reach of a state always contains the state itself. 

<h5> Extended Transition Function </h5>

Describing transitions of an NFA on an input string requires applying transition function multiple times.
The resulting expression would contain nested transition functions like $\delta(\delta(\delta(q,1),0),1)$, which can be wordy and confusing. 
Alternatively, we can define an **extended transition function** $\delta^{\*}$ which defines transitions on an arbitrary string, as follows. 

$$\delta^{*}(q,\epsilon):=\epsilon\text{reach}(q)$$

$$\delta^{*} (q, ax) := \delta^{*} (\delta(q,a),x)$$

Intuitively, the extended transition function is defined by recursively applying the transition function on the current state and the leftmost symbol of the remaining input string.
The transition $\delta(\delta(\delta(q,1),0),1)$ introduced above can now be written as $\delta^{*}(q, 101)$. 
Note that defining the extended transition function does not change the behavior of the NFA at all. 
The extended transition function is more like a syntactic sugar derived from the original transition function. 


&nbsp;
<h4>Additional Resources</h4>
- [Jeff's - Notes on non-deterministic automata](https://jeffe.cs.illinois.edu/teaching/algorithms/models/04-nfa.pdf)
- [Sariel's Lecture 2](https://courses.engr.illinois.edu/cs374/fa2020/lec_prerec/) 
