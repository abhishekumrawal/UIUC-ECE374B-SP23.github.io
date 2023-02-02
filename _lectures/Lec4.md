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

<h4>Nondeterministic Finite Automaton(NFA)</h4>
An NFA is a finite-state automaton that can non-deterministically transition between states.
Unlike a DFA, an NFA can:</br>
1. Transition without taking an input symbol, which is called $\varepsilon$-transition.</br>
2. Have multiple transitions for the given source state and the input symbol. </br></br>

Due to the properties described above, there can be multiple possible ways of transitioning between states given a single input string. 
If there exists a way to transition to an accepting state, the NFA accepts the input string. 
Consider the following example of an NFA.


Suppose the NFA received $1$ as an input string. There exists a transition from $a$ directly to the accepting state $d$, so the NFA accepts the input $1$. 
For an input $0$, there is a transition leading to $d$, by taking the $\varepsilon$-transition to the state $b$ and then to $d$. 
For an input $10$, the NFA can reach $d$ through the state $c$. Therefore, the NFA accepts three strings, $0$, $1$, and $10$. 

<h4>Formal Definition of NFA</h4>
Formal definition of NFA is similar to that of DFA, except for the transition function. 
An NFA $A$ is a 5-tuple $(\Sigma, Q, \vardelta, s, A)$, which are input alphavet, states, transition function, start state, and accepting states, respectively.
However, unlike DFA, the transition function $\vardelta:Q\times \Sigma \rightarrow 2^Q$ is a function that maps a pair of state and an input symbol to a subset of $Q$.
This is because there can be multiple possible transitions for the given source state and the input symbol, each leading to a different state. 
The transition function of the example NFA above can be formally described as the following.
$\vardelta(a, \varepsilon)=\{b\}$
$\vardelta(a, 1)=\{c, d\}$
$\vardelta(c, 0)=\{d\}$
$\vardelta(b, 0)=\{d\}$
 

&nbsp;
<h4>Additional Resources</h4>
- [Jeff's - Notes on non-deterministic automata](https://jeffe.cs.illinois.edu/teaching/algorithms/models/04-nfa.pdf)
- [Sariel's Lecture 2](https://courses.engr.illinois.edu/cs374/fa2020/lec_prerec/) 






