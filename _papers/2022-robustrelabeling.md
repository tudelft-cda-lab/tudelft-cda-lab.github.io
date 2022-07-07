---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Adversarially Robust Decision Tree Relabeling
author_list: Daniël Vos, Sicco Verwer
venue: European Conference on Machine Learning and Principles and Practice of Knowledge Discovery in Databases (ECML/PKDD)
year: 2022
code_link: https://github.com/tudelft-cda-lab/robust-relabeling
---

Decision trees are popular models for their interpretation properties and their success in ensemble models for structured data. However, common decision tree learning algorithms produce models that suffer from adversarial examples. Recent work on robust decision tree learning mitigates this issue by taking adversarial perturbations into account during training. While these methods generate robust shallow trees, their relative quality reduces when training deeper trees due the methods being greedy. In this work we propose robust relabeling, a post-learning procedure that optimally changes the prediction labels of decision tree leaves to maximize adversarial robustness. We show this can be achieved in polynomial time in terms of the number of samples and leaves. Our results on 10 datasets show a significant improvement in adversarial accuracy both for single decision trees and tree ensembles. Decision trees and random forests trained with a state-of-the-art robust learning algorithm also benefited from robust relabeling.