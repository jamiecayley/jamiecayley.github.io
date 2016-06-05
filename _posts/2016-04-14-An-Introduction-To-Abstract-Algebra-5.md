---
layout: post
title:  "An Introduction to Abstract Algebra (Part 5)"
date:   2016-04-14
categories: Abstract_Algebra
---

Welcome to the fifth post on my abstract algebra series. Today I’ll go over centralizers and normalizers.

Centralizers

Let G be a group. $$A \subseteq G$$ is a subset. Let $$C_G(A) = \{ g \in G : gag^{-1} = a\} (a \in A). C_G(A)$$ is called the centralizer of A and is the set of elements of G that commutes with A: $$gag^{-1} = a \rightarrow ga = ag$$.

Proposition: The centralizer of A in G is a subgroup of G $$(C_G(A) \leq G)$$

Proof: if $$gh \in C_G(A)$$ then $$gh^{-1} \in C_G(A)$$. Let $$g \in C_G(A)$$ then for all $$a \in A, gag^{-1} = a$$ so $$a = g^{-1}ag$$ which implies $$g^{-1} \in C_G(A)$$. Let $$h, g \in C_G(A)$$ then for $$a \in A, gh^{-1}a(gh^{-1})^{-1} = gh^{-1}ahg^{-1} = gag^{-1} = a$$ so $$gh^{-1} \in C_G(A)$$ which means $$C_G(A)$$ is a subgroup.

A quick note on notation: if $$A = \{a\}$$ the centralizer of A is denoted $$C_G(\{a\})$$.

Normalizers

Let G be a group, $$A \subseteq G$$ is a subset. For $$g \in G$$ let $$gAg^{-1} = \{gag^{-1} : a \in A\}$$. Then $$N_G(A) = \{g \in G: gAg = A\}$$ is the normalizer of G.

Remark: $$N_G(A) = \{g \in G: \forall a \in A, gag^{-1} \in A, g^{-1}ag \in A \}$$

Propositon: The normalizer of A in G is a subgroup of G $$(N_G(A) \leq G)$$

Proof: if $$g \in N_G(A)$$ then $$g^{-1} \in N_G(A)$$. Let $$g, h \in N_G(A)$$, then $$gh^{-1}A(gh^{-1})^{-1} = gh^{-1}Ahg^{-1} = gAg^{-1} = A$$

 Remarks

 1) $$C_G(G)$$ is a specific kind of centralizer, called the center of G and it is the set of elements of G that commute, usually denoted Z(G)
 2) if G is abelian $$C_G(A) = N_G(A) = Z(G) = G$$
 3) $$C_G(A) \leq N_G(A)$$.
 4) $$C_G(A) = \cup_{a \in A} C_G(a)$$.
 5) $$\{a^n : n \in Z \} \leq C_G(a)$$.

Example: computations in $$D_8$$

Let $$A = \{1, r^2, r^3\}$$
We can easily see that $$A \subseteq C_{D_8}(A)$$. If $$s \in C_{D_8}(A)$$ then $$srs^{-1} = r^{-1}ss^{-1} = r^{-1} = r^3 \neq r$$ hence $$s \not\in C_{D_8}(A)$$. Since every element of $$D_8$$ is a power of r or s that means $$A = C_{D_8}(A)$$.

We know $$A = C_{D_8}(A) \in N_{D_8}(A)$$ by definition, and $$srs^{-1} = r^{-1}ss^{-1} = r^{-1} = r^3 \in A$$ so $$s \in N_{D_8}(A)$$. Since every element of $$D_8$$ is a power of r or s that means $$D_8 = N_{D_8}(A)$$.

We know $$Z(D_8) \in C_{D_8}(A) = A$$. The identity is always in Z(G), hence $$1 \in Z(D_8)$$. Since $$srs^{-1} = r^{-1}ss^{-1} = r^{-1} = r^3$$ then $$r, r^3 \not\in Z(D_8)$$. Finally we can see that $$sr^2s^{-1} = r^{-2}ss^{-1} = r^{-2} = r^2$$ so $$Z(D_8) = \{1, r^2\}$$.

Stay tuned for a post on cyclic groups!
