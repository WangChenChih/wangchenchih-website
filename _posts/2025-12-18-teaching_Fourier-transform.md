# Teaching—Fourier transform

Created: December 18, 2025 10:55 PM

# Coordinate transformation in Linear Algebra

A typical coordinate transformation is a rotation, which is described by a rotation matrix. Take dimension-2 for example, if we want to rotate a vector $\bold{v}=(v_1,v_2)$ by an angle $\theta$, then the new vector obtained after such a rotation is

 

$$
\bold{v}'=R(\theta )\bold{v}\equiv\begin{pmatrix}\cos{\theta} & \sin{\theta}\\ -\sin{\theta} & \cos{\theta}\end{pmatrix}\bold{v}
$$

where $R(\theta)$ is the rotation matrix. This can be represented in terms of its components

$$
v'_i=\sum_{j=1}^{2}[R(\theta)]_{ij}v_j
$$

In general, a coordinate transformation can be written in the following form

$$
v'_{i} = \sum_{j}M_{ij}v_j
$$

in that way, we say that the matrix $M$ transforms a coordinate where the vector $\bold{v}$ is observed, to another coordinate where the vector $\bold{v}'$ is observed.

# Inner Product

So, what exactly is the matrix $M$? The answer is given by two concepts: basis and inner product.

Suppose a vector $\bold{v}$ can be **uniquely** represented in terms of a set of basis vectors  $\{e_1,e_2,e_3,\cdots\}$ in the following way

$$
\bold{v}=\sum_{i}v_ie_i
$$

then we say the set of vectors $\{e_1,e_2,e_3,\cdots\}$ is a choice of a basis. However, there is not only one choice. Suppose there is another basis $\{e'_1,e'_2,e'_3,\cdots\}$, and the vector can be uniquely represented as

$$
\bold{v}=\sum_{i}v'_ie'_i
$$

then what are those new components $v'_i$? 

Now we introduce an assumption that $e_i\cdot e_j=\delta_{ij}$ and $e'_i\cdot e'_j=\delta_{ij}$, where $\delta_{ij}$  is the [Kronecker delta function](https://www.notion.so/Teaching-Fourier-transform-2cdb1af8720580af9722d3373c5f2d87?pvs=21). Then, we can easily get the components $v_i$ by

$$
\bold{v}\cdot e'_i = \sum_{j}v'_je'_j\cdot e'_i = \sum_{j}v'_j\delta_{ij} = v'_i
$$

Use this equation, we have

$$
v'_i = \bold{v}\cdot e'_i = \sum_{j}v_je_j\cdot e_i'
$$

Now you see that we can define the matrix $M_{ij}=e'_i\cdot e_j$ such that

$$
\begin{equation}v'_i=\sum_{j}(e'_i\cdot e_j)v_j = \sum_{j}M_{ij}v_j\end{equation}
$$

The rotation matrix is simply the inner product of the basis vectors in the two different coordinate systems. This manifestation can give you an idea that **the inner product, together with the basis, defines the coordinate transformation**.

Most importantly, from the above manifestation, we also know that any vector can be written in a standard form

$$
\begin{equation}\bold{v}=\sum_{i}e_i(e_i\cdot \bold{v})\end{equation}
$$

This is very general once the orthonormal basis is given.

# General Definition of Inner Product

In linear algebra, an inner product is generally denoted by

$$
\langle f,g \rangle
$$

The bracket has to satisfy several properties called [**inner product axioms.](https://en.wikipedia.org/wiki/Inner_product_space)** 

- $\langle f,g \rangle\in\mathbb{C}$     ($\mathbb{C}$ stands for the set of complex numbers)
- $\langle f,g \rangle = \langle g,f \rangle^*$
- $\langle af+bh,bg \rangle=a\langle f,g \rangle+b\langle h,g \rangle$, where $f,g,h$ are vectors while $a,b$ are complex numbers.
- $\langle f,f \rangle > 0$ if $f$ is not zero.

We can see the following definition

$$
\langle f,g \rangle = \int dx f^*(x)g(x)
$$

satisfies the above properties. I just want to emphasize that the inner product we learned in high school is only one special case. As long as a mapping $\langle f,g \rangle$ satisfies the above four axioms, it is a good definition of an inner product.

But you can still see that the definition $\langle f,g \rangle = \int dx f^*(x)g(x)$ is a generalization of the definition of the inner product we learned in high school via representing it using a Riemann sum.

$$
\begin{aligned}\int dx f^*(x)g(x) &\to \sum_{n}f^*(n\Delta x)g(n\Delta x)\Delta x\\ &= \sum_{n}\left(f^*(n\Delta x)\sqrt{\Delta x}\right)\left(g(n\Delta x)\sqrt{\Delta x}\right)\\ &\equiv \sum_{n}f_ng_n\end{aligned}
$$

where $f_n=\left(f^*(n\Delta x)\sqrt{\Delta x}\right)$ and $g_n=\left(g(n\Delta x)\sqrt{\Delta x}\right)$.

# Fourier Transform as a Coordinate Transformation

A one-dimensional Fourier transform reads

$$
\left\{\begin{aligned}&\tilde{f}(k)=\int_{-\infty}^{\infty}dx\frac{e^{-ikx}}{\sqrt{2\pi}}f(x) \\ & f(x)=\int_{-\infty}^{\infty}dk\frac{e^{ikx}}{\sqrt{2\pi}}\tilde{f}(k)\end{aligned}\right.
$$

Recall equation (1), we can write

$$
\begin{equation}\tilde{f}_k=\sum_{x}(\tilde{e}_k\cdot e_x)f_x\end{equation}
$$

and

$$
\begin{equation}f_x=\sum_{k}(e_x\cdot \tilde{e}_k)\tilde{f}_k\end{equation}
$$

If we define basis vectors $e_x$ and $\tilde{e}_k$ in such a way that

$$
(\tilde{e}_k\cdot e_x) = \langle \tilde{e}_k, e_x \rangle \equiv \frac{e^{-ikx}}{\sqrt{2\pi}}
$$

and according to the definition of the inner product, we have

$$
(e_x\cdot\tilde{e}_k) = \langle e_x, \tilde{e}_k \rangle = \langle \tilde{e}_k, e_x \rangle^* =  \left(\frac{e^{-ikx}}{\sqrt{2\pi}}\right)^* = \frac{e^{ikx}}{\sqrt{2\pi}}
$$

then we will get the Fourier transform!

So the two functions $\tilde{f}_k$ and $f_x$ are just components of a vector $\bold{f}$ in different coordinate systems:

$$
\bold{f}=\sum_{k}\tilde{e}_k\langle \tilde{e}_k,\bold{f}\rangle=\sum_{x} e_x\langle e_x,\bold{f}\rangle
$$

where we can write

$$
\langle \tilde{e}_k,\bold{f}\rangle=\tilde{f}_k\quad,\quad \langle e_x,\bold{f}\rangle=f_x
$$

so

$$
\bold{f}=\sum_{k}\tilde{f}_k\tilde{e}_k=\sum_{x}f_xe_x
$$

After this, we can use the concept of coordinate transformation we have discussed to understand that the Fourier transformation is nothing but a transformation between components of a vector $\bold{f}$ in two different coordinate systems defined by basis sets $\{\tilde{e}_k\}$ and $\{e_x\}$, respectively. 

From this point of view, it becomes clear why the Fourier transform and the inverse Fourier transform share the same form. Suppose both basis sets $\{e_x\}$ and $\{\tilde e_k\}$ are orthonormal (orthogonal and normal at the same time). Plug the inverse Fourier transform (4) into the Fourier transform (3),

$$
\begin{align*}\tilde{f}_k&=\sum_{x}\langle \tilde{e}_k, e_x\rangle f_x \\ &= \sum_{x}\langle \tilde{e}_k, e_x\rangle\left(\sum_{k'}\langle e_x, \tilde{e}_{k'}\rangle\tilde{f}_{k'}\right)\\ & = \sum_{k'}\tilde{f}_{k'}\sum_{x}\langle \tilde{e}_k, e_x\rangle\langle e_x, \tilde{e}_{k'}\rangle\end{align*}
$$

The summation in the last line can be simplified by the properties of the inner product and the orthonormal basis,

$$
\sum_{x}\langle \tilde{e}_k, e_x\rangle\langle e_x, \tilde{e}_{k'}\rangle=\left\langle\tilde{e}_{k},\left(\sum_{x}e_x\langle  e_x,\tilde{e}_{k'}\rangle \right)\right\rangle=\langle\tilde{e}_k,\tilde{e}_{k'}\rangle=\delta_{kk'}
$$

where we have used equation (2). Plug this relation into the last step of the Fourier transform we have done previously, and one gets

$$
\tilde{f}_k=\sum_{k'}\tilde{f}_{k'}\sum_{x}\langle \tilde{e}_k, e_x\rangle\langle e_x, \tilde{e}_{k'}\rangle=\sum_{k'}\tilde{f}_{k'}\delta_{kk'}=\tilde{f}_{k}
$$

 which means all of the above formulas are self-consistent.

# Physical Meaning of the Fourier Transform

The physical meaning of the Fourier transform is the **spectral analysis.**