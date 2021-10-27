---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Alert-driven Attack Graph Generation using S-PDFA
author_list: Azqa Nadeem, Sicco Verwer, Stephen Moskal, Shanchieh Jay Yang
venue: IEEE Transcations on Dependable and Secure Computing
year: 2021
paper_link: https://ieeexplore.ieee.org/abstract/document/9557854
code_link: https://github.com/tudelft-cda-lab/SAGE
---

Ideal cyber threat intelligence (CTI) includes insights into attacker strategies that are specific to a network under observation. Such CTI currently requires extensive expert input for obtaining, assessing, and correlating system vulnerabilities into a graphical representation, often referred to as an attack graph (AG). Instead of deriving AGs based on system vulnerabilities, this work advocates the direct use of intrusion alerts. We propose SAGE, an explainable sequence learning pipeline that automatically constructs AGs from intrusion alerts without a priori expert knowledge. SAGE exploits the temporal and probabilistic dependence between alerts in a suffix-based probabilistic deterministic finite automaton (S-PDFA)-a model that brings infrequent severe alerts into the spotlight and summarizes paths leading to them. Attack graphs are extracted from the model on a per-victim, per-objective basis. SAGE is thoroughly evaluated on three open-source intrusion alert datasets collected through security testing competitions in order to analyze distributed multi-stage attacks. SAGE compresses over 330k alerts into 93 AGs that show how specific attacks transpired. The AGs are succinct, interpretable, and provide directly relevant insights into strategic differences and fingerprintable paths. They even show that attackers tend to follow shorter paths after they have discovered a longer one in 84.5% of the cases.