**Hölder continuous near $x$**: $\lvert f(x+t)-f(x) \rvert\le C \lvert t \rvert^\alpha$ for $\alpha >0$ and $C$ is a constant.

### 1.3 Fourier series of continuous functions
```ad-Theorem
title: Theorem 1.5.
There exists a continous function on $\Pi$ whose Fourier series diverge at 0.

```

```ad-Definition
title: Lemma 1.6: Uniform boundedness principle
Let $X,Y$ be Banach spaces, and let $\{T_{a}\}_{a \in A}$ be a familily of bounded linear operators $T_{a}: X\to Y$.
If $\sup_\limits{a \in A} \lVert T_{a} \rVert_{X\to Y}=\infty$, then there exists $x \in X \qquad\text{s.t.}\quad \sup_\limits{a \in A}\lVert T_{a}x \rVert_{Y}\to \infty$.

```

### Proof of 1.5
Let $X=C(\Pi )\text{, }\quad Y = \mathbb{C}\text{, }\quad \lVert \cdot  \rVert_{X}= \lVert \cdot  \rVert_\infty$.
$T_{N}:X\to Y, \quad f\to S_{N}f(0)=\int_\Pi f(t)D_{N}(t) \text{ d}t$.
Note that $\lVert T_{N} \rVert_{X\to Y}\stackrel{exercise}{=}L_{N}:= \lVert D_{N} \rVert_{L^1}(\Pi )$.
(Hint to exercise: use test function that has the same sign as D_N)

Also, we have 

```ad-Definition
title: Lemma 1.7
$L_{N}= \frac{4}{\pi ^{2}}\text{log } N+\mathcal{O}(1)$
```
Proof:
Taking advantage of the periodicity and collecting small errors in $\mathcal{O}(1)$:
$$\begin{align*}
L_{N}&= 2\int_{0}^{\frac{1}{2}}\left\lVert \frac{\text{ sin}((2N+1)\pi t)}{\pi t} \right\rVert \text{ d}t + \mathcal{O}(1)\\
	&= \frac{2}{\pi. }\int_{0}^{N+ \frac{1}{2}}\left\lvert \frac{\text{ sin}\pi t}{t} \right\rvert \text{ d}t + \mathcal{O}(1)\\
		&= \frac{2}{\pi. }\sum\limits_{k=0}^{N-1}\int_{k}^{k+1}\left\lvert \frac{\text{ sin}\pi t}{t} \right\rvert \text{ d}t + \mathcal{O}(1)\\
&= \frac{2}{\pi. }\sum\limits_{k=0}^{N-1}\int_{k}^{k+1}\frac{\lvert \text{ sin}\pi t \rvert}{k+1} \text{ d}t + \mathcal{O}(1) \\
&= \frac{2}{\pi. }\left(\sum\limits_{k=0}^{N-1} \frac{1}{k+1}\right)\int_{0}^{1}\lvert \text{ sin}\pi t \rvert \text{ d}t + \mathcal{O}(1)\\
	&= \frac{4}{\pi ^{2}}\log N+ \mathcal{O}(1) \qquad \square
\end{align*}$$
Back to proving 1.5:
Since $\log N\to \infty$ as $N \to \infty$, $\exists f \in X \qquad\text{s.t.}\quad \lvert T_{N}f \rvert=\lvert S_{N}f(0) \rvert$ is unbounded $\square$.


## §4 Convergence in norm $L_{P}$
Let $1\le p < \infty$  (not including $L_{\infty}$)

```ad-question
title: Question 1
Dies $\lim_\limits{N \to \infty} \lVert S_{N}f-f \rVert_{p}=0$ hold for each $f \in L^{P}(\Pi)$?

```
```ad-question
title: Question 2
Does $\lim_\limits{N \to \infty}S_{N}=f$ a.e. hold for each $f \in L^{p}(\Pi)$?

```
Q2 hard, cant cover in this course
For Q1, we have
```ad-Definition
title: Lemma 1.8
$S_{N}f$ converges to $f$ in $L^{p}(1\le p<\infty) \quad\Leftrightarrow\quad \exists C_{p} \qquad\text{s.t.}\quad \lVert S_{N}f \rVert_{P}\le C_{p}\lVert f \rVert \quad\forall\quad f \in L^{p}(\Pi )$.     (*)
```
Proof:
Necessity by lemma 1.6
For sufficiency, use the fact that trigonometric polynomials are dense in $L^{p}$.
If $(*)$ is true, $\quad\forall\quad  f \in L^{p}\text{, }\quad\forall\quad \epsilon >0\quad\implies\quad \exists$ a trigonometric polynomial such that $\lVert f-g \rVert_{p}<  \frac{\epsilon }{C_{p}+1}$. This constant comes from:
Then for all large $N$, $S_{N}g=g$. For these $N,$
$$\begin{align*}
\lVert S_{N}f-f \rVert_{p}&\le  \lVert S_{N}(f-g) \rVert_{p}+ \lVert S_{N}g-g \rVert_{p}+ \lVert g-f \rVert_{p}\\
	&\le (C_{p}+1)\lVert f-g \rVert_{p}<\epsilon 
\end{align*}$$
We'll see that $*$ holdes for $1<p<\infty$, but fails for $p=1$