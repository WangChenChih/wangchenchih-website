---
title: 'Scattering Theory -- Density Matrix Formulation'
date: 2026-06-12
permalink: /posts/2026/06/density-matrix-scattering/
tags:
  - physics
---

A primary objective of this note is to figure out a potential relation among different types of scattering, such as Raman scattering and neutron scattering, via formulate the master equations using density matrices instead of state vectors used in Lehmann representation. 

# Raman Scattering
The master equation that describes the Raman scattering amplitude reads

$$
I(\omega) = 2\pi\sum_{n}|\langle 0|R|n\rangle|^2\delta(E_n-E_0-\omega)
$$

where $R$ stands for the Raman vertex. This master equation can be reformulated as follows

$$
\begin{align}
I(\omega) &= 2\pi \sum_{n}\Tr\lr{R \ket{n}\bra{n} R \ket{0}\bra{0}} \delta{E_n - E_0 - \omega} \\
&= 2\pi \sum_{n}\Tr\lr{R \rho_n R \rho_0} \delta{E_n - E_0 - \omega}
\end{align}
$$

