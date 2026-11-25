---
title: 'Higher-Spin Density Matrix'
date: 2026-11-25
permalink: /posts/2026/11/higher-spin-DM/
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
In this note, I’m trying to investigate what a density matrix of a higher-spin system looks like. Can it be represented in terms of merely spin operators? Or does it need other $SU(N)$ generators such as Gell-Mann matrices for $SU(3)$?

# Spin-1

The first example is a spin-1 system consisting of two spins. Let us consider a pure state 

$$
\ket{\psi} = \ket{+}\ket{-} + \ket{-}\ket{+}
$$

First, let’s see if the pure state density matrix can be expressed using the spin-1 operators. The matrix representation of the spin operators in the basis $\{\ket{+},\ket{0},\ket{-}\}$ is as follows

$$
\begin{align*}
& S^x = \frac{1}{\sqrt{2}}
	\begin{pmatrix}
		0 & 1 & 0 \\
		1 & 0 & 1 \\
		0 & 1 & 0
	\end{pmatrix}	\\
& S^y = \frac{1}{\sqrt{2}}
	\begin{pmatrix}
		0 & -i & 0 \\
		i & 0 & -i \\
		0 & i & 0
	\end{pmatrix}	\\
& S^z = \begin{pmatrix}
		1 & 0 & 0 \\
		0 & 0 & 0 \\
		0 & 0 & -1
	\end{pmatrix}	\\
\end{align*}
$$

On the other hand, the density matrix $\rho = \ket{\psi}\bra{\psi}$ in the matrix representation is 

$$
\rho 
\propto 
S_1^z(S_1^z + 1) \otimes S_2^z(S_2^z - 1)
+ 
\left.S^+_1\right.^2 \otimes \left.S^-_2\right.^2
+
\left.S^-_1\right.^2 \otimes \left.S^+_2\right.^2
+
S_1^z(S_1^z - 1) \otimes S_2^z(S_2^z + 1)
$$

In the above equation, we have used the following relations about how to construct single diagonal entries using spin operators.

$$
\left\{
\begin{align*}
& \ket{+}\bra{+} = \frac{S^z(S^z + 1)}{2} \\
& \ket{0}\bra{0} = 1 - \left.S^z\right.^2 \\
& \ket{-}\bra{-} = \frac{S^z(S^z - 1)}{2}
\end{align*}
\right.
$$

The reduced density matrix of the first spin is

$$
\rho_1 = \mathrm{Tr}_2\rho 
\propto 
S_1^z(S_1^z + 1) + S_1^z(S_1^z - 1)
=
\frac{1}{2}\left.S_1^z\right.^2
$$

This makes sense because the two-spin state is symmetric and the local spin is effectively zero. In this case, both the entire pure state and the reduced density matrix of a single spin can be represented using spin operators, including their products and the identity operator.

Let’s see another case. Suppose now the pure state is 

$$
\ket{\psi} = \ket{+}\ket{0} + \ket{0}\ket{+}
$$

The corresponding pure-state density matrix reads

$$
\rho 
\propto 
S_1^z(S_1^z + 1) \otimes (1 - \left.S^z_2\right.^2) 
+ 
S^+_1 \otimes S^-_2
+
S^-_1 \otimes S^+_2
+
(1 - \left.S^z_1\right.^2)  \otimes S_2^z(S_2^z + 1)
$$

The reduced density matrix of the first spin is

$$
\rho_1 
\propto 
S_1^z(S_1^z + 1) + 2(1 - \left.S^z_1\right.^2)
=
\frac{1}{2} - \frac{1}{4}S^z_1(S_1^z-1)
$$

Although we have shown that the density matrices can be expressed in terms of spin operators in the above two simple examples, the disadvantage of this kind of expression is that we cannot keep track of the trace of operators. For spin-1 operators, we have the following pattern

$$
\left\{
\begin{align*}
& \mathrm{Tr}S^\mu = 0 \\
& \mathrm{Tr} \left.S^\mu\right.^2 = 2 \\
& \mathrm{Tr} S^\mu S^\nu = 0 \\
& \mathrm{Tr} S^xS^yS^z = i
\end{align*}
\right.
$$

Unlike spin-1/2 operators, the trace rule for spin-1 operators is more complicated, and the product $S^\mu S^\nu$ cannot simply be represented in terms of spin operators. Another major obstacle is that the reduced density matrix cannot be uniquely determined by the spin-correlation functions.

Take only one spin as an example. Suppose we know both the magnetic dipole, the quadrupole, and the octupole 

$$
\braket{S^\mu} = \mathrm{Tr}(\rho S^\mu) =: p^\mu, 
\quad 
\braket{S^\mu S^\nu} = \mathrm{Tr}(\rho S^\mu S^\nu) =: q^{\mu\nu},
\quad
\braket{S^\mu S^\nu S^\lambda} =: t^{\mu\nu\lambda}
$$

then these quantities together with the fundamental property of density matrices  

$$
\rho^\dagger = \rho, \quad \mathrm{Tr}\rho = 1
$$

provide $3 + 3^2 + 3^3 + 2$ conditions for us to determine the density matrix $\rho$. However, these conditions are not all independent. For example, the permutation of the quadrupole tensor $q^{\mu\nu}$ can be realized by adding dipole components

$$
q^{yx} = \braket{S^y S^x} = \braket{S^x S^y} - i\braket{S^z} = q^{yx} - ip^z
$$

Similarly, the permutation of the octupole tensor $t^{\mu\nu\lambda}$ can be realized by adding quadrupole tensors $q^{\mu\nu}$ due to the angular momentum algebra.

$$
t^{xzy} = \braket{S^x S^z S^y} = \braket{S^x S^y S^z} - i\braket{S^x S^x} = t^{xyz} - iq^{xx}
$$

and don’t forget the cyclic property of the spin-1 operators $\left. S^\mu \right.^3 = S^\mu$. 

Ultimately, there are only $6$ non-trivial independent quadrupole components

$$
q^{xx}, q^{yy}, q^{zz}, q^{xy}, q^{yz}, q^{zx}
$$

and there are only $7$ non-trivial independent octupole components

$$
t^{xxy}, t^{xxz}, t^{yyx}, t^{yyz}, t^{zzx}, t^{zzy}, t^{xyz}
$$

Altogether, we have $3 + 6 + 7 + 2 = 18$ independent, non-trivial conditions for determining the density matrix, which equals the number of degrees of freedom of the spin-1 density matrix $(3\times 3) \times 2 = 18$.

$$
Q^{\mu\nu} = 3\braket{S^\mu S^\nu} -  S(S+1)\delta^{\mu\nu}
$$

# Higher-Spin Kitaev Model

- https://journals.aps.org/prb/abstract/10.1103/PhysRevB.78.115116
- https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.130.156701

In the Kitaev model, the elementary string operator whose endpoints act like particles (bosons or fermions depending on the spin representation, which is also equivalent to the anomaly of the $\mathbb{Z}_2$ spatial string representation) reads $d_{ij} \equiv e^{i\pi S^{\alpha_{ij}}_i}e^{i\pi S^{\alpha_{ij}}_j}$. 

For the spin-1 representation, the local operator can be expanded as follows

$$
e^{i\pi S^\mu} = 1 + i\pi S^\mu - \frac{1}{2!}\pi^2 \left. S^\mu\right.^2 - \frac{1}{3!} \pi^3 S^\mu + \cdots = 1 - 2 \left. S^\mu \right.^2 
$$

## 1D Model

Let’s first investigate the ground state of the spin-1 Kitaev model

$$
H = 
- J_x \sum_{i\in \text{odd}} S^x_{i}S^x_{i+1} 
- J_y \sum_{i\in \text{even}} S^y_{i}S^y_{i+1} 
$$

# Yao-Lee Model

- https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.107.087205
- 

![decohoney-eps-converted-to_page-0001.jpg](decohoney-eps-converted-to_page-0001.jpg)

$$
H = J\sum_{i} \bold{S}_i^2 + \sum_{\braket{ij}} J_{\alpha_{ij}} \tau_i^{\alpha_{ij}} \tau_j^{\alpha_{ij}} 
\bold{S}_i \cdot \bold{S}_j
$$

where $\bold{S}_i = \bold{S}_{i,1} + \bold{S}_{i,2} + \bold{S}_{i,3}$ (therefore, the description is effectively a spin-3/2 system), and the $\tau$ operators are defined as

$$
\begin{align*}
& \tau^x_i = \frac{1}{2} + 2 \bold{S}_{i,1} \cdot \bold{S}_{i,2} \\
& \tau^y_i = \frac{2}{\sqrt{3}} (\bold{S}_{i,1}\cdot\bold{S}_{i,2} - \bold{S}_{i,2}\cdot\bold{S}_{i,3}) \\
& \tau^z_i = \frac{4}{\sqrt{3}} \bold{S}_{i,1}\cdot(\bold{S}_{i,2}\times \bold{S}_{i,3})
\end{align*}
$$