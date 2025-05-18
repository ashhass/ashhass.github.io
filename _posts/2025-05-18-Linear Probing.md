---
layout: page
description:
---


Another method to understand concepts within token embeddings is linear probing. This basically involves analyzing the presence of target concepts within the embedding matrix. It first starts by freezing and extracting vectors from the embedding matrix. Once the vectors are identified, a hypothesis can be generated on what concepts these vectors encode. We then construct two classes, one containing the concept and the other lacking the concept, then train a linear classifier to separate the two classes. In our validation split, we use the classifier to measure the presence of said concept. If classification accuracy is high, we can conclude that the concept was already present in the embedding matrix. 

There are some problems with this approach. The obvious of which is that knowing whether concepts are present does not entail understanding how they’re used or whether they are used in the first place. The other caveat is that, whenever a simpler shortcut correlates with the target concept, a probe may seize on that shortcut and report it as the concept itself—producing a misleading, “false-positive” representation. You end up “detecting plural nouns” when all you really found was an “ends-with-s” dimension.