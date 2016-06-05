---
layout: post
title:  "An Introduction to Abstract Algebra (Part 9)"
date:   2016-04-21
categories: Abstract_Algebra
---

Welcome to the ninth post on my abstract algebra series. Today I’ll go over some theorems and properties relating to the classification of finite simple groups.

Proposition: if G is a finite abelian group and p is a prime that divides $$\vert G \vert$$, then G contains an element of order p.

Proof: we will proceed by induction. Since $$\vert G \vert > 1$$ there is an element $$g \in G \neq 1$$. Let $$\vert G \vert = p$$ then x has order p by Lagrange's theorem. Assume $$\vert G \vert > p$$. Assume p divides $$\vert x \vert$$, this means $$\vert x \vert = pm$$ for some positive integer m. This means that there is a n such that $$\vert x^n\vert = p$$. Assume p does not divide $$\vert x \vert$$. Let $$N = <x>$$. Since G is abelian, N is a normal subgroup. By Lagrange's theorem $$\vert G/N \vert = \frac{\vert G \vert}{\vert N \vert}$$. Given that $$N \neq 1, \vert G/N \vert < \vert G \vert$$. Since p does not divide $$\vert N \vert$$, p has to divide $$\vert G/N \vert$$. Applying the induction hypothesis to G/N we can conclude it has an element y = yN of order p. Since $$y \not\in N$$ but $$y^p \in N, \vert y^p \vert < \vert y \vert$$ which implies p divides $$\vert y \vert$$ completing the induction hypothesis.

A finite or infinite group G is called simple if $$\vert G \vert > 1$$ and the only normal subgroups of G are 1 and G. By Lagrange's theorem if $$\vert G \vert$$ is prime its only subgroups are 1 and G so it is simple.

In a group G a sequence of subgroups $$1 = N_0 \leq N_1 \leq N_2 \leq ... \leq N_{k-1} \leq N_k = G$$ is called a composition series if $$N_i \unlhd N_{i+1}$$ and $$N_{i+1}/N_{i}$$ is a simple group ($$0 \leq i \leq k-1$$). In composition series the quotients $$N_{i+1}/N_{i}$$ are called composition factors of G.
A group G is solvable if there is a chain of subgroups $$1 = G_0 \unlhd G_1 \unlhd G_2 \unlhd ... \unlhd G_s = G$$ such that $$G_{i+1}/G_{i}$$ is abelian for i = 0, 1, .., s-1.

Now I'll list some theorems relevant to the clasification of simple groups. I won't include proofs for any of these (including the ones with relatively straightforward proofs) because they are not relevant to the rest of the upcoming material in this series. I personally find this topic really interesting and it is not commonly covered in introductory abstract algebra courses so I thought it was worth covering, even if not with much depth.

Jordan Holder theorem: let H be a finite group with $$G \neq 1$$. Then
1) G has a composition series and
2) The composition factors in a composition series are unique, namely, if $$1 = N_0 \leq N_1 \leq ... \leq N_r = G$$ and $$1 = M_0 \leq M_1 \leq .. \leq M_s = G$$ are two composition series for G then r = s and there is some permutation $$\pi$$ of $$\{1,2,...,r\}$$ such that $$M_{\pi(i)}/M_{\pi(i)-1} \cong N_i/N_{i-1}, 1 \leq i \leq r$$.

Theorem: there is a list consisting of 18 (infinite) families of simple groups and 26 simple groups not belonging to these families (the sporadic simple groups) such that every finite simple group is isomorphic to one of the groups in this list.

Feilt-Thompson theorem: if G is a simple group of odd order, then $$G \cong \mathbb{Z}_p$$ for some prime p.
Theorem: the finite group G is solvable if and only if for every divisor n of $$\vert G \vert$$ such that $$(n, \frac{\vert G \vert}{n}) = 1$$, G has a subgroup of order n.

These theorems are all related to the Holder program, which has two main goals: classifying all simple groups, and given groups A and B figuring out how to find all groups G with $$N \unlhd G$$ such that $$N \cong B$$ and $$G/N \cong A$$.

Stay tuned for a post on the alternating group!
