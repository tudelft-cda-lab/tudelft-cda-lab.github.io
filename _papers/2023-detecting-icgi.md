---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title:  Detecting Changes in Loop Behavior for Active Learning
author_list: Bram Verboom, Simon Dieck, Sicco Verwer
venue: International Conference on Grammatical Inference (ICGI)
year: 2023
code_link: https://github.com/tudelft-cda-lab/SymLoop
paper_link: https://proceedings.mlr.press/v217/verboom23a/verboom23a.pdf
---

Active automaton learning is a popular approach for building models of software systems. The approach forms a hypothesis model from observations and then performs a heuristic equivalence query to check if the learned model is equal to the model under test.
The current methods for equivalence queries, however often fail to find counterexamples when encountering loops, one of the most common control structures in software. We introduce two novel equivalence checkers that better handle loops. One extends the well-known W-Method, and the other uses symbolic execution. Both methods are tested on RERS challenge problems. We show that our approaches find more counterexamples on suitable problems and thus learn more accurate models. We further test our symbolic execution approach outside active learning and show that it finds more errors than the state-of-the-art method Klee on several problems.