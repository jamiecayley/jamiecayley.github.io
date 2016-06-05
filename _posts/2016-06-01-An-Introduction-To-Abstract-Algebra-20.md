---
layout: post
title:  "An Introduction to Abstract Algebra (Part 20)"
date:   2016-06-01
categories: Abstract Algebra
---

Welcome to the 20th post on my abstract algebra series. Today I'll go over PIDs and UFDs.

Let R be an integral domain. Then R is a PID (Principal Ideal Domain) if every $$I \subseteq R$$ ideal is principal. A GCD always exists in a PID (unique up to unit factors).

Proposition: let R be a PID, $$I \subseteq R$$ prime. Then I is maximal.

Proof: $$I = (a)$$ for some $$a \in R$$. By Krull's theorem there is $$m \in R$$ such that $$(a) \subseteq (m)$$ and (m) is maximal. if $$(a) \subseteq (m)$$ then a =  xm for some $$x \in R$$. Since (a) is prime we need x or m in (a) If $$m \in (a)$$ then $$(m) \subseteq (a)$$ and $$(m) = (a)$$ so (a) is maximal. If $$x \in (a)$$ then x = au for some $$u \in R$$. So a=xm=aum=1,which means $$um = 1$$ and hence $$m \in R^*$$ so $$(m) = R$$ which would mean (m) is not maximal which is a contradiction.

Proposition: Let R be a ring. The following are equivalent:
1) R is a field
2) $$R[x]$$ is Euclidean
3) $$R[x]$$ is a PID.

Proof: $$1 \rightarrow 2$$ was proved in last post, $$2 \rightarrow 3$$ follows because Euclidean $$\rightarrow$$ PID. $$3 \rightarrow 1$$: $$R[x] \leq R[x]$$ is integral $$\rightarrow$$ R is integral. $$R[x]/(x) \cong R$$ by the first isomorphism theorem so (x) is prime and maximal (since $$R[x]$$ is a PID), hence $$R[x]/(x) \cong R$$ is a field.

Let R be an integral domain and $$a,b \in R$$. 1) $$r \in R \backslash (R^* \cup \{0\})$$ is irreducible if whenever r = ab, we have $$a \in R^*$$ or $$b \in R^*$$. 2) if r is not irreducible we say it is reducible. 3) $$r \in R \backslash \{0\}$$ is prime if (r) is prime.

Lemma: if $$r \in R$$ is irreducible and $$u \in R^*$$ then ur is irreducible.

Proof: ur = ab, $$r = u^{-1}ab = (u^{-1}a)b$$. r irreducible implies $$u^{-1}ab = (u^{-1}a)b$$ if $$b \not\in R^*$$.

$$r, s \in R$$ are associated if (r) = (s).

Proposition: let R be an integral domain and $$r \in R$$. Then r prime $$\rightarrow$$ r irreducible.

Proof: Assume r = ab for $$a,b \in R$$. THen ab = $$r \in (r)$$ prime so we must have $$a \in (r)$$ or $$b \in (r)$$. Assume without loss of generality that $$a \in (r)$$. Then $$a = ru$$ for some $$u \in R$$. Thus $$r = ub \rightarrow 1 = rb \rightarrow b \in R^*$$ so r is irreducible. (Note: in general the converse is not true)

Proposition: if R is a PID then prime = irreducible

Proof: $$\rightarrow$$ was proved above. Let $$r \in R$$ be irreducible. Let $$I \subseteq R$$ be an ideal containing (r). Then $$r \in (r) \subseteq m$$ so r = mu for sme $$u \in R$$. Since r is irreducible either m is a unit or u is a unit. If m is a unit then I = R so (r) is maximal, which means (r) is prime so r is prime If u is a unit then $$I = (r)$$.

Let R be an integral domain. R is a UFD if 1) for all $$r \in R \backslash (R^* \cup \{0\})$$ there exists $$p_0 ... p_{n-1}$$ irreducible elements in R such that $$r = \prod_{i=0}^{n-1}p_i$$. 2) The decomposition is unique: if $$p_i, q_j$$ are irreducible and $$\prod_{i=0}^n p_i = \prod_{i=0}^m q_j$$ then n=m and there exists $$\sigma \in S_n$$ such that $$p_i$$ is associated to $$q_{\sigma(i)}$$. Note that the $$p_i$$ might be non distinct.

Examples: $$\mathbb{Z}$$ is a UFD, any PID is a UFD. If R is a UFD then $$R[x]$$ is a UFD. $$\mathbb{Z}[x]$$ is a UFD that is not a PID.

Proposition: let R be a PID, then R is a UFD.

Proof: Let $$r \in R \backslash (R^* \cup \{0\})$$ if r is irreducible we're done. Assume r is not irreducible. Then $$r = r_1\cdot s_1$$ where $$r_1, s_1 \not\in R^* \cup \{0\}$$ such that $$r_i = r_{i+1}\cdot s_{i+1}$$. This process stops if $$r_{i0}$$ is irreducible. Assume the process does not stop. Then $$r_i = r_{i+1}\cdot s_{i+1} \rightarrow (r_i) \subseteq (r_{i+1})$$. Therefore $$s_{i+1} \not\in R^*, (r_i) \subset (r_{i+1})$$. $$I = \bigcup_{i \in \mathbb{Z}_{>0}}r_i$$ is an ideal since an increasing union of ideals is always an ideal. Since R is a PID I = (a) for some a. Then there exists i such that $$a \in (r_i). (r_{i+1}) \subseteq I = (a) \subseteq (r_i)$$ which is a contradiction. Hence there exists i0 such that $$r_{i0}$$ is irreducible and $$r = r_{i0} \cdot \prod_{i < i0}s_i x_i$$. By the same proof applied to $$x_i$$ we get that $$x_1 = p_2 \cdot x_2$$. We go on by induction (we stop if $$x_i$$ is a unit). $$(x_1) \subset (x_2) \subset (x_3) \subset ... \subset (x_i) \subset ...$$. Because we have no infinite increasing chains of ideals there exists i0 such that $$x_{i0} \in R^*$$ and $$r = x_{i0} \cdot \prod_{i < i0}p_i = (x_{i0} \cdot p_{i0}) \cdot \prod_{i < i0}p_i$$ so r is a product of irreducibles.
Uniqueness: we'll proceed by indcution on n: for n = 1 $$p_0 = \prod_{j=0}^{m-1}q_j = q_0 \cdot (\prod_{j>0}q_j)$$. If $$\prod q_j$$ is a unit then $$(q_j) \cap R^*$$ is nonempty so $$q_i$$ is a unit which is not possible because an irreducivle element cannot be a unit, hence m=1 and $$p_0 = q_o$$. Assume case n holds $$\prod_{i=0}^n p_i = \prod_{j=0}^{m-1}q_j$$. Then $$(\prod_{i=0}^{n-1}p_i)p_n= \prod_{j=0}^{m-1}q_j$$ hence $$p_n \vert \prod_{j=0}^{m-1} q_j$$. Since R is a PID there exists $$j_0$$ such that $$q_{j_0} \in (p_n)$$ therefore $$q_{j0} = p_n \cdot u$$ where u is a unit. Then $$(\prod_{i<n}p_i) \cdot p_n = q_{j0}\cdot \prod_{j \neq j0}q_j = p_n \cdot u \prod_{j \neq j0}q_j$$ so $$\prod_{i < n} p_i = (u \cdot q_{j1}) \cdot \prod_{j \neq jo \cdot j1}q_j$$ and by induction we are done.

Fundamental theorem of arithmetic: $$\mathbb{Z}$$ is a UFD

Proof: $$\mathbb{Z}$$ is euclidean $$\rightarrow \mathbb{Z}$$ is a PID $$\rightarrow \mathbb{Z}$$ is a UFD.

Proposition: let R be a UFD, then prime $$\Leftrightarrow$$ irreducible

Proof: prime $$\rightarrow$$ irreducible follows from the ring being integral. Irreducible $$\rightarrow$$ prime: assume $$p, a, b \in R$$ are such that $$p \vert ab$$ so there exists a c in R such that cp =ab. Let $$a = \prod p_i, b = \prod q_j, c = \prod r_p$$ $$p \cdot \prod r_p = \prod p_i \prod q_j$$. By uniqueness we might assume that p and $$p_0$$ are associated so $$p_0 = up, u \in R^*$$. Therefore $$a = p_0 \cdot \prod_{i > 0} p_i = p \cdot (u \cdot \prod_{i >0} p_i)$$ so p divides a and we're done.

Stay tuned for a post on multivariate polynomials next!
