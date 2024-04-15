# HW2

## Identities and Inequalities with Expectation

### 1.1

For $k=0,\mathbb{E}[X^k]=1$
For $k=n$, suppose $\mathbb{E}[X^n]=\frac{n!}{\lambda^n}$,which means $\int_0^\infty\lambda e^{-\lambda x}x^ndx=\frac{n!}{\lambda^n}
$
For $k=n+1$,
$
\begin{aligned}
\mathbb{E}[X^{n+1}]&=\int_0^\infty\lambda e^{-\lambda x}x^{n+1}dx\\
&=-e^{-\lambda x}x^{n+1}\vert_0^\infty+\int_0^\infty\frac{1}{\lambda} e^{-\lambda x}d(\lambda x^{n+1})\\
&=0+(n+1)\int_0^{-\infty}e^{-\lambda x}x^n dx\\
&=\frac{(n+1)!}{\lambda^{n+1}}
\end{aligned}
$
Through induction on k, we can conclude $\mathbb{E}[X^k]=\frac{k!}{\lambda^k}$ for integer $k>0$.

### 1.2

First let us to show that for $a, b>0, \textbf{1}\{a\geq b\}\leq a/b
$. For $a\geq b>0, \textbf{1}\{a\geq b\}=1\leq 1\leq a/b$.  For $b> a >0, \textbf{1}\{a\geq b\}=0< a/b$.
For non-negative random variable $X$ and constant $t>0, \mathbb{P}(X\geq t)=\mathbb{E}[\textbf{1}\{X\geq t\}]\leq \mathbb{E}[X/t]=\mathbb{E}[X]/t$

### 1.3

Assume $X$ admits a density function $f(x)$.
$$
\begin{aligned}
    \mathbb{E}[X]&=\int_0^\infty xf(x)\ dx\\
    &=\int_0^\infty (\int_0^x dt) f(x) dx\\
    &=\int_0^\infty \int_0^x f(x)\ dtdx\\
    &=\int_0^\infty \int_t^\infty f(x)\ dx dt\\
    &=\int_0^\infty \mathbb{P}(X\geq t)\ dt
\end{aligned}
$$

### 1.4

$$
\begin{aligned}
    (\mathbb{E}[X])^2&=(\mathbb{E}[X\textbf{1}\{X>0\})]^2\\
    &\leq \mathbb{E}[X^2]\cdot \mathbb{E}[\textbf{1}\{X>0\}^2]\\
    &=\mathbb{E}[X^2]\cdot \mathbb{E}[\textbf{1}\{X>0\}]\\
    &=\mathbb{E}[X^2]\cdot \mathbb{P}(X>0)
\end{aligned}
$$

Thus $\mathbb{P}(X>0)\geq \frac{(\mathbb{E}[X])^2}{\mathbb{E}[X^2]}$

### 1.5

$
\begin{aligned}
    &(t-X)\leq (t-X)\textbf{1}\{t-X>0\}\\
    \Rightarrow&0\leq t=\mathbb{E}[t-X]\leq \mathbb{E}[(t-X)\textbf{1}\{t-X>0\}]\\
    \Rightarrow&
    (\mathbb{E}[t-X])^2\leq
    (\mathbb{E}[(t-X)\textbf{1}\{t-X>0\}])^2
\end{aligned}
$

$
\begin{aligned}
    t^2&=(\mathbb{E}[t-X])^2\\
    &\leq (\mathbb{E}[(t-X)\textbf{1}\{t-X>0\}])^2\\
    &\leq \mathbb{E}[(t-X)^2]\cdot \mathbb{P}(t-X>0)\\
    &=(t^2+\mathbb{E}[X^2])\cdot \mathbb{P}(X<t)
\end{aligned}
$
We can reformulate this to $\mathbb{P}(X\geq t)\leq \frac{\mathbb{E}[X]^2}{\mathbb{E}[X^2]+t^2}.$

## Probability Potpourri

### 2.1

For any vector $x$,$x^T\Sigma x=x^T\mathbb{E}[(Z-\mu)(Z-\mu)^T]x=\mathbb{E}[x^T(Z-\mu)(Z-\mu)^Tx]=\mathbb{E}[((Z-\mu)^Tx)^2]\geq 0$

### 2.2

$
(i) 0.3*0.4=0.12\\
(ii) 0.3*0.4+0.7*0.7=0.61\\
(iii) 1-(1-0.61)^2-0.61^2=0.4758\\
(iv) 0.3*(1-0.4)/1-0.61=\frac{18}{39}
$

### 2.3

S:scores
$$
\begin{aligned}
    \mathbb{E}[S]&=\int_0^{1/\sqrt{3}}4f(x)\ dx+\int_{1/\sqrt{3}}^1 3f(x)\ dx+\int_1^{\sqrt{3}}2f(x)\ dx\\
    &=\frac{13}{6}
\end{aligned}
$$

### 2.4

Assume $0\leq k\leq n$
$$
\begin{aligned}
    \mathbb{P}(X=k\vert X+Y=n)&=\frac{\mathbb{P}(X=k, Y=n-k)}{\mathbb{P}(X+Y=n)}\\
    &=\frac{\frac{\lambda^ke^{-\lambda}}{k!}\frac{\mu^{n-k}e^{-\mu}}{(n-k)!}}{\sum_{i=0}^n\frac{\lambda^ie^{-\lambda}}{i!}\frac{\mu^{n-i}e^{-\mu}}{(n-i)!}}\\
    &=\frac{C_n^k(\frac{\lambda}{\lambda+\mu})^k(\frac{\mu}{\lambda+\mu})^{n-k}}{\sum_{i=0}^nC_n^i(\frac{\lambda}{\lambda+\mu})^i(\frac{\mu}{\lambda+\mu})^{n-i}}\\
    &=C_n^k(\frac{\lambda}{\lambda+\mu})^k(\frac{\mu}{\lambda+\mu})^{n-k}
\end{aligned}
$$
Thus $\mathbb{P}(X=k\vert X+Y=n)\sim\ B(n,\frac{\lambda}{\lambda+\mu})$

## Properties of the Normal Distribution(Gaussians)

### 3.1

$$
\begin{aligned}
    \mathbb{E}[e^{\lambda X}]&=\int_{-\infty}^\infty e^{\lambda x}\cdot \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}\ dx\\
    &=\int_{-\infty}^{+\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\sigma^2)^2+\lambda^2\sigma^4}{2\sigma^2}}\ dx\\
    &\overset{t=x-\sigma^2}{\xlongequal{\quad}}e^{\lambda^2\sigma^2/2}\int_{-\infty}^{+\infty} \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{t^2}{2\sigma^2}}\ dt\\
    &=e^{\lambda^2\sigma^2/2}
\end{aligned}
$$

### 3.2

Suppose $ \lambda>0, \mathbb{P}(X\geq t)=\mathbb{P}(e^{\lambda X}\geq e^{\lambda t})\leq \mathbb{E}[e^{\lambda X}]/e^{\lambda t}=e^{\sigma^2\lambda^2/2-\lambda t}.
$ Let $\lambda = t/\sigma^2$, we can get $\mathbb{P}(X\geq t)=exp(-t^2/2\sigma^2)$. And $\mathbb{P}(\vert X\vert\geq t)=2\mathbb{P}(X\geq t)=2exp(-t^2/2\sigma^2)$

### 3.3

We can konw $\frac{1}{n}\sum_{i=1}^nX_i\sim \mathcal{N}(0,\sigma^2/n)
$. And from results from 3.2, $\mathbb{P}(\frac{1}{n}\sum_{i=1}^nX_i\geq t)\leq exp(-nt^2/2\sigma^2).
$ When $n\to \infty $, the random variable will distribute more and more densely around its mean value 0.

### 3.4

Assume $A=\begin{pmatrix}
    \boldsymbol{a_1}^T\\
    ...\\
    \boldsymbol{a_n}^T\\
\end{pmatrix}$
$
\begin{aligned}
\mathbb{E}[Y_i]&=
\mathbb{E}[\sum_{k=1}^na_{ik}x_k+b_i]\\
&=b_i\sum_{k=1}^na_{ik}\mathbb{E}[x_k]\\
&=b_i
\end{aligned}
$
$
\begin{aligned}
\sigma(Y_i,Y_j)&=\mathbb{E}[Y_iY_j]-\mathbb{E}[Y_i]\mathbb{E}[Y_j]\\
&=\mathbb{E}[\sum_{k=1}^na_{ik}x_k\cdot \sum_{k=1}^na_{jk}x_k]\\
&=\mathbb{E}[\sum_{k=1}^na_{ik}a_{jk}x_k^2]\\
&=\sum_{k=1}^na_{ik}a_{jk}\mathbb{E}[x_k^2]\\
&=\sigma^2\boldsymbol{a_i^Ta_j}
\end{aligned}
$
Thus $\mathbb{E}[Y]=b, \sigma(Y)=\sigma^2AA^T$

### 3.5

We can know that $u_x, v_x$ are two Gaussian random variables.
$
\begin{aligned}
Cov(u_x, v_x)&=\mathbb{E}[u_xv_x]-\mathbb{E}[u_x]\mathbb{E}[v_x]\\
&=\mathbb{E}[\sum_{i=1}^nu_iX_i\cdot \sum_{i=1}^nv_iX_i]\\
&=\mathbb{E}[\sum_{i=1}^nu_iv_iX_i^2]\\
&=\sum_{i=1}^nu_iv_i\mathbb{E}[X_i^2]\\
&=0
\end{aligned}
$
Thus they are uncorrelated so that they are independent.
If these variables are not identically distributed, then $Cov(u_x,v_x)=\sum_{i=1}iu_iv_i$ may not be equal to 0, and they are possibly not independent.

### 3.6

Assume $\lambda>0.$
$$
\begin{aligned}
\mathbb{E}[\max_{1\leq i\leq N}X_i]&=\mathbb{E}[\frac{1}{\lambda}\log e^{\lambda\max_{1\leq i\leq N}X_i}]\\
&\leq \frac{1}{\lambda}\log\mathbb{E}[e^{\lambda\max_{1\leq i\leq N}X_i}]\\
&=\frac{1}{\lambda}\log\mathbb{E}[\max_{1\leq i\leq N}e^{\lambda X_i}]\\
&\leq \frac{1}{\lambda}\log\sum_{i=1}^N\mathbb{E}[e^{\lambda X_i}]\\
&\leq \frac{1}{\lambda}\log \sum_{i=1}^Ne^{\lambda^2\sigma^2/2}\\
&=\frac{\log n}{\lambda}+\frac{\lambda\sigma^2}{2}
\end{aligned}
$$

Let $\lambda=\sqrt{2(\log N)/\sigma^2}$, we can get $\mathbb{E}[\max_{1\leq i\leq N}X_i]\leq \sqrt{2\sigma^2\log n}$
Moreover, there is a fact that $\max_{1\leq i\leq N}\vert X_i\vert=\max_{1\leq i\leq 2N}X_i$, where $X_{N+i}=-X_i\sim\mathcal{N}(0,\sigma^2)$
Thus $\mathbb{E}[\max_{1\leq i\leq N}\vert X_i\vert]\leq \sqrt{2\log (2N)}\sigma=C\sqrt{\log(2  N)}\sigma$

## Linear Algebra Review

### 4.1

$(a)$
$
\begin{bmatrix}
    I_n\ & 0\\
    0\ & AB
\end{bmatrix}\to
\begin{bmatrix}
    I_n\ & B\\
    0\ & AB\\
\end{bmatrix}\to
\begin{bmatrix}
    I_n\ & B\\
    -A\ & 0\\
\end{bmatrix}\to
\begin{bmatrix}
    I_n\ & B\\
    A\ & 0\\
\end{bmatrix}\to
\begin{bmatrix}
    B & I_n\\
    0 & A\\
\end{bmatrix}
$

$(b)$

1.  
    $
    rank(AB)+n=rank(\begin{bmatrix}
        I_n\ & 0\\
        0\ & AB
    \end{bmatrix})=rank(\begin{bmatrix}
        B & I_n\\
        0 & A\\
    \end{bmatrix})\geq rank A+rank B
    $

2.  
    $
    rank(AB)+n=rank(\begin{bmatrix}
        I_n\ & 0\\
        0\ & AB
    \end{bmatrix})=rank(\begin{bmatrix}
        B & I_n\\
        0 & A\\
    \end{bmatrix})\leq n+rank(A)
    $
    Similarly, we can get $rank(AB)\leq rank(B)$
    Thus $rank(AB)\leq \min\{rank\ A,
    \ rank\ B\}$

$(c)$

$rank(A^TA)\leq $

### 4.2

$(a)\to (b):$  

Suppose there is a eigenvalue $\lambda$ of $A$ and $\lambda<0$.Thus there is a nonzero vector $x$, which satisfies $AX=\lambda x$. Taking this $x$, $x^TAx=x^T\lambda x=\lambda x^Tx< 0$. Contradiction

$(b)\to (c):$

Since $A$ is a real symmertic matrix, $A$ can be written as $A=Q\Lambda Q^T$, where $Q$ is an orthogonal matrix. Thus $A=Q\sqrt{\Lambda}\sqrt{\Lambda}Q^T=(\sqrt{\Lambda}Q^T)^T\sqrt{\Lambda}Q^T=U^TU,
$ where $U=\sqrt{\Lambda}Q^T$

$(c)\to (a):$

For all $x\in R^n, x^TAx=x^TUU^Tx=(U^Tx)^T(Ux)\geq 0$

### 4.3

$(a)$
$
x^TAy=x^T
\begin{bmatrix}
a_1, a_2,..., a_n
\end{bmatrix}
\begin{bmatrix}
    y_1\\
    y_2\\
    ...\\
    y_n
\end{bmatrix}=
x^T\sum_{i=1}^na_iy_i
$
$
<A,xy^T>=trace(A^Txy^T)=trace(\begin{bmatrix}
    a_1^Tx\\
    a_2^Tx\\
    ...\\
    a_n^Tx
\end{bmatrix}
\begin{bmatrix}
    y_1, y_2,...,y_n
\end{bmatrix}
)
=x^T\sum_{i=1}^na_iy_i
$
Thus $x^TAy=<A,xy^T>$

$(b)$

$\begin{aligned}
    <A,B>&=trace(A^TB)\\
    &=\sum_{i=1}^na_i^Tb_i\\
    &\leq \sum_{i=1}^n\vert a_i\vert \vert b_i\vert\\
    &\leq \sqrt{\sum_{i=1}^n\vert a_i\vert^2\sum_{i=1}^n\vert b_i\vert^2}\\
    &=\sqrt{\sum_{i=1}^m\sum_{j=1}^n\vert A_{ij}\vert^2}\sqrt{{\sum_{i=1}^m\sum_{j=1}^n\vert B_{ij}\vert^2}}\\
    &=\Vert A\Vert_F\Vert B\Vert_F
\end{aligned}
$

$(c)$

$trace(AB)=trace(XX^TYY^T)=trace(X^TYY^TX)=trace((Y^TX)^T(Y^TX))\geq 0
$

$(d)$

Let $E=diag\{\lambda_{max}(A)\}\succeq 0$

### 4.4

[补充：Are the eigenvalues of AB
 equal to the eigenvalues of BA
?](https://math.stackexchange.com/questions/124888/are-the-eigenvalues-of-ab-equal-to-the-eigenvalues-of-ba)

[The first answer here is very elegant.](https://math.stackexchange.com/questions/435831/if-a-and-b-are-positive-definite-then-is-b-1-a-1-positive-semidef)

### 4.5

## Matrix/Vector Calculus and Norms

### 5.1

$f(A)=sin(A_{11}^2+e^{A_{11}+A_{22}})+x_1A_{11}y_1+x_1y_2A_{12}+x_2y_1A_{21}+x_2y_2A_{22}
$
Thus the derivative of A with respect to A is
$
cos(A_{11}^2+e^{A_{11}+A_{22}})
\begin{bmatrix}
    2A_{11}+e^{A_{11}+A_{22}} & 0\\
    0 &e^{A_{11}+A_{22}}
\end{bmatrix}+xy^T
$

### 5.2

(a) $\Vert A\Vert_2=\sup_{x\neq 0}\frac{\Vert Ax\Vert_2}{\Vert x\Vert_2}=\sup_{\Vert x\Vert_2=1}\Vert Ax\Vert_2=\sup_{\Vert x\Vert_2\leq 1}\Vert Ax\Vert_2$

### 5.4

By the Taylor's Theorem, $f(x)=f(x^*)+\nabla^T f(x^*)(x-x^*)+\frac{1}{2}(x-x^*)^TH(x^\prime)(x-x^*)$
