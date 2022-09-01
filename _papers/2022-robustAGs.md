---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Robust Attack Graph Generation
author_list: Dennis Mouwen, Sicco Verwer, Azqa Nadeem
venue: Learning and Automata workshop (LearnAut)
year: 2022
code_link: https://github.com/dennism1997/SAAT
paper_link: https://arxiv.org/abs/2206.07776
---


We present a method to learn automaton models that are more robust to input modifications. It iteratively aligns sequences to a learned model, modifies the sequences to their aligned versions, and re-learns the model. Automaton learning algorithms are typically very good at modeling the frequent behavior of a software system. Our solution can be used to also learn the behavior present in infrequent sequences, as these will be aligned to the frequent ones represented by the model. We apply our method to the SAGE tool for modeling attacker behavior from intrusion alerts. In experiments, we demonstrate that our algorithm learns models that can handle noise such as added and removed symbols from sequences. Furthermore, it learns more concise models that fit better to the training data.