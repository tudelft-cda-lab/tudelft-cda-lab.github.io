---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Beyond Labeling Using Clustering to Build Network Behavioral Profiles of Malware Families
author_list: Azqa Nadeem, Christian Hammerschmidt, Carlos H. Ganan, Sicco Verwer
code_link: https://github.com/tudelft-cda-lab/malpaca-pub
pre_link: https://arxiv.org/abs/1904.01371v3
venue: Malware Analysis using Artificial Intelligence and Deep Learning, Springer
year: 2020
---


Malware family labels are known to be inconsistent. They are also black box since they do not represent the capabilities of malware. The current state-of the-art in malware capability assessment include mostly manual approaches, which are infeasible due to the ever-increasing volume of discovered malware samples. We propose a novel unsupervised machine learning-based method called MalPaCA, which automates capability assessment by clustering the temporal behavior in malware’s network traces. MalPaCA provides meaningful behavioral clusters using only 20 packet headers. Behavioral profiles are generated based on the cluster membership of malware’s network traces. A Directed Acyclic Graph shows the relationship between malwares according to their overlapping behaviors. The behavioral profiles together with the DAG provide more insightful characterization of malware than current family designations. We also propose a visualization-based evaluation method for the obtained clusters to assist practitioners in understanding the clustering results. We apply MalPaCA on a financial malware dataset collected in the wild that comprises of 1.1k malware samples resulting in 3.6M packets. Our experiments show that (i) MalPaCA successfully identifies capabilities, such as port scans and reuse of Command and Control servers; (ii) It uncovers multiple discrepancies between behavioral clusters and malware family labels; and (iii) It demonstrates the effectiveness of clustering traces using temporal features by producing an error rate of 8.3%, compared to 57.5% obtained from statistical features.