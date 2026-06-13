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
A primary objective of this note is to figure out a potential relation among different types of scattering, such as Raman scattering and neutron scattering, by formulating the master equations using density matrices instead of state vectors used in the Lehmann representation. 

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

# Neutron Scattering (Magnetic Signal)

At $T=0$, the master equation about the cross section is

$$
\frac{\mrm{d}^2 \sigma}{\mrm{d}\Omega\mrm{d}\omega} = \lr{\frac{m}{2\pi}}^2 \frac{k'}{k}\sum_{\sigma\sigma'} p_\sigma \sum_{n} \abs{ \bra{\bo{k}',\sigma',n} \hat{U} \ket{\bo{k},\sigma,0} }^2 \delta\lr{E_n - E_0 - \omega}
$$

$$
\bra{\bo{k}',\sigma',n} \hat{U} \ket{\bo{k},\sigma,0} = 8\pi\gamma\mu_k\mu_B \bra{\sigma',n} \hat{\sigma}\cdot \hat{W}(\bo{Q}) \ket{\sigma,0}
$$

where $\bo{Q} = \bo{k} - \bo{k}'$ is the amount of momentum transferred from the neutron to the scatterer, also known as the scattering vector.

$$
\hat{W}(\bo{Q}) = \sum_{i} e^{i\bo{Q}\cdot \bo{r}_i} \frac{1}{Q^2} \lr{\bo{Q}\times \lr{\hat{\bo{s}_i}\times \bo{Q}} - i\bo{Q}\times\hat{\bo{p}}_i}
$$

For a non-polarized neutron beam, we could set $p_\uparrow = p_\downarrow = 1/2$, and so
$$
\sum_{\sigma\sigma'}p_\sigma \bra{\sigma}\sigma_\alpha\ket{\sigma'}\bra{\sigma'}\sigma_\beta\ket{\sigma} = \frac{1}{2}\mathrm{tr}(\sigma_\alpha\sigma_\beta) = \delta_{\alpha\beta}
$$

Therefore, 

$$
\frac{\mrm{d}^2 \sigma}{\mrm{d}\Omega\mrm{d}\omega} = (\gamma r_0)^2 \frac{k'}{k} F^2(\bo{Q}) e^{-2W(\bo{Q})} \sum_{\alpha\beta}\lr{\delta_{\alpha\beta} - \frac{Q_\alpha Q_\beta}{Q^2}} S^{\alpha\beta}(\bo{Q},\omega)
$$

where $S^{\alpha\beta}(\bo{Q},\omega)$ is the magnetic scattering function, which is a quantity related to spin-spin correlations and the magnetic susceptibility. At zero temperature, it reads as

$$
S^{\alpha\beta}(\bo{Q},\omega) = 
\sum_{j,j'} 
e^{i\bo{Q}\cdot\lr{\bo{R}_j - \bo{R}_{j'}}} 
\sum_{n}
\bra{0} \hat{S}^\alpha_{j'} \ket{n} 
\bra{n} \hat{S}^\beta_j \ket{0} 
\delta(E_n - E_0 - \omega)
$$

and we could also define the *real-space magnetic scattering function* as

$$
\tilde{\mathcal{S}}^{\alpha\beta}_{j,j'}(\omega) = 
\sum_{n}
\bra{0} \hat{S}^\alpha_{j'} \ket{n} 
\bra{n} \hat{S}^\beta_j \ket{0} 
\delta(E_n - E_0 - \omega)
$$

Later on, we will focus on the properties of the real-space magnetic scattering function since it is able to completely determine the scattering cross section.

## Magnetic Scattering Function

Similar to the discussion about Raman scattering, the magnetic scattering function can also be expressed in terms of density matrices

$$
\begin{align*}
\tilde{\mathcal{S}}_{jj'}^{\alpha\beta}(\omega) 
&= 
\sum_{n}
\bra{0} \hat{S}^\alpha_{j'} \ket{n} 
\bra{n} \hat{S}^\beta_j \ket{0} 
\delta(E_n - E_0 - \omega) \\
&= \sum_{n}
\Tr \lr{ 
    \hat{S}^\alpha_{j'} \rho_n \hat{S}^\beta_j \rho_0
}
\delta(E_n - E_0 - \omega)
\end{align*}
$$

A comparison between the inelastic neutron scattering and the Raman scattering technique in diagnosing of quantum spin liquids

* [Wulferding et. al., Raman spectroscopic diagnostic of quantum spin liquids](https://wangchenchih.github.io/wangchenchih-website/_posts/2026-06-12-Scattering-density-matrix-formulation/references/JPhysCondensMatter.32.043001.pdf)

* [Knolle et. al., Dynamics of a Two-Dimensional Quantum Spin Liquid: Signatures of Emergent Majorana Fermions and Fluxes](https://wangchenchih.github.io/wangchenchih-website/_posts/2026-06-12-Scattering-density-matrix-formulation/references/PhysRevLett.112.207203.pdf)
* [X.-Y. Song et. al., Low-Energy Spin Dynamics of the Honeycomb Spin Liquid Beyond the Kitaev Limit](https://wangchenchih.github.io/wangchenchih-website/_posts/2026-06-12-Scattering-density-matrix-formulation/references/PhysRevLett.117.037209.pdf)
* [Knolle et. al., Raman Scattering Signatures of Kitaev Spin Liquids in \(A_2IrO_3\) Iridates with A = Na or Li](https://wangchenchih.github.io/wangchenchih-website/_posts/2026-06-12-Scattering-density-matrix-formulation/references/PhysRevLett.113.187201.pdf)