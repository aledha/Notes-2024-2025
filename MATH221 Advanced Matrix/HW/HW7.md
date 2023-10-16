Questions 3.11, 3.12, 3.13, 3.14

![[Pasted image 20231015233438.png|800]]

![[Pasted image 20231015233458.png|800]]

![[Pasted image 20231015233512.png|800]]

![[Pasted image 20231015233530.png|800]]


In lecture, we discussed how to solve the ridge regression problem using both a version of the normal equations, and the SVD. In practice, one may want to solve the same ridge regression problem for several values of the parameter lambda, to choose the best one. The SVD makes it quite cheap to do this, but requires an expensive SVD first. The normal equations require an additional O(n^3) work for each lambda, for Cholesky, which can be much cheaper than initially forming A^T*A for O(m*n^2) if m >> n, but it is not backward stable. Show how to use QR to solve ridge regression for an additional cost of O(n^3) per lambda. Hint: use Givens rotations to update R.