---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Learning Optimal Classification Trees Using a Binary Linear Program Formulation
author_list: Sicco Verwer, Yingqian Zhang
venue: Proceedings of the AAAI Conference on Artificial Intelligence, 2019.
paper_link: https://www.aaai.org/ojs/index.php/AAAI/article/view/3978
---


We provide a new formulation for the problem of learning the optimal classification tree of a given depth as a binary linear program. A limitation of previously proposed Mathematical Optimization formulations is that they create constraints and variables for every row in the training data. As a result, the running time of the existing Integer Linear programming (ILP) formulations increases dramatically with the size of data. In our new binary formulation, we aim to circumvent this problem by making the formulation size largely independent from the training data size. We show experimentally that our formulation achieves better performance than existing formulations on both small and large problem instances within shorter running time.