---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title: The Robust Malware Detection Challenge and Greedy Random Accelerated Multi-Bit Search
author_list: Sicco Verwer, Azqa Nadeem, Christian Hammerschmidt, Laurens Bliek, Abdullah Al-Dujaili, Una-May O'Reilly
code_link: https://github.com/tudelft-cda-lab/GRAMS
pre_link: http://pure.tudelft.nl/ws/portalfiles/portal/83427524/GRAMS_draft_2_.pdf
venue: Artificial Intelligence and Security (AISec), 2020
---


Training classifiers that are robust against adversarially modified examples is becoming increasingly important in practice. In the field of malware detection, adversaries modify malicious binary files to seem benign while preserving their malicious behavior. We report on the results of a recently held robust malware detection challenge. There were two tracks in which teams could participate: the attack track asked for adversarially modified malware samples and the defense track asked for trained neural network classifiers that are robust to such modifications. The teams were unaware of the attacks/defenses they had to detect/evade. Although only 9 teams participated, this unique setting allowed us to make several interesting observations.

We also present the challenge winner: GRAMS, a family of novel techniques to train adversarially robust networks that preserve the intended (malicious) functionality and yield high-quality adversarial samples. These samples are used to iteratively train a robust classifier. We show that our techniques, based on discrete optimization techniques, beat purely gradient-based methods. GRAMS obtained first place in both the attack and defense tracks of the competition.