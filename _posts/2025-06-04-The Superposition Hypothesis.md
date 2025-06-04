---
layout: page
description:
---

The superposition hypothesis explains a lot of the intriguing behaviors of neural networks. For one, it explains why it’s difficult to fully remove a concept from a network. If concepts are represented as directions or combinations of multiple neurons in a circuit, a natural speculation is that there are multiple such circuits explaining the same concept. So, removing one circuit reroutes the model towards another circuit which encodes the same concept reducing the presence of the concept, but not removing it entirely. 

It also explains why neurons respond to multiple unrelated concepts. A neuron can be a part of many different circuits, playing different roles according to the circuit context. Perhaps more interestingly, it explains why removing a circuit encoding a particular concept affects the performance on another concept (because neurons are shared).