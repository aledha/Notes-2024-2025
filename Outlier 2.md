Step 3 is labeled as Correct but it is Incorrect. Since $$ x^6+a_1x^5+\cdots+a_6=(x+x_1)(x+x_2)\cdots (x+x_6)\, $$ it follows that $$ a_1=x_1+x_2+x_3+x_4+x_5+x_6\, , $$ but $$ s_{1,6}=-x_1-x_2-x_3-x_4-x_5-x_6\, , $$ so $a_1\neq s_{1,6}$. Step 7 is labeled as Correct but it is Incorrect. The recursive equation of $s_{k,i}$ is $s_{k,i} = -s_{k-1,i-1}x_i + s_{k,i-1}$, not $s_{k,i} = s_{k-1,i-1}x_i + s_{k,i-1}$. Note: The definition of $s_{k,i}$ in GTFA and the model are not the same.


$\sigma (i)=\begin{cases}k\pmod{n}-i & i<k\pmod{n} \\ i & i\ge k\pmod{n}\end{cases}$  and $\tau (i)=\begin{cases}i & i<k\pmod{n} \\ n-(i-k\pmod{n}) & i\ge k\pmod{n}\end{cases}$ 
such that $\sigma (i)+\tau (i)=\begin{cases}k\pmod{n} & i<k\pmod{n} \\ n+k\pmod{n} & i\ge k\pmod{n}\end{cases},$
and $\sigma (i)+\tau (i)\equiv k\pmod{n}$.