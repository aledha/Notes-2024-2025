09/11/23 
Alexander Hatle
- From Chapter 1: 3, 5, 7, 13, 14, 15
- From Chapter 1: 16 (parts 1, 2, 4, 5, 6, 8, 10)
- From Chapter 3: 9
- Extra Credit: From Chapter 1: 20

![[Pasted image 20230910153857.png]]
Let $A$ be a upper triangular and orthogonal. $A$ can be written as
$$A=D(X+I),$$
where $D$ is a diagonal matrix, and $X$ is strictly upper triangular. The inverse of $A$ is then
$$A^{-1}=D^{-1}(X+I)^{-1}=D^{-1}(I-X+X^{2}+\dots+(-1)^{n}X^{n}).$$
In the last homework, we showed that a strictly upper triangular matrix $X^{i}$ is still strictly upper triangular. Then we observe that $A^{-1}$ is upper triangular. 

But since $A$ is upper triangular, $A^{-1}=A^{T}$ is lower triangular as well. Since $A^{-1}$ is both lower and upper triangular, it must be diagonal.

Now that we know that it's diagonal, it's easy to compute the elements. Since $A$ is diagonal and orthogonal,
$$AA^{-1}=AA^{T}=A^{2}=I,$$
implying that
$$A=I.$$
<div style="page-break-after: always;"></div>

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
Deriving the trace definition of the Frobenius norm 
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

<div style="page-break-after: always;"></div>

![[Pasted image 20230910184938.png]]
![[Pasted image 20230910184926.png]]
I don't know how to prove the first part. I will prove that if $A$ is h.p.d, then $\left\langle x \text{ , } y \right\rangle=y^{*}Ax$ is an inner product. 
Using definition 1.4:
![[Pasted image 20230911192646.png|500]]
1. $\left\langle x \text{ , } y \right\rangle= \overline{\left\langle y \text{ , } x \right\rangle}$
	$\left\langle x \text{ , } y \right\rangle= y^{*}Ax = x^{T}A(y^{*})^{T}=\overline{x^{*}Ay}= \overline{\left\langle y \text{ , } x \right\rangle}$.
2. $\left\langle x \text{ , } y+z \right\rangle=(y+z)^{*}Ax=y^{*}Ax+z^{*}Ax= \left\langle x \text{ , } y \right\rangle+\left\langle x \text{ , } z \right\rangle$.
3. $\left\langle \alpha x \text{ , } y \right\rangle=y^{*}A(\alpha x)=\alpha y^{*}Ax=\alpha \left\langle x \text{ , } y \right\rangle.$
4. Since $A$ is h.p.d., then (by definition) $x^{*}Ax \ge 0 \quad\forall\quad x≠0$.

This inner product satisfies all the criteria.

<div style="page-break-after: always;"></div>

![[Pasted image 20230910190657.png]]
![[Pasted image 20230910190626.png]]
## First inequality
$$\lVert x \rVert_{2}=\sqrt{\sum_{i=1}^{n}\lvert x_{i} \rvert^{2}}\le \sqrt{\left(\sum_{i=1}^{n}\lvert x_{i} \rvert\right)\left(\sum_{i=1}^{n}\lvert x_{i} \rvert\right)}\le \lVert x \rVert_{1}$$
$$\lVert x \rVert_{1}=\sum_{i=1}^{n}\lvert x_{i} \rvert \cdot 1 \stackrel{C.S.}{\le }\sqrt{\sum_{i=1}^{n}\lvert x_{i} \rvert^{2}} \sqrt{\sum_{i=1}^{n}1^{2}}= \sqrt{n}\lVert x \rVert_{2}$$
Combining these gives us our desired result,
$$\lVert x \rVert_{2}\le \lVert x \rVert_{1}\le \sqrt{n}\lVert x \rVert_{2}$$

## Second inequality
$$\lVert x \rVert_{\infty}=\max_{j}\lvert x_{j} \rvert$$
The infinity norm is maximised compared to the 2-norm if $x$ only has one nonzero element. Let's say that $\hat x=\left[k,0,0,\dots \right]^{T}$. Then,
$$ \lVert \hat x \rVert_{\infty } =\lvert k \rvert, \qquad \lVert \hat x \rVert_{2}=\lvert k \rvert.$$
If $\hat x$ had more non-zero elements, the 2-norm would grow larger, so we therefore have that $\lVert x \rVert_{\infty}\le \lVert x \rVert_{2}$.

Now we want to maximise the 2-norm while minimising the $\infty$-norm. The best we could do is a vector repeating the same element, i.e. $\tilde x= \left[k,k,k,\dots \right]$. Then,
$$\lVert \tilde x \rVert_{\infty}=\lvert k \rvert, \qquad \lVert \tilde x \rVert_{2}=\sqrt{\sum_{i=1}^{n}\lvert k \rvert^{2}}=\sqrt{n}\cdot \lvert k \rvert.$$
Since any change to $\tilde x$ would either increase the $\infty$-norm or decrease the 2-norm, we obtain that $\lVert x \rVert_{2}\le \sqrt{n} \lVert x \rVert_{\infty}$. Combining the two inequalities gives
$$\lVert x \rVert_{\infty}\le \lVert x \rVert_{2}\le \sqrt{n}\lVert x \rVert_{\infty}.$$

## Third inequality
We can simply use the inequalities proven before. First the upper bound
$$\lVert x \rVert_{1}\le \sqrt{n}\lVert x \rVert_{2} \le \sqrt{n} \sqrt{n}\lVert x \rVert_{\infty}=n \lVert x \rVert_{\infty}.$$
Then the lower bound
$$\lVert x \rVert_{\infty}\le \lVert x \rVert_{2}\le \lVert x \rVert_{1}.$$
Combining,
$$\lVert x \rVert_{\infty}\le \lVert x \rVert_{1}\le n \lVert x \rVert_{\infty}.$$
<div style="page-break-after: always;"></div>


![[Pasted image 20230910190704.png]]
![[Pasted image 20230910190641.png]]
Definition of a matrix norm:
![[Pasted image 20230911193505.png|500]]
Let's check all of these with the operator norm $\lVert A \rVert=\max_{x≠0}\frac{\lVert Ax \rVert}{\lVert x \rVert}.$ 
While showing these properties, I will use the properties that vector norms fulfill.
1. Since the vector norms $\lVert Ax \rVert, \lVert x \rVert\ge0 \quad\implies\quad \lVert A \rVert\ge 0$. 
	Since  $x≠0$, the only way $\lVert A \rVert=0$ is if $A=0$.
2. $\lVert \alpha A \rVert=\max_{x≠0} \frac{\lVert \alpha Ax \rVert}{\lVert x \rVert}=\lvert \alpha  \rvert\max_{x≠0} \frac{\lVert Ax \rVert}{\lVert x \rVert}=\lvert \alpha  \rvert \lVert A \rVert$ 
3. $\lVert A+B \rVert= \max_{x≠0} \frac{\lVert (A+B)x \rVert}{\lVert x \rVert}=\max_{x≠0} \frac{\lVert Ax+Bx \rVert}{\lVert x \rVert}\le \max_{x≠0} \frac{\lVert Ax \rVert+\lVert Bx \rVert}{\lVert x \rVert}=\lVert A \rVert+\lVert B \rVert$.

An operator norm is a matrix norm.

<div style="page-break-after: always;"></div>

![[Pasted image 20230910190721.png]]
(parts 1, 2, 4, 5, 6, 8, 10)
![[Pasted image 20230910190748.png]]
## 1.7.1
The definition of an operator norm
$$\lVert A \rVert=\max_{x≠0} \frac{\lVert Ax \rVert}{\lVert x \rVert}$$
Since this $x$ yields the maximum for the operator norm, any other vector will result in an inequality
$$\lVert A \rVert \ge \frac{\lVert Ax \rVert}{\lVert x \rVert} \quad\forall\quad x≠0$$
$$\lVert Ax \rVert \le \lVert A \rVert \lVert x \rVert,$$
which also holds for $x=0$, because then both LHS and RHS are zero.

For the Frobenius norm and the vector 2-norm, we want to prove
$$\lVert Ax \rVert_{2}\le \lVert A \rVert_{F}\lVert x \rVert_{2}.$$
Writing out the vector 2-norm,
$$\begin{align*}
\lVert Ax \rVert_{2}&=  \sqrt{\sum_{i=1}^{n}\left\lvert \sum_{j=1}^{n}a_{ij}x_{j} \right\rvert^{2}}\\
&\le \sqrt{\sum_{i=1}^{n}\sum_{j=1}^{n}\lvert a_{ij} \rvert^{2}\lvert x_{j} \rvert^{2}}\\
&= \sqrt{\sum_{i=1}^{n}\sum_{j=1}^{n}\lvert a_{ij} \rvert^{2}}\cdot \sqrt{\sum_{j=1 }^{n}\lvert x_{j} \rvert^{2}}\\
	\lVert Ax \rVert_{2}&\le \lVert A \rVert_{F}\lVert x \rVert_{2}. 
\end{align*}$$

## 1.7.2
For any operator norm:
$$\begin{align*}
\lVert AB \rVert&= \max_{\lVert x \rVert=1}\lVert ABx \rVert\\
&= \max_{\lVert x \rVert=1}\lVert A(Bx) \rVert\\
&\le \max_{\lVert x=1 \rVert} \lVert A \rVert \lVert Bx \rVert\\
\lVert AB \rVert	&\le \lVert A \rVert \lVert B \rVert ,
\end{align*}$$
Where I have used the result from the previous problem.

Now for Frobenius norm:
$$\begin{align*}
\lVert AB \rVert_{F}&= \sqrt{\sum_{i=1}^{n}\sum_{j=1}^{n} \left\lvert \sum_{k=1}^{n}a_{ik}b_{kj} \right\rvert^{2}}\\
&\le \sqrt{\sum_{i=1}^{n}\sum_{j=1}^{n}\sum_{k=1}^{n}\lvert a_{ik} \rvert^{2}\lvert b_{kj} \rvert^{2}}  \\
&\le \sqrt{\sum_{i=1}^{n}\sum_{k=1}^{n}\lvert a_{ik} \rvert^{2}} \cdot \sqrt{\sum_{j=1}^{n}\sum_{k=1}^{n}\lvert b_{kj} \rvert^{2}}\\
	\lVert AB \rVert_{F} &\le \lVert A \rVert_{F}\lVert B \rVert_{F}.
\end{align*}$$

## 1.7.4
Using the trace formula for the Frobenius norm
$$\begin{align*}
\lVert QAZ \rVert_{F} &= \sqrt{\text{trace}(QAZ(QAZ)^{T})}\\
&= \sqrt{\text{trace}(QAA^{T}Q^{T})}\\
&\stackrel{\text{tr}(AB)=\text{tr}(BA)}{= } \sqrt{\text{trace}(A^{T}Q^{T}QA)}\\
&= \text{trace}(A^{T} A)\\
	&= \lVert A \rVert_{F}
\end{align*}$$

Now for the 2-norm,
$$\begin{align*}
\lVert QAZ \rVert_{2}&=  \max_{\lVert x \rVert_{2}=1} \lVert QAZx \rVert_{2}\\
&=\max_{\lVert x \rVert_{2}=1} \sqrt{\left\langle QAZx \text{ , } QAZx \right\rangle}\\
&= \max_{\lVert x \rVert_{2}=1}\sqrt{x^{T}Z^{T}A^{T}Q^{T}QAZx}\\
&= \max_{\lVert x \rVert_{2}=1} \sqrt{x^{T}Z^{T}A^{T}AZx}
\end{align*}$$
We denote $y=Zx$, and wish to know $\lVert y \rVert_{2}$ when given $\lVert x \rVert_{2}$.
$$\lVert y \rVert_{2}=\lVert Zx \rVert_{2}=\sqrt{\left\langle Zx \text{ , } Zx \right\rangle}=\sqrt{\left\langle x \text{ , } x \right\rangle}=\lVert x \rVert_{2}.$$
We can change the variable to $y$ such that we end up with
$$\begin{align*}
\lVert QAZ \rVert_{2}&= \max_{\lVert y \rVert_{2}=1} \sqrt{y^{T}A^{T}Ay}\\
\lVert QAZ \rVert_{2}&= \max_{\lVert y \rVert_{2}=1}\lVert Ay \rVert_{2}		\\
\lVert QAZ \rVert_{2}&= \lVert A \rVert_{2}.
\end{align*}$$


## 1.7.5
Using the equivalent definition of a matrix norm:
$$\lVert A \rVert_{\infty}= \max_{\lVert x \rVert_{\infty}=1}\lVert Ax \rVert_{\infty}=\max_{\lVert x \rVert_{\infty}=1} \left[\max_{i} \left\lvert\sum_{j=1}^{n}  a_{ij}x_{j} \right\rvert \right].$$
With the restriction that $\lVert x \rVert_{\infty}=1$, the sum is maximised when $x_{j}=\pm 1$, where the sign is decided by the sign of $a_{ij}$. Thus, every entry in the sum will be positive (or negative), so we can move the absolute value inside. The norm becomes
$$\lVert A \rVert_{\infty}=\max_{i}\sum_{j=1}^{n} \lvert a_{ij} \rvert,$$
which is what we wanted to show.

## 1.7.6

Our strategy will be to show that the 1-norm is bounded both above and below by the maximum absolute column sum.
Let $a_{j}$ denote the $j$-th column of $A$.
$$\lVert A \rVert_{1}=\max_{\lVert x \rVert_{1}=1}\lVert Ax \rVert_{1}=\max_{\lVert x \rVert_{1}=1}\left\lVert \sum_{j=1}^{n}a_{j}x_{j} \right\rVert_{1}\le \max_{\lVert x \rVert_{1}=1} \sum_{j=1}^{n}\lvert x_{j} \rvert \lVert a_{j} \rVert_{1}$$
$$\le \max_{k}\lVert a_{k} \rVert_{1} \cdot \underbrace{\max_{\lVert x \rVert_{1}=1}\sum_{j=1}^{n}\lvert x_{j} \rvert}_{=1}$$
$$=\max_{k} \lVert a_{k} \rVert_{1}$$
So far, we have shown that the 1-norm is bounded above by the maximum absolute column sum. Let's show that this is also a lower bound. Denoting the $k$-th basis vector as $e_{k}$,
$$\max_{k} \lVert a_{k} \rVert_{1}=\max_{k}\lVert Ae_{k} \rVert_{1}\le \max_{k}\lVert A \rVert_{1}\lVert e_{k} \rVert_{1}=\lVert A \rVert_{1}.$$
Combining both of these inequalities, we end up with the equality
$$\lVert A \rVert_{1}=\max_{k} \lVert a_{k} \rVert_{1}=\max_{k}  \sum_{i=1}^{n} \left\lvert a_{ik} \right\rvert.$$
Since the columns of $A^{T}$ are the rows of $A$, and we have corresponded the 1- and $\infty$-norm to the maximum column/row sum, it follows that
$$\lVert A \rVert_{1}=\lVert A^{T} \rVert_{\infty}.$$

## 1.7.8
Hint: if $X,Y \in \mathbb{R}^{n \times n} \quad\implies\quad XY \text{ and } YX$ have the same eigenvalues.
I will assume that the matrix is complex and that it is supposed to say $\lVert A \rVert_{2}=\lVert A^{*} \rVert_{2}$. I also assume that $A \in \mathbb{R}^{n \times n}$.
$$\lVert A \rVert_{2}= \sqrt{\lambda _{\text{max}}(A^{*}A)}, \qquad \lVert A^{*}\rVert_{2}= \sqrt{\lambda _{\text{max}}((A^{*})^{*}A^{*})}=\sqrt{\lambda _{\text{max}}(AA^{*})}.$$
As per the hint, $A^{*}A$ and $AA^{*}$ have the same eigenvalues, and therefore
$$\lVert A \rVert_{2}=\lVert A^{*} \rVert_{2}.$$

## 1.7.10
Using Lemma 1.5,
$$\lVert Ax \rVert_{2}\le  \lVert Ax \rVert_{1} \le \lVert A \rVert_{1}\lVert x \rVert_{1} \le \lVert A \rVert_{1} \sqrt{n} \lVert x \rVert_{2}$$
$$\frac{\lVert Ax \rVert_{2}}{\lVert x \rVert_{2}} \le \sqrt{n} \lVert A \rVert_{1} \quad\implies\quad n^{-\frac{1}{2}}\lVert A \rVert_{2} \le \lVert A_{1} \rVert$$

For the other inequality 
$$\lVert Ax \rVert_{1}\le \sqrt{n}\lVert Ax \rVert_{2} \le \sqrt{n} \lVert A \rVert_{2}\lVert x \rVert_{2}$$
$$\lVert Ax \rVert_{1}\le \sqrt{n}\lVert A \rVert_{2}\lVert x \rVert_{1}$$
$$\lVert A \rVert_{1}\le \sqrt{n} \lVert A \rVert_{2}$$

Combining both inequalities gives
$$ n^{- \frac{1}{2}}\lVert A \rVert_{2}\le \lVert A \rVert_{1} \le n^{\frac{1}{2}}\lVert A \rVert_{2}.$$

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

<div style="page-break-after: always;"></div>

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
