---
layout: post
title:  "An Introduction to Abstract Algebra (Part 7)"
date:   2016-04-17
categories: Abstract Algebra
---

Welcome to the seventh post on my abstract algebra series. Today I’ll go over quotients, normal groups and Lagrange's theorem.

Let $$f : G \rightarrow H$$ be a homomorphism, then the kernel of f is defined as follows: $$\{ g \in G \vert f(g) = 1\}$$ where 1 is the identity of H. In other words, the kernel is the inverse image of the identity.

Proposition: Let G and H be groups and let $$\phi : G \rightarrow H$$ be a homomorphism.
1) $$\phi(1_G) = 1_H$$ where $$1_G, 1_H$$ are the identities of G and H respectively.
2) $$\phi(g^{-1}) = \phi(g)^{-1}$$ for all $$g \in G$$
3) $$\phi(g^n) = \phi(g)^n$$ for all $$n \in \mathbb{Z}$$
4) $$ker(\phi)$$ is a subgroup of G
5) $$im(\phi)$$, the image of G under $$\phi$$, is a subgroup of H

Proof: (I'll prove 4 and 5, the rest are easily proven from the definition of a homomorphism and hence are left as an exercise to the reader)
4) Since $$1_G \in ker(\phi)$$ (by definition), the kernel is not empty. Let x, y $$\in ker(\phi)$$. Then $$\phi(xy^{-1}) = \phi(x)\phi(y^{-1}) = \phi(x)\phi(y)^{-1} = 1_H1_H^{-1} = 1_H$$ so $$xy^{-1} \in ker(\phi)$$ hence $$ker(\phi) \leq G$$.
5) Since $$\phi(1_G) = 1_H$$ the identity of H is in the image of $$\phi$$. If $$x, y \in im(\phi)$$ and $$x = \phi(a), y = \phi(b)$$ then $$y^{-1} = \phi(b^{-1})$$ and $$xy^{_1} = \phi(a)\phi(b^{-1}) = \phi(ab^{-1})$$ hence $$xy^{-1}$$ is in the image $$im(\phi) \leq H$$.

Let G be a group and let H be a subgroup of G. We say that H is normal in G and write $$H \unlhd G$$ if for every $$g \in G, gHg^{-1} \subseteq H$$.

Proposition: Let $$\phi : G \rightarrow H$$ be a homomorphism. Then the kernel of $$\phi$$ is a normal subgroup of G.

Proof: let $$g \in G$$ and $$h \in ker(\phi)$$. Then $$\phi(ghg^{-1}) = \phi(g)\phi(h)\phi(g^{-1}) = \phi(g)\phi(g)^{-1}$$ so $$ghg^{-1} \in ker(\phi)$$

Proposition: let G be an abelian group and let H be any subgroup. Then H is normal in G. (since for every $$h \in H, g \in G, ghg^{-1} = h \in H$$)

Let $$N \leq G$$. For any $$g \in G$$, $$gN = \{gn \vert n \in N\}$$ and $$Ng = \{ng \vert n \in N\}$$ are the left and right cosets of N in G (respectively). if N is a kernel of a homomorphism then the left and right cosets are the same.

Let $$f:G \rightarrow H$$ be a homomorphism with kernel K The quotient group G/K (G mod K) is the group whose elements are the left cosets of K in G with operation defined by $$uK \cdot vK  = (uv)K$$.

Theorem: Let N be a subgroup of the group G. The following are equivalent:
1) $$N \unlhd G$$ (N is a normal subgroup of G)
2) $$N_G(N) = G$$ (the normalizer in G of N is G)
3) $$gN = Ng \forall g \in G$$ (the set of right and left cosets are equal)
4) The operation on left cosets of N in G mentioned above ($$uK \cdot vK  = (uv)K$$) makes the set of left cosets into a group
5) $$gNg^{-1} \leq N$$ for all $$g \in G$$
(proof is left as an exercise to the reader)

Proposition: a subgroup N of the group G is normal if and only if it is the kernel of some homomorphism.

Proof: if N is the kernel of the homomorphism f then the left and right cosets of N are the same. By part 3 of the previous theorem, N is a normal subgroup. Conversely if $$N \unlhd G$$ let $$H = G/N$$ and define $$f: G \rightarrow G/N$$ by $$f(g) = gN$$ for all $$g \in G$$. By definition of $$G/N, f(g_1g_2) = (g_1g_2)N = g_1Ng_2N = f(g_1)f(g_2)$$ so f is a homomorphism. ker(f) = $$\{g \in G \vert f(g) = 1N\} = \{g \in G \vert gN = 1N\} = \{g \in G \vert g ]in N \} = N$$ so N is the kernel of the homomorphism.

Lagrange's theorem: Let G be a finite group and H a subgroup of G, then the order of H divides the order of G and the number of left cosets of H in G equals $$\frac{\vert G \vert}{\vert H \vert}$$

Proof: Let n be the cardinality of H and k the number of left cosets of H in G. Let $$A: H \rightarrow gH$$ be the map $$h \mapsto gh$$ and let $$B : gH \rightarrow H$$ be the map $$k \mapsto g^{-1}k$$. Let $$h \in H$$, then $$(B \circ A)(h) = B(A(h)) = B(gh) = g^{-1}(gh) = h$$. Let $$k \in gH$$, then $$(A \circ B)(k) = A(B(k)) = A(g^{-1}k) = g(g^{_1}k) = k$$. This shows that B is the inverse of A and hence the cardinality of each left coset is equal to the cardinality of H (namely, n). Since G is a disjoint union of its k left cosets, $$\vert G \vert$$ = kn so $$k = \frac{\vert G \vert}{n} = \frac{\vert G \vert}{\vert H \vert}$$ completing the proof.

Let G be a group (possibly infinite) and $$H \leq G$$, the number of left cosets of H in G is called the index of H in G and is denoted by $$\vert G : H \vert$$. In the case of finite groups the index of H in G is $$\frac{\vert G \vert}{\vert H \vert}$$ and in the case of infinite groupsm subgrouos may have finite or infinite index (eg $$\{0\} \in \mathbb{Z}$$ has infinite index and $$<n \in \mathbb{Z}$$ has index n for every $$n > 0$$).

Stay tuned for a post on the isomorphism theorems next! 
