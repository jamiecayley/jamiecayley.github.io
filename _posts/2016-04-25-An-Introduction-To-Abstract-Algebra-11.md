---
layout: post
title:  "An Introduction to Abstract Algebra (Part 11)"
date:   2016-04-25
categories: Abstract Algebra
---

Welcome to the 11th post on my abstract algebra series. Today I’ll cover group actions.

Let $$(G, \cdot)$$ be a group, and X be a set. An action of G on X is a map $$G \times X \rightarrow X$$ such that (1) for all $$g, h \in G$$ and $$x \in X, g*(h*x) = (g\cdot h)*x$$ and (2) for all $$x \in X, 1*x = x$$.

A note on notation: I will write gx instead of g*x if there is no possible confusion but will try to use the g*x notation throughout the post.

Examples: $$S_n$$ acts on $$\{0, ..., n-1\}$$ by $$0*x = \sigma(x), \sigma(\tau(x)) = \sigma \circ \tau(x)$$ id(x) = x.
$$D_{2n}$$ acts on the vertices of the ngon ($$\{0, ..., n-1\}$$) by sending vertices to their image under the transformation.
G acts on titself in the following ways:
1) $$g*x = g \cdot x$$ (action by left translation)
2) $$g*x = g \cdot x \cdot g^{-1}$$ (action by conjugation). $$h*(g*x) = h(gxg^{-1}) = hgxg^{-1}h^{-1} = (hg)x(hg)^{-1} = (hg)*x. 1*x = 1x1^{-1} = x$$
G acts on P(x) in the following ways:
a) $$g*A = gA = \{g \cdot a, a \in A \}$$.
b) $$g*A = gAg^{-1} = \{gag^{-1}, a \in A\}$$.
If V is a K vector space then scalar multiplication is a group action of K* on V: $$\lambda, \mu \in K*, \lambda(\mu x) = (\lambda \mu)x, 1 \cdot x = x$$

Let G be a group, X a set. A right action of G on X is a map $$X \times G \rightarrow X$$ such that (1) for all $$g, h \in G$$ and $$x \in X$$ (x*g)*h = x*(g*h) and (2) for all $$x \in X$$, x*1 = x.

Proposition: let G be a group acting on X.
1) for all $$g \in G$$ the map $$fg: x \mapsto g \cdot x$$ is a bijection
2) the map $$\phi: G \rightarrow S_x g \mapsto fg$$ is a group homomorphism. Conversely if $$\phi: G \rightarrow S_x$$ is a group homomorphism then g*x = fg(x) is a group action.

Proof: 1) $$fg(fg^{-1}(x)) = g*(g^{-1}*x) = (g\cdot g^{-1})*x = x. fg^{-1}(fg(x)) = (g^{-1}\cdot g)*x = x$$ the two functions are inverse bijections.
2) $$\phi(g\cdot h) = fgh \cdot fgh(x) = (gh)*x = g*(h*x) = fg(fh(x)) = (fg \cdot fh)(x)$$ so $$fgh = fg \cdot fh$$ Conversely $$g *(h*x) = fg(fh(x)) = (fg\cdot fh)(x) = fgh(x) = (gh)*x. 1*x = $$id(x) = x.

Let G be a group acting on X and $$A \subset X$$. We define the stabilizer of A in G ($$S_G(A))$$ as $$\{g \in G. \forall a \in A, g*a = a\}$$

Proposition: $$S_G(A) \leq G$$

Proof: $$1*a = a \forall a \in A$$ so $$1 \in S_G(A)$$. Let $$g, h \in S_G(A), (g \cdot h)*a = g*(h*a) = g*a = a$$ Let $$g \in S_G(A), 1*a = (g^{-1} \cdot g)*a = g^{-1}*(g*A) = g^{-1}*a$$ so $$g^{-1} \in S_G(A)$$.

Remarks: (1) $$C_G(A)$$ is the stabilizer of A for the action by conjugation. (2) $$N_G(A)$$ is the stabilizer of $$\{A\}$$ under the action of G on P(G) by conjugation. (3) $$S_G(X)$$ is sometimes called the kernel of the action. It is indeed the kernel of $$G \rightarrow S_x$$ associated with the action.

Let G be a group acting on X and $$x \in X$$. We call the set $$\{g*x: g \in G\} = C_x$$ the orbit of x. The orbit by conjucation action is called the conjugation class.

Stay tuned for a post on conjugation action, the class equation and Cauchy's theorem.
