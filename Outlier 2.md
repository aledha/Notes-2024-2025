$$
\begin{bmatrix}
59 - \lambda & 59 & 71 \\
59 & 77 - \lambda & 101 \\
71 & 101 & 149 - \lambda
\end{bmatrix}
$$

$$
\det \left( K^TK-\lambda I\right)= (59-\lambda )\det\begin{bmatrix}77-\lambda  & 101 \\ 101 & 149-\lambda \end{bmatrix}-59\det\begin{bmatrix}59 & 101 \\ 71 & 149-\lambda \end{bmatrix}+71\det\begin{bmatrix}59 & 77-\lambda  \\ 71 & 101\end{bmatrix}
$$
After computing each determinant, we get
$$\det \left( K^TK-\lambda I\right)= (59-\lambda )((77-\lambda)(149-\lambda )-101^2 )-59(59(149-\lambda )-101\cdot 71)+71(59\cdot 101-(77-\lambda )71)\,.$$

$$\det(K^TK-\lambda I)=-\lambda ^3 +285\lambda ^2 -6084\lambda +14400$$
Now we need to set this equals to zero in order to find the eigenvalues:
$$
\begin{aligned}
-\lambda ^3 +285\lambda ^2 -6084\lambda +14400&= 0
\end{aligned}
$$