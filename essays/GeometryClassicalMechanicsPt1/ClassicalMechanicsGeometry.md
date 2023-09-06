---
layout: post
title:  Geometry and Classical Mechanics Part 1
categories: classical physics, mathematics
usemathjax: true
---

# Learning Geometry with classical mechanics - Part 1

My goal is to try to discuss concepts like manifolds, bundles and other geometric concepts like symplectic geometry and their use in physics. The series will consist of small posts in an attempt to not become boring or cumbersome. Just so I am clear, this is a physicist's approach, so a trigger warning to any mathematician reading it... Knowledge of basic concepts of Analytical Mechanics is assumed.


## Introduction to analytical mechanics

In contrast to the "classical" Classical Mechanics, Analytical Mechanics aims to provide a physically and mathematically deeper and more concise framework of approaching different problems. In short, we begin with some basic principles which constitute the basis of this framework and ultimately provide a universal way to attack problems and get the desired solutions. Interestingly, by the use of smart techniques we are able to also derive popular "laws" such as the conservation of momentum.

Now, let's refresh our memory a bit. We assume a usual classical system i.e. a point-particle of mass $$m$$ and a potential $$V$$ which is a function of the spatial coordinates of the point-particle. We define a functional called *action* as the integral over time of the *Lagrangian* a function of $$x,\dot{x}$$ and $$t$$, $$\mathcal{L}(x,\dot{x},t)$$,

$$
S = \int\limits_t \mathcal{L}\, \text{d}t.
$$

The Lagrangian is usually written as the difference of the kinetic energy and the potential, $$K-V$$, $$\mathcal{L}=K-V$$. To obtain the equations of motion, we solve the Euler-Lagrange equations which we get by getting the extrema of the action.

We start with the ultimate basics: the *configuration space* and the *phase space*. **Configuration space** is the $$n$$-dimensional space where all the "spatial" coordinates live. Note that these coordinates are *generalized* and so the configuration space is not necessarily  identified as the usual 3-dimensional/physical space, as there might exist several constraints. **Phase space** is -roughly defined- the space consisting of the generalized coordinates along with their "conjugate" momenta. In general, we need a set of independent variables (let them be the $$q_n$$'s) and (or a function of) their time derivatives $$\dot{q}_n$$ to fully describe a classical system according to our current theoretical framework. We consider the $$2n$$ coordinates independent.

## Definitions

Now, let's use some geometry! We need a space where our physical system resides and the path along the space corresponds to a physical movement. This means that we need the notion of continuity and differentiability plus, we need the space to look like $$\mathbb{R}^n$$. The configuration space therefore has to behave like an n-dimensional *smooth manifold*, $$M$$.

> **Manifold**: An n-dimensional differentiable manifold $$M$$ is a *topological space*[^1] that consists of open sets $$U_i$$, $$\cup U_i = M$$. There also exist homeomorphic mappings $$\phi_i$$'s from $$U_i$$ to an open $$U_i '\in \mathbb{R}$$. For two open sets $$U_i, U_j$$ such that $$U_i \cap U_j \neq \emptyset$$, the mapping $$\psi_{ij}= \phi_i \circ\phi_j^{-1}$$ (which takes an element from $$U_j' \to U'_i$$​) is infinitely differentiable.

[^1]: Topological spaces are spaces with some extra restrictions. For now, these are not that important but I advise you check out the definitions.


<figure>
<img src="/assets/Images/GeometryAndClassicalMechPt1/manifold.svg"  width="400">
<figcaption>A schematic for the definition of manifolds.</figcaption>
</figure>

The $$\psi_{ij}$$ is the well-known map, namely the *change of coordinates* transformation. In the mathematical world it's usually called a *transition function*.

Now that we have a space for our generalized coordinates, we can proceed to the definition of the phase space. Imagine a path in the configuration space parametrized by $$t$$ and a point $$p$$ on that curve. The generalized velocities, $$\dot{q}_i$$, are geometrically the *tangent vectors* in each point $$p$$ of the curve. Intuitively this makes sense since the velocities are always tangent along the way something moves. We require the phase space to consist of all the possible velocities for the system we are describing so in general we are considering a *tangent* or a *cotangent bundle*, or, in other words, *the set of all possible tangent spaces* for the configuration space. We will see that a Lagrangian formulation induces a phase space along the *tangent bundle* while a Hamiltonian formulation, on the *cotangent*. The transition from one to another is nothing more than the Legendre transform.

Let's get to some rough definitions. For a smooth path in $$M$$, $$c(t)$$, the tangent vector at the base point $$p$$ is the (directional) derivative of $$c$$ with respect to the parameter $$t$$, $$\dot{c}(t)$$, such that $$\dot{c}(0) = p$$. For a point $$p\in M$$ the *tangent space* is the set of all tangent vectors at $$p$$, $$T_pM$$. Tangent spaces are vector spaces. The tangent space at $$p$$ is constructed by the tangent vectors of all the curves in the manifold that pass through $$p$$. Such curves belong to the same equivalence class.

> **Derivation**: A linear $$C^{\infty}$$ map $$d$$ that is also an endomorphism, is called a derivation if
> 
> $$
> d(ab)=a[d(b)] + [d(a)]b
> $$

> **Tangent spaces/Tangent vectors**:
> The set of all derivations on a point $$p\in M$$ constitute the *tangent space* $$T_p M$$, with its elements being the *tangent vectors*.

> **Tangent Bundle**:
> The set of all tangent spaces $$T_p M$$ of the manifold $$M$$ constitute the *tangent bundle* $$TM$$:
>
> $$
> TM = \bigcup\limits_{p \in M}T_pM
> $$

Using the above we are able to describe the Lagrangian formalism if we also include the Euler-Lagrange equations of motion or Hamilton's action principle. A synopsis of the above plus some extras:

* The configuration space, consisting of the spatial coordinates of the system, $$q_i$$ is a manifold $$Q$$ (changed the notation for ease).

* The phase space consisting of the local spatial coordinates ($$q_1, q_2,\dots, q_n$$) induce a tangent local coordinate system, the velocities, ($$\dot{q}_1, \dot{q}_2,\dots , \dot{q}_n$$). The two coordinate systems constitute the **velocity** phase space ($$\mathbf{q},\mathbf{\dot{q}}$$).

* The action $$S[\mathbf{q}(t)]$$ is a functional that subjects to Hamilton's principle, $$\delta S =0$$. The action is defined as usual,
  
  $$
  S[\mathbf{q}(t)] = \int_{t_1} ^{t_2}L(\mathbf{q}(t),\mathbf{\dot{q}}(t))\,\text{d}t
  $$

* Equivalently to the above, given a Lagrangian, we can produce the equations of motion 
  
  $$
  \frac{\text{d}}{\text{d}t}\left(\frac{\partial L}{\partial \mathbf{\dot{q}}} \right)= \frac{\partial L}{\partial \mathbf{q}}
  $$
  
  for each of the pairs $$q_i,\dot{q}_i$$, using the Euler-Lagrange equations. The above equivalence between Hamilton's principle of least action and the Euler-Lagrange equations is non trivial but relatively easy to prove[^2].

  [^2]: See *Geometric Mechanics and Symmetry* p.137

The Hamiltonian, requires the introduction of the *cotangent space*, the dual space of $$T_p M$$. By dual, we mean the linear space of elements that map the elements of $$T_p M$$ to $$\mathbb{R}$$. This is a space of linear functions such that $$T_p M \to \mathbb{R}$$. The cotangent space is denoted by $$T^{\ast}_p M$$ and it's a vector space. By definition, the Legendre transform will be a smooth map (and invertible),

$$
q \to q \quad \text{and} \quad \dot{q} \to p = \frac{\partial L}{\partial \dot{q}}
$$

with $$p$$ the **conjugate momenta** (to $$q$$).

In the next part we will explore the concepts further.