---
layout: post
title:  "An Introduction to Abstract Algebra (Part 13)"
date:   2016-04-29
categories: Abstract Algebra
---

Welcome to the 11th post on my abstract algebra series. Today I’ll cover translation action, Cayley's theorem and semi direct product.

Recall: G acts on itself by $$g \cdot a = ga$$. More generally G acts on P(x) by $$g*X = gX = \{g\cdot x, x \in X\}$$. In particular: $$H \leq G$$, G acts on G/H by $$g*(xH) = gxH$$.

Examples: $$(\mathbb{Z}/2\mathbb{Z})^2 = \{1,a,b,c\}$$ is abelian. $$a^2 = b^2 = c^2$$ all non identity elements have order 2. ab =c, bc = a, ca = b. Let $$\sigma_a : G \rightarrow G$$ be defined as $$x \mapsto a \cdot x. \sigma_a = (1 a)(b c), \sigma_b(1 b)(a c)..., \sigma_a(1) = a, \sigma_a(a) = 1, \sigma_a(b) = c, \sigma_a (c) = b$$.

In $$D_8, H = <s>, D_8/H = \{H, rH, r^2, r^3H\}, \sigma_s(H) = sH = H, \sigma_s(rH) = srH = r^{-1}sH = r^3H, \sigma_s(r^2H) = sr^2H = r^{-2}sH = r^2H, \sigma_s(r^3H) = sr^3H = r^{-3}sH = rH. \sigma_s = (rH r^3H), \sigma_r(H rH r^2H r^3H)$$

Theorem: G is a group, $$H \leq G$$, G acts on G/H by translation.
1) There is only 1 orbit (we say that the action is transitive)
2) The stabilizer of xH is $$xHx^{-1}$$
3) If $$\pi_H : G \rightarrow S_G/H$$ is the permutation representation associated to the translation action, then the kernel is ker($$\pi_H) = \bigcap_{x \in G}xHx^{-1} = K$$ where K is the largest subgroup of H normal in G.

Proof:
1) Let $$xH, yH \in G/H$$, then $$(yx^{-1})xH = yH$$ so xH and yH are in the same orbit.
2) the stabilizer $$\{ g \in G: gxH = xH\}  	\leftrightarrow x^{-1}gxH = H \leftrightarrow x^{-1}gx \in H \leftrightarrow g \in xHx^{-1}$$
3) ker$$(\pi_H) = \bigcap_{x \in G} S_G(xH) = \bigcap_{x \in G} xHx^{-1}$$ so $$K \unlhd G$$ because it is a kernel and $$K = \bigcap_{x \in G} xHx^{-1} \leq H$$. Let $$N \unlhd G, N \leq H, \forall x \in G, N = xNx^{-1} \leq xHx^{-1}, N \leq \bigcap_{x \in G} xHx^{-1} = K$$.

Cayley's Theorem: let G be a group, then G is isomorphic to a subgroup of a symmetric group (potentially infinite). If $$\vert G \vert = n < \infty$$ it is isomorphic to a subgroup of $$S_n$$.

Proof: let $$H = \{1\}, ker(\pi_H) = \{1\}$$ so $$\pi_H$$ is a monomorphism. By the first isomorphism theorem $$G \cong im(\pi_H) \leq S_G$$. If $$\vert G \vert = n \leq \infty, G \rightarrow^{\pi_H} S_G \cong S_n$$ then $$G \cong im(\theta) \leq S_n$$ where $$\theta$$ is a monomorphism from $$G \rightarrow S_n$$.

Corollary: G is a finite group, p the smallest prime dividing n, $$H \leq G$$ of index p, then $$H \unlhd G$$ (note, we are not claiming H exists, if G is simple and nt cyclic such H does not exist)

Proof: let $$\pi_H : G \rightarrow S_{G/H} \cong S_p$$. Let $$K = ker(\pi_H)$$, by the first isomorphism theorem $$G/K \cong im(\pi_H) \leq S_{G/H}$$. Let $$k = [H:K], [G:K] = [G:H][H:K] = pk, \frac{\vert G \vert}{\vert H \vert} = [G:H] \cdot \frac{\vert H \vert}{\vert K \vert}$$ By lagrange's theorem $$[G:K]$$ divides $$\vert S_{G/H} \vert = p!$$. K divides $$\vert G \vert$$ by Lagrange Assume $$K \neq 1$$ let q be the prime that divides K, $$q \vert (p-1)! \rightarrow q < p. q \vert n \rightarrow q \leq p$$ which is a contradiction So K = 1, $$[H:K] = 1$$ so $$H  = K \unlhd G$$

Semi direct products

Let G be a group, $$H, K \leq G$$ and $$H \unlhd G$$, then $$HK \leq G$$. If moreover $$H \cap K = \{1\}$$ then $$\vert H \cap K \vert = \frac{\vert H \vert \vert K \vert}{\vert H \cap K \vert} = \frac{\vert H \vert \vert K \vert}{\vert H\times K \vert}$$. Let $$x, y \in H, y, t \in K$$ then $$xyst = xysy^{-1}yt$$. $$(x,y)(s,t) = (x\cdot ysy^{-1}, yt)$$ where $$ysy^{-1} = y*s$$.

If we don't have an ambiant group G: let H and K be groups. Let $$\phi : K \rightarrow Aut(H)$$ be a homomorphism that sends $$y \mapsto \sigma_y$$, then we have a group action $$y \cdot x =\sigma_y(x)$$. This group action has more properties: $$y*(x_1 \cdot x_2) = (y*x_1) \cdot (y*x_2)$$. We say that K acts on H by group automorphism.

For example, conjugation is a group action by group automorphism, translation is not ($$gxy \neq gxgy$$).

Let $$G = H\times K$$ and $$(x,y)\box (s,t) = (x\cdot(y*s),yt)$$. Note that the action is trivial.

Proposition:
1) $$(G, \box)$$ is a group
2) $$\phi_H : H \rightarrow G$$ defined by $$x \mapsto (x,1)$$ is a group monomorphism. $$\phi_k : K \rightarrow G$$ is defined by $$y \mapsto (y,1)$$ and is also a group monomorphism. We can identify H with $$\tilde{H} = \{(x,1) : x \in H\} \leq G$$ and K with $$\tilde{K} = \{(1,y) : y \in K\} \leq G$$
3) $$\tilde{H} \cap \tilde{K} = \{1\}, H \unlhd G, HK \leq G/ (x,1) = \tilde{x} \in \tilde{H}. (1,y) = \tilde{y} \in \tilde{K}. \tilde{y}\tilde{x}\tilde{y}^{-1} = (y*x,1)$$

Proof (the proof of 3 is left as an exercise):
1) $$((x,y) \box (s,t)) \box (u,v) = (x \cdot (y*s), yt) \box (u,v) = ((x \cdot (y*s)\cdot (yt)*u), ytv). (x,y)\box ((s,t)\box (u,v)) = (x,y) \box (s \cdot (t*u), tv) = (x \cdot (y*s)\cdot y(\cdot(t*u)), ytv)$$ Note that (1,1) is the identity, and $$(y^{-1}*x^{-1}, y^{-1})$$ is the inverse of (y,x) and that y*1 = 1.
2) $$(x,1) \box (s,1) = (x \cdot (t*s), 1\cdot 1) = (x\cdot s,1). (1,y)\box(1,t) = (1 \cdot (g*1), yt) = (1,yt). (x,1) = (1,1)$$ if and only if x = 1. (1,y) = (1,1) if and only if y = 1.

Notation: G (as defined above) is called the semidirect product of H and K and we write $$G = H\times K$$ (for the action *).

Example: $$D_{2n} \cong \mathbb{Z}/n\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$$ for the action $$0*i = i, 1*i = -i$$.
If $$\phi(y)$$ is the identity transformation for all y then $$H \times K$$ is just the product.
