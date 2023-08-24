Solve $Ax=b$: 
Well defined when A square and full rank,
otherwise then least squares may be better (or if A is close to low rank)

## Least Squares
Used wen A is overdetermined
$A^{m \times n}$
* When A is full column rank ($m\ge n$), then  $\underset{x}{\text{argmin }}\lVert Ax-b \rVert^{2}$
* A not full rank ($m<n$)$\quad\implies\quad$ $x$ not unique, so choose the x that minimises $\lVert x \rVert_{2}$

Ridge regression (also called Tikhonov regularization)
$\underset{x}{\text{argmin }}\lVert Ax-b \rVert_{2}^{2}+\lambda \lVert x \rVert_{2}^{2}$ 
Now $x$ will be unique if $\lambda >0$

## Constrained Least Squares
$$\underset{x:\text{ } Cx=d}{\text{argmin }}\lVert Ax-b \rVert_{2}$$

## Weighted least squares
$$\underset{x}{\text{argmin }} \lVert W(Ax-b) \rVert_{2}$$
where $W$ is a weight matrix

## Total least squares
Idea: perturb $A$ and $b$

$$\underset{x:\text{ }(A+E)x=b+r}{\text{argmin }}[E,r]$$
(where $[A,B]$ is concatination)


# Eigenproblems

$X^{n \times n}= [x_{1},\dots,x_{n}], \quad \Lambda =diag(\lambda _{1},\dots, \lambda _{n})$
$\implies\quad AX=X \Lambda$   if $X$ is non-singular
Then we get the eigendecomposition
$$A=X \Lambda X^{-1}$$

Problem: A may not have n independant eigenvectors
One solution: Jordan form
But this is numerically unstable
For $A{'}=\begin{bmatrix}\epsilon  & 1 \\ 0  & 0\end{bmatrix}$   the Jordan form is $\begin{bmatrix}\epsilon  & 0 \\ 0 & 0\end{bmatrix}$

We will use Schur Form instead.

### Singular value decomposition
$$A^{m \times n}= U \Sigma V^{T} \quad\text{for }m\ge n$$
* $U^{m \times m}$, $V^{n \times n}$ orthogonal ($UU^{T}=I$)
* $\Sigma ^{m \times n}$ is rectangular diagonal
$\Sigma =\begin{bmatrix}\sigma _{1} & 0 \\ 0 & \sigma _{2} \\ 0 & 0\end{bmatrix}$ 
Where $\sigma _{i}$ is the i-th singular value
$A^{T}A=V \Sigma ^{T}\Sigma V^{T}$ 

SVD is the most reliable method for Least Squares, but also the most expensive

## Invariant subspaces:
$x'(t)=Ax(t)$ and we are given $x(0)$
Suppose $Ax(0)=\lambda x(0)$,
then $x(t) = e^{\lambda t}x(0)$

Easy to tell if $x(t)\to0$ as $t\to \infty$

Generalising: Suppose $x(0) = \sum\limits_{i}^{}\beta _{i} x_{i}$, where $Ax_{i}= \lambda _{i}x_{i}$
wether $x(t)\to 0$ as $t\to \infty$ depends on whether $\mathbb{R}(\lambda _{i})<0$ for all $\beta _{i}≠0$,
i.e., whether $x(0)$ is in subspace spanned by all eigen vectors with $\mathbb{R}(\lambda _{i})<0$
-called invariant subspace