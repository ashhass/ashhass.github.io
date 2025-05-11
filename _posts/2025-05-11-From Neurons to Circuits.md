---
layout: page
description:
---


Each neuron in a neural network contains some sort of information. The weights corresponding to each neuron dictate the contribution strength of a specific neuron to the formation of more complicated neurons in subsequent layers. Now, certain groups of neurons work together to form concepts. These groups of neurons and the connections between them form circuits. But how are neurons grouped into circuits? Grouping neurons should be based on concepts/features that they fire for. After choosing some behavior, weights can be traced back to components that influence this activation. 

To isolate causal neurons, activations from current prompt are replaced with activations from a control prompt that does not trigger the behavior in question. It’s important to make sure that no other component is causing this behavior change by controlling all other changes. This process is called activation patching. We can also ablate components or zero out weights of certain neurons and observe whether any behavior change is present. This process is called ablation.