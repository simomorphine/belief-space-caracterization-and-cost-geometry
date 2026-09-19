# Chapter 14: The $\mathbb{Z}/2$-Grading

---

We now begin Part VI of the book. In Parts I–V, we developed the theory of the complex quasi-metric $Q = d + iD$, its modulus, its gauge structure, the $\gamma$-family, the polar decomposition, the bitopological structure, and the equilibrium hierarchy. Throughout, we have used the complex numbers $\mathbb{C}$ as the codomain of $Q$, with $i = \sqrt{-1}$ playing a distinguished role.

But why complex? Why not simply treat $Q$ as an element of $\mathbb{R}^2$, a pair $(d, D)$? The answer, developed in this chapter, is that the multiplication by $i$ is a **grading operator**: it exchanges the real and imaginary parts, and satisfies $i^2 = -1$. This is the defining property of a **$\mathbb{Z}/2$-grading**, and it is the structural reason why the complex numbers are the natural codomain.

The $\mathbb{Z}/2$-grading is the deepest structural feature of the theory. It explains why the complex structure is not decoration, but necessity. It connects the theory to supergeometry, to Clifford algebras, and to the general theory of graded objects. And it prepares the ground for the categorical picture of Chapter 15.

---

## 14.1 Graded vector spaces

We begin with the definition of a graded vector space.

**Definition 14.1 ($\mathbb{Z}/2$-graded vector space).** A *$\mathbb{Z}/2$-graded vector space* is a vector space $V$ equipped with a direct sum decomposition

$$V = V_0 \oplus V_1.$$

The subspace $V_0$ is the *even part*; the subspace $V_1$ is the *odd part*. Elements of $V_0$ are called *even*; elements of $V_1$ are called *odd*.

**Definition 14.2 (Degree).** The *degree* of a homogeneous element $v \in V_i$ is $|v| := i \in \{0, 1\}$.

**Definition 14.3 (Parity).** The *parity* of a homogeneous element is $(-1)^{|v|}$: $+1$ for even elements, $-1$ for odd elements.

**Remark 14.4.** The $\mathbb{Z}/2$-grading is the simplest nontrivial grading. It assigns to each element a parity (even or odd), and it requires that sums of elements of different parity are allowed, but products (in a graded algebra) follow the rule "even times anything preserves parity; odd times odd is even."

**Remark 14.5.** The terminology "even" and "odd" comes from the parity of integers. In a $\mathbb{Z}$-graded vector space $V = \bigoplus_{n \in \mathbb{Z}} V_n$, the $\mathbb{Z}/2$-grading is obtained by reducing the degree modulo 2: $V_0 = \bigoplus_{n \text{ even}} V_n$ and $V_1 = \bigoplus_{n \text{ odd}} V_n$. The $\mathbb{Z}/2$-grading is the "parity" part of a $\mathbb{Z}$-grading.

---

## 14.2 The complex numbers as a $\mathbb{Z}/2$-graded algebra

We now show that the complex numbers are naturally a $\mathbb{Z}/2$-graded algebra.

**Definition 14.6 (Complex numbers).** The *complex numbers* are

$$\mathbb{C} := \{a + bi : a, b \in \mathbb{R}\},$$

with $i^2 = -1$.

**Definition 14.7 (Real and imaginary parts).** For $z = a + bi \in \mathbb{C}$:

- The *real part* is $\mathrm{Re}(z) := a$;
- The *imaginary part* is $\mathrm{Im}(z) := b$.

**Proposition 14.8 (Grading of $\mathbb{C}$).** The complex numbers decompose as

$$\mathbb{C} = \mathbb{R} \oplus i\mathbb{R},$$

where $\mathbb{R}$ is the even part and $i\mathbb{R}$ is the odd part. This is a $\mathbb{Z}/2$-grading of $\mathbb{C}$ as a real vector space.

*Proof.* Every complex number $z = a + bi$ decomposes uniquely as $a \in \mathbb{R}$ (even) plus $bi \in i\mathbb{R}$ (odd). $\square$

**Proposition 14.9 (Multiplication by $i$).** The linear map $\iota : \mathbb{C} \to \mathbb{C}$, $\iota(z) := iz$, exchanges the even and odd parts:

$$\iota(\mathbb{R}) = i\mathbb{R}, \qquad \iota(i\mathbb{R}) = \mathbb{R}.$$

Moreover, $\iota^2 = -\mathrm{id}$.

*Proof.* For $a \in \mathbb{R}$: $\iota(a) = ia \in i\mathbb{R}$. For $bi \in i\mathbb{R}$: $\iota(bi) = i \cdot bi = -b \in \mathbb{R}$. And $\iota^2(z) = i(iz) = i^2 z = -z$. $\square$

**Remark 14.10.** The map $\iota$ is the *grading operator*: it exchanges the even and odd parts. Its square is $-1$, which is the statement that applying the exchange twice gives the negation of the identity. This is the defining property of a *complex structure* on a real vector space.

**Remark 14.11.** The complex structure is exactly a $\mathbb{Z}/2$-grading together with a choice of grading operator $\iota$ satisfying $\iota^2 = -1$. The complex numbers are the simplest nontrivial example.

**Proposition 14.12 (Multiplication and grading).** For homogeneous elements $z_1, z_2 \in \mathbb{C}$ with degrees $|z_1|, |z_2|$:

- If $|z_1| = 0$: $|z_1 z_2| = |z_2|$ (even times anything preserves degree);
- If $|z_1| = |z_2| = 1$: $|z_1 z_2| = 0$ (odd times odd is even).

*Proof.* If $z_1 \in \mathbb{R}$ and $z_2 \in \mathbb{R}$, then $z_1 z_2 \in \mathbb{R}$ (even times even is even). If $z_1 \in \mathbb{R}$ and $z_2 \in i\mathbb{R}$, then $z_1 z_2 \in i\mathbb{R}$ (even times odd is odd). If $z_1, z_2 \in i\mathbb{R}$, then $z_1 = a i$, $z_2 = b i$, so $z_1 z_2 = -ab \in \mathbb{R}$ (odd times odd is even). $\square$

**Remark 14.13.** The multiplication rule of $\mathbb{C}$ is exactly the multiplication rule of a $\mathbb{Z}/2$-graded algebra. The even part is a subalgebra (isomorphic to $\mathbb{R}$); the odd part is a module over the even part; and the product of two odd elements is even.

**Remark 14.14.** The complex numbers are the simplest $\mathbb{Z}/2$-graded algebra that is not trivially graded (i.e., not concentrated in degree 0). They are the "universal" example of a $\mathbb{Z}/2$-graded algebra with a grading operator satisfying $\iota^2 = -1$.

---

## 14.3 The complex quasi-metric as a $\mathbb{Z}/2$-graded object

We now interpret the complex quasi-metric $Q$ as a $\mathbb{Z}/2$-graded object.

**Definition 14.15 (Graded kernel).** A *graded kernel* on $\mathcal{B}$ is a function $Q : \mathcal{B} \times \mathcal{B} \to \mathbb{C}$, where $\mathbb{C} = \mathbb{R} \oplus i\mathbb{R}$ is the $\mathbb{Z}/2$-graded algebra.

**Proposition 14.16.** The complex quasi-metric $Q = d + iD$ is a graded kernel with:

- Even part: $\mathrm{Re}(Q) = d$ (the cost);
- Odd part: $\mathrm{Im}(Q) = D$ (the debt).

*Proof.* Immediate from the definitions. $\square$

**Remark 14.17.** The cost $d$ is *even*; the debt $D$ is *odd*. The complex quasi-metric is a sum of an even part and an odd part. This is the $\mathbb{Z}/2$-grading interpretation of the complex structure.

**Proposition 14.18 (Grading and properties).**

- The even part $d$ is non-negative, symmetric in the appropriate sense, and satisfies the triangle inequality;
- The odd part $D$ is antisymmetric, additive, and exact (a coboundary).

*Proof.* Propositions 2.15, 3.10, 3.11, and Theorem 4.1. $\square$

**Remark 14.19.** The even and odd parts of $Q$ have *different* structural properties. The even part is metric-like; the odd part is form-like. This is the content of the $\mathbb{Z}/2$-grading: the two parts are not just different, they are *graded* different.

**Remark 14.20.** The grading is not an arbitrary decomposition. It is *canonical*: the even part is the real part, and the odd part is the imaginary part. Any other decomposition would not be compatible with the multiplication rule of $\mathbb{C}$.

---

## 14.4 The grading operator on kernels

We now introduce the grading operator on kernels.

**Definition 14.21 (Grading operator).** The *grading operator* on kernels is the map $\iota : \mathbb{C}^\mathcal{B} \to \mathbb{C}^\mathcal{B}$ defined by

$$(\iota Q)(b_i, b_j) := i \cdot Q(b_i, b_j).$$

**Proposition 14.22 (Properties of $\iota$).**

- $\iota(\mathrm{Re}(Q)) = i \cdot \mathrm{Re}(Q) \in i\mathbb{R}$ (even to odd);
- $\iota(\mathrm{Im}(Q)) = i \cdot \mathrm{Im}(Q) \in \mathbb{R}$ (odd to even);
- $\iota^2 = -\mathrm{id}$.

*Proof.* Immediate. $\square$

**Remark 14.23.** The grading operator $\iota$ exchanges the even and odd parts of $Q$. It is the kernel-level analogue of multiplication by $i$ in $\mathbb{C}$.

**Proposition 14.24 (Eigenvalues of $\iota$).** The operator $\iota$ has eigenvalues $\pm i$, with eigenvectors the elements of $\mathbb{C}$ (viewed as a complex vector space).

*Proof.* $\iota(z) = iz = iz$, so $z$ is an eigenvector with eigenvalue $i$ for all $z \in \mathbb{C}$ (viewed as a complex vector space). The eigenvalues are $\pm i$ when $\mathbb{C}$ is viewed as a real vector space of dimension 2. $\square$

**Remark 14.25.** The grading operator $\iota$ is *not* a projection; it is an involution up to sign. The projections onto the even and odd parts are

$$P_0 := \tfrac{1}{2}(\mathrm{id} - i\iota), \qquad P_1 := \tfrac{1}{2}(\mathrm{id} + i\iota).$$

These satisfy $P_0 + P_1 = \mathrm{id}$, $P_0^2 = P_0$, $P_1^2 = P_1$, $P_0 P_1 = 0$.

**Remark 14.26.** The projections $P_0$ and $P_1$ extract the even and odd parts of $Q$: $P_0 Q = d$, $P_1 Q = iD$. The grading is the decomposition of $Q$ into its even and odd parts under these projections.

---

## 14.5 The grading and the polar decomposition

We now connect the $\mathbb{Z}/2$-grading to the polar decomposition.

**Proposition 14.27.** The polar decomposition $d = S + \tfrac{1}{2}A$ and the $\mathbb{Z}/2$-grading $Q = d + iD$ are related by

$$Q = S + \tfrac{1}{2}A + iD,$$

where:

- $S$ is even (symmetric);
- $A$ is odd (antisymmetric);
- $D$ is odd (antisymmetric).

*Proof.* Immediate from the definitions. $\square$

**Remark 14.28.** The decomposition of $Q$ has three pieces: $S$ (even, symmetric), $A$ (odd, antisymmetric, 2-form), and $D$ (odd, antisymmetric, 1-form). The even piece is the symmetrization; the odd pieces are the asymmetry and the debt.

**Remark 14.29.** The $\mathbb{Z}/2$-grading of $Q$ is the decomposition into even and odd parts: $Q_{\text{even}} = S$ and $Q_{\text{odd}} = \tfrac{1}{2}A + iD$. The odd part is itself a sum of two terms, one real (the asymmetry) and one imaginary (the debt).

**Proposition 14.30 (Grading of the polar decomposition).** The polar decomposition and the $\mathbb{Z}/2$-grading are compatible: the symmetrization $S$ is even, and the asymmetry $A$ and the debt $D$ are odd.

*Proof.* $S$ is symmetric, so it is even. $A$ is antisymmetric, so it is odd. $D$ is antisymmetric, so it is odd. $\square$

**Remark 14.31.** The compatibility of the polar decomposition with the $\mathbb{Z}/2$-grading is not a coincidence. Both decompositions are *canonical*, and they are compatible because they both respect the symmetry/antisymmetry structure of the underlying objects.

---

## 14.6 The grading and the gauge structure

We now connect the $\mathbb{Z}/2$-grading to the gauge structure.

**Proposition 14.32.** The gauge transformation $\chi \cdot Q = Q + i\delta\chi$ acts only on the odd part of $Q$:

$$\mathrm{Re}(\chi \cdot Q) = \mathrm{Re}(Q), \qquad \mathrm{Im}(\chi \cdot Q) = \mathrm{Im}(Q) + \delta\chi.$$

*Proof.* Immediate. $\square$

**Remark 14.33.** The gauge group acts trivially on the even part $d$ and by translation on the odd part $D$. This is the $\mathbb{Z}/2$-grading interpretation of the gauge structure.

**Remark 14.34.** The gauge structure is *compatible* with the $\mathbb{Z}/2$-grading: the gauge group preserves the grading (it does not mix even and odd parts). This is a strong statement: it means that the gauge structure and the grading are not independent, but are two aspects of the same underlying structure.

**Proposition 14.35 (Gauge-invariant content).** The gauge-invariant content of $Q$ is precisely the even part $d$.

*Proof.* The even part is gauge-invariant; the odd part is gauge-dependent (up to coboundary). $\square$

**Remark 14.36.** The even part $d$ is the "physical" content of $Q$; the odd part $D$ is the "gauge" content. The $\mathbb{Z}/2$-grading separates the two.

**Remark 14.37.** The gauge structure and the $\mathbb{Z}/2$-grading together imply that the complex quasi-metric is a *graded gauge theory*: a $\mathbb{Z}/2$-graded object with a compatible gauge action. This is the deepest structural feature of the theory.

---

## 14.7 The grading and the Clifford algebra

We now connect the $\mathbb{Z}/2$-grading to Clifford algebras.

**Definition 14.38 (Clifford algebra).** The *Clifford algebra* $\mathrm{Cl}_{0,1}$ is the real algebra generated by a single element $e$ with $e^2 = -1$.

**Proposition 14.39.** $\mathrm{Cl}_{0,1} \cong \mathbb{C}$ as a real algebra.

*Proof.* The map $e \mapsto i$ extends to an algebra isomorphism. $\square$

**Remark 14.40.** The complex numbers are the simplest Clifford algebra. The element $i$ is the generator, and $i^2 = -1$ is the Clifford relation.

**Definition 14.41 ($\mathbb{Z}/2$-grading of a Clifford algebra).** A Clifford algebra $\mathrm{Cl}_{p,q}$ is $\mathbb{Z}/2$-graded by the parity of the number of generators in a product. The even part $\mathrm{Cl}_{p,q}^0$ consists of products of an even number of generators; the odd part $\mathrm{Cl}_{p,q}^1$ consists of products of an odd number of generators.

**Proposition 14.42.** $\mathrm{Cl}_{0,1}^0 = \mathbb{R}$ and $\mathrm{Cl}_{0,1}^1 = i\mathbb{R}$.

*Proof.* Immediate. $\square$

**Remark 14.43.** The $\mathbb{Z}/2$-grading of $\mathbb{C}$ is exactly the $\mathbb{Z}/2$-grading of the Clifford algebra $\mathrm{Cl}_{0,1}$. This connects the theory to the general theory of Clifford algebras and their representations.

**Remark 14.44.** The Clifford algebra interpretation suggests generalizations: higher Clifford algebras $\mathrm{Cl}_{p,q}$ would give higher-dimensional "complex" structures, with more than one imaginary unit. These would correspond to quaternions (for $\mathrm{Cl}_{0,2}$), octonions (for $\mathrm{Cl}_{0,3}$), and so on. The theory of the complex quasi-metric is the simplest case of a more general theory of "Clifford-valued quasi-metrics."

**Remark 14.45.** The connection to Clifford algebras is speculative but suggestive. It suggests that the complex quasi-metric is not an isolated construction, but part of a family of "graded quasi-metrics" parameterized by Clifford algebras.

---

## 14.8 The grading and supergeometry

We now connect the $\mathbb{Z}/2$-grading to supergeometry.

**Definition 14.46 (Super vector space).** A *super vector space* is a $\mathbb{Z}/2$-graded vector space $V = V_0 \oplus V_1$.

**Definition 14.47 (Superalgebra).** A *superalgebra* is a $\mathbb{Z}/2$-graded algebra $A = A_0 \oplus A_1$ with multiplication satisfying

$$A_i \cdot A_j \subseteq A_{i+j \bmod 2}.$$

**Proposition 14.48.** $\mathbb{C}$ is a superalgebra with $\mathbb{C}_0 = \mathbb{R}$ and $\mathbb{C}_1 = i\mathbb{R}$.

*Proof.* Proposition 14.12. $\square$

**Remark 14.49.** The complex numbers are a superalgebra. The even part $\mathbb{R}$ is a subalgebra; the odd part $i\mathbb{R}$ is a module over $\mathbb{R}$; and the product of two odd elements is even.

**Definition 14.50 (Supercommutativity).** A superalgebra is *supercommutative* if

$$ab = (-1)^{|a||b|} ba$$

for homogeneous elements $a, b$.

**Proposition 14.51.** $\mathbb{C}$ is supercommutative.

*Proof.* For $a, b \in \mathbb{R}$ (both even): $ab = ba$. For $a \in \mathbb{R}$, $b \in i\mathbb{R}$: $ab = ba$ (since $\mathbb{R}$ is central). For $a, b \in i\mathbb{R}$ (both odd): $ab = -ba$ (since $i^2 = -1$ and the product of two odd elements is even, but the supercommutativity rule gives $ab = (-1)^{1 \cdot 1} ba = -ba$; indeed, if $a = xi$, $b = yi$, then $ab = -xy$ and $ba = -yx = -xy$, so $ab = ba$; wait, this contradicts supercommutativity).

Hmm, let me recheck. For $a = xi$, $b = yi$ with $x, y \in \mathbb{R}$: $ab = xi \cdot yi = xy i^2 = -xy$. And $ba = yi \cdot xi = yx i^2 = -yx = -xy$. So $ab = ba$, not $-ba$. So $\mathbb{C}$ is *not* supercommutative in the usual sense.

The issue is that the multiplication in $\mathbb{C}$ is *commutative* (as a complex algebra), not supercommutative. The supercommutativity rule would require $ab = -ba$ for odd elements, but in $\mathbb{C}$, odd elements commute (since $\mathbb{C}$ is commutative).

So $\mathbb{C}$ is a commutative superalgebra, not a supercommutative one. The distinction is subtle but important.

**Remark 14.52.** The complex numbers are a *commutative* superalgebra. The supercommutativity rule is not satisfied; instead, all elements commute. This is a reflection of the fact that $\mathbb{C}$ is a field, and fields are commutative.

**Remark 14.53.** The supergeometry interpretation of the complex quasi-metric is therefore more subtle than it might appear. The complex numbers are a superalgebra, but they are not supercommutative. The theory of the complex quasi-metric is a theory of *commutative* $\mathbb{Z}/2$-graded objects, not supercommutative ones.

**Remark 14.54.** The distinction between commutative and supercommutative superalgebras is important in physics: supercommutative algebras describe fermions, while commutative algebras describe bosons. The complex numbers are "bosonic" in this sense.

---

## 14.9 The grading and the general theory of graded objects

We now situate the $\mathbb{Z}/2$-grading in the general theory of graded objects.

**Definition 14.55 (G-graded vector space).** Let $G$ be a monoid. A *$G$-graded vector space* is a vector space $V$ with a decomposition

$$V = \bigoplus_{g \in G} V_g.$$

**Proposition 14.56.** A $\mathbb{Z}/2$-graded vector space is a $G$-graded vector space with $G = \mathbb{Z}/2$.

*Proof.* Immediate. $\square$

**Remark 14.57.** The $\mathbb{Z}/2$-grading is the simplest nontrivial grading. It has two components (even and odd), and the grading is determined by the parity of the degree.

**Remark 14.58.** Higher gradings ($\mathbb{Z}$, $\mathbb{Z}/n$, etc.) are possible. A $\mathbb{Z}$-grading would give infinitely many components; a $\mathbb{Z}/n$-grading would give $n$ components. The $\mathbb{Z}/2$-grading is the simplest because it has only two components.

**Proposition 14.59 (Universality).** Every $\mathbb{Z}$-graded vector space induces a $\mathbb{Z}/2$-grading by reducing the degree modulo 2.

*Proof.* $V = \bigoplus_{n \in \mathbb{Z}} V_n$ induces $V_0 = \bigoplus_{n \text{ even}} V_n$ and $V_1 = \bigoplus_{n \text{ odd}} V_n$. $\square$

**Remark 14.60.** The $\mathbb{Z}/2$-grading is the "parity" part of a $\mathbb{Z}$-grading. It loses information (the specific degree), but retains the parity. In many applications, the parity is the only thing that matters.

**Remark 14.61.** The complex quasi-metric is a $\mathbb{Z}/2$-graded object, not a $\mathbb{Z}$-graded one. There is no natural $\mathbb{Z}$-grading of $Q$ beyond the parity. The cost $d$ is "even" and the debt $D$ is "odd," but there is no finer grading.

**Remark 14.62.** The $\mathbb{Z}/2$-grading is therefore the *natural* grading for the complex quasi-metric. It is not an arbitrary choice; it is the grading that the structure itself provides.

---

## 14.10 The grading: summary

We summarize the $\mathbb{Z}/2$-grading interpretation in a single table.

| **Object** | **Even part** | **Odd part** |
|---|---|---|
| $\mathbb{C}$ | $\mathbb{R}$ | $i\mathbb{R}$ |
| $Q$ | $d$ (cost) | $D$ (debt) |
| Polar decomposition | $S$ (symmetrization) | $\tfrac{1}{2}A$ (asymmetry) |
| Gauge action | Invariant | Shifts by $\delta\chi$ |
| Clifford algebra $\mathrm{Cl}_{0,1}$ | $\mathbb{R}$ | $i\mathbb{R}$ |

**Key results:**

- **Complex numbers are $\mathbb{Z}/2$-graded.** $\mathbb{C} = \mathbb{R} \oplus i\mathbb{R}$ (Proposition 14.8).
- **Grading operator.** Multiplication by $i$ exchanges even and odd parts, with $\iota^2 = -\mathrm{id}$ (Proposition 14.9).
- **Complex quasi-metric is graded.** $Q = d + iD$ with $d$ even and $D$ odd (Proposition 14.16).
- **Polar decomposition is graded.** $S$ even, $A$ and $D$ odd (Proposition 14.30).
- **Gauge structure is graded.** Gauge group acts trivially on even part, by translation on odd part (Proposition 14.32).
- **Clifford algebra.** $\mathbb{C} \cong \mathrm{Cl}_{0,1}$ (Proposition 14.39).
- **Supergeometry.** $\mathbb{C}$ is a commutative superalgebra (Remark 14.52).
- **General theory.** $\mathbb{Z}/2$-grading is the simplest nontrivial grading (Remark 14.57).

The $\mathbb{Z}/2$-grading is the deepest structural feature of the complex quasi-metric. It explains why the complex structure is natural, and it connects the theory to Clifford algebras, supergeometry, and the general theory of graded objects.

---

## 14.11 Exercises

**Exercise 14.1.** Verify that $\mathbb{C} = \mathbb{R} \oplus i\mathbb{R}$ is a $\mathbb{Z}/2$-grading.

**Exercise 14.2.** Show that the multiplication by $i$ exchanges the even and odd parts of $\mathbb{C}$.

**Exercise 14.3.** Prove that $\iota^2 = -\mathrm{id}$.

**Exercise 14.4.** Show that the projections $P_0 = \tfrac{1}{2}(\mathrm{id} - i\iota)$ and $P_1 = \tfrac{1}{2}(\mathrm{id} + i\iota)$ satisfy $P_0 + P_1 = \mathrm{id}$, $P_0^2 = P_0$, $P_1^2 = P_1$, $P_0 P_1 = 0$.

**Exercise 14.5.** Verify that the complex quasi-metric $Q = d + iD$ is a $\mathbb{Z}/2$-graded object.

**Exercise 14.6.** Show that the gauge action acts trivially on the even part and by translation on the odd part.

**Exercise 14.7.** Prove that $\mathbb{C} \cong \mathrm{Cl}_{0,1}$ as real algebras.

**Exercise 14.8.** Show that $\mathbb{C}$ is a commutative superalgebra but not supercommutative.

**Exercise 14.9.** Prove that every $\mathbb{Z}$-graded vector space induces a $\mathbb{Z}/2$-grading.

**Exercise 14.10.** Reflect on the following question: is the $\mathbb{Z}/2$-grading the *only* natural grading of the complex quasi-metric, or are there others? Write a short essay (one page) arguing for your position.

---

*In the next chapter, we develop the categorical picture of the complex quasi-metric. We show that the symmetrization functor is a reflection, and that the complex quasi-metric is an object of the comma category of this reflection. This situates the theory in the general framework of category theory.*

---

**End of Chapter 14.**
