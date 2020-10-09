---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Solving bin-packing problems under privacy preservation: Possibilities and trade-offs
author_list: Rowan Hoogervorst, Yingqian Zhang, Gamze Tillem, Zekeriya Erkin, Sicco Verwer
venue: Information Sciences, 2019.
paper_link: https://www.sciencedirect.com/science/article/pii/S0020025519303974
---


We investigate the trade-off between privacy and solution quality that occurs when a k-anonymized database is used as input to the bin-packing optimization problem. To investigate the impact of the chosen anonymization method on this trade-off, we consider two recoding methods for k-anonymity: full-domain generalization and partition-based single-dimensional recoding. To deal with the uncertainty created by anonymization in the bin-packing problem, we utilize stochastic programming and robust optimization methods. Our computational results show that the trade-off is strongly dependent on both the anonymization and optimization method. On the anonymization side, we see that using single dimensional recoding leads to significantly better solution quality than using full domain generalization. On the optimization side, we see that using stochastic programming, where we use the multiset of values in an equivalence class, considerably improves the solutions. While publishing these multisets makes the database more vulnerable to a table linkage attack, we argue that it is up to the data publisher to reason if such a loss of anonymization weighs up to the increase in optimization performance.