---
title: 'Raman Scattering in Strongly Correlated Magnets'
date: 2025-11-19
permalink: /posts/2025/11/raman-scattering/
tags:
  - physics
---
$$
\newcommand{\ket}[1]{\left| #1 \right\rangle}
\newcommand{\bra}[1]{\left\langle #1 \right|}
$$
Raman scattering has become a powerful experimental tool to detect novel phases of matter, especially because its energy scale is near that of creating elementary excitations in condensed matter physics. For quantum spin liquids, a common mechanism of the interaction between the matter and the detection EM wave is the Loudon-Fleury mechanism, in which photons perturb the Mott insulator and produce a vertex with a weight in a form similar to that of the spin model in the corresponding low-energy effective theory. In this note, I try to organize important references on Raman scattering and its applications in strongly correlated magnets.

# Basic Raman

The scattering intensity is given by

$$
I(\omega) = \int\mathrm{d}te^{i\omega t}\langle R(t)R(0)\rangle
$$

Note that the operator $R$ depends on the polarizations of the internal and scattered light. Which can be rewritten into another form using the spectral representation

$$
\langle R(t)R(0)\rangle = \bra{0}R(t)R(0)\ket{0} = \sum_{n}e^{i(E_0-E_n)t}\langle 0|R|n\rangle\langle n|R|0\rangle
$$

Based on this, the intensity $I(\omega)$ in the spectral representation reads

$$
I(\omega) = 2\pi\sum_{n}|\langle 0|R|n\rangle|^2\delta(E_n-E_0-\omega)
$$

which is nothing but the Fermi golden rule.

If the temperature is finite, then the ensemble average reads

$$
\begin{align*}\langle R(t)R(0)\rangle &= \frac{1}{\mathcal{Z}}\mathrm{Tr}\left[e^{-\beta H}R(t)R(0)\right] \\ &=\frac{1}{\mathcal{Z}}\sum_{mn}e^{-\beta E_m}e^{i(E_m-E_n)t}\bra{m}R\ket{n}\bra{n}R\ket{m}\end{align*}
$$

So, the Raman intensity $I(\omega)$ becomes

$$
I(\omega) = \frac{2\pi}{\mathcal{Z}}\sum_{mn}e^{-\beta E_m}|\langle m|R|n\rangle|^2\delta(E_n-E_m-\omega)
$$

# Fermi Liquids

# Superconductors

# Strongly-Correlated Superconductors

Here, we review how to derive the [Loudon-Fleury vertex](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/PhysRev.166.514.pdf). The derivation basically follows the [Shastry-Shraiman paper](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/PhysRevLett.65.1068.pdf).

First of all, consider a Hubbard model

$$
H = -t\sum_{\langle i,j\rangle}(c^\dagger_{i,\sigma}c_{j,\sigma}+\mathrm{H.c.}) + U\sum_{i}n_{i\uparrow}n_{i\downarrow}\equiv H_t + H_U
$$

To include the interaction between the external EM field and the electrons, we can apply a Peierls substitution

$$
H_t\to -t\sum_{\langle i,j\rangle}\left(e^{i\frac{e}{c}\int_{i}^{j}\mathbf{A}\cdot d\mathbf{r}} c^\dagger_{i,\sigma}c_{j,\sigma}+\mathrm{H.c.}\right)
$$

Notice that the [Peierls substitution is valid only if the basis states of the lattice Hamiltonian are well localized](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/ncomms9944.pdf) (see also review articles: [Wannier](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/RevModPhys.34.645.pdf) and [Nenciu](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/RevModPhys.63.91.pdf)), so we need to be careful. Fortunately, the electrons are highly localized in our consideration here. 

Suppose the wavelength of the incident EM wave is way larger than the lattice constant, then the phase becomes

$$
\int_{i}^{j}\mathbf{A}\cdot d\mathbf{r}\approx \mathbf{A}\left(\frac{i+j}{2}\right)\cdot\mathbf{d}_{ij}
$$

After this approximation, the Hamiltonian can be expanded in the powers of $eA/c$, and one gets

$$
H_t = H_t^{\mathbf{A}=0} - \frac{e}{\hbar c} \sum_{q}\mathbf{j}_q\cdot\mathbf{A}_{-q} + \frac{1}{2}\left(\frac{e}{\hbar c}\right)^2\sum_{q_1q_2}A_{-q_1}^\alpha\tau_{q_1+q_2}^{\alpha\beta}A^\beta_{-q_2}
$$

where

$$
\begin{align*}
j^\alpha_q &= \sum_{k,\sigma} \frac{\partial \epsilon_k}{\partial k_\alpha}c^\dagger_{k+q/2,\sigma}c_{k-q/2,\sigma} \\
\tau^{\alpha\beta}_{q} &= \sum_{k,\sigma}\frac{\partial^2 \epsilon_k}{\partial k_\alpha\partial k_\beta}c^\dagger_{k+q/2,\sigma}c_{k-q/2,\sigma}
\end{align*}
$$

and \\(\epsilon_k\\) is the electron dispersion. 

[to be continue](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/PhysRevB.52.9760.pdf)

# Strongly-Correlated Magnets

- [Theory of Raman response in three-dimensional Kitaev spin liquids](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/PhysRevB.92.094439.pdf)
- [Raman signature of the $U(1)$ Dirac spin-liquid state](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/PhysRevB.81.024414.pdf)
    
This paper also revisits a claim made in the [Shastry-Shraiman paper](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/PhysRevLett.65.1068.pdf) (see also their [review article](https://www.worldscientific.com/doi/abs/10.1142/S0217979291000237)) that a chiral term $\mathbf{S}_i\cdot({\mathbf{S}_j\times\mathbf{S}_k})$ appears in the fourth-order perturbation of the Raman vertex, and it turns out that such a term didn’t actually appear. (see Appendix A of this paper)
    
- [Raman Scattering Signatures of Kitaev Spin Liquids](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/PhysRevLett.113.187201.pdf)
- [Resonant Raman scattering theory for Kitaev models and their Majorana fermion boundary modes](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/PhysRevB.94.104427.pdf)

The backbone of the theory is the [Loudon-Fleury vertex](https://wangchenchih.github.io/wangchenchih-website/_posts/2025-11-19-Raman-Scattering/PhysRev.166.514.pdf) (Shastry and Shraiman also wrote a [review article](https://www.worldscientific.com/doi/abs/10.1142/S0217979291000237))

$$
\begin{equation}R=\sum_{i,j;\alpha,\beta}(\boldsymbol{\epsilon}_{in}\cdot\mathbf{d}_{ij})(\boldsymbol{\epsilon}_{out}\cdot\mathbf{d}_{ij})\Gamma_{ij}^{\alpha\beta}\sigma_i^\alpha\sigma_j^\beta\end{equation}
$$

if the Hamiltonian is of the form

$$
H = \sum_{i,j;\alpha,\beta}\Gamma_{ij}^{\alpha\beta}\sigma_i^\alpha\sigma_j^\beta
$$

From the Loudon-Fleury vertex, we can define the polarization-dependent vertex as

$$
R_{\mu\nu}=\sum_{i,j;\alpha,\beta}d^\mu_{ij}d^\nu_{ij}\Gamma_{ij}^{\alpha\beta}\sigma_i^\alpha\sigma_j^\beta
$$

such that the total vertex can be written in a tensor contraction form

$$
R=\sum_{\mu,\nu}\epsilon_{in}^\mu R_{\mu\nu}\epsilon_{out}^{\nu}
$$

## Kitaev Model