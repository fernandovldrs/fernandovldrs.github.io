---
title: Resonators in circuit QED
author: Fernando Valadares
layout: post
---

If you wish to learn more about circuit quantum electrodynamics (cQED), this is where you should start. To eventually understand the design of superconducting quantum processors, the best strategy is to first understand the simplest quantum circuit: the superconducting resonator. 

This post will give the first introduction to this device. First, we take a look at resonators in classical physics. Then we lay down the recipe for translating classical circuits into quantum mechanics. We apply this procedure to a lump-element resonator, which is a simple but useful model. To wrap up, we will see how the same procedure can be used for more realistic distributed-element circuits, which gives origin to multi-mode resonators. By the end, you will have an idea of how to apply the same procedure to other circuits, as will be done in future posts.

# The classical resonator

In classical electrical circuits, the resonator is nothing more than an LC circuit. That is, it can be modeled as a capacitor shunted by an inductor. If one node of the circuit is grounded, the second node has a voltage $V$. Then the inductor follows the dynamical equations

$$
V = L\frac{di}{dt}, \ \ L = -\frac{\phi}{i}, \ \ E_L = \int_{-\infty}^tV i dt = \frac{L i^2}{2} = \frac{\phi^2}{2L}. 
$$

Where $i$ is the current flowing through the inductor and the node flux is defined as $\phi = \int_{-\infty}^tV(t)dt$. $E_L$ is the inductive energy stored in the circuit at a given moment $t$, assuming all variables are null at $t\to-\infty$. The capacitor shares the current and voltage over the inductor and follows the known dynamics

$$Q = CV, \ \ i = -\frac{dQ}{dt}, \ \ E_C = -\int_{-\infty}^tV i dt = \frac{Q^2}{2C}. $$

$E_C$ is the capacitive energy stored in the circuit at a given moment. So far, no groundbreaking physics has been shown. This circuit behaves as a harmonic oscillator, as we see in the dynamical equation of the current:

$$\frac{dQ}{dt} = C\frac{dV}{dt} \rightarrow i = -LC \frac{d^2i}{dt^2}$$

The solution is $i(t) = i_0\cos(\omega_r t + \theta)$, where the current oscillates with a frequency $\omega_r = (LC)^{-\frac{1}{2}}$. This type of system has been studied to exhaustion by any physicist, so there's no need to talk more about it. The interesting part comes next when this circuit becomes quantum.


# Circuit quantization: modeling superconducting resonators

cQED is the formulation of circuits in the quantum mechanical regime. It is based on a very straightforward (although complex) premise that we can quantize the parameters of the circuit. The node charges $Q$ and fluxes $\phi$ become quantum variables described by operators and the circuit state evolves according to the Schrodinger equation. But to follow through with this idea, as with any quantum problem, we need to find the correct Hamiltonian.

The procedure to find a Hamiltonian is often done wrongly, so it is worth showing the general step-by-step. The first step is to obtain the classical Hamiltonian of the circuit, and then substitute the conjugate pairs of dynamical variables by non-commuting operators. In circuit QED, that is:
1. Numerate all the nodes of the circuit and define the variables $Q_k$ and $i_k$ for the $k$-th node.
