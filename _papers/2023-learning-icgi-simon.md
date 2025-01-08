---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Learning state machines from data streams&#58; A generic strategy and an improved heuristic
author_list: Robert Baumgartner, Sicco Verwer
venue: International Conference on Grammatical Inference (ICGI)
year: 2023
code_link: https://github.com/tudelft-cda-lab/FlexFringe/tree/Publications/CSS_and_streaming
paper_link: https://proceedings.mlr.press/v217/baumgartner23a/baumgartner23a.pdf
---

State machines models are models that simulate the behavior of discrete event systems, capable of representing systems such as software systems, network interactions, and control systems, and have been researched extensively. The nature of most learning algorithms however is the assumption that all data be available at the begining of the algorithm, and little research has been done in learning state machines from streaming data. In this paper, we want to close this gap further by presenting a generic method for learning state machines from data streams, as well as a merge heuristic that uses sketches to account for incomplete prefix trees. We implement our approach in an open-source state merging library and compare it with existing methods. We show the effectiveness of our approach with respect to run-time, memory consumption, and quality of results on a well known open dataset.