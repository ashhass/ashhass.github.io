---
layout: page
description:
---


Wouldn’t it have been beautiful if each neuron encoded one and only one concept? If we want to remove a specific learned concept from a model, we could just zero out the weight of the corresponding neuron. Sure, but sadly, there seems to be more concepts than neurons within models. So, instead of relying on individual neurons, models encode many concepts using different combinations of neurons. One neuron can be a part of multiple groups of neurons, so it can activate to multiple concepts. 

The idea of features was created as a quest to define atomic units of analysis for neural network computations. This means that features are not decomposable to other meaningful units. In the activation space, features are represented usually as interpretable directions but can also be abstract. Features can be represented by multiple neurons working together. In some cases, individual neurons can also encode features. 

So, do features equate to concepts? No, features are not about you, they’re about the model. Whatever the model uses that causally affects performance is considered a feature. Sometimes it does encode some human-interpretable concept, but many times it does not.