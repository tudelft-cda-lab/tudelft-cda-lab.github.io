---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Learning state machines via efficient hashing of future traces
author_list: Robert Baumgartner, Sicco Verwer
venue: LearnAUT 2022
year: 2022
code_link: https://github.com/tudelft-cda-lab/FlexFringe
paper_link: https://arxiv.org/abs/2207.01516
---


State machines are popular models to model and visualize discrete systems such as software systems, and to represent regular grammars. Most algorithms that passively learn state machines from data assume all the data to be available from the beginning and they load this data into memory. This makes it hard to apply them to continuously streaming data and results in large memory requirements when dealing with large datasets. In this paper we propose a method to learn state machines from data streams using the count-min-sketch data structure to reduce memory requirements. We apply state merging using the well-known red-blue-framework to reduce the search space. We implemented our approach in an established framework for learning state machines, and evaluated it on a well know dataset to provide experimental data, showing the effectiveness of our approach with respect to quality of the results and run-time. 