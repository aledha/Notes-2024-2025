**Given:**
- Pipe diameter: \\(d = 1\,200 \text{ mm} = 1.2 \text{ m}\\).
- Flow rate: \\(Q = 126 \mathrm{\,l/s} = 0.126 \mathrm{\,m^3/s}\\).
- Elevation of water surface in tank: \\(z_1 = 540 \text{ m}\\).
- Elevation at pressure meter location: \\(z_2 = 434 \text{ m}\\).
- Pressure at pressure meter location: \\(P_2 = 586 \text{ kPa} = 586\,000 \text{ N/m²}\\).
- Distance between tank and meter location: \\(L = 2 \text{ km} = 2000 \text{ m}\\).

**To find:** Rate of head loss \\(h_f\\)) in the pipe

**Step 1: Calculate the velocity in the pipe:**
We can rearrange the formula for the flow rate \\(Q\\) to solve for the velocity \\(v\\):
\\[
\begin{aligned}
Q&= Av\\
v&= \frac{Q}{A}\\
&= \frac{Q}{\frac{\pi }{4}d^2}\\
&= \frac{0.126 \mathrm{\, m^3/s}}{\frac{\pi}{4}(1.2 \text{ m})^2}\\
&\approx 0.111 \text{ m/s}.
\end{aligned}
\\]


**Step 2: Calculate the Reynolds number:**

\\[
Re = \frac{\rho   v  d }{\mu}
\\]
If we assume that the water temperature is \\(20\degree\\)C, we can look up the following values:
- Density: \\(\rho = 998.23 \mathrm{\, kg/m^3}\\)
- Viscosity: \\(\mu = 0.01 \mathrm{\, Ns/m^2}\\).

\\[
\begin{aligned}
Re &= \frac{998.23 \mathrm{\, kg/m^3} \cdot  0.111 \text{ m/s}\cdot 1.2 \text{ m}}{0.01 \mathrm{\,Ns/m^2}}\\
&= 13\,296.42 
\end{aligned}
\\]

**Step 3: Determine the friction factor:**

Since \\(Re\\) is turbulent (\\(>4000\\)), we'll use the Colebrook equation to solve for the friction factor \\(f\\):

\\[
\frac{1}{\sqrt{f}}=-2\log_{10}\left[\frac{2.51}{Re \sqrt{f}}+\frac{\epsilon }{3.7d} \right]
\\]

Assume pipe roughness \\(\epsilon = 0.0015 \text{ m}\\) (for a new steel pipe).

This is a complicated implicit equation with \\(f\\) on both sides. Using numerical iterators, one can find \\(f \approx 0.0308\\).

**Step 4: Calculate the head loss using Darcy-Weisbach equation:**
The head loss, \\(h_f\\), can be calculated by inserting our found values in the Darcy-Weisbach equation:
\\[
\begin{aligned}
h_f &= f \frac{Lv^2}{2gd}\\
&= 0.0308 \cdot \frac{2000 \text{ m} \cdot (0.111 \text{ m/s})^2}{2 \cdot 9.81 \mathrm{\, m/s^2} \cdot 1.2 \text{ m}}\\
&= 0.0322 \text{ m}.
\end{aligned}
\\]

**Step 5: Calculate the total head loss from tank to meter:**

Total head loss (\\(h_t\\)) is the sum of the elevation head loss, the pressure head loss, and the friction head loss.

\\[
\begin{aligned}
h_t &= (z_1-z_2)+ \frac{P_2}{\rho g}+h_f\\
&= (540 \text{ m}-434 \text{ m})+ \frac{586\,000 \text{ N/m²}}{998.23 \mathrm{\, kg/m^3}\cdot 9.81 \mathrm{\, m/s^2}}+0.0322 \text{ m}\\
&\approx 165.87 \text{ m}.
\end{aligned}
\\]


Therefore, the rate of head loss in the pipe is \\(165.87\\) meters of water column.