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

where $$\lrg{p_A}$$ is a probability distribution. A state is ***genuinely multipartite entangled*** if it is **not biseparable**. 

## A simple example of inseparable states
$$
\varrho = \frac{1}{4}\lr{\mathds{1} + \bog{\sigma}_1\cdot \bog{\sigma}_2}
$$

If this two-spin system is separable, then there exists a probability distribution $\lrg{p_k}$ and two sets of vectors $$\lrg{\bo{v}_k}$$ and $$\lrg{\bo{u}_k}$$ whose norms are less than unity such that

$$
\varrho
=
\frac{1}{4}\lr{\mathds{1} + \bog{\sigma}_1\cdot \bog{\sigma}_2}
=
\sum_{k}
p_k
\lr{
\frac{\mathds{1} + \bo{v}_k\cdot \bog{\sigma}_1}{2}
}
\lr{
\frac{\mathds{1} + \bo{u}_k\cdot \bog{\sigma}_2}{2}
}
$$

$$
\sum_{k} p_k v^\mu_k = 0 
,\qquad 
\sum_{k} p_k u^\nu_k = 0 
,\qquad 
\sum_{k} p_k u^\mu_k v^\nu_k = \delta^{\mu\nu}
$$



```markdown
For any matrix $$M$$, its *nuclear norm*, defined as the sum of singular values of $M$, satisfies 

$$
\norm{M}_* = \sup_{\norm{A}\leq 1} \Tr\lr{A^\dagger M},
$$

where $$\norm{A}$$ represents the operator norm of $$A$$.
```

```markdown
*Proof:*
First, we prove that there exists an operator $A = UV^\dagger$ that satisfies the above equation, where $U$ and $V$ are the SVD matrices of $M$. The proof is straightforward
\[
\Tr\lr{
A^\dagger M
}
=
\Tr\lr{
VU^\dagger U\Sigma V^\dagger
}
=
\Tr\lr{\Sigma} = \norm{M}_*.
\]
Next, we need to prove that $\norm{M}_*$  indeed provides an upper bound for $\Tr\lr{A^\dagger M}$. A direct calculation shows that
\[
\Tr\lr{
A^\dagger M
}
=
\sum_{i} \Sigma_{ii} \lrm{U^\dagger A V}_{ii}
\leq
\sum_{i} \Sigma_{ii} \norm{U^\dagger A V}
=
\norm{M}_*
\norm{U^\dagger A V}
\]
Since both $U$ and $V$ are unitary, the operator norm in the last term reduces to the operator norm of $A$ itself.
\[
\norm{U^\dagger A V}
=
\sup_{\psi\neq 0} \frac{\abs{U^\dagger A V \ket{\psi}}}{\abs{\psi}}
=
\sup_{\psi\neq 0}
\sqrt{
\anglelr{
V^\dagger A^\dagger A V
}_\psi
}
=
\sup_{\phi\neq 0}
\sqrt{
\anglelr{
A^\dagger A 
}_\phi
}
=
\norm{ A}
\]
Together, we obtain the inequality
\[
\Tr\lr{A^\dagger M} = \norm{M}_* \norm{A} \leq \norm{M}_*.
\]
```

\begin{theorem}
    Let $\bo{u}^\mu_k$ and $\bo{v}^\nu_k$ are real vectors (indices are $\mu$ and $\nu$, respectively) bounded below by $R_1$ and $R_2$, respectively, for all $k$. The upper bound for the nuclear norm of the matrix
    \[
    C^{\mu\nu}\equiv \sum_{k} p_k u^\mu_k  v^\nu_k
    \]
    is determined by $R_1$ and $R_2$
    \[
    \sup_{\lrg{p_k}, \lrg{\bo{u}_k}, \lrg{\bo{v}_k}} \norm{C}_* = R_1R_2
    \]
\end{theorem}
\begin{proof}
Let $A$ be a bounded operator $\norm{A} \leq 1$,
    \[
    \Tr\lr{A^\dagger C} = 
    \sum_{k} p_k \bo{u}_k^T A \bo{c}_k
    \leq
    \sum_{k} p_k \abs{\bo{u}_k} \abs{A \bo{v}_k}
    \leq
    \sum_{k} p_k \abs{\bo{u}_k} \norm{A} \abs{\bo{v}_k}
    \leq
    \sum_{k} p_k R_1 R_2 = R_1 R_2
    \]
    According to the Lemma~\ref{lemma:nuclear-norm-lemma}, we have
    \[
    \norm{C}_* = \sup_{\norm{A}\leq 1}\Tr\lr{A^\dagger C} \leq R_1R_2.
    \]
    This completes the proof.
\end{proof}

\[
\norm{\sum_{k} p_k u^\mu_k v^\nu_k}_* = \norm{\delta^{\mu\nu}}_* = 3
\]
\[
\norm{\sum_{k} p_k u^\mu_k v^\nu_k}_* \leq 1
\]
Contradiction