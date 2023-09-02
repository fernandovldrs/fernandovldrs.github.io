---
title: Optimal integration weights in qubit readout
author: Fernando Valadares
layout: post
---

# Introduction

The state of a superconducting qubit can be measured using a probe microwave signal. By analyzing the probe after it has interacted with the system, 
we extract its phase and amplitude values (or, equivalently, the signal quadratures) and assign the qubit state either to $\left|0\right>$ or $\left|1\right>$. 

But how to extract the quadrature values of a pulse, and how to do so in an optimal, noise-resistant way? 

The objective of this post is to go through the math and the code for finding the optimal integration weights of a readout. These are functions that weigh each data point of a readout integration process, assigning high weight to time bins that carry high information content of the qubit and assigning low weight to instants in which noise dominates. I will show the relevant Python code and you will be able to apply this procedure regardless of the control electronics that are used.

# Table of Contents
* TOC
{:toc}


{% include image.liquid url="/assets/readout-opt_acd_signal_noisy.png" description="Example of probe signal to be analyzed." %}
