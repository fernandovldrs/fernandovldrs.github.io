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


# The Is and Qs of a signal

Suppose you have, inside a dilution refrigerator at millikelvin temperature, a superconducting qubit dispersively coupled to a readout resonator.
The resonator is coupled to a coaxial line connected to your control electronics on the exterior of the refrigerator. The qubit readout process
consists of the following steps:
- A baseband probe signal is created by an FPGA controller with 100s of MHz bandwidth;
- The signal is upconverted to GHz frequencies to be near-resonance to the readout resonator;
- The upconverted signal travels into the refrigerator, interacts with the system, and travels back out, and
- The signal is again downconverted to baseband, and then its trace is acquired by an ADC.

This is what the ADC-aquired signal looks like:
{% include image.liquid url="/assets/readout-opt_acd_signal_noisy.png" description="Example of probe signal to be analyzed." %}
