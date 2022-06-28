---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: Enabling Visual Analytics via Alert-driven Attack Graphs
author_list: Azqa Nadeem, Sicco Verwer, Stephen Moskal, Shanchieh Jay Yang
venue: ACM SIGSAC Conference on Computer and Communications Security (CCS)
year: 2021
paper_link: https://dl.acm.org/doi/abs/10.1145/3460120.3485361
code_link: https://github.com/tudelft-cda-lab/SAGE
---

Attack graphs (AG) are a popular area of research that display all the paths an attacker can exploit to penetrate a network. Existing techniques for AG generation rely heavily on expert input regarding vulnerabilities and network topology. In this work, we advocate the use of AGs that are built directly using the actions observed through intrusion alerts, without prior expert input.We have developed an unsupervised visual analytics system, called SAGE, to learn alert-driven attack graphs.We show how these AGs (i) enable forensic analysis of prior attacks, and (ii) enable proactive defense by providing relevant threat intelligence regarding attacker strategies. We believe that alert-driven AGs can play a key role in AI-enabled cyber threat intelligence as they open up new avenues for attacker strategy analysis whilst reducing analyst workload.