---
layout: post
title:  "Jamie's Math Review Part 3: Series"
date:   2016-10-27
categories: Calculus
---

Welcome to the third part of my Math Review! The topic of this post will be series (Power Series, Taylor Series and Mclaurin Series). 

A series of the form $$a_0+a_1(x--c)+a_2(x-c)^2+... = \sum_{r=0}^{\infty} a_r(x-c)^r$$ is called a power series in x-c or a power series for the point x = c. c is the centre of convergence of the series. The series converges provided that $$\vert x-c \vert < R$$, ie $$C - R \leq x \leq C+R$$ where R is the radius of convergence given by $$R = 1/L$$ and $$L = lim_{n \rightarrow \infty} \vert \frac{a_{n+1}}{a_n} \vert$$. Note that if $$L = 0, R = \infty$$ and if $$L = \infty, R = 0$$. The series obviously converges for x = c if nowhere else. 

Example: find the centre, radius and interval of convergence of the series $$\sum_{n=0}^{\infty} \frac{(2x+5)^n}{3^n(n^2+1)}$$. Note that $$\sum_{n=0}^{\infty} \frac{(2x+5)^n}{3^n(n^2+1)}$$ = $$\sum_{n=0}^{\infty} (\frac{2}{3})^n \frac{1}{n^2+1}(x+\frac{5}{2})^n$$. Therefore the centre of convergence is $$-5/2$$. L = $$lim_{n \rightarrow \infty} \vert \frac{(\frac{2}{3})^{n+1} \frac{1}{(n+1)^2+1}}{(\frac{2}{3})^n \frac{1}{n^2+1}} \vert $$= $$lim_{n \rightarrow \infty} \frac{\frac{(2^{n+1})}{(3^{n=1})(n+1)^2+1}}{\frac{2^n}{3^n(n+1)^2+1)}}$$ = $$\lim_{n \rightarrow \infty} \frac{(2^{n+1})(3^n)(n^2+1)}{(3^{n+1})((n+1)^2+1)(2^n)}$$ = $$lim_{n \rightarrow \infty} \frac{2(n^2+1)}{3((n+1)^2+1)}$$ = 2/3. Therefore $$L = \frac{2}{3}$$ and $$R = \frac{3}{2}$$. $$\frac{-5}{2}-\frac{3}{2} = \frac{-8}{2} = -4$$. $$\frac{-5}{2}+\frac{3}{2} = \frac{-2}{2} = -1$$. Therefore the series is convergent on $$x \in (-4,-1)$$ and divergent for $$ x \in \{(-\infty, -4) \cup (-1, \infty)\}$$. Finally, examine the ends of the intervals of convergence: at x = -1 we have $$\sum_{n=0}^{\infty} \frac{1}{n^2+1}$$ and at x = -4 we have $$\sum_{n=0}^{\infty} \frac{(-1)^n}{n^2+1}$$. Since both of those series converge the interval of convergence is $$x \in [-4,-1]$$. 

Operations on power series

A convergent power series in X (ie with c = 0) or x-c is a function of x. This if f(x) is represented by the convergent power series p(x) then f(g(x)) is represented by p(g(x)). The interval of convergence of the original series was $$\vert x \vert < R$$, of the new series it is the interval such that $$ \vert g(x) \vert < R$$. The binomial series expansion of $$\frac{1}{1-x} = 1+x+x^2+x^3+...$$ is convergent for $$\vert x \vert < 1$$. By replacing the argument with g(x) = $$-x^2$$ we get $$\frac{1}{1+x^2} = 1-x^2+x^4-x^6...$$ which is convergent for $$\vert x^2 \vert < 1$$ or $$\vert x \vert < 1$$. 

The Cauchy product

We can add and substract convergent series to obtain another series with radius of convergence at least as large as the samller of the radii of convergence of the original series. We can multiply two convergent series together, to obtain the Cauchy product, thus $$(\sum_{n=1}^{\infty} a_n)(\sum_{n=0}^{\infty} b_n) = \sum_{n=0}^{\infty} c_n$$ where $$c_n = \sum_{j=0}^n a_jb_{n-j} = a_0b_n + a_1b_{n-1}+...+a_nb_0$$. 

Example: the bionmial series for $$\frac{1}{1-x^2} = 1+x^2+x^4+x^6+...$$ converges for $$\vert x \vert < 1$$. We find the series expansion for $$\frac{1}{(1-x^2)^2}$$ by finding the Cauchy product of the series with itself: $$\frac{1}{(1-x^2)^2} = (1+x^2+x^4+x^6+x^8+...)(1+x^2+x^4+x^6+x^8+...)$$ Note that $$a_0 = b_0 = 1$$, $$a_1 = b_1 = x^2$$, $$a_2 = b_2 = x^4$$, $$$a_3 = b_3 = x^6$$, $$a_4 = b_4 = x^8$$. Then $$c_0 = a_0b+0 = 1$$, $$c_1 = a_0b_1+a_1b_0 = 2x^2$$, $$c_2 = a_0b_2+a_1b_1+a_2b_0$$ =$$x^4+(x^2)(x^2)+x^4 = 3x^4$$, $$c_3 = a_0b_3+a_1b_2+a_2b_1+a_3b_0$$ = $$x^6+(x^2)(x^4)+(x^4)(x^2)+x^6 = 4x^6$$, $$c_4 = a_0b_4+a_1b_3+a_2b_2+a_3b_1+a_4b_0$$ = $$x^8+(x^2)(x^6)+(x^4)(x^4)+(x^6)(x^2)+x^8$$ = $$5x^8$$. It follows that $$\frac{1}{(1-x^2)^2} = (1+x^2+x^4+x^6+x^8+...)(1+x^2+x^4+x^6+x^8+...) = 1+2x^2+3x^4+4x^6+5x^8+..$$. The interval of convergence of this series is the same as the original series, ie $$\vert x \vert < 1$$. 

Differentiating power series

We treat a convergent power series as an infinite polynomial in x and differentiate it term by term to obtain another series with the same radius of convergence. 

Example: to find a power series representation for $$\frac{1}{(1-x^2)^2}$$ we diffferentiate both sides of the series for $$\frac{1}{1-x^2}$$. Thus $$\frac{(0)(1-x^2)-(-2x)(1)}{(1-x^2)^2} = \frac{2x}{(1-x^2)^2} = 2x+4x^3+6x^5+8x^7+...$$. Dividing through by 2x we obtain the same result as on the previous example, as expected. 

Integrating power series

We can integrate a convergent power series term by term, making sure to evaluate the constant of integration and obtain another series with the same radius of convergence. 

Example: find a power series expansion for $$tan^{-1}x$$ about x = 0. We have $$\frac{1}{1+x^2} = 1-x^2+x^4-x^6+...$$. Integrating we obtain $$tan^{-1}x = x-\frac{x^3}{3}+\frac{x^5}{5}+...+c$$

Taylor series

Provided $$f^{[n]}(c)$$ exists for all $$n \in \mathbb{N}$$, we can represent $$f(x)$$ as a power series in x-c: $$f(x) = f(c)+f'(c)(x-c)+\frac{f''(c)(x-c)^2}{2!}+\frac{f'''(c)(x-c)^3}{3!}+...$$. This is called the Taylor series of f about c. if c = 0 it is known as a Maclaurin series. The series will converge provided that $$\vert x vert < R$$, where R is the raidus of convergence $$R = lim_{n \rightarrow \infty} \vert \frac{(n+1)f^{[n]}(c)}{nf^{[n+1]}(c)} \vert$$. Remark: we can also write the Taylor series in the form $$f(x+h) = f(x)+hf'(x)+h^2\frac{f''(x)}{2!}+h^3\frac{f'''(x)}{3!}+...$$. This form is useful for approximating functions and solving differential equations. 

Some common Maclaurin series

The following series are convergent for all real x unless otherwise stated. In trigonometric series, x must be in radians. 
* $$e^x = 1+x+\frac{x^2}{2!}+\frac{x^3}{3!}+\frac{x^4}{4!}+... = \sum_{r=0}^{\infty} \frac{x^r}{r!}$$
* $$sin(x) = x-\frac{x^3}{3!}+\frac{x^5}{5!}-...= \sum_{r=0}^{\infty} (-1)^r \frac{x^{2r+1}}{(2r+1)!}$$
* $$cos(x) = 1 - \frac{x^2}{2!}+\frac{x^4}{4!}-...=\sum_{r=0}^{\infty} (-1)^r\frac{x^{2r}}{(2r)!}$$
* $$sinh(x) = x+\frac{x^3}{3!}+\frac{x^5}{5!}+... = \sum{r=0}^{\infty} \frac{x^{2r+1}}{(2r+1)!}$$
* $$cosh(x) = 1 + \frac{x^2}{2!}+\frac{x^4}{4!}+... = \sum_{r=0}{\infty} \frac{x^{2r}}{(2r)!}$$
* $$ln(1+x) = x-\frac{x^2}{2}+\frac{x^3}{3}-... = \sum_{r=1}^{\infty} (-1)^{r-1} \frac{x^r}{r} (-1 < x \leq 1)$$
* $$ln(1-x) = -x-\frac{x^2}{2}-\frac{x^3}{3}-...=-\sum_{r=1}^{\infty} \frac{x^r}{r} (-1 \leq x < 1)$$
Note that ln(x) itself has no Maclaurin series, as it is not defined at x = 0. $$\sqrt[3]{x}$$ has no Maclaurin series as its first derivative is not defined at x=0. 

Example: the expansion of $$e^{\frac{-x^2}{2}}$$ is obtained from that of $$e^x$$ directly: recall $$e^x = 1+x+\frac{x^2}{2!}+\frac{x^3}{3!}+...$$. Plugging in $$\frac{-x^2}{2}$$ for x we obtain: $$1+(\frac{-1}{2}x^2)+(\frac{-1}{2}x^2)(\frac{-1}{2}x^2)(\frac{1}{2})+(\frac{-1}{2}x^2)(\frac{-1}{2}x^2)(\frac{-1}{2}x^2)(\frac{1}{6})$$. Simplifying we get: $$1-\frac{1}{2}x^2+\frac{1}{8}x^4-\frac{1}{48}x^6+...$$. 

Example: by taking logarithms we have, for $$cos(x) > 0$$ ie $$\vert x \vert < \frac{\pi}{2}$$. $$ln(cos(x)) = ln(1-(\frac{x^2}{2!}-\frac{x^4}{4!}+...)) = -(\frac{x^2}{2!}-\frac{x^4}{4!})-\frac{1}{2}(\frac{x^2}{2!}-\frac{x^4}{4!})^2-...$$ = $$-\frac{1}{2}x^2-\frac{1}{12}x^4-\frac{1}{45}x^6-\frac{17}{2520}x^8+...$$ and by differentiating both sides $$tan(x) = x+\frac{1}{3}x^3+\frac{2}{15}x^5+\frac{17}{315}x^7+...$$. This series converges for $$\vert x \vert < \frac{\pi}{2}$$, the same interval of convergence as the original series.

Example: to find the Taylor series for ln(x) about x = 3 we write $$ln(x) = ln[3(1+\frac{x-3}{3})] = ln(3)+ln(1+\frac{x-3}{3})$$. Then $$ln(x) = ln(3)+\frac{x-3}{3}-\frac{1}{2}(\frac{x-3}{3})^2+\frac{1}{3}(\frac{x-3}{3})^3+... = ln(3)+\sum_{n=0}^{\infty}\frac{(-1)^{n-1}}{n}(\frac{x-3}{3})^n$$. 

The remainder term 

Truncating the Taylor series for $$f(x)$$ around c at the term in $$(x-c)^n$$ will leave an error term. This term can be written as the Lagrange reminder, $$E_n$$: $$E_n = \frac{f^{[n+1]}(\zeta)(x-c)^{n+1}}{(n+1)!}$$ where $$\zeta \in [c,x]$$. 

Example: the error in calculating $$e^{-0.5}$$ if the Maclaurin series is truncated at the term in $$x^4$$ is $$\vert E_5 \vert = max(\vert \frac{x^3e^{-\zeta}}{5!} \vert_{x=-.5} \leq \vert \frac{0.5^5}{120} = 0.0002604$$ where the value of $$\zeta$$ that maximizes $$x^5e^{-\zeta}$$ is $$\zeta = 0$$.
