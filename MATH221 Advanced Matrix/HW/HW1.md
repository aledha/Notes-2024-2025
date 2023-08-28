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
$$A^{2}=\begin{bmatrix}a_{1} & a_{2} & \dots & a_{n}\end{bmatrix}\begin{bmatrix}b_{1}^{T} \\   \vdots  \\ b_{n}^{T}\end{bmatrix}=a_{1}b_{1}^{T}+a_{2}b_{2}^{T}+\dots+a_{n}b_{n}^{T}$$
$$a^{T}_{j}=\begin{bmatrix}a_{1j} & \dots & a_{j-1,j} & 0 & \dots & 0\end{bmatrix}, \qquad b_{j}^{T}=\begin{bmatrix}0 & \dots & 0 & a_{j,j+1} & \dots & a_{jn}\end{bmatrix}$$
$$a_{j}b_{j}^{T}=\begin{bmatrix}a_{1j} \\ \vdots \\ a_{j-1,j} \\ 0 \\ \vdots \\ 0\end{bmatrix}\begin{bmatrix}0 & \dots & 0 & a_{j,j+1} & \dots & a_{jn}\end{bmatrix}$$
We see that the first $j$ columns and the last $n-j$ rows in the resulting matrix will be zero. $a_{j}b_{j}^{T}$ can therefore be written as a concatenation between submatrices:  $\begin{bmatrix}0 & B \\ 0 & 0\end{bmatrix}$ where $B \in \mathbb{R}^{(j-1) \times (n-j-1)}$



```ad-question
title: Q10
Show that, barring overflow or underflow, $fl(\sum_{i=1}^{d} x_iy_i) = \sum_{i=1}^{d} x_iy_i(1 + \delta _i)$, where $|\delta _{i}|\le d \epsilon$. Use this to prove the following fact. Let $A^{m×n}$ and $B^{n×p}$ be matrices, and compute their product in the usual way. Barring overflow or underflow show that $|fl(A · B) − A · B| ≤ n · ε · |A| · |B|$. Here the absolute value of a matrix $|A|$ means the matrix with entries $(|A|)_{ij} = |a_{ij}|$, and the inequality is meant componentwise.
```


```ad-question
title: Q11
Let $L$ be a lower triangular matrix and solve $Lx = b$ by forward substitution. Show that barring overflow or underflow, the computed solution $\hat x$ satisfies $(L + δL)\hat x = b$, where $|δl_{ij} | ≤ nε|l_{ij} |$, where $ε$ is the machine precision. This means that forward substitution is backward stable. Argue that backward substitution for solving upper triangular systems satisfies the same bound.

```
