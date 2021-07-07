---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: SAGE Intrusion Alert-driven Attack Graph Extractor
author_list: Azqa Nadeem, Sicco Verwer, Stephen Moskal, Shanchieh Jay Yang
venue: KDD Workshop on AI-enabled Cybersecurity Analytics (AI4cyber)
year: 2021
pre_link: https://arxiv.org/abs/2107.02783?context=cs.LG
---

Attack graphs (AG) are used to assess pathways availed by cyber adversaries to penetrate a network. State-of-the-art approaches for AG generation focus mostly on deriving dependencies between system vulnerabilities based on network scans and expert knowledge. In real-world operations however, it is costly and ineffective to rely on constant vulnerability scanning and expert-crafted AGs. We propose to automatically learn AGs based on actions observed through intrusion alerts, without prior expert knowledge. Specifically, we develop an unsupervised sequence learning system, SAGE, that leverages the temporal and probabilistic dependence between alerts in a suffix-based probabilistic deterministic finite automaton (S-PDFA) -- a model that accentuates infrequent severe alerts and summarizes paths leading to them. AGs are then derived from the S-PDFA. Tested with intrusion alerts collected through Collegiate Penetration Testing Competition, SAGE produces AGs that reflect the strategies used by participating teams. The resulting AGs are succinct, interpretable, and enable analysts to derive actionable insights, e.g., attackers tend to follow shorter paths after they have discovered a longer one.