---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Optimal Decision Tree Policies for Markov Decision Processes
author_list: Daniël Vos, Sicco Verwer
venue: International Joint Conference on Artificial Intelligence (IJCAI)
year: 2023
code_link:
paper_link: https://www.ijcai.org/proceedings/2023/606
---

Interpretability of reinforcement learning policies is essential for many real-world tasks but learning such interpretable policies is a hard problem. Particularly, rule-based policies such as decision trees and rules lists are difficult to optimize due to their non-differentiability. While existing techniques can learn verifiable decision tree policies, there is no guarantee that the learners generate a policy that performs optimally. In this work, we study the optimization of size-limited decision trees for Markov Decision Processes (MPDs) and propose OMDTs: Optimal MDP Decision Trees. Given a user-defined size limit and MDP formulation, OMDT directly maximizes the expected discounted return for the decision tree using Mixed-Integer Linear Programming. By training optimal tree policies for different MDPs we empirically study the optimality gap for existing imitation learning techniques and find that they perform sub-optimally. We show that this is due to an inherent shortcoming of imitation learning, namely that complex policies cannot be represented using size-limited trees. In such cases, it is better to directly optimize the tree for expected return. While there is generally a trade-off between the performance and interpretability of machine learning models, we find that on small MDPs, depth 3 OMDTs often perform close to optimally.