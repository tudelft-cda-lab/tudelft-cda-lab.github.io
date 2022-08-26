---
layout: paper
feature_image: "https://picsum.photos/2560/600?image=872"

title:  Learning State Machines to Monitor and Detect Anomalies on a Kubernetes Cluster
author_list: Clinton Cao, Sicco Verwer, Agathe Blaise, Filippo Rebecchi
venue: International Conference on Availability, Reliability and Security (ARES) - IWCSEC Workshop
year: 2022
paper_link: https://dl-acm-org.tudelft.idm.oclc.org/doi/10.1145/3538969.3543810
---

These days more companies are shifting towards using cloud environments
to provide their services to their client. While it is easy
to set up a cloud environment, it is equally important to monitor
the system’s runtime behaviour and identify anomalous behaviours
that occur during its operation. In recent years, the utilisation
of Recurrent Neural Networks (RNNs) and Deep Neural
Networks (DNNs) to detect anomalies that might occur during runtime
has been a trending approach. However, it is unclear how to
explain the decisions made by these networks and how these networks
should be interpreted to understand the runtime behaviour
that they model. On the contrary, state machine models provide
an easier manner to interpret and understand the behaviour that
they model. In this work, we propose an approach that learns state
machine models to model the runtime behaviour of a cloud environment
that runs multiple microservice applications. To the best of our
knowledge, this is the first work that tries to apply state machine
models to microservice architectures. The state machine model is
used to detect the different types of attacks that we launch on the
cloud environment. From our experiment results, our approach can
detect the attacks very well, achieving a balanced accuracy of 99.2%
and an 𝐹1 score of 0.982.
