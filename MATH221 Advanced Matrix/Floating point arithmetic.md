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
