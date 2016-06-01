---
layout: post
title:  "An Introduction to Abstract Algebra (Part 14)"
date:   2016-05-18
categories: Abstract Algebra
---

Welcome to the 14th post on my abstract algebra series. Today I'll give a brief introduction to rings.

A ring is a set R with two binary operations, $$+, \cdot$$ such that
1) $$(R, +)$$ is an abelian group
2) $$\cdot$$ is associative ($$\forall x, y, z \in R, x \cdot (y \cdot x) = (x \cdot y) \cdot z$$)
3) $$\cdot$$ distributes over $$+$$ ($$\forall x, y, z \in R x\cdot (y+z) = x \cdot y + x \cdot z, (x+y)\cdot z = x \cdot z + y \cdot z$$)

A ring is commutative if $$\cdot$$ is commutative ($$\forall x, y \in R, x \cdot y = y \cdot x$$). A ring is unitary if there is an identity for $$\cdot$$. (there exists $$1 \in R$$ such that $$\forall x \in R, x \cdot 1 = 1 \cdot x = x$$).

A note on notation: $$ab = a \cdot b$$ and parenthesis will be excluded if unambiguous.

Examples:
* $$(\mathbb{Z}, +, \cdot)$$ is a commutative ring
* $$(\mathbb{Z}/n\mathbb{Z}, +, \cdot)$$ is a commutative ring for all $$n > 1$$.
* $$\{0\}$$ is a commutative unitary ring
* ($$M_n(\mathbb{R}), +, \cdot)$$ which is the ring of $$n \times n$$ matrices is a unitary ring.
* Let R be a ring and X a set, then $$R^x = \{f:X \rightarrow R\}$$ forms a ring with pointwise addition and multiplication ($$f+g = x \mapsto f(x)+g(x), f \cdot g = x \mapsto f(x)\cdot g(x)$$).

A division ring (or skew field) is a unitary ring R such that for all $$x \in R\\ \{0\}$$ there exists $$y \in R, xy = yx = 1$$.

A field is a commutative division ring. For example. $$(\mathbb{Q}, +, \cdot), (\mathbb{R}, +, \cdot), (\mathbb{C}, +, \cdot)$$ are fields.

Proposition: Let R be a ring
1) for all $$x \in R, 0 \cdot 0 = 0$$
2) for all $$x, y \in R, (-x)y = -xy = x(-y)$$
3) if R is unitary: multiplicative identity 1 is unique and $$(-1)a = -a$$.

Proof:
1) $$) \cdot x = (0+0)\cdot x = 0\cdot x + 0 \cdot x$$ so $$0 = 0 \cdot x$$ (because cancellation in (R,+)) $$x \cdot 0 = x \cdot (0+0) = x \cdot 0+x \cdot 0$$ so $$0 = x \cdot 0$$
2) $$0 = 0 \cdot y = (x+(-x))\cdot y = x \cdot y + (-x)y$$ so $$(-x)y = -xy$$. $$0 = x \cdot 0 = x \cdot (y+(-y)) = xy + x(-y)$$ so $$x(-y) = -xy$$.
3) Let 1 and e be multiplicative identities. Then $$1 = 1 \cdot e = e$$ so the identity is unique. Also $$(-1)\cdot a = -(1 \cdot a) = -a$$.

Zero divisor: let R be a ring, an element $$x \in R$$ such that $$y \in R \\ \{0\} : xy = 0$$ or $$yx = 0$$. For example, $$\begin{bmatrix}0 & 1\\0 & 0\end{bmatrix}^2 = \begin{bmatrix}0 & 0\\0 & 0\end{bmatrix}$$ so $$\begin{bmatrix}0 & 1\\0 & 0\end{bmatrix}$$ is a zero divisor.

Unit: let R be a unitary ring, $$x \in R$$ is a unit if there exists $$y \in R : xy = yx = 1$$. A division ring is unitary if every $$x \in R \\ \{0\}$$ is a unit.

Proposition: if R is a unitary ring, then $$R* = \{x \in R: \exists y \in R xy = yx = 1\}$$ is a group.

Proof (non rigurous): 1 is the identity, R* is associative (due to ring axioms), and it is closed under inverses by definition, hence R* is a group.

Proposition: Let R be a unitary ring, $$1 \neq 0$$. Then no element is both a unit and a zero divisor.

Proof: assume $$x, y, v \in R$$ are nonzero such that xy = 0 and xv = 1 = vx. Then $$y = 1 \cdot y = vxy = v \cdot 0 = 0$$ which is a contradiction. If instead yx = 0 then $$y = y \cdot 1 = yxv = 0 \cdot v = 0$$ which is also a contradiction.

Proposition: let R be a ring. If a \in R is not a zero divisor then for all $$ b \in R$$ if ab = ac then b = c, if ba = ca, then b = c (proof is left as an exercise to the reader).

A commutative unitary ring whose only zero divisor is 0 is called an integral domain. For example, every field is an integral domain, $$\mathbb{Z}$$ is an integral domain and $$\mathbb{Z}/n\mathbb{Z}$$ is both an integral domain and a field if n is prime.

Proposition: A finite integral domain is a field.

Proof: Let R be an integral domain. Pick $$a \in R \\ \{0\}$$. Then $$R \rightarrow R$$ defined by $$x \mapsto a\cdot x$$ is injective. Since $$\vert R \vert = \vert R \vert$$ and both are finite, the map is surjective. Then there exists an $$x \in R$$ such that $$a \cdot x = 1$$.

That's all for today! Next up: polynomial rings and matrices. 
