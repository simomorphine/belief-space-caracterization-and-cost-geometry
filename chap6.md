# Chapter 6: The Full Cohomology of Debt

---

Chapter 5 introduced the cohomological framework informally. It defined 0-cochains, 1-cochains, the coboundary operator $\delta$, cocycles, coboundaries, and the first cohomology group $H^1$. It proved that on a complete state space, additivity alone implies exactness, and it sketched the extension to strongly connected directed graphs.

This chapter does three things that Chapter 5 did not do:

1. **It develops the full cochain complex** $\delta : C^k \to C^{k+1}$ for all $k \geq 0$, not just the first two levels.
2. **It proves $\delta^2 = 0$ in general**, not only for 0-cochains.
3. **It computes $H^1(G; \mathbb{R})$ for several concrete graphs**, so that the reader can see what the cohomology group actually measures.

The chapter also proves the **discrete Poincaré lemma** in full generality: on a strongly connected directed graph with antisymmetric edge data, $H^1(G; \mathbb{R}) = 0$. This is the graph analogue of the basepoint theorem.

**Remark 6.0 (Relation to Chapter 5).** Chapter 5 established that on a complete pairwise state space, every debt function is exact. This chapter extends that result to more general structures by developing the cohomological machinery in full. The reader who wants only the main result of Part II can read Chapter 4 and skip this chapter. The reader who wants to understand the global structure of debt should read both.

---

## 6.1 The cochain complex

Let $\mathcal{B}$ be a set of states. We build a sequence of vector spaces and linear maps.

**Definition 6.1 (Cochain complex).** For each integer $k \geq 0$, the space of **$k$-cochains** on $\mathcal{B}$ is

$$C^k(\mathcal{B}; \mathbb{R}) := \lbrace \text{functions } \omega : \mathcal{B}^{k+1} \to \mathbb{R} \rbrace,$$

where $\mathcal{B}^{k+1} = \mathcal{B} \times \cdots \times \mathcal{B}$ ($k+1$ factors). A $k$-cochain is thus a real-valued function of $k+1$ variables.

We equip $C^k$ with the structure of a real vector space by pointwise addition and scalar multiplication.

**Example 6.2.** 

- A **0-cochain** is a function $\psi : \mathcal{B} \to \mathbb{R}$. This is a potential.
- A **1-cochain** is a function $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$. This is a debt function.
- A **2-cochain** is a function $\Omega : \mathcal{B} \times \mathcal{B} \times \mathcal{B} \to \mathbb{R}$. This will measure the failure of additivity.

**Remark 6.3.** In a simplicial complex, the space $C^k$ consists of functions on *oriented $k$-simplices*, and the coboundary operator involves sign conventions. Here we work with the full Cartesian product $\mathcal{B}^{k+1}$, which is the cochain complex of the complete simplex on $\mathcal{B}$. This is the simplest setting and is sufficient for our purposes. The extension to sparse graphs requires restricting to the edges that exist, which we treat in §6.6.

---

## 6.2 The coboundary operator

We now define the operator that connects consecutive cochain spaces.

**Definition 6.4 (Coboundary operator).** For each $k \geq 0$, the **coboundary operator** $\delta : C^k \to C^{k+1}$ is defined by

$$(\delta \omega)(b_0, b_1, \ldots, b_{k+1}) := \sum_{j=0}^{k+1} (-1)^j \, \omega(b_0, \ldots, \widehat{b_j}, \ldots, b_{k+1}),$$

where the hat $\widehat{b_j}$ means that $b_j$ is omitted.

The alternating signs $(-1)^j$ are the standard convention of simplicial cohomology. They ensure that $\delta^2 = 0$ (Theorem 6.7 below).

**Example 6.5.** Let us write out the first few cases.

- For $k = 0$: $\delta : C^0 \to C^1$ is given by
$$(\delta\psi)(b_0, b_1) = \psi(b_1) - \psi(b_0).$$

- For $k = 1$: $\delta : C^1 \to C^2$ is given by
$$(\delta D)(b_0, b_1, b_2) = D(b_1, b_2) - D(b_0, b_2) + D(b_0, b_1).$$

- For $k = 2$: $\delta : C^2 \to C^3$ is given by
$$(\delta \Omega)(b_0, b_1, b_2, b_3) = \Omega(b_1, b_2, b_3) - \Omega(b_0, b_2, b_3) + \Omega(b_0, b_1, b_3) - \Omega(b_0, b_1, b_2).$$

The pattern is clear: each term omits one argument, and the signs alternate.

**Remark 6.6.** The formula for $(\delta D)(b_0, b_1, b_2)$ is exactly the failure of additivity:

$$(\delta D)(b_0, b_1, b_2) = 0 \quad \Longleftrightarrow \quad D(b_0, b_2) = D(b_0, b_1) + D(b_1, b_2).$$

This will be the key observation connecting the coboundary operator to the debt axioms.

---

## 6.3 The fundamental identity $\delta^2 = 0$

We now prove the central algebraic identity of the cochain complex.

**Theorem 6.7 ($\delta^2 = 0$).** For every $k \geq 0$, the composition

$$C^k \xrightarrow{\delta} C^{k+1} \xrightarrow{\delta} C^{k+2}$$

is zero. That is, $\delta \circ \delta = 0$ as a map $C^k \to C^{k+2}$.

*Proof.* Let $\omega \in C^k$. We must show that $(\delta(\delta\omega))(b_0, \ldots, b_{k+2}) = 0$ for all $(b_0, \ldots, b_{k+2}) \in \mathcal{B}^{k+3}$.

By Definition 6.4 applied twice,

$$(\delta(\delta\omega))(b_0, \ldots, b_{k+2}) = \sum_{j=0}^{k+2} (-1)^j (\delta\omega)(b_0, \ldots, \widehat{b_j}, \ldots, b_{k+2}).$$

Now expand each $(\delta\omega)(b_0, \ldots, \widehat{b_j}, \ldots, b_{k+2})$ using Definition 6.4:

$$(\delta\omega)(b_0, \ldots, \widehat{b_j}, \ldots, b_{k+2}) = \sum_{\substack{i=0 \\ i \neq j}}^{k+2} (-1)^{i'} \omega(b_0, \ldots, \widehat{b_i}, \ldots, \widehat{b_j}, \ldots, b_{k+2}),$$

where $i' = i$ if $i < j$ and $i' = i - 1$ if $i > j$ (accounting for the fact that $b_j$ has already been omitted).

Substituting and exchanging the order of summation:

$$(\delta(\delta\omega))(b_0, \ldots, b_{k+2}) = \sum_{0 \leq i < j \leq k+2} \left[ (-1)^j (-1)^i + (-1)^i (-1)^{j-1} \right] \omega(\ldots, \widehat{b_i}, \ldots, \widehat{b_j}, \ldots).$$

For each pair $i < j$, the two terms in the bracket have opposite signs:

$$(-1)^j (-1)^i + (-1)^i (-1)^{j-1} = (-1)^{i+j} + (-1)^{i+j-1} = (-1)^{i+j} - (-1)^{i+j} = 0.$$

Therefore, the entire sum vanishes, and $(\delta(\delta\omega))(b_0, \ldots, b_{k+2}) = 0$. $\square$

**Remark 6.8.** The proof is a standard computation. The key idea is that each $(k+2)$-simplex is counted twice, with opposite signs, once for each ordering of the two omitted vertices. The alternating signs are designed precisely to make this cancellation happen.

**Corollary 6.9.** For any 0-cochain $\psi \in C^0$,

$$\delta(\delta\psi) = 0.$$

That is, the 2-cochain $\delta D$ vanishes when $D = \delta\psi$.

*Proof.* Immediate from Theorem 6.7 with $k = 0$. $\square$

**Corollary 6.10.** The image of $\delta : C^k \to C^{k+1}$ is contained in the kernel of $\delta : C^{k+1} \to C^{k+2}$.

*Proof.* If $\omega' = \delta\omega$ for some $\omega \in C^k$, then $\delta\omega' = \delta(\delta\omega) = 0$ by Theorem 6.7. $\square$

---

## 6.4 Cocycles, coboundaries, and cohomology

We can now define the cohomological objects precisely.

**Definition 6.11 (Cocycles).** A $k$-cochain $\omega \in C^k$ is a **$k$-cocycle** if $\delta\omega = 0$. The space of $k$-cocycles is

$$Z^k(\mathcal{B}; \mathbb{R}) := \ker(\delta : C^k \to C^{k+1}).$$

**Definition 6.12 (Coboundaries).** A $k$-cochain $\omega \in C^k$ is a **$k$-coboundary** if $\omega = \delta\eta$ for some $(k-1)$-cochain $\eta \in C^{k-1}$. The space of $k$-coboundaries is

$$B^k(\mathcal{B}; \mathbb{R}) := \mathrm{im}(\delta : C^{k-1} \to C^k).$$

For $k = 0$, we define $B^0 := 0$ (there is no $C^{-1}$).

**Definition 6.13 (Cohomology).** The **$k$-th cohomology group** of $\mathcal{B}$ with coefficients in $\mathbb{R}$ is

$$H^k(\mathcal{B}; \mathbb{R}) := \frac{Z^k(\mathcal{B}; \mathbb{R})}{B^k(\mathcal{B}; \mathbb{R})} = \frac{\ker(\delta : C^k \to C^{k+1})}{\mathrm{im}(\delta : C^{k-1} \to C^k)}.$$

**Remark 6.14.** By Corollary 6.10, $B^k \subseteq Z^k$, so the quotient is well-defined. In general, the inclusion may be strict, and the extent to which it is strict is what $H^k$ measures.

**Remark 6.15.** The cochain complex is

$$0 \to C^0 \xrightarrow{\delta} C^1 \xrightarrow{\delta} C^2 \xrightarrow{\delta} C^3 \to \cdots$$

The condition $\delta^2 = 0$ means that this is a complex (the image of each map is contained in the kernel of the next). The cohomology groups $H^k$ measure the failure of the complex to be exact at each stage.

---

## 6.5 Additivity is the cocycle condition

We now connect the cochain complex to the debt axioms.

**Proposition 6.16.** Let $D \in C^1$ be a 1-cochain. Then $D$ is a 1-cocycle if and only if $D$ satisfies additivity:

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$$

for all $b_i, b_j, b_k \in \mathcal{B}$.

*Proof.* By Definition 6.4, for any triple $(b_0, b_1, b_2)$,

$$(\delta D)(b_0, b_1, b_2) = D(b_1, b_2) - D(b_0, b_2) + D(b_0, b_1).$$

Setting this equal to zero and rearranging,

$$D(b_0, b_2) = D(b_0, b_1) + D(b_1, b_2).$$

Renaming $b_0 = b_i$, $b_1 = b_j$, $b_2 = b_k$, this is exactly additivity. Therefore, $\delta D = 0$ if and only if $D$ is additive. $\square$

**Corollary 6.17.** A 1-cochain $D$ is a 1-cocycle if and only if it satisfies (D1).

**Proposition 6.18.** Let $D \in C^1$ be a 1-coboundary. Then $D$ is antisymmetric:

$$D(b_i, b_j) = -D(b_j, b_i).$$

*Proof.* If $D = \delta\psi$ for some $\psi \in C^0$, then

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i),$$

and

$$D(b_j, b_i) = \psi(b_i) - \psi(b_j) = -(\psi(b_j) - \psi(b_i)) = -D(b_i, b_j).$$

So $D$ is antisymmetric. $\square$

**Remark 6.19.** The converse of Proposition 6.18 is not true in general: an antisymmetric 1-cochain need not be a coboundary. But if $D$ is also a cocycle, then (by the basepoint theorem, applied to the complete space) $D$ is a coboundary. This is the content of the exactness theorem.

**Remark 6.20.** Combining Propositions 6.16 and 6.18: a 1-coboundary is both a cocycle (by $\delta^2 = 0$) and antisymmetric. Conversely, a 1-cocycle that is antisymmetric is a 1-coboundary (on a complete space). The content of the basepoint theorem is that the antisymmetry condition is automatic from additivity, so every 1-cocycle is a 1-coboundary.

---

## 6.6 The cochain complex of a directed graph

For applications to sparse transition structures, we need a version of the cochain complex adapted to a directed graph.

**Definition 6.21 (Cochain complex of a directed graph).** Let $G = (V, E)$ be a directed graph. For each $k \geq 0$, define $C^k(G; \mathbb{R})$ to be the space of functions on *oriented $k$-paths* in $G$:

- $C^0(G; \mathbb{R})$: functions $\psi : V \to \mathbb{R}$.
- $C^1(G; \mathbb{R})$: functions $D : E \to \mathbb{R}$ (with the convention that $D(v, u) = -D(u, v)$ when both edges exist).
- $C^k(G; \mathbb{R})$ for $k \geq 2$: functions on ordered $(k+1)$-tuples of vertices that form a directed path in $G$, with the alternating convention.

The coboundary operator $\delta : C^k(G) \to C^{k+1}(G)$ is defined by the same formula as in Definition 6.4, restricted to the paths that exist in $G$.

**Remark 6.22.** In the graph case, the formula for $\delta D$ on a directed triangle $(b_0, b_1, b_2)$ requires the edges $(b_0, b_1)$, $(b_1, b_2)$, and $(b_0, b_2)$ to exist. If the edge $(b_0, b_2)$ does not exist, then $(\delta D)(b_0, b_1, b_2)$ is undefined. This is the key difference between the complete case and the sparse case.

**Remark 6.23.** There are two conventions in the literature for the cochain complex of a directed graph. The one adopted here treats $D(v, u) = -D(u, v)$ whenever both edges exist, which corresponds to working with the **symmetric closure** of the graph. An alternative convention works only with the edges that exist and does not impose antisymmetry. We adopt the antisymmetric convention because it matches the debt axioms.

---

## 6.7 The discrete Poincaré lemma

We now prove the main theorem of the chapter: on a strongly connected directed graph, $H^1(G; \mathbb{R}) = 0$.

**Theorem 6.24 (Discrete Poincaré lemma).** Let $G = (V, E)$ be a strongly connected directed graph, and let $D \in C^1(G; \mathbb{R})$ be a 1-cochain satisfying:

1. **Antisymmetry:** $D(v, u) = -D(u, v)$ whenever both $(u, v)$ and $(v, u)$ are edges.
2. **Zero circulation:** $\sum_{e \in \gamma} D(e) = 0$ for every closed directed path $\gamma$ in $G$.

Then $D$ is a 1-coboundary: there exists a potential $\psi \in C^0(G; \mathbb{R})$ such that

$$D(u, v) = \psi(v) - \psi(u)$$

for every edge $(u, v) \in E$.

*Proof.* Choose a basepoint $s_0 \in V$. Since $G$ is strongly connected, for every $v \in V$ there exists a directed path from $s_0$ to $v$. Define

$$\psi(v) := D(\gamma_{s_0 \to v}),$$

where $\gamma_{s_0 \to v}$ is any directed path from $s_0$ to $v$, and $D(\gamma) := \sum_{e \in \gamma} D(e)$.

We first show that $\psi$ is well-defined, i.e., independent of the choice of path. Let $\gamma_1$ and $\gamma_2$ be two paths from $s_0$ to $v$. Since $G$ is strongly connected, there exists a path $\gamma_2^{-1}$ from $v$ to $s_0$. Consider the closed path $\gamma_1 \cdot \gamma_2^{-1}$. By hypothesis 2,

$$D(\gamma_1 \cdot \gamma_2^{-1}) = 0.$$

By additivity of path debt,

$$D(\gamma_1) + D(\gamma_2^{-1}) = 0.$$

Similarly, the closed path $\gamma_2 \cdot \gamma_2^{-1}$ gives

$$D(\gamma_2) + D(\gamma_2^{-1}) = 0.$$

Subtracting the two equations, $D(\gamma_1) = D(\gamma_2)$. So $\psi$ is well-defined.

Now let $(u, v) \in E$. Choose a path $\gamma_{s_0 \to u}$ from $s_0$ to $u$. Then $\gamma_{s_0 \to u} \cdot (u, v)$ is a path from $s_0$ to $v$. By definition of $\psi$,

$$\psi(v) = D(\gamma_{s_0 \to u} \cdot (u, v)) = D(\gamma_{s_0 \to u}) + D(u, v) = \psi(u) + D(u, v).$$

Therefore, $D(u, v) = \psi(v) - \psi(u)$. So $D = \delta\psi$ is a coboundary. $\square$

**Corollary 6.25.** On a strongly connected directed graph, every 1-cocycle is a 1-coboundary. That is,

$$H^1(G; \mathbb{R}) = 0.$$

*Proof.* A 1-cocycle satisfies zero circulation around every closed path (this is the cocycle condition in the graph setting). By Theorem 6.24, it is a 1-coboundary. Therefore, $Z^1(G) = B^1(G)$, and $H^1(G; \mathbb{R}) = 0$. $\square$

**Remark 6.26.** Theorem 6.24 is the graph analogue of the basepoint theorem (Theorem 4.1). The basepoint construction is the same: choose a reference state and define the potential as the debt along any path from the reference. The difference is that in the graph case, we must verify that the construction is well-defined (using strong connectivity and zero circulation), whereas in the complete case, the construction is automatic.

**Remark 6.27.** The theorem requires the graph to be **strongly connected** so that every state is reachable from the basepoint and every path can be reversed (via some path, not necessarily the edge-reverse). If the graph is not strongly connected, the construction can be applied to each strongly connected component separately, and the potential is unique up to a constant on each component.

---

## 6.8 Computations of $H^1$

We now compute $H^1(G; \mathbb{R})$ for several concrete graphs.

### Example 6.28 (Triangle with zero circulation)

Let $G$ be the directed triangle with vertices $b_1, b_2, b_3$ and edges $b_1 \to b_2$, $b_2 \to b_3$, $b_3 \to b_1$.

The space $C^0(G)$ is $\mathbb{R}^3$ (one value per vertex). The space $C^1(G)$ is $\mathbb{R}^3$ (one value per edge). The coboundary $\delta : C^0 \to C^1$ is

$$(\delta\psi)(b_1, b_2) = \psi(b_2) - \psi(b_1),$$
$$(\delta\psi)(b_2, b_3) = \psi(b_3) - \psi(b_2),$$
$$(\delta\psi)(b_3, b_1) = \psi(b_1) - \psi(b_3).$$

The image $B^1 = \mathrm{im}(\delta)$ is the subspace of $\mathbb{R}^3$ consisting of triples $(D_{12}, D_{23}, D_{31})$ with $D_{12} + D_{23} + D_{31} = 0$. This is a 2-dimensional subspace.

The space $C^2(G)$ is $\mathbb{R}$ (one value on the triangle). The coboundary $\delta : C^1 \to C^2$ is

$$(\delta D)(b_1, b_2, b_3) = D(b_2, b_3) - D(b_1, b_3) + D(b_1, b_2).$$

But in the directed triangle, the edge $(b_1, b_3)$ does not exist! So we must use the antisymmetry convention: $D(b_1, b_3) = -D(b_3, b_1)$. Then

$$(\delta D)(b_1, b_2, b_3) = D_{23} + D_{31} + D_{12}.$$

The kernel $Z^1 = \ker(\delta)$ is the subspace of $\mathbb{R}^3$ where $D_{12} + D_{23} + D_{31} = 0$. This is also a 2-dimensional subspace.

Therefore, $Z^1 = B^1$, and

$$H^1(G; \mathbb{R}) = 0.$$

This is consistent with Corollary 6.25: the triangle is strongly connected, so $H^1 = 0$.

### Example 6.29 (Triangle with nonzero circulation)

Now let $G$ be the same triangle, but suppose we only consider 1-cochains that are *not* required to be cocycles. For example, the 1-cochain $(1, 2, 1)$ has circulation $1 + 2 + 1 = 4 \neq 0$. This 1-cochain is not a cocycle, so it does not represent a class in $H^1$. It is simply not in $Z^1$.

The point is that $H^1$ measures the obstruction *after* imposing the cocycle condition. A 1-cochain with nonzero circulation is not even a candidate for cohomology—it fails the local consistency condition.

### Example 6.30 (Two vertices with parallel edges)

Let $G$ have vertices $u, v$ and two parallel edges $e_1, e_2$ from $u$ to $v$. There is no edge from $v$ to $u$.

The space $C^0(G)$ is $\mathbb{R}^2$. The space $C^1(G)$ is $\mathbb{R}^2$ (one value per edge, with no antisymmetry constraint since no reverse edges exist).

The coboundary $\delta : C^0 \to C^1$ is

$$(\delta\psi)(e_1) = \psi(v) - \psi(u), \qquad (\delta\psi)(e_2) = \psi(v) - \psi(u).$$

So $B^1$ is the diagonal subspace $\lbrace (a, a) : a \in \mathbb{R} \rbrace$, which is 1-dimensional.

The space $C^2(G)$ is trivial (there are no 2-simplices, since no closed paths of length 3 exist). So $Z^1 = C^1 = \mathbb{R}^2$.

Therefore,

$$H^1(G; \mathbb{R}) = \frac{\mathbb{R}^2}{\lbrace (a, a) \rbrace} \cong \mathbb{R}.$$

This is the simplest example where $H^1 \neq 0$. The obstruction is the "parallel edge" structure: two edges between the same vertices can carry different debts, and no potential can account for both.

**Remark 6.31.** This example shows that $H^1 \neq 0$ is possible even on a graph that is not strongly connected. The failure of strong connectivity is what allows the parallel edges to carry independent debt values.

### Example 6.32 (Square with zero circulation)

Let $G$ be the directed square with vertices $b_1, b_2, b_3, b_4$ and edges $b_1 \to b_2$, $b_2 \to b_3$, $b_3 \to b_4$, $b_4 \to b_1$. The square is strongly connected, so by Corollary 6.25, $H^1(G; \mathbb{R}) = 0$.

Let us verify this by computation. The space $C^1(G)$ is $\mathbb{R}^4$. The cocycle condition is $D_{12} + D_{23} + D_{34} + D_{41} = 0$, which is 1 equation, so $Z^1$ is 3-dimensional. The coboundary $B^1$ is the image of $\delta : \mathbb{R}^4 \to \mathbb{R}^4$, which has rank 3 (the kernel is the constant functions, dimension 1). So $B^1$ is 3-dimensional. Therefore, $H^1 = 0$.

### Example 6.33 (Complete graph on $n$ vertices)

Let $G$ be the complete directed graph on $n$ vertices. Then $G$ is strongly connected (for $n \geq 1$), so $H^1(G; \mathbb{R}) = 0$.

Let us verify this for $n = 3$ (the triangle), which we already did. For general $n$, the argument is the same: strong connectivity implies $H^1 = 0$.

**Remark 6.34.** The pattern is clear: $H^1(G; \mathbb{R}) = 0$ whenever $G$ is strongly connected. The cohomology is nontrivial only when the graph has "holes" in the appropriate sense—parallel edges, disconnected components, or more general obstructions to strong connectivity.

---

## 6.9 Higher cohomology

The cochain complex does not stop at $C^1$. The higher cohomology groups $H^k$ for $k \geq 2$ measure higher-dimensional obstructions.

**Definition 6.35.** The **$k$-th cohomology group** of $\mathcal{B}$ is

$$H^k(\mathcal{B}; \mathbb{R}) := \frac{Z^k(\mathcal{B}; \mathbb{R})}{B^k(\mathcal{B}; \mathbb{R})}.$$

**Proposition 6.36.** For the complete cochain complex on a set $\mathcal{B}$, we have $H^k(\mathcal{B}; \mathbb{R}) = 0$ for all $k \geq 1$.

*Proof.* The complete cochain complex on $\mathcal{B}$ is the cochain complex of the complete simplex on $\mathcal{B}$, which is contractible. By the standard computation of simplicial cohomology, $H^k = 0$ for $k \geq 1$ and $H^0 = \mathbb{R}$ (the constant functions). $\square$

**Remark 6.37.** Proposition 6.36 says that on the complete state space, there are no higher obstructions. Every $k$-cocycle is a $k$-coboundary for $k \geq 1$. This is the cohomological statement of the fact that the complete space is "rigid"—there are no holes of any dimension.

**Remark 6.38.** On a sparse graph, the higher cohomology groups $H^k(G; \mathbb{R})$ for $k \geq 2$ can be nontrivial. These measure higher-dimensional obstructions—for example, the failure of a 2-cocycle to be a 2-coboundary. We do not develop the higher theory in detail here; the reader is referred to the standard literature on simplicial cohomology.

---

## 6.10 Summary

This chapter developed the full cohomological framework for debt.

**The cochain complex.** For each $k \geq 0$, the space $C^k(\mathcal{B}; \mathbb{R})$ consists of real-valued functions on $(k+1)$-tuples of states. The coboundary operator $\delta : C^k \to C^{k+1}$ is defined by the alternating sum formula.

**The fundamental identity.** $\delta^2 = 0$ (Theorem 6.7). This is the algebraic foundation of the entire theory.

**Cocycles, coboundaries, cohomology.** A $k$-cocycle is a $k$-cochain with $\delta\omega = 0$. A $k$-coboundary is a $k$-cochain of the form $\delta\eta$. The $k$-th cohomology group is $H^k = Z^k / B^k$.

**Additivity is the cocycle condition.** A 1-cochain $D$ satisfies additivity if and only if $\delta D = 0$ (Proposition 6.16). This connects the debt axioms to the cochain complex.

**The discrete Poincaré lemma.** On a strongly connected directed graph, every 1-cocycle is a 1-coboundary, so $H^1(G; \mathbb{R}) = 0$ (Theorem 6.24).

**Computations.** We computed $H^1$ for the triangle ($0$), the square ($0$), the complete graph ($0$), and the graph with parallel edges ($\mathbb{R}$).

**Higher cohomology.** On the complete space, $H^k = 0$ for all $k \geq 1$. On sparse graphs, the higher cohomology groups can be nontrivial.

The central idea of the chapter can be summarized as:

$$\boxed{\text{Debt is a 1-cochain; exactness is the statement } D = \delta\psi; \text{ the obstruction is } H^1.}$$

---

## 6.11 Exercises

**Exercise 6.1 — The coboundary operator.** Write out the formula for $\delta : C^2 \to C^3$ explicitly. Verify that $(\delta\Omega)(b_0, b_1, b_2, b_3)$ is an alternating function of its arguments.

**Exercise 6.2 — Verify $\delta^2 = 0$ for $k = 1$.** Let $D \in C^1$. Compute $(\delta(\delta D))(b_0, b_1, b_2, b_3)$ explicitly and verify that it equals zero.

**Exercise 6.3 — Additivity and cocycles.** Prove that a 1-cochain $D$ satisfies additivity if and only if $(\delta D)(b_0, b_1, b_2) = 0$ for all triples $(b_0, b_1, b_2)$.

**Exercise 6.4 — Antisymmetry and coboundaries.** Prove that if $D = \delta\psi$ for some $\psi \in C^0$, then $D$ is antisymmetric.

**Exercise 6.5 — The triangle.** Let $G$ be the directed triangle. Compute $Z^1(G)$, $B^1(G)$, and $H^1(G; \mathbb{R})$ explicitly.

**Exercise 6.6 — Parallel edges.** Let $G$ have two vertices and two parallel edges from $u$ to $v$. Compute $H^1(G; \mathbb{R})$ explicitly. Give an example of a 1-cocycle that is not a 1-coboundary.

**Exercise 6.7 — The square.** Let $G$ be the directed square with vertices $b_1, b_2, b_3, b_4$ and edges $b_1 \to b_2 \to b_3 \to b_4 \to b_1$. Compute $Z^1(G)$, $B^1(G)$, and $H^1(G; \mathbb{R})$.

**Exercise 6.8 — Strong connectivity.** Prove that if $G$ is strongly connected, then for every $u, v \in V$, there exists a path from $u$ to $v$. Use this to complete the proof of Theorem 6.24.

**Exercise 6.9 — Disconnected graphs.** Let $G$ have two strongly connected components with no edges between them. Compute $H^1(G; \mathbb{R})$. What is the dimension of $H^1$ in terms of the number of components?

**Exercise 6.10 — Higher cohomology.** Prove that on the complete state space with $n$ states, $H^k = 0$ for all $k \geq 1$. (Hint: use the fact that the complete simplex is contractible.)

**Exercise 6.11 — Conceptual question.** Explain why $H^1$ measures the obstruction to exactness. Why is it a quotient, rather than just the kernel of $\delta$?

**Exercise 6.12 — Gauge freedom and cohomology.** Explain the relationship between the gauge freedom $\psi \mapsto \psi + c$ and the cohomology group $H^0$. What is $H^0(\mathcal{B}; \mathbb{R})$ for a connected space?
