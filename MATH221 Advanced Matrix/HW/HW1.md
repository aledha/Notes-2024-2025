Chapter 1: questions 2, 4, 10, 11

## Q2

```ad-question
title: Q2
The rank of a matrix is the dimension of the space spanned by its columns. Show that A has rank one if and only if $A = ab^{T}$ for some column vectors a and b.

```

If $\text{rank}(A)=1=\text{dim}(\text{col}(A))$, then each column are linearly dependant of each other. Column number $j$ can therefore be written as a scalar $b_{j}$ multiplied with a vector $a$, i.e., $A=\begin{bmatrix}ab_{1}|ab_{2}|\dots|ab_{n}\end{bmatrix}=ab^{T}$. 

```ad-question
title: Q4
A matrix is strictly upper triangular if it is upper triangular with zero diagonal elements. Show that if A is strictly upper triangular and $n$-by-$n$, then $A^n = 0$.

```
$$A=\begin{bmatrix}0 & a_{12}  & \dots  & a_{1n} \\ \vdots & \ddots & \ddots  & \vdots\\ \vdots &   & \ddots  & a_{n-1,n}\\ 0 &  \dots & \dots  & 0\end{bmatrix}$$
Denote the $k$-th column vector and the $k$-th row vector as
$$c^{T}_{k}=\begin{bmatrix}a_{1k} & \dots & a_{k-1,k} & 0 & \dots & 0\end{bmatrix}, \qquad r_{k}^{T}=\begin{bmatrix}0 & \dots & 0 & a_{k,k+1} & \dots & a_{kn}\end{bmatrix}.$$
Then the square $A$ can be written as
$$A^{2}=\begin{bmatrix}c_{1}  & \dots & c_{n}\end{bmatrix}\begin{bmatrix}r_{1}^{T} \\   \vdots  \\ r_{n}^{T}\end{bmatrix}=c_{1}r_{1}^{T}+c_{2}r_{2}^{T}+\dots+c_{n}r_{n}^{T}=\sum\limits_{k=1}^{n}c_{k}r_{k}^{T}$$
Let's take a closer look at the summation matrices,
$$c_{k}r_{k}^{T}=\begin{bmatrix}a_{1k} \\ \vdots \\ a_{k-1,k} \\ 0 \\ \vdots \\ 0\end{bmatrix}\begin{bmatrix}0 & \dots & 0 & a_{k,k+1} & \dots & a_{kn}\end{bmatrix},$$
and realise that 
$$(c_{k}r_{k}^{T})_{ij}=\begin{cases}
0 & \quad\text{for }i\ge k ,\\
0  & \quad\text{for }j\le k, \\
a_{ik}a_{kj} & \quad\text{else. }
\end{cases}$$

This matrix is zero along both the main diagonal and the 1-diagonal, and the only nonzero entry on the 2-diagonal is when $i=k-1, j=k+1$.

The resulting matrix $A^{2}=\sum_{k=1}^{n} c_{k}r_{k}^{T}$ is therefore zero along the main and 1-diagonal.
$$A \cdot A^{2}= \sum\limits_{k=1}^{n}c_{k}(r_{k}')^{T},$$
where $c_{k}$ remains the same but $r_{k}'$ is the row vector of $A^{2}$ and $r'_{kj}=0\quad\text{for }j\le k+1$. 
Then $(c_{k}(r'_{k})^{T})_{ij}=0 \quad\text{for }i\ge k \text{ or }j\le k+1$. 
$c_{k}(r'_{k})^{T}$ is zero on the main diagonal, 1-diagonal and 2-diagonal, and therefore the same holds for $A^{3}$.

Repeating this until $n$ times yields that $A^{n}=0$ on the main diagonal until the $n$-diagonal, meaning that $A^{n}=0$.

```ad-question
title: Q10
Show that, barring overflow or underflow, $fl(\sum_{i=1}^{d} x_iy_i) = \sum_{i=1}^{d} x_iy_i(1 + \delta _i)$, where $|\delta _{i}|\le d \epsilon$. Use this to prove the following fact. Let $A^{m×n}$ and $B^{n×p}$ be matrices, and compute their product in the usual way. Barring overflow or underflow show that $|fl(A · B) − A · B| ≤ n · ε · |A| · |B|$. Here the absolute value of a matrix $|A|$ means the matrix with entries $(|A|)_{ij} = |a_{ij}|$, and the inequality is meant componentwise.
```
Will use the roundoff error model 
$$\text{fl}(a \odot b)=(a \odot b)(1+\delta ), \qquad \lvert \delta  \rvert\le \epsilon .$$
For now, I will use $\beta$ instead of $\delta$.
$$\begin{align*}
\text{fl}\left(\sum\limits_{i=1}^{d}x_{i}y_{i}\right)&= \left(x_{1}y_{1} + \text{fl}\left(\sum\limits_{i=2}^{d}x_{i}y_{i}\right)\right)(1+\beta _{1})\qquad\text{for }\lvert \beta _{1} \rvert\le \epsilon \\
	&= x_{1}y_{1}(1+\beta _{1})+ (1+\beta _{1})\left(x_{2}y_{2}+ \text{fl} \left(\sum\limits_{i=3}^{d}x_{i}y_{i}\right)\right)(1+\beta _{2})\\
&\vdots\\
	 &= \sum\limits_{i=1}^{d}x_{i}y_{i} \prod_{k=1}^{i}(1+\beta_{k}) \qquad\text{for }\lvert \beta _{1} \rvert,\dots, \lvert \beta _{i} \rvert\le \epsilon \\
\end{align*}$$
We can bound the product
$$\begin{align*}
(1-\epsilon )^{i}&\le \prod_{k=1}^{i}1+\beta _{k}&\le (1+\epsilon )^{i},\\
1- i \epsilon + \mathcal{O}(\epsilon ^{2})&\le \prod_{k=1}^{i}1+\beta _{k}&\le 1+i \epsilon +\mathcal{O}(\epsilon ^{2}).
\end{align*}$$
Ignoring the small $\mathcal{O}(\epsilon ^{2})$, we can rewrite $\prod_{k=1 }^{i}1+ \beta _{k}=1+\delta _{i}\quad\text{for }\lvert \delta _{i} \rvert\le i \epsilon \le d \epsilon$. Then,
$$\text{fl}\left(\sum\limits_{i=1}^{d}x_{i}y_{i}\right)=\sum\limits_{i=1 }^{d}x_{i}y_{i}(1+\delta _{i})\quad \quad\text{for }\lvert \delta _{i} \rvert\le d \epsilon. $$
Now that we have shown this inequality, 
$$\begin{align*}
\text{fl}(A \cdot B)_{ij}&= \text{fl}\left(\sum\limits_{k=1}^{n}a_{ik}b_{kj}\right)= \sum\limits_{k=1}^{n}a_{ik}b_{kj}(1+ \delta _{i}), \qquad \lvert \delta _{i} \rvert\le n \epsilon 
\\
(\lvert \text{fl}(A \cdot B)-A \cdot B \rvert)_{ij}&= \left\lvert \sum\limits_{k=1}^{n}a_{ik}b_{kj}(1+\delta _{i})-a_{ik}b_{kj} \right\rvert\\
&= \left\lvert \sum\limits_{k=1}^{n}a_{ik}b_{kj}\delta_{i}\right\rvert\le n \epsilon \left\lvert \sum\limits_{k=1}^{n}a_{ik}b_{kj} \right\rvert\\
			&\le n \epsilon \sum\limits_{k=1}^{n} \lvert a_{ik} \rvert \lvert b_{kj} \rvert =(n \epsilon \lvert A \rvert \cdot \lvert B \rvert)_{ij}\\
	\lvert \text{fl}(A \cdot B)-A \cdot B \rvert&\le n \epsilon \lvert A \rvert \cdot \lvert B \rvert
\end{align*}$$



```ad-question
title: Q11
Let $L$ be a lower triangular matrix and solve $Lx = b$ by forward substitution. Show that barring overflow or underflow, the computed solution $\hat x$ satisfies $(L + δL)\hat x = b$, where $|δl_{ij} | ≤ nε|l_{ij} |$, where $ε$ is the machine precision. This means that forward substitution is backward stable. Argue that backward substitution for solving upper triangular systems satisfies the same bound.

```
