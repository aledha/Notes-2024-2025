 Alexander Hatle

```ad-question
Question 1, Part 1: Consider an n by m matrix A in Compressed Sparse Row (CSR) data format: if A has nnz nonzero entries then

- val(1:nnz) contains the nonzero entries packed row by row, from left to right in each row
- colindex(1:nnz) contains the column index of each nonzero entry, i.e. val(i) is in column colindex(i) of A
- rowbegin(1:n+1) points to where each row begins: the nonzeros of row j are contained in val( rowbegin(j) : rowbegin(j+1)-1 )

Write, in Matlab, or your preferred language, explicit loops to compute the matrix-vector product y = A\*x, where x and y are (dense) vectors of length m and n. (In other words, don't use any of Matlab's built in function for sparse matrices, though you may use notation like sum(a(i:j).\*b(i:j)) or (a(i:j))'\*b(i:j) for the dot product of parts of two column vectors.) Test it by running it on a few (small) sparse matrices, and comparing to Matlab's built-in routine for y=A\*x. Make sure to test a matrix A with one or more zero rows. (Matlab has a built in sparse-matrix-vector-multiplication routine, that is called when doing A\*x in Matlab on a matrix A that has been declared "sparse." But the point of this question is to understand CSR format, which is very commonly used.)
```


```ad-question
Question 1, Part 2: Now suppose that A is stored in Compressed Sparse Column (CSC) data format; this means storing A^T in CSR. Again write in Matlab explicit loops to compute y = A\*x.

```



- Question 2.19. 

![[Pasted image 20231001155810.png|800]]
Hint for Part 1: To show A is nonsingular, we need to show that if the column vector x is nonzero, so is x'\*A. Suppose x(i) is the largest component of x in absolute value. What can you say about the i-th component of x'\*A?

$$A \text{ nonsingular}\quad\Leftrightarrow\quad x^{T}A≠0 \quad\text{for }x≠0$$
Suppose that $\lvert x_{i} \rvert \ge \lvert x_{j} \rvert$ for $j≠1,$
$$(x^{T}A)_{i}=\sum_{k=1}^{n}x_{k}a_{ki}$$


![[Pasted image 20231001155835.png|800]]

