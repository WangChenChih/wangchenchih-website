---
title: 'Multipartite Entanglement'
date: 2026-06-15
permalink: /posts/2026/06/multipartite-entanglement/
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
\newcommand{\braket}[1]{\langle #1 \rangle}
$$
In this notes, I would like to review materials on multipartite entanglement, including different types of theoretical definition of entanglement measure and their relation with the experimental observables.

## Separability

A state $\varrho$ is called ***separable*** if there exists a bipartition of the Hilbert space $$\mathcal{H} = \mathcal{H}_A\otimes\mathcal{H}_{\overline{A}}$$ such that

$$
\varrho^{\mrm{sep}}_{A\vert\overline{A}} = \sum_{n} p_n \rho^{(A)}_n
\otimes \rho^{(\overline{A})}_n
$$

where each component $$\rho^{(A/\overline{A})}_n$$ is a density matrix acting on the subspace $$\mathcal{H}_A$$ and $$\mathcal{H}_{\overline{A}}$$. Weights $$p_n$$ are convex, satisfying $$0\leq p_n\leq 1\forall n$$ and $$\sum_{n}p_n = 1$$. In other words, $$\lrg{p_n}$$ is a *probability distribution*. A state that is separable with respect to a bipartition $$A\vert\overline{A}$$ is denoted by $$\varrho^{\mrm{sep}}_{A\vert\overline{A}}$$. Such a state is often referred to as a *classically correlated* state. 

The fact that two physical observables supported on $$A$$ and $$\overline{A}$$, respectively, are *classically correlated* if the state is separable with respect to $$A\vert\overline{A}$$ can be understood from computing their correlation function. Suppose that the density matrix takes the form used for defining separability, then the correlation of two operators $$\mathcal{O}_A$$ and $$\mathcal{O}_{\overline{A}}$$ is 

$$
\braket{\mathcal{O}_A\mathcal{O}_{\overline{A}}} = \sum_{n} p_n \Tr_{A}\lr{\rho^{(A)}_n\mathcal{O}_A} \Tr_{\overline{A}}\lr{\rho^{(\overline{A})}_n\mathcal{O}_{\overline{A}}} = \sum_{n} p_n \braket{\mathcal{O}_A}_n \braket{\mathcal{O}_{\overline{A}}}_n.
$$

This result implies that the observables can be measured locally in two spatially separated regions, respectively. After that, the correlation can be computed using classical probability theory with the given probability distribution $$\lrg{p_n}$$, rendering the result no different from a classical theory with hidden variables.

## Biseparability

A state $$\varrho$$ is called \textbf{\textit{biseparable}} if it can be expressed as a mixture of separable states defined by previously

$$
\varrho = \sum_{A \subset \Lambda}p_{A} \varrho^{\mrm{sep}}_{A\vert\overline{A}}
$$

where $$\lrg{p_A}$$ is a probability distribution.