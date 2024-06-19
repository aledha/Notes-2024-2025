Using Vieta's formulas, the sum of the roots of the polynomial $z^4 - (3+2i)z^3 + (5-4i)z^2 - (7+6i)z+ (2-8i) = 0$ is $3+2i$. To find the sum of the squares of the roots, we use the identity $(z_1+z_2+z_3+z_4)^2 = z_1^2+z_2^2+z_3^2+z_4^2 + 2(z_1z_2+z_1z_3+z_1z_4+z_2z_3+z_2z_4+z_3z_4)$. The term $z_1z_2+z_1z_3+z_1z_4+z_2z_3+z_2z_4+z_3z_4$ corresponds to the coefficient of the third-highest degree term, which is $5-4i$. 

Thus, we can calculate the sum of the squares of the roots as follows:
$$\sum_{k=1}^4 z_k^2 = (3+2i)^2 - 2(5-4i) = 9 + 12i + 4i^2 - 10 + 8i = -5 + 20i.$$

Next, we determine the magnitude of the complex number $-5 + 20i$ using the formula $|z| = \sqrt{a^2 + b^2}$ for a complex number $z = a + bi$. Applying this formula, we get:
$$\left| \sum_{k=1}^4 z_k^2 \right| = | -5 + 20i | = \sqrt{(-5)^2 + 20^2} = \sqrt{25 + 400} = \sqrt{425}.$$

Finally, simplifying $\sqrt{425}$ by factoring out the square of the greatest perfect square that divides $425$, we have:
$$\sqrt{425} = \sqrt{25 \cdot 17} = \sqrt{25} \sqrt{17} = 5 \sqrt{17}.$$

Therefore, $\left| \sum_{k=1}^4 z_k^2 \right| = 5 \sqrt{17}$.
___
In order to solve the sum of the roots of the polynomial $z^4 - (3+2i)z^3 + (5-4i)z^2 - (7+6i)z+ (2-8i) = 0$, we will use Vieta's formulas. Vieta's formulas for a polynomial of the form $az^4+bz^3+cz^2+dz+e$ with roots $z_1,z_2,z_3$ and $z_4$ are 
$$
\begin{aligned}
\sum_{k=1}^{4}z_k &= -\frac{b}{a}\,,\\
z_1z_2+z_1z_3+z_1z_4+z_2z_3+z_2z_4+z_3z_4&= \frac{c}{a}\,,\\
z_1z_2z_3+z_1z_2z_4+z_1z_3z_4+z_2z_3z_4&= -\frac{d}{a}\,,\\
z_1z_2z_3z_4&= \frac{e}{a}
\end{aligned}
$$
Calculating the right hand side of the first two equations gives
$$
\begin{aligned}
\sum_{k=1}^{4}z_k &= - \frac{-(3+2i)}{1}\\
&= 3+2i\\
z_1z_2+z_1z_3+z_1z_4+z_2z_3+z_2z_4+z_3z_4&= \frac{5-4i}{1}\\
&= 5-4i
\end{aligned}
$$

To find the sum of the squares of the roots, $\sum_{k=1}^{4}z_k^2\,$, we use the identity 
$$(z_1+z_2+z_3+z_4)^2 = z_1^2+z_2^2+z_3^2+z_4^2 + 2(z_1z_2+z_1z_3+z_1z_4+z_2z_3+z_2z_4+z_3z_4)\,,$$
which can be written as
$$\sum_{k=1}^{4}z_k ^2=\sum_{k=1}^{4}z_k-2(z_1z_2+z_1z_3+z_1z_4+z_2z_3+z_2z_4+z_3z_4)\,.$$
Plugging in the values we found above, we get
$$
\begin{aligned}
\sum_{k=1}^4 z_k^2 &=  (3+2i)^2 - 2(5-4i) \\
&=  9 + 12i + 4i^2 - 10 + 8i \\
&=  -5 + 20i.
\end{aligned}
$$

Next, we determine the magnitude of the complex number $-5 + 20i$ using the formula $|z| = \sqrt{a^2 + b^2}$ for a complex number $z = a + bi$. Applying this formula, we get:
$$
\begin{aligned}
\left| \sum_{k=1}^4 z_k^2 \right| &=  | -5 + 20i | \\
&=  \sqrt{(-5)^2 + 20^2} \\
&=  \sqrt{25 + 400} \\
&=  \sqrt{425}\\
&= \sqrt{25\cdot 17}\\
&= 5\sqrt{17}
\end{aligned}\,.
$$
Therefore, $\left| \sum_{k=1}^4 z_k^2 \right| = 5 \sqrt{17}$.