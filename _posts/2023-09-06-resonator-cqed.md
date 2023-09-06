---
title: Resonators in circuit QED
author: Fernando Valadares
layout: post
---

If you wish to learn more about circuit quantum electrodynamics (cQED), this is where you should start. To eventually understand the design of superconducting quantum processors, the best strategy is to first understand the simplest quantum circuit: the superconducting resonator. 

This post will give the first introduction to this device. First, we lay down the recipe for circuit quantization. Then we apply it to a lump-element resonator, which is a simple but useful model. Then we will see how the same procedure can be used for more realistic distributed-element circuits, which gives origin to multi-mode resonators. By the end, you will have an idea of how to apply the same procedure to other circuits, as will be done in future posts.

# The classical resonator

In classical electrical circuits, the resonator is nothing more than an LC circuit. That is, it can be modeled as a capacitor shunted by an inductor. If one node of the circuit is grounded, the second node has a voltage $V$. Then the inductor follows the dynamical equations

$$
V = L\frac{di}{dt}, \ \ L = -\frac{\phi}{i}, \ \ E_L = \int_{-\infty}^tV i dt = \frac{\phi^2}{2L}. 
$$

Where $i$ is the current flowing through the inductor and the node flux is defined as $\phi = \int_{-\infty}^tV(t)dt$. $E_L$ is the inductive energy stored in the circuit at a given moment $t$, assuming all variables are null at $t\to-\infty$. The capacitor shares the current and voltage over the inductor, and follows the known dynamics

$$Q = CV, \ \ i = -\frac{dQ}{dt}, \ \ E_C = -\int_{-\infty}^tV i dt = \frac{Q^2}{2C}. $$

So far
cQED is the formulation of circuit parameters in the quantum mechanical regime: node charges and fluxes become quantum variables akin to position and momentum, and the circuit states can maintain properties such as superposition and entanglement as long as the system is protected from the environment.
