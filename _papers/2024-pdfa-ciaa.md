---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: PDFA Distillation with Error Bound Guarantees
author_list: Robert Baumgartner, Sicco Verwer
venue: Interational Conference on Implementation and Application of Automata (CIAA)
year: 2024
code_link: 
paper_link: https://link-springer-com.tudelft.idm.oclc.org/chapter/10.1007/978-3-031-71112-1_4
---

Active learning algorithms to infer probabilistic finite automata (PFA) have gained interest recently, due to their ability to provide surrogate models for some types of neural networks. However, recent approaches either cannot guarantee determinism, which makes the automaton harder to understand and compute, or they rely on techniques that bound errors on individual transitions. In this work we propose a derivative of the recent algorithm to learn deterministic PFA (PDFA) from systems returning a distribution over a set of tokens given an input string. Along with determinism, we can give error bounds on probabilities assigned to whole strings with an easy to understand approach. We show formal correctness of our algorithm and test it on neural networks trained to model three datasets from computer- and network-systems respectively. We show that the algorithm can learn the network’s behaviour closely, and provide an example application of how the model can be used to interpret the network. We note that our approach is in theory applicable in general to learn deterministic weighted finite automata. We provide the source code of our algorithm and relevant scripts on our public repository.