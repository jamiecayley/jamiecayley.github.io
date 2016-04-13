---
layout: post
title:  "An Introduction to Abstract Algebra (Part 3)"
date:   2016-04-12
categories: Abstract Algebra
---

Welcome to the third post on my abstract algebra series. Today I’ll try to go over permutation groups and some of their basic properties.

Given a finite set n containing $$\{0, 1, ..., n-1\}$$ n elements, the permutations of the set are exactly all of the one to one and onto functions from S to S (where one to one means injective, which means that if f(x) = f(y), then x = y and onto which means surjective, so for all $$b \in B \exists a \in A$$ such that f(a) = b).

The set of permutations is denoted $$S_n$$. $$S_n$$ contains an identity, which is the identity function, namely the permutation that sends each element to itself, and it has an inverse function. In general the product in a permutation group is not commutative, but disjoint cycles do commute (disjoint means that the numbers moved by one cycle are leaved fixed by the other). 

We can actually represent $$D_{2n}$$ as a permutation group: let $$D_{2n} = \{\sigma \in S_n : \sigma \text{preserves the edge relation}\}$$. An element of $$D_{2n}$$ is identified with a permutation of $$\{0, ..., n-1 \}$$ by its action on the vertices. 

A note on notation: permutations can be denoted in various ways, throughout this blog they will be denoted in the following way: (1 2 3 4) denotes the permutation that sends 1 to 2, 2 to 3, 3 to 4, and 4 to 1. 
