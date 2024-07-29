In order to determine the curvature of

\\[
\mathbf r(t) = ⟨t, 3\sin t, 3\cos t⟩,
\\]

we can use the following formula to find the curvature:

\\[
\kappa (t) = \frac{\lvert\langle \mathbf r'(t) \times \mathbf r''(t)\rangle\rvert}{\lvert \mathbf r'(t)\rvert^3}
\\]

Let's break it down step by step:

Step 1: Find \\(\mathbf r'(t)\\) and \\(\mathbf r''(t)\\):

\\[
\begin{aligned}
 \mathbf r'(t) &=  \langle 1, 3\cos t, -3\sin t\rangle,\\
\mathbf r''(t) &=  \langle0, -3\sin t, -3\cos t\rangle.
\end{aligned}
\\]

Step 2: Calculate \\(\mathbf r'(t) \times \mathbf r''(t)\\):

\\[
\begin{aligned}
\mathbf r'(t) \times \mathbf r''(t) &=  \left\lvert \begin{bmatrix}\mathbf i  & \mathbf j  & \mathbf k  \\ 1  & 3\cos t  & -3\sin t  \\ 0  & -3\sin t  & -3\cos t \end{bmatrix}\right\rvert\\
&= \mathbf i [(3\cos t)(-3\cos t)-(-3\sin t)(-3\sin t) ]-\mathbf j[1(-3\cos t)-(-3\sin t)(0) ]+\mathbf k[1(-3\sin t)-3\cos t(0)]\\
&= \mathbf i[-9\cos ^2t-9\sin ^2t]-\mathbf j[-3\cos t]+\mathbf k[-3\sin t]\\
&= -9\mathbf i+3\cos (t)\mathbf j -3 \sin (t)\mathbf k,
\end{aligned}
\\]

where we used the Pythagorean trigonometric identity.

Step 3. Find \\(\lvert \mathbf r'(t) \times \mathbf r''(t)\rvert\\):

\\[
\begin{aligned}
\lvert \mathbf r'(t) \times \mathbf r''(t)\rvert &= \sqrt{(-9)^2+(3\cos t)^2+(-3\sin t)^2}\\
&= \sqrt{81+9\cos ^2t+9\sin ^2t}\\
&= \sqrt{81+9}\\
&= \sqrt{90}\\
&= 3 \sqrt{10}.
\end{aligned}
\\]

Step 4. Find \\(\lvert \mathbf r'(t)\rvert^3\\):

\\[
\begin{aligned}
\lvert \mathbf r'(t)\rvert^3&= \lvert \langle 1,3\cos t,-3\sin t \rangle \rvert^3\\
&= \left(\sqrt{1^2+(3\cos t)^2+(-3\sin t)^2} \right)^3\\
&= \left(\sqrt{1^2+9\cos ^2t+9\sin ^2t} \right)^3\\
&= \left(\sqrt{1+9} \right)^3\\
&= (\sqrt{10})^3\\
&= 10 \sqrt{10.}
\end{aligned}
\\]


Step 5: Substitute values into the curvature formula:

\\[
\begin{aligned}
\kappa (t) &= \frac{\lvert\langle \mathbf r'(t) \times \mathbf r''(t)\rangle\rvert}{\lvert \mathbf r'(t)\rvert^3}\\
&= \frac{3 \sqrt{10}}{10 \sqrt{10}}\\
&= \frac{3}{10}
\end{aligned}
\\]

Therefore, the curvature of the given curve is \\(\kappa (t) = \frac{3}{10}\\).