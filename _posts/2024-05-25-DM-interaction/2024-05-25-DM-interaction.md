---
title: 'Dzyaloshinskii-Moriya Interaction'
date: 2024-05-25
permalink: /posts/2024/05/DM-interaction/
tags:
  - physics
---
$$
\newcommand{\ket}[1]{\left| #1 \right\rangle}
\newcommand{\bra}[1]{\left\langle #1 \right|}
\newcommand{\lr}[1]{\left(  #1  \right)}
\newcommand{\lrm}[1]{\left[  #1  \right]}
\newcommand{\lrg}[1]{\left\{  #1  \right\}}
\newcommand{\abs}[1]{\left|  #1  \right|}
\newcommand{\de}{\partial}
\newcommand{\pdif}[1]{\frac{\partial}{\partial#1}}
\newcommand{\pdiff}[2]{\frac{\partial#1}{\partial#2}}
\newcommand{\mrm}[1]{\mathrm{#1}}
\newcommand{\bo}[1]{\mathbf{#1}}
\newcommand{\Tr}{\mathrm{Tr}}
\newcommand{\norm}[1]{\left\lVert#1\right\rVert}
$$
The Dzyaloshinskii-Moriya interaction, also known as the antisymmetric interaction, 

Here lists several review articles
- [Theory of Monoaxial Chiral Helimagnet](https://www.sciencedirect.com/science/chapter/bookseries/abs/pii/S0081194715000041)

# Microscopic Origin: a Simple Interpretation
- [T. Moriya, Anisotropic Superexchange Interaction and Weak Ferromagnetism](https://wangchenchih.github.io/wangchenchih-website/_posts/2024-05-25-DM-interaction/references/PhysRev.120.91.pdf)
- [N. E. Bonesteel, Theory of anisotropic superexchange in insulating cuprates](https://wangchenchih.github.io/wangchenchih-website/_posts/2024-05-25-DM-interaction/references/PhysRevB.47.11302.pdf) (Specifically, see Eq. (3.10))

Consider an insulator, where each localized electron $i$ contributes to the local magnetic moment by its spin \(\bo{S}_i\) and angular momentum \(\bo{L}_i\), then the interaction Hamiltonian of a subsystem consisting of only two electrons can be written as

$$
H' = - J \mathbf{S}_1\cdot\mathbf{S}_2 + \lambda \mathbf{S}_1\cdot\mathbf{L}_1 + \lambda \mathbf{S}_2\cdot\mathbf{L}_2
$$

where the last two terms describe the spin-orbit copling, while the first term represents the spin exchange interaction between two electrons. Treating the above Hamiltonian as an interaction (the main Hamiltonian is unknown in this context, but we assume its eigenstates are known and the orbit and spin are decoupled) and perform the second order perturbation, we have

$$
\hat{H}_{\mathrm{spin}} = \sum_{n_1}\sum_{n_2}\frac{\bra{0_1,0_2} H' \ket{n_1,n_2}\bra{n_1,n_2} H' \ket{0_1,0_2}}{E_0 - E_n} 
$$

$$
\bra{n_1,n_2} H' \ket{0_1,0_2} = - J \mathbf{S}_1\cdot\mathbf{S}_2 \delta_{n_10_1}\delta_{n_20_2} + \lambda \mathbf{S}_1\cdot\mathbf{L}_1 + \lambda \mathbf{S}_2\cdot\mathbf{L}_2
$$

$$
\mathbf{D} = -i\lambda J \left( \sum_{n_1}\frac{\bra{0_1} \mathbf{L}_1 \ket{n_1}}{E_{n_1} - E_{0_1}}  - \sum_{n_2}\frac{\bra{0_2} \mathbf{L}_2 \ket{n_2}}{E_{n_2} - E_{0_2}} \right)
$$

In conclusion, the key to the DM interaction is the *spin-orbit coupling*. 