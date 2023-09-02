---
title: Optimal integration weights in qubit readout
author: Fernando Valadares
layout: post
---

The state of a superconducting qubit is measured with a probe microwave signal. By analyzing the probe after it has interacted with the system, 
we extract its phase and amplitude values (or, equivalently, the signal quadratures) and assign the qubit state either to $\left|0\right>$ or $\left|1\right>$. 

But how to extract the quadrature values of a pulse, and how to do so in an optimal, noise-resistant way? 

The objective of this post is to go through the math and the code for finding the optimal integration weights of a readout. These are functions that weight each data point of a readout integration process, assigning high weight to time bins that carry high information content of the qubit and assigns low weight to instants in which noise dominates.
