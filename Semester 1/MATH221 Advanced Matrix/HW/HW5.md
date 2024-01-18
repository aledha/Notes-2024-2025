 Alexander Hatle
```matlab
function [y] = CSR_multiply(val, colindex, rowbegin, n, m, x)
    y = zeros(n, 1);
    for i = 1:n
        for j=rowbegin(i):rowbegin(i+1)-1
            y(i) = y(i) + val(j) * x(colindex(j));
        end
    end
end 

function [y] = CSC_multiply(val, rowindex, colbegin, n, m, x)
    y = zeros(n, 1);
    for i = 1:m
        for j=colbegin(i):colbegin(i+1)-1
            y(rowindex(j)) = y(rowindex(j)) + val(j) * x(i);
        end
    end
end
```

I tested this with 4 matrices of different sizes, including zero rows and columns, and it agreed with matlabs solver. Gradescope does not allow me to attach code files, so I've pasted the whole code in the bottom of this document.

<div style="page-break-after: always;"></div>

![[Pasted image 20231001155810.png|800]]
Hint for Part 1: To show A is nonsingular, we need to show that if the column vector x is nonzero, so is x'\*A. Suppose x(i) is the largest component of x in absolute value. What can you say about the i-th component of x'\*A?
$$A \text{ nonsingular}\quad\Leftrightarrow\quad x^{T}A≠0 \quad\text{for }x≠0$$
Suppose that $\lvert x_{i} \rvert \ge \lvert x_{j} \rvert$ for $j≠1,$
$$\begin{align*}
(x^{T}A)_{i}&= \sum_{k=1}^{n}x_{k}a_{ki}\\
&= x_{i}a_{ii} + \sum_{k=1,k≠i}^{n}x_{k}a_{ki}
\end{align*}$$
Since $A$ is diagonally dominant and $x_{i}$ is absolutely larger than all other indices, the first term is always larger than the sum in absolute value, and therefore
$$(x^{T}A)_{i}≠0.$$
For any nonzero $x$, there must exist a nonzero largest component $x_{i}$, and then $i$th component of $x^{T}A$ is nonzero. Then $A$ is nonsingular.
![[Pasted image 20231001155835.png|800]]
Before the first step, the matrix can be written as
$$A=\begin{bmatrix}a_{11} & v^{T} \\ w & A_{22}\end{bmatrix}.$$
After one step, the Schur complement is
$$S= A_{22}- \frac{1}{a_{11}}wv^{T}$$
The diagonal and the sum of the off diagonals can be written as
$$\begin{align*}
S_{ii}&= a_{ii}- \frac{1}{a_{11}}a_{i1}a_{1i}\\
		\sum_{j=2, j≠i}^{n}\lvert S_{ji} \rvert&= \sum_{j=2,j≠i}^{n}\left\lvert a_{ji}- \frac{1}{a_{11}}a_{j1}a_{1i} \right\rvert\\
&\le \sum_{j=2, j≠i}^{n} \lvert a_{ji} \rvert + \sum_{j=2, j≠i}^{n} \left\lvert \frac{1}{a_{11}}a_{j1}a_{1i} \right\rvert\\
&< \lvert a_{ii} \rvert-\lvert a_{1i} \rvert + \left\lvert \frac{a_{1i}}{a_{11}} \right\rvert\sum_{j=2, j≠i}^{n} \left\lvert  a_{j1}\right\rvert\\
&< \lvert a_{ii} \rvert-\lvert a_{1i} \rvert+\left\lvert \frac{a_{1i}}{a_{11}} \right\rvert(\lvert a_{11} \rvert-\lvert a_{i1} \rvert)\\
&\le \lvert a_{ii} \rvert-\lvert a_{1i} \rvert+ \lvert a_{1i} \rvert- \left\lvert \frac{1}{a_{11}}a_{1i}a_{i1} \right\rvert\\
&\le \left\lvert a_{ii}- \frac{1}{a_{11}}a_{1i}a_{i1} \right\rvert\\
&\le \lvert S_{ii} \rvert,
\end{align*}$$
which implies that the Schur complement is diagonally dominant.

Since for each step, the diagonal element is chosen, and each trailing matrix is also diagonally dominant, Gaussian elimination with partial pivoting does not swap any rows.


<div style="page-break-after: always;"></div>

```matlab
A1 = [0 3 0 0;
      2 8 0 0;
      0 0 0 0];
x1 = [1; 2; 3; 4];

A2 = [1 2 3;
      0 0 0;
      4 5 6];
x2 = [1; 2; 3];

A3 = [0 1; 
      0 0;
      -2 0;
      0 0];
x3 = [1; 2];

A4 = [0 0 1 8;
      5 0 0 0;
      0 0 0 0;
      9 0 0 2];
x4 = [1; 2; 3; 4];

As = {A1 A2 A3 A4};
xs = {x1 x2 x3 x4};

for i=1:4
    testSparseCSR(As{i}, xs{i})
    testSparseCSC(As{i}, xs{i})
end 

function [y] = CSR_multiply(val, colindex, rowbegin, n, m, x)
    y = zeros(n, 1);
    for i = 1:n
        for j=rowbegin(i):rowbegin(i+1)-1
            y(i) = y(i) + val(j) * x(colindex(j));
        end
    end
end 

function [y] = CSC_multiply(val, rowindex, colbegin, n, m, x)
    y = zeros(n, 1);
    for i = 1:m
        for j=colbegin(i):colbegin(i+1)-1
            y(rowindex(j)) = y(rowindex(j)) + val(j) * x(i);
        end
    end
end

function [] = testSparseCSR(A, x)
    csr = matrixToCSR(A);
    val = csr.val;
    colindex = csr.colindex;
    rowbegin = csr.rowbegin;
    n = size(A,1);
    m = size(A, 2);

    y_csr = CSR_multiply(val, colindex, rowbegin, n, m, x);
    y_matlab = A*x;
    if y_matlab == y_csr
        disp("Solver agrees with matlab")
    else
        disp("Solver does not agree with matlab")
        disp(y_csr)
        disp(y_matlab)
    end
end


function csr_matrix = matrixToCSR(matrix)
    [m, n] = size(matrix);
    
    % Initialize CSR data structures
    val = [];
    colindex = [];
    rowbegin = [1];
    nnz_count = 0;
    
    for i = 1:m
        for j = 1:n
            if matrix(i, j) ~= 0
                val = [val, matrix(i, j)];
                colindex = [colindex, j];
                nnz_count = nnz_count + 1;
            end
        end
        rowbegin = [rowbegin, nnz_count + 1];
    end

    csr_matrix = struct('val', val, 'colindex', colindex, 'rowbegin', rowbegin);
end

function [] = testSparseCSC(A, x)
    csr = matrixToCSC(A);
    val = csr.val;
    rowindex = csr.rowindex;
    colbegin = csr.colbegin;
    n = size(A,1);
    m = size(A, 2);

    y_csc = CSC_multiply(val, rowindex, colbegin, n, m, x);
    y_matlab = A*x;
    if y_matlab == y_csc
        disp("Solver agrees with matlab")
    else
        disp("Solver does not agree with matlab")
        disp(y_csc)
        disp(y_matlab)
    end
end

function csc_matrix = matrixToCSC(matrix)
    [m, n] = size(matrix);
    
    val = [];
    rowindex = [];
    colbegin = [1];
    nnz_count = 0;
    
    for j = 1:n
        for i = 1:m
            if matrix(i, j) ~= 0
                val = [val, matrix(i, j)];
                rowindex = [rowindex, i];
                nnz_count = nnz_count + 1;
            end
        end
        colbegin = [colbegin, nnz_count + 1];
    end

    csc_matrix = struct('val', val, 'rowindex', rowindex, 'colbegin', colbegin);
end
```