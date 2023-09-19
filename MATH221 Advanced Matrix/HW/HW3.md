- Question 2.13, parts 1 and 2
- Consider the problem of solving LX = B where B is a given n-by-n matrix, L is a given n-by-n nonsingular lower triangular matrix, and X is an unknown n-by-n matrix.
    
    - Write down the simplest algorithm you can, and count the flops.
    - Analogous to the blocked matrix-multiplication algorithm presented in class, write down a blocked version of this algorithm, and analyze the number of words moved; can you make it move as few words as matrix-multiply (in the Big-Oh sense)?
    - Does it satisfy the same backward error analysis as the simple algorithm (as in Q. 1.11)?
    - Analogous to the recursive matrix-multiplication algorithm presented in class, write down a recursive version of this algorithm, and analyze the number of words moved; can you make it move as few words as matrix-multiply (in the Big-Oh sense)?
    - Does it satisfy the same backward error analysis as the simple algorithm (as in Q. 1.11)?
    - (Extra credit) Show that you can't communicate fewer words to solve LX=B than in matrix-multiply, namely Omega(n^3/sqrt(M)). Hint: Show that any routine for solving LX=B can be used to do matrix-multiplication (of slightly smaller matrices), so the lower bound for matrix-multiplication applies (perhaps with a smaller constant, all hidden in the Big-Omega notation).

![[Pasted image 20230915180413.png]]




![[Pasted image 20230915180432.png]]


# Solve $LX=B$
Where $L \in \mathbb{R}^{n \times n}$ is nonsingular and lower triangular, $B \in \mathbb{R}^{n \times n}$, and $X \in \mathbb{R}^{n \times n}$ is unknown.
- Write down the simplest algorithm you can, and count the flops.

$$\begin{bmatrix}l_{11} & 0  & 0 \\ \vdots & \ddots & 0 \\ l_{n1} & \dots & l_{nn}\end{bmatrix}\begin{bmatrix}x_{11} & \dots &  x_{1n} \\ \vdots &   & \vdots \\ x_{1n} & \dots & x_{nn}\end{bmatrix}=\begin{bmatrix}b_{11} & \dots &  b_{1n} \\ \vdots &   & \vdots \\ b_{1n} & \dots & b_{nn}\end{bmatrix}$$
Forward substitution:
for i=1 to n:
	$x_{i1}= \frac{b_{i1}}{l_{i1}}$
	for j=2 to n:
		$x_{ij}= \frac{b_{ij}- \sum_{k=1}^{i-1}l_{ik}x_{kj} }{l_{ij}}$

Firstly, we have $n$ divisions in the first for-loop. In the second loop
