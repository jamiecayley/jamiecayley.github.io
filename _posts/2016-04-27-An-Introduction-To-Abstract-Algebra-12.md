---
layout: post
title:  "An Introduction to Abstract Algebra (Part 12)"
date:   2016-04-27
categories: Abstract Algebra
---

Welcome to the 11th post on my abstract algebra series. Today I’ll cover the conjugation action, the class equation and Cauchy's theorem.

The conjugation action was briefly covered on the previous post, namely it is an action of G on itself defined by $$g*a = gag^{-1}$$. The prbots of this action are called the conjugacy classes and if g and h are the same conjugacy class, we say g and h are conjugated.

Examples: $$\{1\}$$ is always a conjugacy class. If G is abelian, every conjugacy class is a singleton (more generally, the conjugacy class of a is a singleton if and only if $$a \in Z(G)$$. In $$D_8$$ the conjugacy classes are $$\{1\}, \{r, r^3\}, \{r^2\}, \{s, r^2s\}, \{rs, r^3s\}$$. In $$S_3 : \{1\}, \{(1 2 3), (1 3 2)\}, \{(1 2), (2 3), (1 3)\}$$. In $$S_n$$ the conjugacy class of $$\sigma$$ is all permutations whose cycle decomposition has the same shape (ie the lenghts of the cycles are the same).

Theorem (class equation): let g be a finite group, let $$g_1,...,g_k \in G\\Z(G)$$ such that if $$g_i$$ and $$g_j$$ are conjugated then i = j. If $$g \in G\\Z(G)$$ then there exists an i such that g and $$g_i$$ are conjugated. Then $$\vert G \vert = \vert Z(G) \cert + \sum[G:C_G(g_i)]$$

Proof: let $$O_g$$ denote the conjugacy class of g. Then $$G = \bigcup_{g \in G} O_g = \bigcup_{g \in G, \vert O_g \vert = 1} O_g \cup \bigcup_{g \in G, \vert O_g \vert > 1} O_g = \bigcup_i O_g_i$$ Hence $$\vert G \vert = \vert Z(G) \vert + \sum \vert O_g \vert = \vert G \vert = \vert Z(G) \vert + [G: S_G(g_i)]$$ where $$S_G(g_i)$$ is the stabilizer for conjugation action and equal to $$C_G(g_i)$$

Theorem: Let $$\vert G \vert = p^n, n \in \mathbb{Z}_{>0}$$. Then $$ Z(G) \neq \{1\}$$.

Proof: $$\vert G \vert = \vert Z(G) \vert + \sum [G: C_G(g_i)]$$ note that the last part is divisible by p. So $$0 = \vert Z(G) \vert + \sum 0$$ mod p so p divides $$\vert Z(G) \vert \geq 1. \vert Z^i(G) \vert > p > 1$$ and $$Z(G) \neq \{1\}$$.

Corollary: if $$\vert G \vert = p^2$$ then either $$g \cong \mathbb{Z}/p^2\mathbb{Z}$$ or $$G \cong (\mathbb{Z}/p\mathbb{Z})^2$$

Theorem (Cauchy's theorem): Let G ve a finite group and p prime dividing $$\vert G \vert$$ then there exists a $$g \in G$$ of order p.

Proof: let's prove the theorem when G is abelian. We proceed by generalized induction. Pick an element $$x \in G$$. If p divides $$\vert x \vert = pd$$ then $$x^d$$ is order p. If p does not divide $$\vert x \vert$$ then $$\vert G/<x> = \frac{\vert G \vert}{\vert x \vert}, \vert G/<x> \vert < \vert G \vert$$. By induction there exists $$y \in G$$ such that $$y<x>$$ is order p. Since $$y \not\in <x> and (y<x>)^p = <x>$$ then $$y^p \in <x>$$ and $$<y^p> < <y>, [<y> : <y^p>] = gcd(\vert y \vert , p) \neq 1$$ so p divides $$\vert y \vert$$. We are done by the cyclic group case. General case: (we also proceed by generalized induction). By the class equation $$\vert G \vert = \vert Z(G) \vert + \sum \vert [G: C_G(g_i)]$$. Assume p divides all $$[G: C_G(g_i)]$$ then p divides $$\vert Z(G) \vert$$ so we are done by the abelian case. Otherwise, i does not divide $$[G: C_G(g_i)]$$ for some i. $$\vert G \vert = [G: C_G(g_i)]\cdot \vert C_G(g_i) \vert$$ (p divides $$\vert G \vert$$ and $$\vert C_G(g_i)\vert$$) $$\vert C_G(g_i) \vert < \vert G \vert$$ so by induction we're done.

Stay tuned for a post on translation action, Cayley's theorem and semi direct product! 
