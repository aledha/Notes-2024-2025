Alexander Hatle
![[Pasted image 20230915180413.png]]



![[Pasted image 20230915180432.png]]
From the list of errata:
	Page 95, question 2.13, parts 2 and 3: The intent is to suppose that you have already done Gaussian elimination on A to get its L and U factors, so that solving Ax=b is fast (costs just O(n^2)), and then to exploit this to solve By=c in O(n^2), rather than O(n^3), which is what Gaussian elimination on B would cost. (Matt Podolsky)



# Solve $LX=B$
Where $L \in \mathbb{R}^{n \times n}$ is nonsingular and lower triangular, $B \in \mathbb{R}^{n \times n}$, and $X \in \mathbb{R}^{n \times n}$ is unknown.
```ad-question
Write down the simplest algorithm you can, and count the flops.

```

This is my idea:
for $j=1$ to $n$
	$x_{1j}= \frac{b_{1j}}{l_{11}}$
	for $i=2$ to $n$:
		$x_{ij}= \frac{b_{ij}- \sum_{k=1}^{i-1}l_{ik}x_{kj} }{l_{ii}}$

In the sum we have $i-1$ multiplications and $i-2$ additions. After the sum we have one additional addition and a division. So the line in the second for loop as $i-1+i-2+1+1=2i-1$ flops. The second for-loop has therefore $\sum_{i=2}^{n}2i-1=n^{2}-1$ flops. 

Accounting for the first for-loop and the division, he total number of flops is $$n(1+n^{2}-1)=n^{3}.$$

```ad-question
Analogous to the blocked matrix-multiplication algorithm presented in class, write down a blocked version of this algorithm, and analyze the number of words moved; can you make it move as few words as matrix-multiply (in the Big-Oh sense)?

```
As the blocked matrix-multiply algorithm, divide L, X and B into $b \times b$ sized blocks.
```matlab
for j=1:n/b do
	for i=1:n/b do
		initialize S as a b x b zero matrix
		for k=1:i-1 do
			Read X[k,j] into cache
			Read L[i, k] into cache 
			S = S + L[i,k] * X[k,j]
		end for
		Read L[i, i] into cache
		Read B[i,j] into cache
		Solve L[i, i] * X[i,j] = B[i,j] - S
		Write X[i,j] into main memory
	end for
end for
```

Reading X and L: $$\frac{n}{b} \cdot \sum_{i=1}^{{\frac{n}{b}}-1}ib^{2}=nb \cdot \frac{\left(\frac{n}{b}-1\right) \frac{n}{b}}{2}=\frac{n^{2}( \frac{n}{b}-1)}{2}=\frac{n^{3}}{2b}- \frac{n^{2}}{2}$$ Reading $L[i,i]$ and B: $\left(\frac{n}{b} \right)^{2} \cdot b^{2}=n^{2}$ words moved.
Writing X: $\left(\frac{n}{b}\right)^{2} \cdot b^{2}=n^{2}$ words moved

Total words moved is
$$2 \cdot \left(\frac{n^{3}}{2b}- \frac{n^{2}}{2} \right)+3n^{2}= \frac{n^{3}}{b}+2n^{2}.$$
We can minimize this by maximising $b$. Calling the cache size for $M$, we cannot set $b$ higher than $2b^{2}=M \quad\implies\quad b=\sqrt{\frac{M}{2}}$. Then, in the Big-Oh sense, this algorithm moves
$$\mathcal{O}\left(\frac{n^{3}}{\sqrt{M}}\right)$$
words, which is the same as matrix multiply.

```ad-question
Does it satisfy the same backward error analysis as the simple algorithm (as in Q. 1.11)?

```


```ad-question
Analogous to the recursive matrix-multiplication algorithm presented in class, write down a recursive version of this algorithm, and analyze the number of words moved; can you make it move as few words as matrix-multiply (in the Big-Oh sense)?

```


```ad-question
Does it satisfy the same backward error analysis as the simple algorithm (as in Q. 1.11)?

```


```ad-question
(Extra credit) Show that you can't communicate fewer words to solve LX=B than in matrix-multiply, namely Omega(n^3/sqrt(M)). Hint: Show that any routine for solving LX=B can be used to do matrix-multiplication (of slightly smaller matrices), so the lower bound for matrix-multiplication applies (perhaps with a smaller constant, all hidden in the Big-Omega notation).

```
