---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: On Bidirectional Deterministic Finite Automata
author_list: Simon Dieck, Sicco Verwer
venue: Interational Conference on Implementation and Application of Automata (CIAA)
year: 2024
code_link: 
paper_link: https://link-springer-com.tudelft.idm.oclc.org/chapter/10.1007/978-3-031-71112-1_8
---

Bidirectional deterministic finite automata (biDFA) are a recent innovation with many potential applications. In this paper, we present novel theoretical results for bidirectional automata. We show that there exist regular languages, where minimal biDFA models are exponentially smaller than minimal DFA models. We show this for a language that has a structure common to software logs. This makes biDFA especially interesting when inferring models from such data. However, we also prove that the problem of biDFA minimization is NP-hard. As our key contribution, we provide a Myhill-Nerode style congruence-based characterization for the languages they can recognize. Since most algorithms for learning DFAs are based on such a congruence, this characterization is an important building block for obtaining learning algorithms.