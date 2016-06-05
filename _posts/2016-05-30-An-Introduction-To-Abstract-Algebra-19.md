---
layout: post
title:  "An Introduction to Abstract Algebra (Part 19)"
date:   2016-05-30
categories: Abstract Algebra
---

Welcome to the 19th post on my abstract algebra series. Today I'll go over Euclidean domains.

Note: from now on in this post series every ring is unitary and commutative and every homomorphism is unitary except when otherwise noted.

A norm on a ring R is a map $$N = R \rightarrow \mathbb{Z}_{> 0}$$ such that N(0) = 0.

An integral domain R is Euclidean for the norm N if for all $$a, b \in R$$ if $$b \neq 0$$ there exists $$qr \in R$$ such that a=bq+r and $$N(r) < N(b)$$ or $$r = 0$$ where q is the quotient and r is the reminder.

Example: any field is an Euclidean domain (for any norm) since $$a = (ab^{-1})b+0$$.

Proposition: $$\mathbb{Z}$$ is an Euclidean domain, $$N(x) = \vert x \vert$$.

Proof: let $$a, b \in \mathbb{Z}, b \neq 0$$. The intervals $$[\vert b \vert n, \vert b \vert (n+1)]$$ for $$n \in \mathbb{Z}$$ cover $$\mathbb{Z}$$. This means there exists $$q \in \mathbb{Z}$$ such that $$a \in [\vert b \vert q, \vert b \vert )q+1]$$. Then $$r = a - \vert b \vert q, 0 \leq r < \vert b \vert$$. If $$b>0, a = bq+r$$. If $$b < 0, a = (-q)b+r$$.

Proposition: Let K be a field, $$K[X]$$ is euclidean for $$N(P) = deg(P), (N(0)=0)$$.

Proof: let $$A, B \in K[X], B \neq 0$$. If A = 0, then Q=R=0. If $$deg(A) < deg(B)$$ then Q = 0, R = A. If $$deg(A) > deg(B)$$ we proceed by induction on deg(A).$$A = \sum_{i=0}^m a_iX^i, B = \sum_{i=0}^n b_iX^i, C-A = \frac{a_m}{b_n} X^{m \cdot n}B$$. By induction $$C = QB+R$$ where $$deg(R) < deg(B)$$.$$A = C+ \frac{a_m}{b_n} X^{m-n}B = (Q + \frac{a_m}{b_n}X^{m-n})B+R$$. In fact in that case Q and R are unique. $$A = Q_1B+R_1 = $$ $$Q_2B+R_2. A - Q_1B = $$ $$R_1, A+Q_2B = $$ $$-R_2 < deg(N)$$. So $$deg(B(Q_1 Q_2)) < deg(B)$$. $$deg(B)+deg(Q_1-Q_2)$$ so $$Q_1 = Q_2$$ and $$R_1 = R_2$$.

Proposition: Let R be an Euclidean domain, if $$I \subseteq R$$ is an ideal then I is principal.

Proof: if $$I = (0)$$, I is principal by definition. Otherwise let $$a \in I \backslash \{0\}$$ have minimal norm. Let $$x \in I$$, by Euclidean division, x=aq+r so $$N(r) < N(a)$$ or r = 0. If r = 0 then $$x = aq \in (a)$$. If $$N(r) < N(a)$$ then $$r = r-aq \in I$$. So r = 0 and $$x \in (a)$$ hence $$I = (a)$$.

Let R be a ring and $$a, b \in R$$. 1) b divides a if there is an $$x \in R$$ such that a = xb (equivalently $$a \in (b)$$) 2) a gcd (greatest common divisor) of a and b (if it exists) is $$d \in R$$ such that $$d \vert a$$ and $$d \vert b$$ and for all $$d' \in R$$ if $$d' \vert a$$ and $$d' \vert b$$ then $$d' \vert d$$. Equivalently d is a generator of the smallest principal ideal containing a and b (when it exists). In $$\mathbb{Z}[X], (2,x)$$ is maximal, non principal and gcd(2,x) = 1.

Proposition: let R be an integral domain and $$d_1, d_2 \in R$$. Then $$(d_1) = (d_2)$$ if and only if there exists $$u \in R^*$$ such that $$d_1 = ud_2$$.

Proof: assume $$(d_1) = (d_2)$$. We have $$d \in (d_2), d_1 = ud_2$$ for $$u \in R$$ and $$d_2 \in (d_1), d_2 = vd_1$$ for $$v \in R$$. Then $$d_1 = uvd_1 \rightarrow uv \in R^*$$. Assume $$d_1 = ud_2, u \in R^*$$. Then $$d_2 = u^{-1}d_1$$, so $$d_1 \in (d_2), (d_1) \subseteq (d_2)$$ and $$d_2 \in (d_1)$$ so $$(d_2) \subseteq (d_1)$$ hence $$(d_1) = (d_2)$$.

Corollary: the GCD, if it exists is well defined up to multiplication by units.

Proposition (Euclid's Algorithm): let R be an euclidean domain, $$a, b \in R, b \neq 0$$. We define $$r_i, q_i$$ by induction as follows: $$a = bq_0+r+0, N(r_0) < N(b)$$ or $$r_0 = 0$$. $$b = r_0q_1+r_1, N(r_1) < N(r_0)$$ or $$r_1 = 0$$ ... $$r_i = r_{i-1}q_i+r_i$$ until $$r_{n+1} = 0$$. Then $$r_n =$$ gcd(a,b).

Proof: First, by induction on i we show that $$r_i \in (a,b)$$. $$r_0 = a-bq_0 \in (a,b), r_1 = b-r_0q_1 \in (a,b), r_i = r_{i-2}-r_iq_i \in (a,b)$$ so $$r_n = r_{i-2}-r_iq_i \in (a,b)$$. So $$r_n \in (a,b)$$ and $$(r_n) \subseteq (a,b)$$. By decreasing induction we prove that $$r_i \in (r_n)$$. By convention $$b = r_{-1}, a = r_{-2}, r_n \in (a,b)$$. $$r_{n-1} = r_{n+1}q_n+r_{n+1} = r_{n+1}q_n \rightarrow r_{n+1} \in (r_n)$$. $$r_{i-2} = r_i+q_i+r_i \in (r_n)$$. $$a,b \in (r_n) \rightarrow (a,b) \in (r_n)$$. Therefore (a,b) = $$(r_n)$$. so gcd(a,b) = $$r_n$$.

Stay tuned for a post on PIDs and UFDs next!
