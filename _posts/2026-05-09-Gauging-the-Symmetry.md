---
title: 'Gauging the Symmetry'
date: 2026-05-09
permalink: /posts/2026/05/gauging/
tags:
  - physics
---

Symmetry is one of the most important concepts in physics.One motivation for *gauging* symmetry is to see whether two seemingly different models share common physical features. For example, the 2D transverse field Ising model exhibits topological order, which is the same as the toric code model, in some specific limits. 

Another motivation is to manifest the *emergent symmetry* if the original symmetry is broken slightly. For example, the toric code model is still in the topologically ordered phase even when an external field is added. 

This note basically follows the three remarkable lectures given by Xie Chen

* [ICTP Condensed Matter and Statistical Physics Topological lattice models from gauging I](https://www.youtube.com/watch?v=Bn8vA5-o5Mg)
* [ICTP Condensed Matter and Statistical Physics Topological lattice models from gauging II](https://www.youtube.com/watch?v=PhuydbwXTNU)
* [ICTP Condensed Matter and Statistical Physics Topological lattice models from gauging III](https://www.youtube.com/watch?v=gdvaQ-iFDVE)

# Transverse Field Ising Model: Gauging the $\mathbb{Z}_2$ Symmetry

The model Hamiltonian is

$$
H_{\mathrm{Ising}} = -J\sum_{\braket{ij}}Z_iZ_j - h\sum_{i}X_i
$$

The Hamiltonian has a global $\mathbb{Z}_2$ symmetry 

$$
U_{X} = \prod_{i}X_i 
$$

After knowing the global symmetry of the system, we now turn to the gauge symmetry. Gauge symmetry is a concept that contrasts with global symmetry. We usually refer to gauge symmetry as the *local* version of the original global symmetry. Therefore, gauging a symmetry is modifying the model Hamiltonian so that we can find a local operator that does similar work to the original symmetry. At the end of the discussion, we will find that the local version of the symmetry is exactly the **Gauss law** of the gauge theory.

Look at the original Hamiltonian $H_{\mathrm{Ising}}$, we find that there is no local unitary symmetry operator. Any local operator either flips the sign of the first term or the second term. However, the situation will be different if we add redundant degrees of freedom to the system and insert these objects into the Hamiltonian. The spirit is similar to the $U(1)$ gauge theory in QED, where we insert the gauge field in between the electron fields to promote the original derivative to a covariant derivative. In that way, the Lagrangian can possess a *local* $U(1)$ symmetry. Inspired by QED, if we refer to each local $Z_i$ as a matter field, then we can insert a *gauge field* in between a pair of adjacent matter fields,

$$
H_g = -J\sum_{\braket{ij}}Z_i \tau^Z_{\braket{ij}} Z_j - h\sum_{i}X_i - K\sum_{p}B_p
$$

where

$$
B_p = \prod_{\braket{ij}\in p}\tau^Z_{\braket{ij}}
$$

The gauge flux term $B_p$ is the lowest-order local symmetry-preserving term that lifts the degeneracy of eigenstates in the Hilbert space enlarged by redundant gauge degrees of freedom at edges of the lattice. The gauge flux term is the dynamics of the gauge field, analogous to the term $F^{\mu\nu}F_{\mu\nu}$ in QED. 

With the gauge field, the local symmetry operator in the gauge theory can be defined as $A_iX_i$

$$
[H_g,A_iX_i] = 0
$$

where $A_i$ is the divergence of the electric field in the gauge theory, composed of $\tau^X$ operators around the site $i$.

$$
A_i \equiv \prod_{j\in \mathcal{N}(i)}\tau^X_{\braket{ij}}
$$

$\tau^X$ is the Pauli operator that anti-commutes with the gauge field $\tau^Z$. In other words, $\tau^X$ is the generator of flipping the $\mathbb{Z}_2$ gauge field, analogous to the electric field in the quantized $U(1)$ gauge theory, in which we have the canonical quantization condition for the electric field and the gauge field $[E_{ij},A_{i'j'}]=i\delta_{ii'}\delta_{jj'}$. The matter field $Z$ and $X$ also have a QED analogy. In a conventional quantum field theory, the matter field can be separated into the amplitude part $\hat{\rho}$ and the phase part $\hat{\theta}$ satisfying the canonical quantization relation, $[\hat{\rho}_i, \hat{\theta}_j] = i\delta_{ij}$, implied by the relation $[\hat{\psi}_i,\hat{\psi}^\dagger_j\hat{\psi}_j] = \delta_{ij}\hat{\psi}_j$, where $\hat{\psi}^\dagger_j\hat{\psi}_j$ corresponds to the amplitude part, and  $\hat{\psi}$ corresponds to the phase part. Similar to the way $\tau^Z$ and $\tau^X$ are related to the gauge field, we can relate $Z$ with the phase part $\psi$ and $X$ with the amplitude part $\hat{\psi}^\dagger\hat{\psi}$. With these correspondences, the $J$ term in $H_g$ becomes analogous to the covariant derivative

$$
Z_i\tau^Z_{\braket{ij}} Z_j \to \hat{\psi}_i^\dagger e^{iA_{ij}}\hat{\psi}_j \to \bar\psi (\partial + iA)\psi
$$

The transverse field term becomes analogous to the mass term, or the chemical potential term in condensed matter physics

$$
\mu X_i \to \mu e^{-i\pi\rho} \to m\psi^\dagger\psi
$$

The gauge flux term becomes analogous to the magnetic flux

$$
\prod_{\braket{ij}\in p}\tau^Z_{\braket{ij}} \to e^{i\oint A} \to e^{i(\partial_\mu A_\nu - \partial_\nu A_\mu)} \to F^{\mu\nu}F_{\mu\nu}
$$

On the other hand, the local symmetry operator becomes analogous to 

$$
A_iX_i \to \left(\prod_{j\in\mathcal{N}(i)}e^{i\pi E_{ij}}\right)e^{-i \pi\rho} \to e^{i\pi (\mathbf{\nabla}\cdot E - \rho)}
$$

The exponent $(\mathbf{\nabla}\cdot E -\rho)$ in the above analogy implies that the physical meaning of a gauge symmetry is the **Gauss law** of the gauge theory. This is the reason why we refer to the Gauss law as the *generator of the gauge transformation*.

The Gauss law of the gauge theory is the constraint for the local symmetry

$$
A_iX_i = 1
$$

The reason why we add this constraint is that *the gauge symmetry is not a real symmetry of the system*. Recall that the *real* system is the original Ising model described by the Hamiltonian $H_{\mathrm{Ising}}$ and its eigenstates, which has a global $\mathbb{Z}_2$ symmetry. However, in order

## $h\to 0$ Limit

$$
H_g = -J\sum_{\braket{ij}}Z_i\tau^Z_{\braket{ij}}Z_j - K\sum_p B_p 
$$

## $J\to 0$ Limit

$$
H_g = -h\sum_iX_i - K\sum_p B_p 
$$

The ground state is a state with $X_i=1\;\forall i$ since the two terms in the above Hamiltonian are from different sectors, and can be minimized simultaneously without competition. With this ground state property, the Gauss law constraint becomes

$$
A_vX_v=1 \to A_v=1
$$

And we can energetically implement this Gauss law by adding a term to the Hamiltonian that enforces the ground state to obey the Gauss law.

$$
H_g \to -K\sum_p B_p - K'\sum_v A_v
$$

Where the transverse field term has been neglected because we have employed the ground state condition. 

After the series of transformations, the Hamiltonian ends up with an equivalent theory completely defined in the gauge sector, and the equivalent theory is the toric code model. 

# Toric Code Model and Emergent Symmetry

https://iopscience.iop.org/article/10.1088/0034-4885/80/1/016502/meta

A pure toric code model reads

$$
H_{\mathrm{toric}} = -K\sum_p B_p - K'\sum_v A_v
$$

where $B_p\equiv\prod_{e\in p}Z_e$ and $A_v\equiv \prod_{e\in v}X_e$ are now physical objects. The model has inherited local symmetry generated by $A_v$ defined on the vertices of the lattice.

Consider a generalized model that includes external fields

$$
H = H_{\mathrm{toric}} - h_Z\sum_e Z_e - h_X\sum_e X_e
$$

The external fields break the exact local symmetry generated by $A_v$. 

# Half Gauging