I have noticed the following problem:

### Statement of the Problem

Let $A$ and $B$ be given matrices. Assume that we have perturbed matrices $A_{\varepsilon} = A + \varepsilon I$ and $B_{\varepsilon} = B + \varepsilon I$. When the Gram–Schmidt algorithm is applied to $A_{\varepsilon}$ ($B_{\varepsilon}$) and $A$ ($B$), we observe significantly large errors:

$$
\lVert A^{\text{orth}} - A^{\text{orth}}_{\varepsilon}\rVert_{\infty} \gg \varepsilon \quad \text{and} \quad \lVert B^{\text{orth}} - B^{\text{orth}}_{\varepsilon}\rVert_{\infty} \gg \varepsilon.
$$

The same issue arises when using the modified Gram-Schmidt process, which is generally considered more stable than the usual algorithm. Biorthogonalization for the $A$, $B$ matrices using the same algorithms naturally leads to similarly large errors (even larger for $A$ if $B^T A = I$ is required).

Is there a modified algorithm to handle perturbed matrices?

### Note

I am currently reading the so-called _Matrix Perturbation Theory_, which I am completely new to. If a solution exists, it is most likely discussed there, I think. If you are aware of an algorithm that can address this problem, feel free to contact me.

**keyword**: Perturbation bounds for the QR factorization
