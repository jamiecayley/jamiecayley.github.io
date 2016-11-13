---
layout: post
title:  "Jamie's Math Review Part 2: Derivatives"
date:   2016-10-20
categories: Calculus
---

Welcome to the second part of my Math Review! The topic of this post will be derivatives (the majority of them uninteresting) and the one part of calculus I actually think is pretty cool: Leibniz's rule to find the nth derivative of a product of two functions.

Let f be a function defined in some neighbourhood of a point $$(x, f(x))$$. If the limit $$lim_{\delta x \rightarrow 0} \frac{f(x) - f(a)}{x-a}$$ exists then f is said to be differentiable at $$(x, f(x))$$. Alternatively $$f'(a) = \lim_{x \rightarrow a} \frac{f(x) - f(a)}{x-a}$$

Derivatives of hyperbolic functions 

From the definitions of sinh and cosh in terms of exponentials it follows that $$\frac{d}{dx} sinh(x) = cosh(x)$$ and $$\frac{d}{dx} cosh(x) = sinh(x)$$. Using the quotient and composite function rules we can obtain the following derivatives:
* $$\frac{d}{dx} sinh(ax+b) = a*cosh(ax+b)$$
* $$\frac{d}{dx} cosh(ax+b) = a*sinh(ax+b)$$
* $$\frac{d}{dx} tanh(ax+b) = a*sech^2(ax+b)$$
* $$\frac{d}{dx} coth(ax+b) = a*cosech^2(ax+b)$$
* $$\frac{d}{dx} sech(ax+b) = a*sech(ax+b)+tanh(ax+b)$$
* $$\frac{d}{dx} cosech(ax+b) = a*cosech(ax+b)coth(ax+b)$$

Derivatives of inverse functions

By the chain rule ($$\frac{d}{dx} f(g(x)) = f'(g(x)) \cdot g'(x)$$) it follows that $$\frac{d}{dx} f^{-1}(x) = \frac{1}{f'(f^{-1}(x))}$$ 

For example, let $$f(x) = sin(x)$$. Then $$f^{-1}(x) = arcsin(x), f'(x) = cos(x)$$. Then $$\frac{d}{dx}f^{-1}(x) = \frac{1}{f'(f^{-1}(x))} = \frac{d}{dx} arcsin(x) = \frac{1}{cos(arcsin(x))} = \frac{1}{\sqrt{1-x^2}}$$ Below is a list of some common inverse an hyperbolic derivatives: 
* $$\frac{d}{dx} arcsin(x) = \frac{1}{\sqrt{1-x^2}}, x \in (-1,1)$$
* $$\frac{d}{dx} arcos(x) = \frac{-1}{\sqrt{1-x^2}}, x \in (-1,1)$$
* $$\frac{d}{dx} arctan(x) = \frac{1}{1+x^2}$$
* $$\frac{d}{dx} arcsinh(x) = \frac{1}{\sqrt{1+x^2}}$$
* $$\frac{d}{dx} arcosh(x) = \frac{1}{\sqrt{x^2-1}}, x \in (1,\infty)$$
* $$\frac{d}{dx} archtanh(x) = \frac{1}{1-x^2}, x \in (-1,1)$$

Parametric differentiation

If $$x=x(t)$$ and $$y=y(t)$$ then $$\frac{dy}{dx} = \frac{dy/dt}{dx/dt}$$ provided $$dx/dt \neq 0$$. 

Example: find $$\frac{dy}{dx}$$ when $$x = t^3-t$$ and $$y = 4-t^2$$. $$dx/dt = 3t^2-1, dy/dt = -2t$$. Therefore $$\frac{dy}{dx} = \frac{dy/dt}{dx/dt} = \frac{-2t}{3t^2-1}$$. 

Implicit differentiation 

Examples: 

$$\frac{dy}{dx} sin(x)+y*cos(x) = 2x^2-3y^2 \frac{dy}{dx}$$. Hence $$\frac{dy}{dx} = \frac{3x^2-y*cos(x)}{sin(x)+3y^2}$$. 

Given $$xy+y^2 = 2x, y = y(t)$$ find $$\frac{dy}{dx}, \frac{d^2y}{dx^2}$$. $$xy'+y+2yy' = 2$$. Therefore $$y' = \frac{2-y}{x+2y}$$. $$y'' = \frac{y-2-(x+4)y'}{(x+2y)^2}$$ so $$y'' = \frac{-8}{(x+2y)^3}$$. 

Logarithmic differentiation

if $$ y > 0, y = f(x)$$ becomes $$ln(y)-ln(f(x))$$ which differentiates to $$\frac{1}{y}\frac{dy}{dx} = \frac{1}{f(x)}f'(x)$$. 

Example: let $$f(x) = a^x, a > 0$$. Then $$ln(f(x)) = x*ln(a)$$ so $$\frac{f'(x)}{f(x)} = ln(a) \rightarrow f'(x) = a^xln(a)$$. 

Leibniz's rule

Let $$f$$ and $$g$$ be n times differentiable functions. let $$h$$ be defined by $$h(x) = f(x)g(x)$$. Then $$h$$ is also n times differentiable and $$h^{(n)}(x) = \sum_{r=0}^n \binom{n}{r}f^{(r)}(x)g^{(n-r)}(x)$$, where $$\binom{n}{r} = \frac{n!}{r!(n-r)!}$$. 

Example: find $$\frac{d^3(x^3e^{2x})}{dx^3}$$. Let $$f(x) = x^3, g(x) = e^{2x}$$. Then $$f'(x) = 3x^2, f''(x) = 6x, f'''(x) = 6$$ and $$g'(x) = 2e^{2x}, f''(x) = 4e^{2x}, f'''(x) = 8e^{2x}$$. Note that $$\binom{3}{0} = 1, \binom{3}{1} = 3, \binom{3}{2} = 3, \binom{3}{3} = 1$$. Using Leibniz's rule we obtain $$\frac{d^3(x^3e^{2x})}{dx^3} = x^3*8e^{2x}$$+$$3*3x^2*4e^{2x}$$+$$3*6x*2e^{2x}$$+$$6*e^{2x} = 2e^{2x}(4x^3+18x^2+18x+3)$$. 

Radius of Curvature

The radius of curvature of $$y = f(x)$$ is defined as $$\rho = \frac{[1+(dy/dx)^2]^{2/3}}{\vert d^2y/dx^2 \vert}$$. The curvature is defined to be $$\kappa = 1/\rho$$. 

L'Hopital's rule

Let f and g be differentiable real valued functions with $$f(a) = g(a) = 0$$. The $$lim_{x \rightarrow a} \frac{f(x)}{g(x)} = \frac{f'(a)}{g'(a)}$$ provided $$g'(a) \neq 0$$. If $$f'(a) = g'(a) = 0$$ we can repeat the process and obtain $$lim_{x \rightarrow a} \frac{f(x)}{g(x)} = \frac{f''(x)}{g''(x)}$$. If $$lim_{x \rightarrow a} f(x) = lim_{x \rightarrow a} g(x) = \infty$$ then $$lim_{x \rightarrow a} \frac{f(x)}{g(x)} = \frac{f'(a)}{g'(a)}$$. 

Related rates of change

If x and y are both functions of t then if $$z = f(x,y)$$ we have $$\frac{dz}{dt} = \frac{dt}{dx} \frac{dx}{dt} + \frac{df}{dy} \frac{dy}{dt}$$. 
Small changes in dependent variable: $$\Delta y \approx \frac{dy}{dx} \Delta x$$. 


