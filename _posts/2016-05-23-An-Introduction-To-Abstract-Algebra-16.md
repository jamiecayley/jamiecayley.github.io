---
layout: post
title:  "An Introduction to Abstract Algebra (Part 16)"
date:   2016-05-23
categories: Abstract Algebra
---

Welcome to the 16th post on my abstract algebra series. Today I'll go over ring homomorphisms and quotients.

Let R be a ring, $$S \subseteq R$$ is a subring of R $$(S \leq R$$) if 1) $$(S, +) \leq (R, +)$$ (equivalently, S is closed under subraction and nonempty)
2) for all $$x, y \in S xy \in S$$

Remark: if R is unitary we also want $$1_R \in S$$, in which case we say S is a unitary subring.

Examples: $$\mathbb{Z} \leq \mathbb{Q} \leq \mathbb{R} \leq \mathbb{C}$$ (unitary subrings).
$$n\mathbb{Z} \leq \mathbb{Z}$$ is a subring but is not unitary unless $$n = \pm 1$$.

Let R and S be rings and $$\phi : R \rightarrow S$$ is a function. If for all $$x, y \in R \phi(x+y) = \phi(x) + \phi(y)$$ (it is a ring homomorphism) and for all $$x, y \in R \phi(xy) = \phi(x)\phi(y)$$ then $$\phi$$ is a ring homomorphism.

Remarks: if R and S are unitary we might want $$\phi(1_R) = 1_S$$ (in that case we will talk of a homomorphism of unitary rings). A bijective ring homomorphism is called an isomorphism.

Proposition: Let R and S be rings and $$\phi: R \rightarrow S$$ be a ring homomorphism.
1) for all $$U \leq R, \phi(u) \leq S$$
2) for all $$V \leq S, \phi^{-1}(V) \leq R$$

Let $$I \subseteq R$$ (where R is a ring). I is an ideal if
1) $$(I, +) \leq (R, +)$$ are groups
2) for all $$x \in I, y \in R xy \in I, yx \in I$$
When R is unitary and $$I \leq R$$ is an ideal, if $$1 \in I$$ then I = R (in fact if $$I \cap R*$$ is nonempty then I = R)

Proposition: let R and S be rings and $$\phi : R \rightarrow S$$ a ring hommorphism, then ker($$\phi$$) is an ideal in R.

Proof: $$(ker(\phi), +) \leq (R,+)$$ by definition.
For all $$x \in ker(\phi), y \in R \phi(xy) = \phi(x)\phi(y) = 0 \cdot \phi(y) = 0$$ hence $$xy \in ker(\phi)$$. $$\phi(xy) = \phi(y)\phi(x) = \phi(y)\cdot 0$$ hence $$yx \in ker(\phi)$$.

Proposition: let R be a ring and $$I \subseteq R$$ an ideal. The group $$(R/I, +)$$ can be made into a ring such that the map $$\pi : R \rightarrow R/I$$ that sends $$x \mapsto x+I$$ is a ring homomorphism.

Proof: $$(x+I) \cdot (y+I) = xy + I$$ (where $$x,y \in R$$). Well defined? let $$x, y, z \in R$$ and $$s, t \in I$$, then $$(x+s)(y+t) = xy + sy + xt + st \in I$$ (by definition of ideals).
Associativity: $$((x+I)(y+I))(z+I) = (xy+I)(z+I) = xyz+I = (x+I)((y+I)(z+I))$$ .
Distributivity: $$(x+I)((y+I)+(z+I)) = $$ $$(x+I)(y+z+I) = $$ $$x(y+z)+I = $$ $$xy+xz+i = (x+I)(y+I)+(x+I)(z+I)$$ (the proof of right distributivity is left as an exercise).
So $$(R/I, +, \cdot)$$ is a ring (we call R/I the quotient ring of R modulo I).

Note that if R is unitary and $$I \subseteq R$$ is an ideal then R/I is unitary (similarly if R is commutative, R/I is commutative).

Propositon: let R be a ring, $$I \subseteq R$$. The following are equivalent:
1) I is an ideal
2) there exists a $$\phi: R \rightarrow S$$ such that $$I = ker(\phi)$$

Proof: for $$ 1 \rightarrow 2: \phi = \pi: R \rightarrow R/I, ker(\phi) = I$$.
$$2 \rightarrow 1$$ was proved above ($$ker(\phi)$$ is an ideal in R)

First isomorphism theorem (for rings): let R and S be rings and $$\phi : R \rightarrow S$$ is a ring homomorphism. Then $$\phi(R) \cong R/ker(\phi)$$ (the proof is left as an exercise to the reader, as it is very similar to the proof of this theorem for groups).

Stay tuned for a more in depth overview of ideals next!
