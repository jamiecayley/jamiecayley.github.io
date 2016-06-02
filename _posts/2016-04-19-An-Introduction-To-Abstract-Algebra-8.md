---
layout: post
title:  "An Introduction to Abstract Algebra (Part 8)"
date:   2016-04-19
categories: Abstract Algebra
---

Welcome to the eight post on my abstract algebra series. Today I’ll go over the isomorphism theorems.

1st isomorphism theorem: if $$f : G \rightarrow H$$ is a homomorphism of groups, then ker(f) $$\unlhd G$$ and $$G/ker(f) \cong f(G)$$.

Proof: Let $$\phi : G/ker(f) \rightarrow im(f)$$ be a homomorphism that sends x ker(f) $$\mapsto$$ f(n). This is a well defined map because x ker(f) = y ker(y) $$\rightarrow$$ f(x) = f(y). Let $$x^{-1}y \in$$ ker(f), then $$f(x^{-1}y) = 1 \rightarrow f(x)^{-1}f(y) \rightarrow f(x) = f(y)$$. It is a well defined homomorphism because $$\phi$$(x ker(f) $$\cdot$$ y ker(y)) = $$\phi$$(xy ker(f)) = $$\phi(xy) = \phi(x)\phi(y) = \phi$$(x ker(f))$$\phi$$(y ker(f)). Let $$y \in im(f)$$. Then y = f(n) = $$\phi$$(n ker(n)) so it is surjective. Note that ker$$(\phi) = \{ \text{ x ker(f)} \vert f(n) = 1 \} = \{ \text{x ker(f)} : x \in ker(f)\} = \{\text{ker(f)}\}$$ so $$\phi$$ is injective. This completes the proof.

Remark: the size of the image is $$\vert Im(f) \vert = [G : ker(f)]$$. If G is finite, $$\vert Im(f) \vert = \frac{\vert G \vert}{\vert ker(f) \vert}$$ and $$\vert G \vert = \vert Im(f) \vert \vert ker(f) \vert$$.

2nd isomorphism theorem: let $$H, K \leq G$$ and $$H \leq N_G(K)$$, then $$K \unlhd HK \leq G, H \cap K \unlhd H$$ and $$HK/K \cong H/H\cap K$$

Proof: let $$\phi : HK \rightarrow H/H \cap K$$ be a map defined by $$x \cdot y \mapsto x(H \cap K)$$. It is well defined because if $$x_1 \cdot y_1 = x_2 \cdot y_2$$ then $$x_2^{-1}\cdot x_1 = y_2 \cdot y_1^{-1} \in H \cap K$$ so $$x_1H\cap K = x^2 H \cap K$$. It is a homomorphism because $$\phi(x_1 \cdot y_1 \cdot x_2 \cdot y_2) = $$ $$\phi(x_1x_2x_2^{-1}y_1x_1y_2) = x_1x_2(H \cap K) = $$ $$x_1(H \cap K)x_2(H \cap K) =$$ $$ \phi(x_1y_1) \cdot \phi(x_2y_2)$$. By definition HK is a subgroup, and we know that $$H \cap K \leq H$$. To show that it is normal see that if $$ x \in H \cap K, y \in H, yxy^{-1} \in H$$ and $$yxy^{-1} \in K$$ hence $$yxy^{-1} \in H \cap K$$ and it is normal. Im($$\phi$$) = $$H/H \cap K, xH\cap K = \phi(x \cdot 1)$$, ker($$\phi) = \{ x \cdot y : x(H \cap K) = H \cap K \} (x \in H \cap K$$ so K = ker($$\phi$$), which means K is normal. By the first isomorphism theorem $$Im(\phi) = H/H \cap K \cong HK/K$$ (here K = ker($$\phi$$)), completing the proof.

Note that if $$H \unlhd HK$$ then we would have $$HK/H \cong K/H \cap K$$.

3rd isomorphism theorem: let G be a group and let H and K be normal subgroups of G with $$H \leq K$$. Then $$K/H \unlhd G/H$$ and $$(G/H)(K/H) \cong G/K$$.

Proof: the proof that $$K/H \unlhd G/H$$ is left as an exercise to the reader. Let $$\phi : G/H \rightarrow G/K$$ be a map defined by $$(gH) \mapsto gK$$. Assume $$g_1H = g_2H$$ then $$g_1 = g_2h$$ for some $$h \in H$$. Since $$H \leq K, h \in K$$ so $$g_1K = g_2K$$ which means $$\phi(g_1H) = \phi(g_2H)$$ so it is well defined. ker$$(\phi) = \{gH \in G/H \vert \phi(gH) =$$ $$ 1K\} =$$ $$ \{gH \in G/H \vert gK = 1K\} = $$ $$\{gH \in G/H \vert g \in K \} = $$ $$K/H.$$ By the first isomorphism theorem $$(G/H)(K/H) \cong G/K$$

Stay tuned for a short post with some theorems and properties relating to the classification of finite simple groups!
