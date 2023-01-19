---
title: Lecture 2 - Languages and regular expression
placeholder: false
back-color: faffff
card-link: LecLink2
# subtitle: And a subtitle
description: We'll discuss regular languages and representing them as regular expressions (the OG RegEx). 
people:
layout: lecture
# no-link: true  # stops link to page 
deliverydate: 2023-01-19
link-slides: /lecture_slides/lec2.pdf
link-scribbles:
link-recording:
---

#### Strings and Languages
- Strings are the elements of the lenguauges. Each string represents a problem instance. 
- A alphabet($\Sigma$) is a finite set of symbols (example: $\Sigma = \{0, 1\}$).

Some string and set facts: 
<div class="row">
    <div class="col-md-6">
    Strings:
    - $x \cdot y = xy$ is the concatenation of two strings. 
    - $\vert w \vert$ is the length of a string
    - $\Sigma^n$ is the set of all strings over $\Sigma$ of length $n$
    - $\Sigma^*$ is the set of all strings over $\Sigma$ of all lengths
    - $\varepsilon$ is the empty string
    - Subsequence of string is a subset of its charcaters that appear in the same order as they do in the original string
    </div>
    <div class="col-md-6">
    Sets:
    - $\emptyset$ is the empty set
    - $\{ \varepsilon \}$ is the non-empty set containing one element, the empty string.
    - Concatentation of two sets is all possible pairs of elements
    </div>    
</div>

#### Regular Languages

**Kleene's Theorem:** A language is regular if and only if it can be obtained from finite labguages by applying the three operations: union, concatentation, repetition a finite numer of times. 

**Base Case:** $\emptyset$, $\{ \varepsilon \}$, $\{a\}$ (for each $a \in \Sigma$) are all regular langauges. 



&nbsp;
<h4>Additional Resources</h4>
- [Jeff's - Notes on strings](https://jeffe.cs.illinois.edu/teaching/algorithms/models/01-strings.pdf)
- [Jeff's notes on regular languages](https://jeffe.cs.illinois.edu/teaching/algorithms/models/02-regular.pdf)
- [Sariel's Lecture 1](https://courses.engr.illinois.edu/cs374/fa2020/lec_prerec/) 







