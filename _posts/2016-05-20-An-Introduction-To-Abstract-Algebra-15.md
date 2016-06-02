---
layout: post
title:  "An Introduction to Abstract Algebra (Part 15)"
date:   2016-05-20
categories: Abstract Algebra
---

Welcome to the 15th post on my abstract algebra series. Today I'll go over polynomial rings and matrices.

The Ring of polynomials

Let R be a commutative unitary ring. A polynomial is a formal sum $$\sum_{i = 0}^n a_iX^i$$ where each $$a_i \in R$$ and $$a_n \neq 0$$. The leading term is $$a_nX^n$$, the degree is n, the leading coefficient is $$a_n$$, and it is monic if $$a_n = 1$$.

$$R[x]$$ is a ring of polynomials of x with coefficients from R. Addition is defined by $$(\sum_{i=0}^n a_ix^i)+(\sum_{i=1}^n b_iX^i) = \sum_{i=1}^n (a_i+b_i)X^i$$. Multiplication is defined by: $$(\sum_{i=0}^n a_iX^i)(\sum_{j=0}^n b_jX^j) = \sum_{i=0}^n\sum_{j=0}^n a_ib_jX^{i+j}$$ (note that it is commutative because R is commutative). It is associative because $$(\sum_{i=0}^n a_iX^i)\cdot (\sum_{j=0}^nb_jX^j)(\sum_{k=0}^nc_kX^k) = (\sum_{i=0}^n a_iX^i)(\sum_{j=0}^n \sum_{k=0}^n b_jc_kX^{j+k}) = \sum_{i=0}^n\sum_{j=0}^n\sum_{k=0}^n a_ib_jc_kX^{i+j+k} = (\sum_{i=0}^na_iX^i)(\sum_{j=0}^nb_jX^j)(\sum_{k=0}^nc_kX^k)$$ distributivity also holds, 1 is the multiplicative identity. Hence $$R[x]$$ is a commutative unitary ring.

Example: $$\mathbb{Q}[x]$$ is the ring of polynomials with rational coefficients. $$\mathbb{Z}/3\mathbb{Z}[x]$$ is a ring of polynomials with coefficients in $$\{0,1,2\}$$. Some sample computations in $$\mathbb{Z}/3\mathbb{Z}[x]: (x^2+2x+1)+(x^3+x+2) = x^3+x^2+3x+2 = x^3+x^2+2$$ (addition) $$(x^2+2x+1)(x^3+x+2) = x^5+2x^4+3x^3+4x^2+5x+2 = x^5+2x^4+2x^3+x^2+2x+2$$ (multiplication). In $$\mathbb{Z}/2\mathbb{Z}[x]$$, $$x^2+2x+1 = (x+1)^2$$ so $$x^2+1$$ is a square (however it is not a square in $$\mathbb{Z}[x]$$).

Matrix rings:

Let R be a ring and $$n > 0$$ an integer. $$M_n(R)$$ is the ring of all $$n \times n$$ matrices with entries from R. Addition is defined coordinate wise: $$((a_{ij})_{i,j} +(b_{ij}))_{i,j} = (a_{ij}+b_{ij})_{i,j}$$. Multiplication: $$((a_{ij})_{i,j} \cdot (b_{ij}))_{i,j} = \sum+{k =0}^{n-1} a_{ik}b_{kj}$$.

Why is it a ring?
* $$(M_n(R), +)$$ is an abelian group
* Distributivity: $$(a_{ij})\cdot (b_{ij}) + (c_{ij}) = (a_{ij})_{i,j}(b_{ij}+c_{ij})_{i,j} = (\sum_{k=0}^{n-1}a_{ik}(b_{kj}+c_{kj}))_{i,j} = (\sum_{k=0}^{n-1}a_{ik}b_{kj}+\sum_{k=0}^{n-1}a_{ik}c_{kj}) = (a_{ij})(b_{ij})+(a_{ij})(c_{ij})$$
* It is associative (the proof is left as an exercise)

Notes:
* R can be identified with $$\{ \begin{bmatrix}a & 0\\0 & a\end{bmatrix} : a \in R \}$$
* if $$n \geq 2, M_n(R)$$ is not commutative (unless we're considering a ring where for all a and b, $$a \cdot b = 0$$)
* $$M_n(R)$$ has nonzero zero divisers

If R is unitary, the group of units in $$M_n(R)$$ is generally called $$GL_n(R)$$, where GL stands for general linear. 
