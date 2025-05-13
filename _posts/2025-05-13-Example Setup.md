---
layout: page
description:
---


To put concepts into a practical example, we can try to simulate a trivial example to understand the general flow. We can extract the Sobel horizontal filter from a CNN trained to mimic an edge detection algorithm. 

To clarify the components, the input would be a 28 by 28 image, the kernel would be a 3 by 3 filter akin to the Sobel filter, padding would be 1. We generate the ground truth by applying an edge detection algorithm to the images. 

The point is to observe whether the weights converge to Sobel-like filters. Weights in this case refer to the connections between the 3 by 3 image patch to the hidden layer which consists of a single neuron. This neuron is the output of applying the weights on the image patch (also called the activation). We can visualize this activation to see whether an edge is detected in the patch. 

Now, what happens if there are more neurons than necessary to extract the algorithm? What happens if there are fewer neurons? What happens when we ablate some filter values? Can we patch in these Sobel-like filters into any trained CNN architecture?