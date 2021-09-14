---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: SAGE Intrusion Alert-driven Attack Graph Extractor
author_list: Azqa Nadeem, Sicco Verwer, Shanchieh Jay Yang
venue: Symposium on Visualization for Cyber Security (VizSec)
year: 2021
paper_link: https://azqa.github.io/assets/pdf/SAGE-for-VizSec.pdf
code_link: https://github.com/tudelft-cda-lab/SAGE
---

Attack graphs (AG) are used to assess pathways availed by cyber adversaries to penetrate a network. State-of-the-art approaches for AG generation focus mostly on deriving dependencies between system vulnerabilities based on network scans and expert knowledge. In real-world operations however, it is costly and ineffective to rely on constant vulnerability scanning and expert-crafted AGs. We propose to automatically learn AGs based on actions observed through intrusion alerts, without prior expert knowledge. Specifically, we develop an unsupervised sequence learning system, SAGE, that leverages the temporal and probabilistic dependence between alerts in a suffix-based probabilistic deterministic finite automaton (S-PDFA) – a model that accentuates infrequent severe alerts and summarizes paths leading to them. AGs are then derived from the S-PDFA on a per-objective, per-victim basis. Tested with intrusion alerts collected through Collegiate Penetration Testing Competition, SAGE compresses over 330k alerts into 93 AGs. These AGs reflect the strategies used by the participating teams. The AGs are succinct, interpretable, and capture behavioral dynamics, e.g., that attackers will often follow shorter paths to re-exploit objectives.