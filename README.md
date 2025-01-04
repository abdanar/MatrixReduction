# Causal LTI System and Parametrized Linear Coercive Models for IRKA

The transfer function for the causal LTI system with a realization $(A, B, C, D)$ is given by

$$
H(s) = C(sI_{n} - A)^{-1}B.
$$

Notice that $H(s) = C v(s)$, where $v(s)$ is the solution of a parametrized linear coercive model

$$
a(v, w; s) = l(w),
$$

where $a(v, w; s) = w^*(sI_{n} - A)v$ and $l(w) = w^{*}B$. In other words, we replace the matrix computation of $(sI_{n} - A)^{-1}B$ with a parametrized model (1). However, if one wants to apply this to the Iterative Rational Krylov Algorithm (IRKA), then the following matrix computations must be done to construct the projection matrices $V$ and $W$:

<p>
  $$ (-\mu_{i}I_{n} - A)^{-1}B\hat{b}_{i} \quad \text{and} \quad (-\mu_{i}I_{n} - A)^{-*}C^{T}\hat{c}_{i} \quad \text{for} \quad i = 1,\ldots,r $$
</p>


where $-\mu_{i}$, $\hat{c}_{i}$, $\hat{b}_{i}$ are some initial interpolation data and $0 < r \leq n$ is the desired order of approximating ROM. So, we have decided to solve two parametrized linear coercive models to construct projection matrices $V$ and $W$:

$$
a_{1}(v_{1}, w; s) = l_{1}(w) \quad \text{and} \quad a_{2}(v_{2}, w; s) = l_{2}(w),
$$

where $a_{1}(v_{1}, w; s) = w^{*}(sI_{n} - A)v_{1}$ and $l_{1}(w) = w^{*}B$, and $a_{2}(v_{2}, w; s) = w^{*}(sI_{n} - A)^{*}v_{2}$ and $l_{2}(w) = w^{*}C^{T}$, and solutions to these parametrized linear coercive models are

$$
v_{1}(s) = (sI_{n} - A)^{-1}B \quad \text{and} \quad v_{2}(s) = (sI_{n} - A)^{-*}C^{T}.
$$

Therefore, knowing $v_{1}(\mu_{i})$ and $v_{2}(\mu_{i})$ for $i = 1, \ldots, r$ will suffice for constructing the projection matrices $V$ and $W$. Also, note that these two FOMs are parameter-separable, i.e.,
<p>
$$
a_{1}(v_{1},w;s) = w^{*}(sI_{n} - A)v_{1} = sw^{*}I_{n}v_{1} - w^{*}Av_{1}  \quad  a_{2}(v_{2},w;s) = w^{*}(sI_{n} - A)^{*}v_{2} = \overline{s}w^{*}I_{n}v_{2} - w^{*}A^{*}v_{2}.
$$
</p>
