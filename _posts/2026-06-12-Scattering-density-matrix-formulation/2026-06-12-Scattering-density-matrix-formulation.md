---
title: 'Scattering Theory -- Density Matrix Formulation'
date: 2026-06-12
permalink: /posts/2026/06/density-matrix-scattering/
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

A primary objective of this note is to figure out a potential relation among different types of scattering, such as Raman scattering and neutron scattering, via formulate the master equations using density matrices instead of state vectors used in Lehmann representation. 

# Raman Scattering
The master equation that describes the Raman scattering amplitude reads

$$
I(\omega) = 2\pi\sum_{n}|\langle 0|R|n\rangle|^2\delta(E_n-E_0-\omega)
$$

where $R$ stands for the Raman vertex. This master equation can be reformulated as follows

$$
\begin{align*}
I(\omega) &= 2\pi \sum_{n}\Tr\lr{R \ket{n}\bra{n} R \ket{0}\bra{0}} \delta{E_n - E_0 - \omega} \\
&= 2\pi \sum_{n}\Tr\lr{R \rho_n R \rho_0} \delta\lr{E_n - E_0 - \omega}
\end{align*}
$$

