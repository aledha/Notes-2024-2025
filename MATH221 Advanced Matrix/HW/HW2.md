- From Chapter 1: 3, 5, 7, 13, 14, 15
- From Chapter 1: 16 (parts 1, 2, 4, 5, 6, 8, 10)
- From Chapter 3: 9
- Extra Credit: From Chapter 1: 20

![[Pasted image 20230910153857.png]]
Let $A$ be a lower triangular matrix, meaning that $a_{ij}=0 \quad\text{for }i\ge j$. We will inspect $A^{-1}=:B$.

$$AB=I$$
$$\begin{align*}
(AB)_{ij}&= \sum_{k=1}^{n}a_{ik}b_{kj}=\begin{cases}
1 \quad\text{for }i=j \\
0 \quad\text{for }i≠j
\end{cases}\\
	&= \sum_{k=i}^{n}a_{ik}b_{kj}\\
\end{align*}$$









$$\begin{align*}
LL^{T}&= I\\
(D+M)(D+M)^{T}&= I\\
(D+M)(D+M^{T})&= I\\
D^{2}+DM^{T}+MD+MM^{T}&= I 
\end{align*}$$
$$\begin{align*}
(D^{2}+DM^{T}+MD+MM^{T})_{ij}&= \begin{cases}
1  & \quad\text{for } i=j\\
0 & \quad\text{for } i≠j
\end{cases}
\end{align*}$$
For $i=j$:
$$d_{i}^{2}+ \sum_{k=i+1}^{n}m_{ik}^{2}=1$$
For $i≠j$.
$$d_{i}m_{ji}+m_{ij}d_{j}+ \sum_{k=\max\{i,j \}+1}^{n}m_{ik}m_{jk}=0$$
For $i<j$
$$d_{i}m_{ji}+\sum_{k=j+1}^{n}m_{ik}m_{jk}$$

![[Pasted image 20230909122524.png]]
A norm must have the following properties
1. Triangle inequality: $\lVert x+y \rVert \le \lVert x \rVert + \lVert y \rVert \quad\forall\quad x,y$.
2. Homogeneity: $\lVert \alpha x \rVert=\lvert s \rvert \cdot  \lVert x \rVert \quad\forall\quad \alpha  \in \mathbb C$.
3. Positive definiteness: $\lVert x \rVert=0 \quad\Leftrightarrow\quad x=0$.

If these hold for $\lVert \cdot  \rVert_{C}$, then it is a vector norm. Let's check them.
1. Triangle inequality
$$\begin{align*}
\lVert x+y \rVert_{C}&= \lVert C(x+y) \rVert=\lVert Cx+Cy \rVert\\
\lVert x+y \rVert_{C}	&\le \lVert Cx \rVert+\lVert Cy \rVert\\
		\lVert x+y \rVert_{C}&\le \lVert x \rVert_{C}+\lVert y \rVert_{C},
\end{align*}$$
where we used that the triangle inequality holds for $\lVert \cdot  \rVert$.
2. Homogeneity
$$\begin{align*}
\lVert \alpha  x \rVert_{C}&= \lVert C (\alpha  x) \rVert=\lvert \alpha  \rvert \cdot  \lVert Cx \rVert\\
	\lVert \alpha  x \rVert_{C}&= \lvert \alpha  \rvert \cdot \lVert x \rVert_{C}
\end{align*}$$
3. Positive definiteness
$$\lVert x \rVert_{C}=\lVert Cx \rVert=0 \quad\Leftrightarrow\quad Cx=0$$
Since $\text{rank}(C)=n$, the only solution to the above equation is $x=0$. Therefore,
$$\lVert x \rVert_{C}=0 \quad\Leftrightarrow\quad x=0$$
We have shown that the three properties holds, so $\lVert \cdot  \rVert_{C}$ is a vector norm if $\text{rank}(C)=n$.

<div style="page-break-after: always;"></div>


![[Pasted image 20230910174832.png]]
Deriving a another definition of the Frobenius norm gives
$$\begin{align*}
(AA^{H})_{ij}&= \sum_{k=1}^{n}a_{ik}\overline{a_{jk}}\\
\text{trace}(AA^{H})&= \sum_{i=1}^{n}\sum_{k=1}^{n}\lvert a_{ik} \rvert^{2}\\
	\sqrt{\text{trace}(AA^{H})}&= \lVert A \rVert_{F}.
\end{align*}$$
We can use this to relate the Frobenius norm and the vector norms
$$\begin{align*}
\lVert xy^{H} \rVert_{F}&= \sqrt{\text{trace}((xy^{H})^{H}(xy^{H}))}\\
&= \sqrt{\text{trace}(yx^{H}xy^{H})}\\
	&= \sqrt{x^{H}x} \cdot \sqrt{\text{trace}(yy^{H})}\\
	&= \lVert x \rVert_{2}\cdot \lVert y \rVert_{2}.
\end{align*}$$
$$\begin{align*}
\lVert xy^{H} \rVert_{2}&=  \sqrt{\lambda _{\text{max}} ((xy^{H})^{H}xy^{H})}\\
&= \sqrt{\lambda _{\text{max}} (yx^{H}xy^{H})}\\
&=  \sqrt{x^{H}x}\cdot \sqrt{\lambda _{\text{max}} (yy^{H})}\\
	&= \lVert x \rVert_{2}\cdot \sqrt{\text{trace}(yy^{H})}\\
	&= \lVert x \rVert_{2}\cdot \lVert y \rVert_{2},
\end{align*}$$
Where $\lambda _\text{max}(yy^{H})=\text{trace}(yy^{H})$ since it's a rank 1 matrix.

Now we have shown that $\lVert xy^{H} \rVert_{F}=\lVert xy^{H} \rVert_{2}=\lVert x \rVert_{2}\lVert y \rVert_{2}$ for any $x,y \in \mathbb C^{n}$.


![[Pasted image 20230910184938.png]]
![[Pasted image 20230910184926.png]]


![[Pasted image 20230910190657.png]]
![[Pasted image 20230910190626.png]]


![[Pasted image 20230910190704.png]]
![[Pasted image 20230910190641.png]]


(parts 1, 2, 4, 5, 6, 8, 10)
![[Pasted image 20230910190721.png]]
![[Pasted image 20230910190748.png]]

## 1.7.10


## 1.7.2
First, for the operator norm:
$$\begin{align*}
\lVert AB \rVert&= \max_{\lVert x \rVert=1}\lVert ABx \rVert\\
&= \max_{\lVert x \rVert=1}\lVert A(Bx) \rVert\\
&= \max_{\lVert x \rVert=1}\left\lVert A \frac{Bx}{\lVert Bx \rVert}\cdot \lVert Bx \rVert  \right\rVert\\
	&= \max_{\lVert y \rVert=1}\lVert Ay \rVert \cdot \max_{\lVert x \rVert=1}\lVert Bx \rVert\\
	&= \lVert A \rVert \cdot \lVert B \rVert
\end{align*}$$
Now, for the Frobenius norm 
$$\begin{align*}
\lVert AB \rVert_{F}&=  \sqrt{\sum_{i,j=1}^{n}\lvert (AB)_{ij} \rvert^{2}}\\
&= \sqrt{\sum_{i,j=1}^{n} \left\lVert \sum_{k=1}^{n}a_{ik}b_{kj} \right\rVert^{2}}\\
&\le \sqrt{\sum_{i,j=1}^{n} \sum_{k=1}^{n} (\lVert a_{ik} \rVert^{2}\cdot \lVert b_{kj} \rVert^{2})}\\
&\le \sqrt{\sum_{i,j=1}^{n}\sum_{k=1}^{n}\lVert a_{ik} \rVert^{2}}\cdot \sqrt{\sum_{i,j=1}^{n}\sum_{k=1}^{n}\lVert b_{kj} \rVert^{2}}\\
		&\le \lVert A \rVert_{F}\cdot \lVert B \rVert_{F}
\end{align*}$$



![[Pasted image 20230910190933.png]]
![[Pasted image 20230910191008.png]]

## 1. $(A^{T}A)^{-1}$
$$\begin{align*}
(A^{T}A)^{-1}&= (V \Sigma ^{T}U^{T}U \Sigma V^{T})^{-1}\\
&= (V \Sigma ^{T} \Sigma V^{T})^{-1}\\
&= V^{-T}(\Sigma ^{T}\Sigma )^{-1}V^{-1}\\
&= V (\Sigma ^{T}\Sigma )^{-1}V^{T}
\end{align*}$$
## 2. $(A^{T}A)^{-1}A^{T}$
We can just continue from where we left off:
$$\begin{align*}
(A^{T}A)^{-1}A^{T}&= V (\Sigma ^{T}\Sigma )^{-1}V^{T}(U \Sigma V^{T})^{T}\\
&= V (\Sigma ^{T}\Sigma )^{-1}V^{T}V \Sigma ^{T}U^{T}\\
&= V \Sigma ^{-1}\Sigma ^{-T} \Sigma ^{T}U^{T}\\
&= V \Sigma ^{-1}U^{T}
\end{align*}$$
## 3. $A(A^{T}A)^{-1}$
$$\begin{align*}
A(A^{T}A)^{-1}&= U \Sigma V^{T}V (\Sigma ^{T}\Sigma )^{-1}V^{T}\\
&= U \Sigma \Sigma^{-1} \Sigma ^{-T}V^{T}\\
&= U \Sigma ^{-T}V^{T}
\end{align*}$$
## 4. $A(A^{T}A)^{-1}A^{T}$
$$\begin{align*}
A(A^{T}A)^{-1}A^{T}&=  U \Sigma V^{T}V (\Sigma ^{T}\Sigma )^{-1}V^{T} (U \Sigma V^{T})^{T}\\
&= U \Sigma \Sigma ^{-1}\Sigma ^{-T}\Sigma ^{T}U^{T}\\
&= UU^{T}=I
\end{align*}$$
