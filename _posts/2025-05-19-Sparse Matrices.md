---
layout: page
description:
---



Reading weights from neural connections results in dense matrices with values filling up the matrix. Pinpointing which column or neuron fires for a certain feature is difficult since a lot of neurons might respond to the same feature even at varying degrees of strength. Hence, we derive multiple sparse matrices in hopes that we remove noise and focus on spotting interpretable, causal features. 

In addition, sparse matrices do not require the same amount of memory as a dense matrix since a lot of the entries are set to 0. So instead of casually allocating memory for every entry of the matrix, an efficient method is to sequentially save the non-zero weight values in an array with its matrix index. Entries in the matrix that are zero are not saved in memory, but rather set on the fly to 0.