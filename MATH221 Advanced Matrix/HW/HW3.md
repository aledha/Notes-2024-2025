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
