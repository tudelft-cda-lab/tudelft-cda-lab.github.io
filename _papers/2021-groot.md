---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Efficient training of robust decision trees against adversarial examples
author_list: Daniël Vos, Sicco Verwer
venue: International Conference on Machine Learning (ICML)
year: 2021
code_link: https://github.com/tudelft-cda-lab/GROOT
paper_link: https://proceedings.mlr.press/v139/vos21a.html
---

Current state-of-the-art algorithms for training robust decision trees have high runtime costs and require hours to run. We present GROOT, an efficient algorithm for training robust decision trees and random forests that runs in a matter of seconds to minutes. Where before the worst-case Gini impurity was computed iteratively, we find that we can solve this function analytically to improve time complexity from O (n) to O (1) in terms of n samples. Our results on both single trees and ensembles on 14 structured datasets as well as on MNIST and Fashion-MNIST demonstrate that GROOT runs several orders of magnitude faster than the state-of-the-art works and also shows better performance in terms of adversarial accuracy on structured data.