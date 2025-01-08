---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Learning Syntactic Monoids from Samples by extending known Algorithms for learning State Machines
author_list: Simon Dieck, Sicco Verwer
venue: International Conference on Grammatical Inference (ICGI)
year: 2023
code_link:
paper_link: https://proceedings.mlr.press/v217/dieck23a.html
---

For the inference of regular languages, most current methods learn a version of deterministic finite automata. Syntactic monoids are an alternative representation of regular languages, which have some advantages over automata. For example, traces can be parsed starting from any index and the star-freeness of the language they represent can be checked in polynomial time. But, to date, there existed no passive learning algorithm for syntactic monoids. In this paper, we prove that known state-merging algorithms for learning deterministic finite automata can be instrumented to learn syntactic monoids instead, by using as the input a special structure proposed in this paper: the interfix-graph. Further, we introduce a method to encode frequencies on the interfix-graph, such that models can also be learned from only positive traces. We implemented this structure and performed experiments with both traditional data and data containing only positive traces. As such this work answers basic theoretical and experimental questions regarding a novel passive learning algorithm for syntactic monoids.