---
layout: post
title:  "An Introduction to Abstract Algebra (Part 4)"
date:   2016-04-13
categories: Abstract Algebra
---

Welcome to the fourth post on my abstract algebra series. Today I’ll go over homomorphisms and subgroups.

First what is a homomorphism? Let $$(G, \cdot), (H, *)$$ be groups. Then $$f:G\rightarrow H$$ is a homomorphism if for all $$x, y \in G, f(x\cdot y) = f(x)*f(y)$$

Some basic properties of homomorphisms:
let $$f: G \rightarrow H$$ be a homomorphism 

1. f$$(1_G) = 1_H$$
2. For all $$x \in G, f(x^{-1}) = f(x)^{-1}$$

Proof:

1. $$f(1_G) = f(1_g \cdot 1_G) = f(1_G)*f(1_G)$$ so $$1_H = f(1_G)$$
2. $$f(1_G) = f(x\cdot x^{-1}) = f(x) * f(x^{-1})$$ so $$f(x)^{-1} = f(x^{-1})$$ 

An automorphism is a group isomorphism from some group to itself. We denote the set of automorphisms of a group G by Aut(G)

Proposition: Aut(G) is a group under composition

Proof: composition is associative. The identity, id:$$G \rightarrow G$$ is a group automorphism and $$x, y \in G, id(x\cdot y) = x \cdot y = id(x)\cdot id(y)$$ 

$$f \in$$ Aut(G), $$f^{-1}$$ is also an automorphism and $$f^{-1}$$ is the inverse of the group. 

A monomorphism is an injective homomorphism. $$f: G\rightarrow H$$ is a group homomorphism then f is a monomorphism if and only if $$f^{-1}(1_H) = \{1_G\}$$ 

Now onto subgroups.

If G is a group, the subset H of G is a subgroup of G if H is nonempty and H is closed under products and inverses (ie $$x, y \in H$$ implies $$x^{-1} \in H$$ and $$xy \in H$$). If H is a subgroup of G we shall write $$H \leq G$$ 

Proposition: G is a group, H is a subset of G. H is a subgroup if and only if $$H \neq \{\oslash\}$$ and $$\forall x, y, x \cdot y^{-1} \in H$$ 

Proof: ($$\rightarrow$$) trivial
($$\leftarrow$$) $$H \neq \{\oslash\}$$ so let $$x \in H, 1 = x \cdot x^{-1} \in H, x^{-1} = 1 \cdot x^{-1} \in H$$ 
$$x, y \in H, y^{-1} \in H, x\cdot (y^{-1})^{-1} \in H \rightarrow x \cdot y \in H$$

Remark: If G is a group, $$H \leq G$$ is finite, H is a subgroup if and only if $$H \neq \{\oslash\}$$ and $$\forall x, y, x \cdot y \in H$$ 

Proposition: let $$f: G \rightarrow H$$ be a homomorphism. Then $$f(G) \leq H, f^{-1} \leq H, f^{-1}(\{1_H\}) \leq G$$ More generally if $$K \leq G$$ then $$f(K) \leq H$$ and $$L \leq H$$ then $$f^{-1}(L) \leq G$$ 

Stay tuned for a post on centralizers, normalizers and center!
