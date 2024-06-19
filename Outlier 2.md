Using Vieta's formulas, the sum of the roots of the polynomial $z^4 - (3+2i)z^3 + (5-4i)z^2 - (7+6i)z+ (2-8i) = 0$ is $3+2i$. To find the sum of the squares of the roots, we use the identity $(z_1+z_2+z_3+z_4)^2 = z_1^2+z_2^2+z_3^2+z_4^2 + 2(z_1z_2+z_1z_3+z_1z_4+z_2z_3+z_2z_4+z_3z_4)$. The term $z_1z_2+z_1z_3+z_1z_4+z_2z_3+z_2z_4+z_3z_4$ corresponds to the coefficient of the third-highest degree term, which is $5-4i$. 

Thus, we can calculate the sum of the squares of the roots as follows:
$$\sum_{k=1}^4 z_k^2 = (3+2i)^2 - 2(5-4i) = 9 + 12i + 4i^2 - 10 + 8i = -5 + 20i.$$

Next, we determine the magnitude of the complex number $-5 + 20i$ using the formula $|z| = \sqrt{a^2 + b^2}$ for a complex number $z = a + bi$. Applying this formula, we get:
$$\left| \sum_{k=1}^4 z_k^2 \right| = | -5 + 20i | = \sqrt{(-5)^2 + 20^2} = \sqrt{25 + 400} = \sqrt{425}.$$

Finally, simplifying $\sqrt{425}$ by factoring out the square of the greatest perfect square that divides $425$, we have:
$$\sqrt{425} = \sqrt{25 \cdot 17} = \sqrt{25} \sqrt{17} = 5 \sqrt{17}.$$

Therefore, $\left| \sum_{k=1}^4 z_k^2 \right| = 5 \sqrt{17}$.
___
$$\lvert x_2-x_1 \rvert$$