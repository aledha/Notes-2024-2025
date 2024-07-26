Given:
\\[
3x^2 + 5y^2 = 10,
\\]
where \\(x, y > 0\\).

Step 1: Find an expression for \\(x^2\\):
\\[
x^2=\frac{10-5y^2}{3}.
\\]

Step 2: Insert the expression for \\(x\\) into \\(125x^4y^6\\) and simplify:
\\[
\begin{aligned}
125x^4y^6&= 125\left(\frac{10-5y^2}{3} \right)^2y^6\\
&= \frac{125}{9} \left(10-5y^2 \right)^2y^6\\
&= \frac{125}{9} \left(100-100y^2+25y^4 \right)y^6\\
&= \frac{125\cdot 25}{9}(4-4y^2+y^4)y^6\\
&= \frac{3125}{9}(4y^6 -4y^8+y^{10}).
\end{aligned}
\\]

Step 3: Differentiate with respect to \\(y\\) and simplify:
\\[
\begin{aligned}
\frac{\text{d}}{\text{d}y}\left(\frac{3125}{9}(4y^6 -4y^8+y^{10}) \right)&= \frac{3125}{9} (24y^5-32y^7+10y^9)\\
&= \frac{3125}{9} \cdot2y^5(12-16y^2+5y^4)\\
&= \frac{6250}{9}y^5\cdot (12-16y^2+5y^4).
\end{aligned}
\\]
Step 4: Set this expression equals to zero to find maximum and minimum points:
\\[
\frac{6250}{9}y^5\cdot (12-16y^2+5y^4)=0.
\\]
Since \\(y>0\\), \\(y^5\neq0\\). Therefore, the expression inside the parenthesis must be equal to zero,
\\[
5y^4-16y^2+12=0.
\\]
Notice that this is a quadratic equation in \\(y^2\\), and we can therefore use the quadratic formula:
\\[
\begin{aligned}
y^2 &= \frac{-(-16)\pm \sqrt{(-16)^2-4\cdot 5\cdot 12}}{2 \cdot 5}\\
&= \frac{16 \pm \sqrt{256-240}}{10}\\
&= \frac{16 \pm \sqrt{16}}{10}\\
&= \frac{16 \pm 4}{10}.
\end{aligned}
\\]
This gives us two maximizing or minimizing values for \\(y^2\\), either 
\\[
\begin{aligned}
y^2&= \frac{16+4}{10}\\
&= \frac{20}{10}\\
&= 2,
\end{aligned}
\\]
or
\\[
\begin{aligned}
y^2 &= \frac{16-4}{10}\\
&= \frac{12}{10}\\
&= \frac{6}{5}.
\end{aligned}
\\]

Step 5: Put these values of \\(y^2\\) back into \\(125x^4y^6\\):
\\[
\begin{aligned}
125x^4y^6&= 125\left(\frac{10-5y^2}{3} \right)^2y^6\\
&= 125\left(\frac{10-5y^2}{3} \right)^2(y^2)^3
\end{aligned}
\\]
Starting with \\(y^2=2\\), we get
\\[
\begin{aligned}
125\left(\frac{10-5\cdot 2}{3} \right)^2 (2)^3&= 125\left(\frac{10-10}{3} \right)^2 8\\
&= 0.
\end{aligned}
\\]
With \\(y^2=\frac{6}{5}\\), we get
\\[
\begin{aligned}
125\left(\frac{10-5\cdot \frac{6}{5}}{3} \right)^2 \left(\frac{6}{5} \right)^3&= 125 \left(\frac{4}{3} \right)^2\left(\frac{6}{5} \right)^3\\
&= 125 \cdot \frac{16}{9}\cdot \frac{216}{125}\\
&= 384.
\end{aligned}
\\]
This implies that the maximum value of \\(125x^4y^6\\) is \\(384\\), which is **answer C**.

