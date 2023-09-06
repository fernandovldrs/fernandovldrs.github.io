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

**1\. Numerate all the nodes of the circuit and define the variables $Q_k$ and $i_k$ for the $k$-th node.**

In the case of the resonator, there is only one pair of $Q$ and $i = \dot{Q}$.

**2\. Write the Lagrangian in terms of these variables $L(Q_k, i_k, t) = T - V$. T and V are the kinetic and potential energies of the system, respectively.**

The kinetic energy is the capacitive energy $T = E_C$, while the potential energy is the inductive energy $V = E_L$. Our lagrangian is

$$L(Q, i) = \frac{Q^2}{2C} - \frac{L i^2}{2}$$

**3\. Calculate the generalized momentum $p_k$ of each charge $Q_k$: $p_k = \frac{\partial L}{\partial i_k}$ **

The generalized momentum is $p = -Li = \phi$!

**4\. Apply the Legendre transform to the Lagrangian to obtain the classical Hamiltonian: H(Q_k, p_k, t) = L - \sum_k p_k i_k**

In this step, we have to remember to rewrite every $i_k$ as $p_k$. The solution is again very simple for the resonator:

$$H(Q, \phi) = \frac{Q^2}{2C} - \frac{Li^2}{2} - \phi i = \frac{Q^2}{2C} + \frac{\phi^2}{2L} $$

The Hamiltonian is essentially the total energy $E_C + E_L$ in terms of $Q$ and $\phi$. It is common to jump to this step and simply write the Hamiltonian as the total energy, and it is correct most of the time. But this might not be so easy to do in more complicated systems, so I decided to show how to get here in the correct way.

**5\. Quantize the Hamiltonian by replacing the variables $Q$ and $\phi$ by operators $\hat{Q}$ and $\hat{\phi}$ such that $\[\hat{Q}, \hat{\phi}\] = i\hbar$
**

This step is sometimes called "first quantization". It is a simple substitution that makes the function $H(Q, \phi)$ into an operator $\hat{H}(\hat{Q}, \hat{\phi})$. The Hamiltonian of a superconducting resonator is:

$$\hat{H} = \frac{\hat{Q}^2}{2C} + \frac{\hat{\phi}^2}{2L}$$.

As expected, this is the Hamiltonian of a quantum harmonic oscillator.
