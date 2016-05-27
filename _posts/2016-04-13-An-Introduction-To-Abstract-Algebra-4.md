---
layout: post
title:  "An Introduction to Abstract Algebra (Part 4)"
date:   2016-04-13
categories: Abstract Algebra
---

Welcome to the fourth post on my abstract algebra series. Today I’ll give a quick overview of homomorphism and subgroups. 

Homomorphisms

Let $$(G, \cdot), (H, *)$$ be groups (where $$\cdot, *$$ are the group operations, respectively). We say $$f: G \rightarrow H$$ is a homomorphism if for all $$x, y \in G$$ $$f(x\cdot y) = f(x)*f(y)$$. 
Proposition: let $$f: G \rightarrow H$$ be a homomorphism. 
1) $$f(1_G) = 1_H$$ (when we apply f to the identity element of G we get the identity element of H)

2) $$\forall x \in G, f(x^{-1}) = f(x)^{-1}$$ (here $$\forall$$ means for all)

Proof:
1) $$f(1_G) = f(1_G \cdot 1_G) = f(1_G)*f(1_G)$$ so $$1_H = f(1_G)$$ 
2) $$f(1_G) = f(x \cdot x^{-1}) = f(x)*f(x^{-1})$$ so $$f(x)^{-1} = f(x^{-1})$$ 

An isomorphism is a bijective homomorphism. 

Proposition: Let $$f: G \rightarrow H$$ be an isomorphism, then $$f^{-1}:H \rightarrow G$$ is an isomorphism. 

Proof: $$f^{-1}$$ is a bijection (inverse of bijection is a bijection). Let $$x, y \in H, x = f(f^{-1}(x)), y = f(f^{-1}(y))$$ where $$f^{-1}(x) = s \in G, f^{-1}(y) = t \in G$$. Then $$f^{-1}(x*y) = f^{-1}(f(s)*f(t))=f^{-1}(f(s\cdot t)) = s\cdot t = f^{-1}(x)\cdot f^{-1}(y)$$ 

An automorphism is a group isomorphism from some group to itself. We denote the set of automorphisms of a group G by Aut(G). 

Proposition: Aut(G) is a group under composition (here composition refers to function composition). 

Proof: composition by definition is associative. The identity function $$i:G\rightarrow G$$ is a group automorphism so it is in Aut(G) and if $$x, y \in G$$ then $$i(x\cdot y) = x\cdot y = i(x)\cdot i(y)$$. If $$f \in$$ Aut(G), $$f^{-1}$$ is also an automorphism and $$f^{-1}$$ is the inverse of the group. 

A monomorphism is an injective homomorphism. $$f: G \rightarrow H$$ is a group homomorphism, then f is a monomorphism if and only if $$f^{-1}(1_H) = \{1_G\}$$ 

Subgroups 

Let G be a group and H a subset of G. We say H is a subgroup of G if H is nonempty and H is closed under products and inverses and we denote it $$H \leq G$$. In other words, $$H \leq G$$ if and only if $$H \neq \{\varnothing\}$$ and $$\forall x, y \in H, x \cdot y^{-1} \in H$$ (or $$x \cdot y \in H$$ if $$H \leq G$$ is finite). 

Proposition: Let $$f: G \rightarrow H$$ be a homomorphism. Then $$f(G) \leq H, f^{-1}(\{1+H\})\leq G$$. More generally, if $$K \leq G$$ then $$f(K) \leq H$$ and if $$L \leq H$$ then $$f^{-1}(L) \leq G$$

Proof: $$x, y \in f(K), x = f(s), y = f(t) \rightarrow s, t \in K. x\cdot y^{-1} = f(s)f(t)^{-1} = f(s\cdot t^{-1}) \in f(K)$$. $$x, y \in f^{-1}(L), f(x), f(y) \in L$$. 
$$f(x\cdot y^{-1}) = f(x)f(y^{-1}) \in L$$.

Stay tuned for a post on centralizers and normalizers next! 
