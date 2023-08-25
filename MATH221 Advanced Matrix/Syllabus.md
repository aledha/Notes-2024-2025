4 "axes" of design space of linear algebra algorithms
1. **Math problem we want to solve**
	solve $Ax=b$
	least squares  $\underset{x}{\text{argmin }}\lVert Ax-b \rVert_{2}$ 
	eigenproblems $Ax=\lambda x$
2. **Structure of $A$**
	dense, 
	symmetric, 
	positive definite, 
	sparse, 
	"structured" (example constant diagonals)
3. **Desired accuracy**
	guaranteed correct (too expensive, will not cover)
	"guaranteed correct" except for "rare cases"
		eg: iterative refinement for $Ax=b$, using mixed precision
	"backward stable"
		exact answer for a slightly wrong problem
		Want $y=f(x)$
		Get $alg(x)=f(x+\delta )$ 
		where $\delta << x$ small compared to $x$.
		$\delta$ should be proportional to error in arithmetic
		"machine epsilon"
	residual as small desired
		$\epsilon = \lVert Ax-b \rVert_{2}$
		good when problem is too big for a direct, backwards stable method
	"probably okay" (randomised algorithms)
		replace large problem with a small approx by random projection or random sampling
		then solve small problem with deterministic algorithm:
			some iterative and can control error
			some not
	error bounds
4. **as fast as possible on your target computer**
	laptop (with GPU)
	parallell computer
	cloud, cellphone...


For one problem, choose from 1,2,3,4
answer could be
	"type A/b" 
	"project available to implement a proposed algorithm"
	"open problem"

We will choose a subset of 1,2,3,4