### Example: Polynomial evaluation and zero finding
Recall the bisection method:
``` python
def bisect(f, x1, x2):
	assert(f(x1) * f(x2) < 0)
	while error < tol:
		mid = (x1 + x2) / 2
		if f(mid) * f(x1) < 0:
			x2 = mid
		else:
			x1 = mid
		error = ...
	return x1, x2
```
Our example case is evaluating $f(x)=(x-2)^{13}$ using Horner's rule.

#### Floating point: How to represent real numbers
A little history:
	Before 1985 most computers did arithmetic differently $\quad\implies\quad$ hard to write portable code. Standard committee formed to create a standard.
	First standard 1985, then 2008, then 2019, forming a committee for 2028.

The standard is to represent numbers with **scientific notation**.
$\text{number}= ddd\dots \text{ d}\cdot radix^{e}$
Where we need to store
* The sign bit
* exponent $e$
* matissa $ddd\dots d$

We will denote $p=$ number of digits in matissa
Both p and number of bits in $e$ are limited to 16, 32, 64, 128

$e4p4$ denotes 4 exponent bits and 4 digits in matissa

For starters, we ignore limits on $e$. So we assume no overflow and no underflow. (too big or small numbers)

**Normalization**: use $3.1 \cdot 10^{0}$ not $0.0031\cdot 10^{3}$
	Unique representation, simpler hardware
	In binary, the leading bit will be 1, so it's a free bit$\quad\implies\quad$ don't store it.

```ad-summary
title: Definition
$\text{rnd}(x)=$ nearest floating point number to $x$. 
When $x$ is right in the middle, we round to the "nearest even", i.e., the last bit is 0.
```
In this way, we round up half the time, round down the other half time on average. Unbiased

```ad-summary
title: Definition: Relative Representation Error (RRE)
$\text{RRE}(x)= \frac{\lvert x- \text{rnd}(x) \rvert}{\lvert \text{rnd}(x) \rvert}$

Subdefinition: Maximum RRE/Machine epsilon $\epsilon$
$\text{Max RRE}=\max_\limits{x≠0}(x)$
```
Max RRE = half distance from 1 to next larger floating point number = $1+(\text{radix})^{1-p}$
MaxRRE $= 0.5 \cdot  \text{radix}^{1-p}=2^{-p}$ in binary

Round off model (no over/underflow)
$$\mu (a  \text{ op } b )=rnd (a \text{ op } b)\tag{*}$$
$$=\text{true result rounded to nearest even}$$
$$=(a \text{ op }b)(1+\delta )\text{, }\qquad \lvert \delta  \rvert\le \epsilon $$
Where op can be +,-,*,/....

$(*)$ is also true for complex arithmetic with larger $\epsilon$.


### Existing IEEE Binary Formats
half(H), single(S) double(D), quad(Q)
The largest exponent is reserved for representing 0, $\infty$, NaN

S: 32 bits = 1 (sign) + 8 (exponent bits) + 23 (mantissa bits)
because of not storing the first 1: p = 1 + 23 = 24 $\quad\implies\quad \epsilon =2^{-24}\sim6 \cdot 10^{-8}$
$-126\le e\le 127 \quad\implies\quad \text{OV = overflow threshold}≈2^{128}≈10^{38}$
$\quad\implies\quad \text{UV = underflow threshold}≈2^{-126}≈10^{-38}$

D: 64=1+11+52 $\quad\implies\quad P=53 \quad\implies\quad \epsilon =2^{-53}\sim10^{-16}$ 
$-1022 \le e\le 1023$
$OV = 2^{1024}=10^{308}\text{, }UN = 2^{-1022}=10^{-308}$


Bfloat16: 16=1+8+7 $\quad\implies\quad \epsilon \sim 10^{-4}$
8 is same as single arithmetic, hardware easier


Let us use for error analysis:
$$\mu (a \text{ op } b)=(a \text{ op } b)(1+\delta )\qquad \lvert \delta  \rvert\le \epsilon  \tag{*}$$
Harners rule for $p(x)=\sum\limits_{i=0}^{d}a_{i}\cdot x^{i}$
	$p=a_\text{ d}$
	for $i=d-1:-1:0$
		$p=p \cdot x + a_{i}$

Label intermediate terms:
$p_\text{ d}=a_\text{ d}$
for ...
	$p_{i}=p_{i+1}x$

#copy lecture notes (30/8)