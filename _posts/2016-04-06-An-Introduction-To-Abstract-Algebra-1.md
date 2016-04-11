---
layout: post
title:  "An Introduction to Abstract Algebra (Part 1)"
date:   2016-04-06 
categories: Abstract Algebra
---
Welcome to the first post on my introduction to abstract algebra series! This series is primarily meant to help me study by forcing me to consolidate my notes and thoughts into a format that is easy for others to understand and that it is easily accessible and harder to lose that the handwritten notes currently contained on my clipboard. The content in this notes might include excerpts from my lecture notes from Math 113 taught by professor Rieffel at UC Berkeley in Fall 2015, Math 113 taught by professor Rideau at UC Berkeley in Spring 2016, Math 120 taught by professor Vakil at Stanford in Fall 2014 and the textbooks *Abstract Algebra* by Dummit and Foote and *Algebra, Abstract and Concrete* by Goodman (which is available for free [here](http://homepage.math.uiowa.edu/~goodman/algebrabook.dir/download.htm)). 

Our topic for today: what is a group? 

Groups are what most introductory abstract algebra courses focus on, as it is a really useful algebraic structure and learning about it serves as a basis for learning about all the other exciting algebraic structures we'll learn about in this post series. 

Intuitively it is a collection of elements such that you can combine any two elements on it, there is one element that combined with any of the elements on it results in just the element you combined it with, and there are elements that are capable of undoing the element combinations. 

In math speech, a group is a set G equipped with a binary operation, ie a function $$G \times G \rightarrow G$$ which is associative and for which there is an identity element and every element is invertible. In math notation: a group is a set G with a binary operation $$ \cdot $$ such that 

* $$ \forall x, y, z \in G, (x\cdot y)\cdot z = x\cdot (y \cdot z)$$ (associativity)
* $$ \exists e \in G$$ such that $$\forall x \in G, x \cdot e = e \cdot x = x$$ (identity)
* $$ \forall x \in G \exists y \in G$$ such that $$x \cdot y = y \cdot x = e$$ (inverse) 
Note: a group G is said to be abelian if $$\forall x, y \in G, x \cdot y = y \cdot x$$ (the group is commutative)

With the definition out of the way, now on to some basic properties! 

1. The identity is unique
2. The inverse is unique 
3. $$\forall x \in G, (x^{-1})^{-1} = x$$ (here $$x^{-1}$$ denotes the inverse of x)
4. $$\forall x, y \in G, (x \cdot y)^{-1} = y^{-1} \cdot x^{-1}$$ (this property is often called conjugation)

And now to finish this post we'll prove those properties

1. Let $$e_1$$ and $$e_2$$ both be identity elements. Then $$e_1 = e_1 \cdot e_2 = e_2$$ so $$e_1 = e_2$$ and hence the identity is unique
2. Let $$x, y, z \in G$$ where y and z are both inverses for x, then we have $$y \cdot (x \cdot z) = y \cdot e = y$$ and $$(y \cdot x) \cdot z = e \cdot z = z$$ hence y = z so the inverse is unique 
3. Since $$x^{-1}$$ is the inverse of x we have $$x \cdot x^{-1} = x^{-1} \cdot x = e$$ hence $$(x^{-1})^{-1} = x$$ as desired
4. Let $$c = (x \cdot y)^{-1}$$, by the definition of inverse $$c \cdot (x \cdot y) = e$$. By the property of associativity we get that $$x \cdot (y \cdot z) = e$$

$$x^{-1} \cdot (x \cdot (y \cdot c)) = x^{-1} \cdot e$$

$$e \cdot (y \cdot c) = x^{-1}$$

$$x \cdot c = x^{-1}$$

$$y^{-1} \cdot (y \cdot c) = y^{-1} \cdot x^{-1}$$

$$(y^{-1} \cdot y) \cdot c = y^{-1} \cdot x^{-1}$$

$$e \cdot c = y^{-1} \cdot x^{-1}$$

$$c = y^{-1} \cdot x^{-1}$$

$$\square$$

That's all for today. On the next post I'll go over basic examples of groups and some intuition behind some of the properties. 

Note on mathematical notation:

* $$\forall$$ = for all
* $$\exists$$ = there exists 
* $$x \in G$$ = x is an element of G 






