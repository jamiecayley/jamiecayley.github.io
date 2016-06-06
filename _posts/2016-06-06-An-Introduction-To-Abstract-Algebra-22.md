---
layout: post
title:  "An Introduction to Abstract Algebra (Part 22)"
date:   2016-06-06
categories: Abstract_Algebra
---

Welcome to the 22nd post on my abstract algebra series. Today I'll go over polynomial roots.

Let R be a ring, and let $$P \in R[x]$$. $$a \in R$$ is a root of P if P(a) = 0.

Proposition: Let F be a field, $$P \in F[x]$$ and $$a \in F$$, a is a root of P if and only if x-a divides P.

Proof: if P = (x-a)Q then P(a) = $$(a-a)\cdot Q(a)$$ = 0. Conversely, P = (x-a)Q+R (here deg(R) < 1), then $$P(a) = 0 = (a-a) \cdot Q(a) + R(a)$$ so (x-a) divides P.

Let F be a field, $$P \in F[x], a \in F, n \in \mathbb{Z}_{>0}$$. We say that a is a root of multiplicity n of P if $$(x-a)^n \vert P$$ and $$(x-a)^{n+1} \not\vert P$$.

Proposition: Let F be a field, and $$a_i \in F$$ be distinct (finitely many) roots of P of multiplicity $$n_i$$, then $$deg(P) \geq \sum n_i$$

Proof: by definition $$(x-a_i)^{n_i} \vert P$$. If $$i \neq j$$ then $$a_i \neq a_j$$ so $$(x-a_i)$$ is an irreducible not associated to $$(x-a_j)$$. Hence $$\prod (x-a_i)^{n_i} \vert P$$ and $$p = \prod (x-a_i)^{n_i}Q$$ which means $$deg(P) = \sum deg(x-a_i)^{n_i}+deg(Q) \geq \sum n_i$$.

Corollary: let F be a field, $$P \in F[x]$$. Then P has at most deg(P) roots, counting multiplicity.

Let $$P \in R[x]$$. Then $$P'[x] \in R[x]$$ (the derivative of P) is defined as follows $$P = \sum a_ix^i \rightarrow P' = \sum(i-a_{i+1})x^i$$.

Stay tuned for a post on basic properties of fields next!
