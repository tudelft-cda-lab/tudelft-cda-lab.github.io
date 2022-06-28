---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: SECLEDS&#58; Sequence Clustering in Evolving Data Streams via Multiple Medoids and Medoid Voting
author_list: Azqa Nadeem, Sicco Verwer
venue: European Conference on Machine Learning and Principles and Practice of Knowledge Discovery in Databases (ECML/PKDD)
year: 2022
paper_link: https://arxiv.org/abs/2206.12190
code_link: https://github.com/tudelft-cda-lab/SECLEDS
---

Sequence clustering in a streaming environment is challenging because it is computationally expensive, and the sequences may evolve over time. K-medoids or Partitioning Around Medoids (PAM) is commonly used to cluster sequences since it supports alignment-based distances, and the k-centers being actual data items helps with cluster interpretability. However, offline k-medoids has no support for concept drift, while also being prohibitively expensive for clustering data streams. We therefore propose SECLEDS, a streaming variant of the k-medoids algorithm with constant memory footprint. SECLEDS has two unique properties: i) it uses multiple medoids per cluster, producing stable highquality clusters, and ii) it handles concept drift using an intuitive Medoid Voting scheme for approximating cluster distances. Unlike existing adaptive algorithms that create new clusters for new concepts, SECLEDS follows a fundamentally different approach, where the clusters themselves evolve with an evolving stream. Using real and synthetic datasets, we empirically demonstrate that SECLEDS produces high-quality clusters regardless of drift, stream size, data dimensionality, and number of clusters. We compare against three popular stream and batch clustering algorithms. The state-of-the-art BanditPAM is used as an offline benchmark. SECLEDS achieves comparable F1 score to BanditPAM while reducing the number of required distance computations by 83.7%. Importantly, SECLEDS outperforms all baselines by 138.7% when the stream contains drift. We also cluster real network traffic, and provide evidence that SECLEDS can support network bandwidths of up to 1.08 Gbps while using the (expensive) dynamic time warping distance.