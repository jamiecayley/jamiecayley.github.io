---
layout: post
title:  "Jamie's Math Review Part 1: Functions"
date:   2016-10-06
categories: Calculus
---

Welcome to the first part of my Math Review! The topic of this post will be functions. The majority of the content should be roughly around a pre-calculus level, plus some of the trigonometry I decided to never actually study until now. 

How many parts this will be and what topics will be covered throughout the series is still unclear. As of right now its purpose is to give me a reason to actually care to review several areas of math I haven't done in like 4-6 years and hopefully help me not fail my upcoming calculus exam. The flow of these posts might not be great, as it is mainly intended for my own review and record, but if there is anything you would like me to include or explain in detail please get in touch by emailing me at jamie@theeyrie.co.uk. 

Let X and Y be sets. A function $$f: X \rightarrow Y$$ is a rule which assigns to each x in the domain X exactly one element $$f(x)$$ in the codomain Y; x called the argument of the fuction $$f$$. If no domain is specified we take $$f$$ to have it's maximal domain. 

If $$f(-x) = f(x)$$ for all $$x \in X$$ we say that $$f$$ is an even function. The graph of an even function is symmetric about the y axis. Similarly, if $$f(-x) = -f(x)$$ for all $$x \in X$$ then we say that $$f$$ is an odd function. The graph of an odd function is the same when rotated by 180 degrees about the origin. 

We have the following rules for functions: 
* odd $$\pm$$ odd = odd
* even $$\pm$$ even = even
* odd $$\pm$$ even = neither odd nor even
* odd $$\times$$ odd = even
* even $$\times$$ even = even
* even $$\times$$ odd = odd

A function is periodic if there is a $$T \in \mathbb{R}$$ such that if $$0 < T < \infty, f(x+T) = f(x)$$ for all $$x \in X$$. Periodic functions are said to exhibit translational symmetry. 

###Trigonometric functions

The sine and cosine functions have range $$[-1,1]$$, so a function of the form $$r sin(nx+\alpha)$$ has range $$[-r,r]$$. r is the amplitude and the period is $$\frac{2\pi}{n}$$. The phase is $$\alpha$$. The range of the tangent function is $$\mathbb{R}$$. 

###The exponential function

The exponential function exp(x) (also denoted $$e^x$$) can be defined as the sum of the convergent series: $$exp(x) = 1+x+\frac{x^2}{2!} + \frac{x^3}{3!} + ...$$. $$e^x$$ can also be defined by $$\lim_{n \rightarrow \infty} (1 + \frac{x}{n})^n = e^x$$

###Hyperbolic functions 

Any function $$f$$ defined on a domain which is symmetrical about the origin can be expressed as the sum of an odd function and an even function as follows: $$f(x) = \frac{1}{2}(f(x)-f(-x))+\frac{1}{2}(f(x)+f(-x))$$. Taking $$f(x) = e^x$$ we obtain the hyperbolic functions: $$sinh x = \frac{e^x-e^{-x}}{2}$$ and $$cosh x = \frac{e^x+e^{-x}}{2}$$. tanhx, cosechx, sechx, and cothx are defined as expected. The hyperbolic functions have simular properties to the trigonometric functions (eg $$cosh^2x-sinh^2x = 1, 1-tanh^2x = sech^2x, coth^2x -1 = cosech^2x$$). Also note that $$coshx+sinhx = e^x$$ by construction. 

Osborne's rule: to convert a trig identity into a hyperbolic one replace cos by cosh and sin by sinh but whenever $$sin^2$$ occurs either explicitly or implicitly, change the sign. Examples: $$sin(A+B) = sin(A)cos(B)+cos(A)sin(B)$$ becomes $$sinh(A+B) = sinh(A)cos(B)+cosh(A)sinh(B)$$, $$cos(A+B) = cos(A)cos(B)-sin(A)sin(B)$$ becomes $$cosh(A+B) = cosh(A)cosh(B)+sinh(A)sinh(B)$$, $$tan(A-B) = \frac{tan(A)-tan(B)}{1+tan(A)tan(B)}$$ becomes $$tanh(A-B) = \frac{tanh(A)-tanh(B)}{1-tanh(A)tanh(B)}$$. 

The inverse hyperbolic functions are degined on the given domains and can be written in logarithm form: 
* $$sinh^{-1}x = ln(x+ \sqrt{x^2+1}), x \in \mathbb{R}$$
* $$cosh^{-1}x = ln(x+ \sqrt{x^2-1}), x \in [0, \infty)$$
* $$tanh^{-1}x = \frac{1}{2} \frac{ln(1+x)}{(1-x)}$$

###Limits

The limit of $$f(x)$$ as $$x$$ tends to $$a$$ is a number $$l$$ such that we can make f(x) as close as we like to $$l$$ by taking $$x$$ very close (but not equal) to $$a$$. 

Some important limits for trig functions: for any acute angle x, sin x < x < tan x. Dividing through by sin x, $$1 < \frac{x}{sinx} < \frac{1}{cosx}$$ so $$cos x < \frac{sinx}{x} < 1$$. As $$x \rightarrow 0, cosx \rightarrow 1$$ so $$\frac{sinx}{x} \rightarrow 1$$. It can be deduced that $$lim_{n \rightarrow 0} \frac{sin(x)}{x} = 1, lim_{x /rightarrow 0} \frac{1-cos(x)}{x} = 0, lim_{x \rightarrow 0} \frac{tan(x)}{x} = 1$$. 

Limits for exponential and logarithmic functions: As mentioned above, $$e^x = lim_{n \rightarrow \infty} (1+ \frac{x}{n})^n$$. Letting $$n = \frac{1}{p}$$ we have $$e^x = lim_{p \rightarrow 0}(1+px)^{1/p}$$. Since the inverse function of $$(1+px)^{1/p}$$ is $$\frac{x^p -1}{p}$$ the inverse function of $$e^x$$ can be expressed as $$ln x = lim_{p \rightarrow 0}(\frac{x^p -1}{p})$$. 

###Curve sketching

To sketch the graph of a function follow these steps:
* set y = 0, x = 0 to find the intersections with the x axis and y axis respectively. 
* when the denominator of a rational function approaches zero then $$y \rightarrow \pm \infty$$. At such value of x there is a vertical asymptote. 
* Find $$z = lim_{x \rightarrow \pm \infty}f(x)$$. If the limit exits, there is a horizontal asymptote at y = z.
* If the numerator is of higher degree than the denominator, divide through to find oblique asymptotes. 
* if the function is even then there is symmetry about the y-axis, if the function is odd then there is 180 degree rotatiosnal symmetry about the origin. If the function is periodic the function will show translational symmetry. If the function is self-inverse then there is symmetry about y=x. 
* Turning points can be found by the usual calculus methods: solve $$f'(x) = 0$$. The second derivative $$f''(x)$$ is positive at a minimum, negative at a maximum and 0 at a point of inflection. 
 
 
