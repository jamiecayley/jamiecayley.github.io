---
layout: post
title:  "An Introduction to Abstract Algebra (Part 5)"
date:   2016-04-14
categories: Abstract Algebra
---

Welcome to the fifth post on my abstract algebra series. Today I’ll go over homomorphisms and subgroups.

Our first topic of the day: centralizers! Let G be a group and A is a subset of G. Let $$C_G(A) = \{ g \in G: gag^{-1}=a\} (a \in A)$$. $$C_G(A)$$ is the set of elements of G that commutes with $$A \rightarrow gag^{-1} = a \rightarrow ga = ag$$ 

Proposition: The centralizer of A in G is a subgroup of G $$C_G(A) \leq G$$ 

Proof: if $$gh \in C_G(A)$$ then $$gh^{-1} \in C_G(A)$$. Let $$g \in C_G(A)$$ then for all $$a \in A, gag^{-1} = a$$ then $$a = g^{-1}ag$$ so $$g^{-1} \in C_G(A)$$. Let $$h, g \in C_G(A)$$ then $$a \in A. gh^{-1}a(gh^{-1})^{-1} = gh^{-1}ahg^{-1} = gag^{-1} = a$$ so $$gh^{-1} \in C_G(A)$$ then $$C_G(A)$$ is a subgroup. 

Note: if $$A = \{a\}$$ we write $$C_G(\{a\})$$

Definition: 
