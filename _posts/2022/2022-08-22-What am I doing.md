---
layout: post
title:  About my studies (or what I was doing in Sweden)
categories: physics, mathematics
usemathjax: true
---

This post is inspired by the awkward real-life encounters with people asking me what I am doing in my life. Since I am never satisfied with my answers, I'm gonna try to explain in text form...

# The short answer
First things first: I studied physics! Physics is the science that studies nature. My MSc programme focused on the theoretical aspect of high-energy and fundamental physics. That is quantum field theories from a more mathematical perspective; we studied the way small things interact with each other and how we can employ sophisticated mathematical tools to explain how the 4 fundamental forces work. The department has a strong presence in that particular field, especially in the scattering amplitudes domain which is what I am currently focused on with my thesis. If you'd like to check these subjects out, you can search for [QFT][qft] (main theoretical framework), [QED][qed], [QCD][qcd] and [String Theory][string_theory] but beware of the maths!

Another domain I am very interested in is [Quantum Information and Quantum Computing & Algorithms][qc]. In this field, we exploit the extraordinary properties of quantum particles to create powerful computational systems that can perform specific computations much faster than their classical counterparts.


# In more detail...
A theoretical physicist builds models (either empirically or mathematically) that aim to explain certain phenomena and make predictions. 

In my area of interest _a theory_ usually refers to the mathematical properties of the framework which can actually be incorporated into the Lagrangian (when dealing with fields we make use of the _Lagrangian density_) of the system. The Lagrangian is a function that basically encodes almost all the information of the physical properties of the system we are studying in a single expression. In more advanced and sophisticated theories, we will also need a few extras to build our models and get meaningful results.

Now, how can one quantity, $$L(q,p,t)$$- the Lagrangian, hold all the available information of the system? The truth is that in order to fully use $$L$$, we need to build the _action_, $$S$$, a [functional][functional] that takes the Lagrangian and sums it over the time period of the phenomenon. Then, we use the [Principle of Least Action][pola] which helps us produce equations that upon solving, we can obtain a complete picture of the phenomenon.

Take [$$N=4$$ super(symmetric) Yang-Mills][sym] for example. This is a supersymmetric theory, with 4 generators and a Yang-Mills potential term. The term "supersymmetric theory" refers to a Lagrangian which has an intrinsic property that allows for the exchange "Fermion $$\leftrightarrow$$ Boson" without changing in a meaningful way (i.e. it has a **symmetry**). $$N=4$$ refers to the number of supersymmetry generators, i.e. the number of operators whose action on a state performs a supersymmetry transformation. Another set of rules in the form of commutation/anti-commutation relations is needed in order to have a complete picture of the theory. This is the supersymmetric algebra. Of course, supersymmetry is not yet observed. Nevertheless, it's a great example of highlighting the tools that go beyond the standard Lagrangian (generators, supersymmetric algebra, etc.). The _Standard Model_ of particle physics, one of the most successful models/theories/frameworks the physics community has built works in a similar fashion (and gives actual results that can be observed in an accelerator).

The ultimate goal of a theory like that is to produce results that can be tested against experiments. Using the above (and spending an enormous amount of time calculating) we can produce expressions that correspond to real-life results in the form of _scattering amplitudes_. These mathematical expressions are written in terms of quantities that can be measured in an experimental setting. To derive such expressions, we make use of the Feynman diagrams and rules, a scheme that translates the huge mathematical expressions derived from Lagrangian formalism into simple diagrams. Each part of such diagram corresponds to a mathematical expression which is used, along with the rest of the diagram, to build the amplitude. Depending on the theory (Lagrangian) the rules that map the diagram to the expressions are modified accordingly.

# My thesis
My thesis is focused on the [5-dimensional spinor-helicity formalism][5dspinorhelicity]. The spinor-helicity formalism is a very compact way of expressing states of particles in quantum field theory. This comes in handy whenever the on-shell amplitudes are complicated (they usually are). Apparently, we can do some modifications to our momenta that would allow us to build up even more complicated amplitudes from simpler ones. For now, we are exploring these shifts and how they can work in the 5-D setting. Using that result, we can then implement this technique to construct more complicated amplitudes.


[functional]: https://en.wikipedia.org/wiki/Functional_(mathematics)
[pola]: https://en.wikipedia.org/wiki/Stationary-action_principle
[qft]: https://en.wikipedia.org/wiki/Quantum_field_theory
[qed]: https://en.wikipedia.org/wiki/Quantum_electrodynamics
[qcd]: https://en.wikipedia.org/wiki/Quantum_chromodynamics
[string_theory]: https://en.wikipedia.org/wiki/String_theory
[qc]: https://en.wikipedia.org/wiki/Quantum_computing
[5dspinorhelicity]: https://arxiv.org/abs/2202.08257
[sym]: https://en.wikipedia.org/wiki/N_%3D_4_supersymmetric_Yang%E2%80%93Mills_theory
