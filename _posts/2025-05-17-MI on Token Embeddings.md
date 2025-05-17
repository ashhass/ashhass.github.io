---
layout: page
description: 
---

Features are thought to be directions in the embedding space. The superposition problem states that a single direction might encode multiple features. One direction can encode seemingly unrelated concepts like savannah and carpets. That might not be the case for all directions. In order to figure out what each direction corresponds to, we work with the token embedding matrices. One plausible way is to sparsify the embedding matrix by either introducing a sparsity constraint during training or choosing the top-k largest magnitudes. The way to enforce a sparsiy constraint is by adding a term to the loss function that penalizes any non-zero entry. Gradient descent therefore drives many coordinates toward exactly 0 so long as the reconstruction error stays acceptable. 