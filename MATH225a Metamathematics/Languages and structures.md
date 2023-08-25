```ad-abstract
title: Definition
collapse: open
A **language** $L$ consists of symbols $\{\mathcal{F}, \mathcal{R}, \mathcal{C}\}$, where 
* $\mathcal{F}$ denotes function symbols
* $\mathcal{R}$ denotes relation symbols
* $\mathcal{C}$ denotes constant symbols

We also define the arity function $n:\mathcal{F}\cup \mathcal{R}\to \mathbb{N}$, where the output denotes how many inputs a relation or function takes in.
```

```ad-abstract
title: Definition
An $\mathcal{L}$-structure $\mathcal{M}$ consists of 
* a domain $M$
* For each $c \in \mathcal{C}$, we associate $c^{\mathcal{M}}\in M$
* For each $f \in \mathcal{F}$, we associate $f^{\mathcal{M}}: M^{n(f)}\to M$
* For each $r \in \mathcal{R}$, we associate $r^{\mathcal{M}} \subseteq  M^{n(f)}$
```

```ad-note
title: Notation
When we write a symbol supscripted with a structure, i.e., $c^{\mathcal{M}}$, we mean $c$ interpreted in the structure $\mathcal{M}$.

```

```ad-abstract
title: Definition
An $\mathcal{L}$-embedding from $\mathcal{M}$ to $\mathcal{n}$ is a one-to-one map $\eta : M \to N$ such that
* For all $c \in \mathcal{C}, \qquad \eta (c^{\mathcal{M}})=c^\mathcal{N}$
* For all $f \in \mathcal{F} \text{ and } \overline{m} \in M^{n(f)}, \qquad \eta (f^{\mathcal{M}}(\overline{m}))=f ^{\mathcal{N}}(\eta (m_{0}),\dots,\eta (m_{n}))$
* For all $r \in \mathcal{R} \text{ and } \overline{m}\in M^{n(r)}, \qquad \overline{m}\in r^{\mathcal{M}}\quad\Leftrightarrow\quad \eta (\overline{m})\in r^{\mathcal{N}}$
```

```ad-abstract
title: Definition
If 

```
