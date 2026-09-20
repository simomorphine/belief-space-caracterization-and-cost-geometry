# Chapter 17: Open Structure

---

We have now completed the mathematical core of the book. Parts I–VI developed the theory of the complex quasi-metric from its foundations (belief space, energy quasi-metric, debt) through its structure (modulus, gauge, $\gamma$-family, polar decomposition, bitopology, equilibrium hierarchy, $\mathbb{Z}/2$-grading, categorical picture).

But a mathematical theory is never complete. There are always further questions, unexplored directions, and alternative structures. This chapter surveys the **open structure** of the theory: the questions that the theory raises but does not yet answer, the directions that are suggested but not yet developed, and the alternative structures that are consistent with the axioms but not explored.

The chapter is not a list of unsolved problems in the usual sense. It is a map of the *adjacent possible*: the regions of mathematical space that the theory touches but does not yet occupy. It is the bridge between the completed theory and the work that remains.

The eight open directions are grouped into three tiers:

- **Well-developed.** Directions with substantial mathematical content, developed in the literature, and directly connected to the base theory: non-conservative, multiplicative, probabilistic, non-abelian.
- **Emerging.** Directions with significant partial development, but where the connection to the base theory is not fully worked out: topological, geometric.
- **Speculative.** Directions where the mathematical content is not yet clear, and where the generalization from the base theory may or may not be possible: $n$-categorical, quantum.

The chapter closes with a unifying picture that organizes the eight directions into a single map, with at least one concrete relation between regimes.

---

## 17.1 The non-conservative regime

The first and most important open direction is the **non-conservative regime**.

**The conservative regime.** In the theory developed in this book, the debt $D$ is assumed to be *exact*: $D = \delta\psi$ for some potential $\psi$. This is the content of the basepoint theorem (Chapter 4), and it implies that the debt cancels on every closed loop:

$$\sum_{\text{cycle}} D = 0.$$

The conservative regime is the regime in which the debt is a coboundary, the connection $D$ is flat, and the cohomology $H^1(\mathcal{B}; \mathbb{R})$ is trivial.

**The non-conservative regime.** What if we drop the exactness assumption? What if the debt is a general 1-cochain, not necessarily a coboundary? Then:

- The debt does *not* cancel on closed loops. There is a *holonomy*: a nonzero integral around cycles.
- The potential $\psi$ does not exist globally. The debt is a *connection* with nonzero *curvature*.
- The cohomology $H^1(\mathcal{B}; \mathbb{R})$ is nontrivial. The debt has a *cohomology class* $[D] \in H^1$.

**Open questions.**

1. **Holonomy.** What is the correct definition of holonomy in the discrete setting? How does it relate to the topology of the belief space?
2. **Curvature.** What is the curvature 2-form of the connection $D$? How does it interact with the asymmetry $A$?
3. **Cohomology.** How does the cohomology class $[D]$ affect the structure of the complex quasi-metric? What are the gauge-invariant observables?
4. **Optimization.** How does the optimal path depend on the holonomy? Is there a "phase transition" in the optimal path structure as the holonomy varies?
5. **Topology.** How does the non-conservative regime affect the bitopological structure and the equilibrium hierarchy?

**Remark 17.1.** The non-conservative regime is the regime of *non-trivial topology*. It is the regime in which the belief space has "holes" that cannot be filled, and the debt detects them. This is the regime of physical gauge theories (electromagnetism, Yang–Mills), and it is the regime of topological data analysis (persistent homology).

**Remark 17.2.** The transition from conservative to non-conservative is the transition from *integrable* to *non-integrable*, from *potential* to *connection*, from *flat* to *curved*. It is the central open direction of the theory.

**Remark 17.3.** The non-conservative regime is *well-developed* in the mathematical literature. The theory of connections on principal bundles, the theory of holonomy, and the theory of characteristic classes are all mature. The open problem is not to develop the mathematics, but to *apply* it to the complex quasi-metric.

---

## 17.2 The multiplicative regime

The second open direction is the **multiplicative regime**.

**The additive regime.** In the theory developed in this book, the complex quasi-metric $Q = d + iD$ is an *additive* object: paths compose by addition of costs and debts, and the total cost/debt of a path is the sum of the costs/debts of its edges. This is the content of the additivity axiom (D1) for debt, and of the definition of $d$ as a minimum over paths.

**The multiplicative regime.** What if paths compose by *multiplication* instead? What if the "cost" of a path is the *product* of the costs of its edges, and the "debt" is the product of the debts? Then:

- The complex quasi-metric is a *multiplicative* object: $Q(\gamma_1 \cdot \gamma_2) = Q(\gamma_1) \cdot Q(\gamma_2)$.
- The modulus is multiplicative: $|Q(\gamma_1 \cdot \gamma_2)| = |Q(\gamma_1)| \cdot |Q(\gamma_2)|$.
- The phase is additive: $\arg Q(\gamma_1 \cdot \gamma_2) = \arg Q(\gamma_1) + \arg Q(\gamma_2)$.

**Open questions.**

1. **Definition.** What is the correct definition of a multiplicative complex quasi-metric? What are the axioms?
2. **Examples.** What are natural examples of multiplicative complex quasi-metrics? (Hint: transition matrices, transfer operators, Feynman path integrals.)
3. **Modulus and phase.** How do the modulus and phase behave under multiplication? Is there a "multiplicative triangle inequality"?
4. **Optimization.** What is the analog of shortest-path optimization in the multiplicative regime? (Hint: it is the problem of finding the "most likely" path, or the "least action" path.)
5. **Relation to additive.** Can every multiplicative complex quasi-metric be transformed into an additive one by taking logarithms? What are the obstructions?

**Remark 17.4.** The multiplicative regime is the regime of *interference*. Two paths to the same point can have their phases add, leading to constructive or destructive interference. This is the regime of quantum mechanics, and it is the regime of multiplicative weights.

**Remark 17.5.** The relation between the additive and multiplicative regimes is the relation between *tropical* and *classical* mathematics. The additive regime is tropical (min-plus); the multiplicative regime is classical (sum-product). The logarithm map (when it exists) connects the two.

**Remark 17.6.** The multiplicative regime is the natural setting for the *path integral* formulation of the theory. If $Q$ is a multiplicative complex quasi-metric, then the "partition function" $Z = \sum_\gamma Q(\gamma)$ is a sum over paths, and the phase of $Q$ controls the interference between different paths.

**Remark 17.7.** The multiplicative regime is *well-developed* in physics (path integrals, transfer matrices) and in mathematics (Perron–Frobenius theory, tropical geometry). The open problem is to connect it precisely to the complex quasi-metric.

---

## 17.3 The probabilistic regime

The third open direction is the **probabilistic regime**.

**The deterministic regime.** In the theory developed in this book, the cost $d$ and the debt $D$ are *deterministic* functions. The potential $\psi$ is a fixed function; the debt is a fixed coboundary. There is no randomness.

**The probabilistic regime.** What if the potential $\psi$ is a *random field*? What if the debt is a *random variable*? Then:

- The complex quasi-metric $Q$ is a *random complex variable*.
- The modulus $|Q|$ is a *random metric*.
- The phase $\theta$ is a *random angle*.
- The holonomy $H(\gamma)$ is a *random variable* around each cycle.

**Open questions.**

1. **Distribution.** What is the distribution of $Q$ given a distribution on $\psi$? What are its moments?
2. **Expected modulus.** What is the expected value $\mathbb{E}[|Q|]$? Is it a metric? Does it satisfy the triangle inequality?
3. **Fluctuations.** What is the variance of $|Q|$? How do fluctuations propagate along paths?
4. **Concentration.** Does the modulus $|Q|$ concentrate around its expectation for large paths? What are the concentration inequalities?
5. **Phase transitions.** Does the distribution of $Q$ undergo phase transitions as the distribution of $\psi$ varies? What is the order parameter?

**Remark 17.8.** The probabilistic regime is the regime of *statistical mechanics*. If $\psi$ is a random field, then $Q = d + i\delta\psi$ is a random complex quasi-metric, and its distribution is a *Gibbs measure*. The expected modulus is a *free energy*, and the fluctuations are *correlations*.

**Remark 17.9.** The original motivation for the theory (Chapter 1) included the statement "with probability $\alpha$, the cost behaves as a quasi-metric, and with probability $1-\alpha$, a debt is generated." This is a probabilistic statement, and it is not yet developed in the book. The probabilistic regime is the regime in which this statement is made precise.

**Remark 17.10.** The probabilistic regime is the natural setting for *machine learning*. If $\psi$ is a learned potential, then $Q$ is a learned complex quasi-metric, and the learning process is a stochastic optimization over the space of potentials. This is a direction for applications, but it is also a direction for pure mathematics: the space of complex quasi-metrics is a statistical manifold, and the learning process is a gradient flow on this manifold.

**Remark 17.11.** The probabilistic regime is *well-developed* in probability theory and statistical mechanics. The open problem is to apply the machinery of random fields, Gibbs measures, and concentration inequalities to the complex quasi-metric.

---

## 17.4 The non-abelian regime

The fourth open direction is the **non-abelian regime**.

**The abelian regime.** In the theory developed in this book, the debt $D$ takes values in $\mathbb{R}$ (or $i\mathbb{R}$, in the complex quasi-metric). The gauge group is $\mathbb{R}^\mathcal{B}$, which is *abelian*. The gauge action is a translation, and the gauge transformations commute.

**The non-abelian regime.** What if the debt takes values in a *non-abelian group* $G$? What if the potential $\psi$ takes values in a non-abelian group? Then:

- The debt $D(b_i, b_j) = \psi(b_j) \psi(b_i)^{-1}$ is a *group-valued* 1-cochain.
- The gauge group is $G^\mathcal{B}$, which is non-abelian if $G$ is.
- The gauge action is $\psi \mapsto g \psi$, and the gauge transformations do not commute.

**Open questions.**

1. **Definition.** What is the correct definition of a non-abelian complex quasi-metric? What are the axioms?
2. **Exactness.** Is there a basepoint theorem for non-abelian debt? (Hint: the obstruction is the non-abelian cohomology $H^1(\mathcal{B}; G)$.)
3. **Gauge structure.** What is the gauge group? What are the gauge-invariant observables?
4. **Holonomy.** What is the holonomy of a non-abelian connection? How does it relate to the fundamental group of the belief space?
5. **Physics.** What are the physical applications of non-abelian complex quasi-metrics? (Hint: Yang–Mills theory, lattice gauge theory.)

**Remark 17.12.** The non-abelian regime is the regime of *non-commutative geometry*. The complex quasi-metric is a connection on a principal $G$-bundle, and the gauge group is the group of sections of the bundle. The curvature is a 2-form with values in the Lie algebra of $G$.

**Remark 17.13.** The non-abelian regime is the natural setting for *quantum computation*. The potential $\psi$ takes values in the unitary group $U(n)$, and the debt is a unitary matrix. The complex quasi-metric is a unitary connection, and the holonomy is a unitary matrix (the "gate" of a quantum circuit). This is a direction for applications, but it is also a direction for pure mathematics: the space of unitary connections is a moduli space, and its geometry is the subject of non-abelian gauge theory.

**Remark 17.14.** The non-abelian regime is *well-developed* in gauge theory and non-commutative geometry. The open problem is to connect it precisely to the complex quasi-metric, and to determine whether the basepoint theorem generalizes.

---

## 17.5 The topological regime

The fifth open direction is the **topological regime**. It is *emerging*: the mathematics is well-developed, but the connection to the base theory is not fully worked out.

**The set-theoretic regime.** In the theory developed in this book, the belief space $\mathcal{B}$ is a *set*. It has no topology, no smooth structure, no geometry. The topology is induced by the quasi-metric, not assumed.

**The topological regime.** What if the belief space $\mathcal{B}$ is a *topological space*? What if it is a *smooth manifold*? Then:

- The complex quasi-metric is a *continuous* or *smooth* function on $\mathcal{B} \times \mathcal{B}$.
- The debt $D$ is a *continuous* or *smooth* 1-cochain.
- The potential $\psi$ is a *continuous* or *smooth* function.
- The gauge group is the group of *continuous* or *smooth* functions.

**Open questions.**

1. **Definition.** What is the correct definition of a topological complex quasi-metric? A smooth complex quasi-metric?
2. **Exactness.** Is there a basepoint theorem for topological complex quasi-metrics? What are the obstructions? (Hint: the topological cohomology $H^1(\mathcal{B}; \mathbb{R})$ may be nontrivial.)
3. **Gauge structure.** What is the topological gauge group? What are the topologically gauge-invariant observables?
4. **Examples.** What are natural examples of topological complex quasi-metrics? (Hint: Riemannian manifolds, symplectic manifolds, algebraic varieties.)
5. **Relation to set-theoretic.** How does the topological theory reduce to the set-theoretic theory? What is the "forgetful" functor?

**Remark 17.15.** The topological regime is the regime of *continuous geometry*. The complex quasi-metric is a continuous function, the debt is a continuous 1-cochain, and the gauge group is the group of continuous functions. This is the natural setting for applications to geometry and topology.

**Remark 17.16.** The topological regime is closely related to the non-conservative regime. If $\mathcal{B}$ is a manifold, then $H^1(\mathcal{B}; \mathbb{R})$ may be nontrivial, and the debt may have a nontrivial cohomology class. The non-conservative regime is the *algebraic* version of the topological regime.

**Remark 17.17.** The topological regime is *emerging*: the mathematics (topology, differential geometry, sheaf theory) is well-developed, but the connection to the complex quasi-metric is not yet fully worked out. The open problem is to define the topological complex quasi-metric precisely, to prove the basepoint theorem in the topological setting, and to characterize the topological obstructions to exactness.

---

## 17.6 The geometric regime

The sixth open direction is the **geometric regime**. It is also *emerging*.

**The metric regime.** In the theory developed in this book, the cost $d$ is a quasi-metric. It satisfies the triangle inequality, but it is not necessarily symmetric, and it is not necessarily smooth.

**The geometric regime.** What if the cost $d$ is a *Riemannian metric*? What if it is a *Finsler metric*? What if it is a *sub-Riemannian metric*? Then:

- The complex quasi-metric is a *complex Finsler metric*.
- The debt $D$ is a *1-form* on the manifold.
- The potential $\psi$ is a *function* on the manifold.
- The gauge group is the group of *diffeomorphisms* of the manifold.

**Open questions.**

1. **Definition.** What is the correct definition of a complex Finsler metric? What are the axioms?
2. **Geodesics.** What are the geodesics of a complex Finsler metric? How do they depend on the phase?
3. **Curvature.** What is the curvature of a complex Finsler metric? How does it relate to the asymmetry $A$ and the debt $D$?
4. **Examples.** What are natural examples of complex Finsler metrics? (Hint: complex manifolds, Kähler manifolds, Hermitian manifolds.)
5. **Relation to metric.** How does the complex Finsler theory reduce to the metric theory? What is the "forgetful" functor?

**Remark 17.18.** The geometric regime is the regime of *differential geometry*. The complex quasi-metric is a complex Finsler metric, the debt is a 1-form, and the gauge group is the group of diffeomorphisms. This is the natural setting for applications to geometry and physics.

**Remark 17.19.** The geometric regime is closely related to the topological regime. The main difference is that the geometric regime requires a *smooth* structure, while the topological regime requires only a *continuous* structure. The geometric regime is the "smooth" version of the topological regime.

**Remark 17.20.** The geometric regime is *emerging*: the mathematics of Finsler metrics and complex manifolds is well-developed, but the connection to the complex quasi-metric is not yet fully worked out. The open problem is to define the complex Finsler metric precisely, to compute its geodesics and curvature, and to relate them to the asymmetry and the debt.

---

## 17.7 The $n$-categorical regime

The seventh open direction is the **$n$-categorical regime**. It is *speculative*: the mathematical content is not yet clear, and the generalization from the base theory may or may not be possible.

**The 1-categorical regime.** In the theory developed in this book, the complex quasi-metric is a *1-categorical* object: it is a function on pairs, and the composition is a 1-morphism. The categorical picture (Chapter 16) is a 1-category.

**The $n$-categorical regime.** What if the complex quasi-metric is an *$n$-categorical* object? What if the debt is a 2-morphism, or a 3-morphism, or higher? Then:

- The complex quasi-metric is a *higher* object: a 2-functor, a 3-functor, etc.
- The composition is a higher composition, with coherence conditions.
- The gauge structure is a higher gauge structure, with higher gauge transformations.

**Open questions.**

1. **Definition.** What is the correct definition of a higher complex quasi-metric? What are the axioms?
2. **Coherence.** What are the coherence conditions for higher composition? What are the higher analogs of the triangle inequality?
3. **Gauge structure.** What is the higher gauge group? What are the higher gauge-invariant observables?
4. **Examples.** What are natural examples of higher complex quasi-metrics? (Hint: higher categories, higher stacks, higher gauge theory.)
5. **Relation to 1-categorical.** How does the higher theory reduce to the 1-categorical theory? What is the "truncation" functor?

**Remark 17.21.** The $n$-categorical regime is the regime of *higher structures*. The complex quasi-metric is a higher morphism in a higher category, and the gauge structure is a higher gauge structure. This is a direction for pure mathematics, connecting the theory to higher category theory and higher topos theory.

**Remark 17.22.** The $n$-categorical regime is speculative. It is not clear whether the theory generalizes to higher categories, or whether the 1-categorical version is the only natural one. This is an open question.

---

## 17.8 The quantum regime

The eighth open direction is the **quantum regime**. It is also *speculative*.

**The classical regime.** In the theory developed in this book, the complex quasi-metric is a *classical* object: it is a function on pairs, and the composition is a classical composition. The complex structure is a $\mathbb{Z}/2$-grading, but it is not a quantum structure.

**The quantum regime.** What if the complex quasi-metric is a *quantum* object? What if the cost and debt are *operators* on a Hilbert space? What if the composition is a *quantum* composition? Then:

- The complex quasi-metric is a *quantum channel*: a completely positive trace-preserving map.
- The cost $d$ is a *Hamiltonian*: a self-adjoint operator.
- The debt $D$ is a *gauge field*: a connection on a Hilbert bundle.
- The modulus $|Q|$ is a *transition amplitude*: a complex number whose square is a probability.

**Open questions.**

1. **Definition.** What is the correct definition of a quantum complex quasi-metric? What are the axioms?
2. **Composition.** What is the composition of quantum complex quasi-metrics? Is it associative? Does it satisfy the triangle inequality?
3. **Gauge structure.** What is the quantum gauge group? What are the quantum gauge-invariant observables?
4. **Examples.** What are natural examples of quantum complex quasi-metrics? (Hint: quantum channels, density matrices, entanglement measures.)
5. **Relation to classical.** How does the quantum theory reduce to the classical theory? What is the "classical limit"?

**Remark 17.23.** The quantum regime is the regime of *quantum information theory*. The complex quasi-metric is a quantum channel, the cost is a Hamiltonian, and the debt is a gauge field. This is a direction for applications, but it is also a direction for pure mathematics: the space of quantum channels is a convex set, and its geometry is the subject of quantum information geometry.

**Remark 17.24.** The quantum regime is speculative. It is not clear whether the classical theory generalizes to the quantum setting, or whether the quantum version is a fundamentally different theory. This is an open question.

---

## 17.9 The unifying picture

The open directions can be organized into a single unifying picture.

**The base regime.** The regime developed in the book is the *conservative-additive-deterministic-abelian-set-theoretic-classical-metric* regime. It is the simplest and most tractable regime, and it is the foundation for all the others.

**The generalizations.** Each open direction is a generalization of the base regime, obtained by relaxing one or more assumptions:

| **Regime** | **Assumption relaxed** | **Tier** |
|---|---|---|
| Non-conservative | Exactness of $D$ | Well-developed |
| Multiplicative | Additivity of composition | Well-developed |
| Probabilistic | Determinism of $\psi$ | Well-developed |
| Non-abelian | Abelianness of the gauge group | Well-developed |
| Topological | Set-theoreticness | Emerging |
| Geometric | Metric-only structure | Emerging |
| $n$-categorical | 1-categoricalness | Speculative |
| Quantum | Classicality | Speculative |

**The relations.** The generalizations are not independent. Here are the main relations, with at least one concrete example:

**Relation 1 (Non-conservative + Topological).** A non-conservative debt on a manifold is a connection with nonzero curvature. **Concrete example:** Let $\mathcal{B} = S^1$ (the circle), and let $D$ be a constant 1-cochain with $D(\theta, \theta') = c \cdot (\theta' - \theta)$ for some $c \neq 0$. The holonomy around the circle is $\oint D = 2\pi c \neq 0$, so $D$ is not exact. The cohomology class $[D] \in H^1(S^1; \mathbb{R}) \cong \mathbb{R}$ is nontrivial.

**Relation 2 (Probabilistic + Quantum).** A quantum channel is a probabilistic object (a completely positive map). **Concrete example:** A depolarizing channel on a qubit is a probabilistic mixture of the identity and the completely depolarizing channel, with probabilities $1-p$ and $p$. The cost is the Hamiltonian, the debt is the gauge field, and the modulus is the transition amplitude.

**Relation 3 (Non-abelian + Geometric).** A non-abelian connection on a manifold is a gauge field. **Concrete example:** Let $\mathcal{B} = \mathbb{R}^4$ (Minkowski space), and let $D$ be a connection with values in $SU(2)$. The curvature is the field strength $F = dD + D \wedge D$, and the holonomy is the Wilson loop. This is the setting of Yang–Mills theory.

**The unifying theme.** The unifying theme is that the complex quasi-metric is a *section of a fibered category* over the category of assumptions. Each regime is a *fiber* of this category, corresponding to a different choice of assumptions. The base regime is the simplest fiber; the generalizations are the other fibers. The relations between regimes are the *morphisms* of the fibered category, which connect different fibers.

**Remark 17.25.** This unifying theme is a *precise* statement: the complex quasi-metric is a section of a fibered category over the category of assumptions. The base regime is the fiber over the "base" assumptions (conservative, additive, deterministic, abelian, set-theoretic, classical, metric). The other regimes are the fibers over the "relaxed" assumptions.

**Remark 17.26.** The unifying theme is a *direction for future work*: to make the fibered category precise, to identify the morphisms between fibers, and to study the *global* structure of the fibered category. This is a research program in its own right.

---

## 17.10 Summary

We have surveyed the open structure of the theory of the complex quasi-metric. Eight open directions were identified, grouped into three tiers:

**Well-developed:**

1. **Non-conservative regime.** Debt as a general 1-cochain, with holonomy and curvature.
2. **Multiplicative regime.** Paths compose by multiplication, with interference.
3. **Probabilistic regime.** Potential as a random field, with fluctuations.
4. **Non-abelian regime.** Debt takes values in a non-abelian group.

**Emerging:**

5. **Topological regime.** Belief space as a topological space or manifold.
6. **Geometric regime.** Cost as a Finsler metric, debt as a 1-form.

**Speculative:**

7. **$n$-categorical regime.** Complex quasi-metric as a higher morphism.
8. **Quantum regime.** Cost and debt as operators on a Hilbert space.

Each direction is a generalization of the base regime, obtained by relaxing one or more assumptions. The directions are connected, and the most interesting questions are at their intersections.

The open structure is not a list of unsolved problems in the usual sense. It is a map of the adjacent possible: the regions of mathematical space that the theory touches but does not yet occupy. It is the bridge between the completed theory and the work that remains.

---

## 17.11 Exercises

**Exercise 17.1.** Give an example of a non-conservative debt on a belief space with nontrivial topology. Compute the holonomy around a cycle.

**Exercise 17.2.** Define a multiplicative complex quasi-metric and prove that it satisfies a "multiplicative triangle inequality."

**Exercise 17.3.** Let $\psi$ be a random field with i.i.d. Gaussian values. Compute the distribution of $Q(b_i, b_j)$ and its expected modulus.

**Exercise 17.4.** Give an example of a non-abelian debt on a belief space. Compute the gauge group and the gauge-invariant observables.

**Exercise 17.5.** Define a 2-categorical complex quasi-metric and state the coherence conditions.

**Exercise 17.6.** Let $\mathcal{B}$ be a smooth manifold. Define a smooth complex quasi-metric and prove the basepoint theorem in the smooth setting.

**Exercise 17.7.** Define a quantum complex quasi-metric (with cost a Hamiltonian and debt a gauge field). Prove that it satisfies the triangle inequality in the appropriate sense.

**Exercise 17.8.** Let $\mathcal{B}$ be a Finsler manifold. Define a complex Finsler metric and compute its geodesics.

**Exercise 17.9.** Discuss the relationship between the non-conservative and topological regimes. Give an example (beyond the one in Section 17.9) that illustrates the connection.

**Exercise 17.10.** Write out the fibered category structure suggested in Section 17.9: define the base category (the category of assumptions), the fibers (the regimes), and the morphisms between fibers. What are the morphisms between the conservative and non-conservative fibers?

**Exercise 17.11 (Reflection question).** Which of the eight open directions is the most promising for future research, and why? Write a short essay (one page) arguing for your position.



