---
layout: post
title:  "An Introduction to Abstract Algebra (Part 21)"
date:   2016-06-03
categories: Abstract Algebra
---

Welcome to the 21th post on my abstract algebra series. Today I'll go over multivariate polynomials.

Let R be a ring and $$X_1, ..., X_K$$ be variables. We define $$R[X_1,...,X_k] = R[X_1,...,X_{k-1}][X_k]$$. An element of $$R[X_1,...,X_k]$$ is of the form $$\sum a_{\alpha_1,...,\alpha_k}X_1^{\alpha_1},...,X_k^{\alpha_k}$$ (finite sum).

Remark: the order of the variables does not matter $$R[X_1, ..., X_k] \cong R[X_{\sigma(1)},...,X_{\sigma(k)}], \sigma \in S_n$$. If $$(X_i)_{i \in \mathbb{Z}_{>0}}$$ are variables we can define the ring of polynomials on finitely many varibles $$R[(x_i)_{i \in \mathbb{Z}_{>0}}] = \bigcup R[X_1,...,X_i]$$. Each polynomial will only contain finitely many variables.

Proposition: if R is an integral domain then $$R[X_1,..,X_n]$$ is an integral domain.

Lemma: R is a ring, $$I \subseteq R$$ is an ideal. $$\phi: R[x] \rightarrow R/I[x], \pi: R \rightarrow R/I, \sum a_iX^i \mapsto \sum \pi(a_i)X^i$$. $$\phi$$ is a ring homomorphism and ker($$\phi) = I[x] = I \cdot R[x] = \{ \sum a_iX^i: a_i \in I\}$$.

Proof: $$\phi(\sum_i a_i X^i \cdot \sum_j b_j X^j) = \phi (\sum_k(\sum_{i+j = k}a_ib_j)x^k) = \sum_k \pi(\sum_{i+j = k}a_ib_j)x^k = \sum_k(\sum_{i+j=k}\pi(a_i)\pi(b_j))x^k = \sum_i\pi(a_i)x^i \cdot \sum_j \pi(b_j)x^j = \phi(\sum_i a_ix^i)\phi(\sum_j b_jx^j$$ $$ker(\phi) = \{\sum a_ix^i : \sum \pi(a_i) x^i =0\}$$. For all i, $$\pi(a_i) = 0, a_i \in I$$ so the kernel is equal to $$\{\sum a_ix^i : a_i \in I \}$$.

Corollary: Let R be a ring, $$I \subseteq R$$ a prime ideal, then $$I \cdot R[x]$$ is prime

Proof: by the first isomorphism theorem $$R[x]/I \cdot R[x] \cong R/I[x]$$. Since I is prime, R/I is integral so R/I[x] is integral so $$R[x]/I \cdot R[x]$$ is integral and hence $$I \cdot R[x]$$ is prime.

Proposition (Gauss' Lemma): Let R be a UFD, $$P \in R[x]$$ and $$A, B \in F[x]$$ such that $$P = AB$$ (F = Frac(R)) Then there exists $$c \in F$$ such that $$cA, c^{-1}B \in R[x]$$.

Proof: $$A = \sum a_i c_i^{-1}x^i, B = \sum b_i d_i^{-1}x^i$$ where $$a_i, b_i, c_i, d_i \in R$$ and $$b_i, d_i \neq 0$$. Then $$A = \prod c_i A^*, B = \prod d_i B^*$$ where $$A^*, B^* \in R[x]$$. So $$dP = A^*b^*$$ where $$d = \prod c_i \prod d_i$$. Let p be irreducible and let p divide d (then $$d = pd^*$$). Then in $$R/(p)[x], 0 = \bar{A^*}\bar{B^*}$$ (reduction mod p). Since (p) is prime, $$R/(p)[x]$$ is integral so $$\bar{A^*} = 0$$ or $$\bar{B^*} = 0$$. Assume $$\bar{A^*} = 0$$ then all coefficients are in (p) so $$A^* = pC, C \in R[x].$$ now $$pd^*P=pCB^*$$ but R[x] is integral so $$d^*P = cB^*$$. By induction we may assume that $$d \in R^*$$, we can keep pulling out irreducible factors. Now $$P = (d^{-1}A^*)\cdot B^*, P = (d^{-1}\prod c_i)A \cdot (\prod d_i)B$$.

If $$P \in R[x]$$ is a polynomial we define c(P) to be the gcd of the $$a_i, P = \sum a_ix^i$$ c(P) divides $$a_i$$ for all i and if d divides $$q_i$$ for all i, d divides c(P). $$P = c(P)P^*$$, where $$c(P^*) =1$$.

Corollary to Gauss' lemma: Let $$P \in R[x]$$, c(P) = 1. P is irreducible in $$R[x]$$ if and only if P is irreducible on $$F[x]$$ (here $$F[x]$$ is Frac(R)).

Stay tuned for a post n polynomial roots and basic properties of fields!
