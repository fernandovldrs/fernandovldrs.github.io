---
title: Filter design in Ansys HFSS for circuit QED
author: Fernando Valadares
layout: post
---
Transmission lines (TLs) are the backbone of any radio-frequency (RF) circuit. For anyone using RF signals to control quantum systems such as superconducting circuits, the transmission lines will be the ones connecting the grubby, classical outside world with the low-noise environment of the dilution refrigerator.

Most of the time, TLs such as SMA cables are just bought off the shelf and used without much thought - not even with a glance at the specs sheet. This is almost aways perfectly fine. But sometimes when working with superconducting circuits, understanding the nuances of TL physics is necessary to engineer the systems more accurately. For example, on-chip filters are often designed solely based on a bunch of connected TLs. And that’s when the false familiarity of everyday use leads to confusion. 

My purpose is to give the basic tools researchers need to design transmission lines in superconducting circuits. This knowledge could be used to design qubit control lines, on-chip filters and resonators, or simply help better understand how electromagnetic fields behave at circuit level. I will split the story into two post: the first one will explain some of the physics behind TLs. The second post will show how to design filters in superconducting circuits using finite-element simulations.

As a guideline, in this post I will comment on a few confusion points that I sometimes see in the laboratory. We will build some intuitive understanding of transmission lines, and explore some relevant circuit equations.

# Table of Contents
* TOC
{:toc}


# Transmission lines are not just DC wires
What is the difference between the two images below?

{% include image.liquid url="/assets/disentangling_TL_circuit.png" %}
