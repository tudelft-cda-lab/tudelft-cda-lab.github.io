---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Hybrid Connection and Host Clustering for Community Detection in Spatial-temporal Network Data
author_list: Mark Patrick Roeling, Azqa Nadeem, Sicco Verwer
venue: Machine Learning for Cybersecurity (MLCS) @ ECML-PKDD
year: 2020
paper_link: https://link.springer.com/chapter/10.1007/978-3-030-65965-3_12
---


Network data clustering and sequential data mining are large fields of research, but how to combine them to analyze spatial-temporal network data remains a technical challenge. This study investigates a novel combination of two sequential similarity methods (Dynamic Time Warping and N-grams with Cosine distances), with two state-of-the-art unsupervised network clustering algorithms (Hierarchical Density-based Clustering and Stochastic Block Models). A popular way to combine such methods is to first cluster the sequential network data, resulting in connection types. The hosts in the network can then be clustered conditioned on these types. In contrast, our approach clusters nodes and edges in one go, i.e., without giving the output of a first clustering step as input for a second step. We achieve this by implementing sequential distances as covariates for host clustering. While being fully unsupervised, our method outperforms many existing approaches. To the best of our knowledge, the only approaches with comparable performance require manual filtering of connections and feature engineering steps. In contrast, our method is applied to raw network traffic. We apply our pipeline to the problem of detecting infected hosts (network nodes) from logs of unlabelled network traffic (sequential data). On data from the Stratosphere IPS project (CTUMalware-Capture-Botnet-91), which includes malicious (Conficker botnet) as well as benign hosts, we show that our method perfectly detects peripheral, benign, and malicious hosts in different clusters. We replicate our results in the well-known ISOT dataset (Storm, Waledac, Zeus botnets) with comparable performance: conjointly, 99.97% of nodes were categorized correctly.