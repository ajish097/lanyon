---
layout: post
title: THE MAX LINES [MAXLN]
link: http://www.spoj.com/problems/MAXLN/
---
<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-MML-AM_CHTML'></script>

This is an interesting problem which can be solved with the help of some elementary level calculus. The whole idea is to use the concept of maximizing a function.

From [Thales theorem](https://en.wikipedia.org/wiki/Thales%27_theorem) we know that the  $$\angle CAB$$ is right angle. 

By [Pythagoras's theorem](https://en.wikipedia.org/wiki/Pythagorean_theorem),

$$\begin{equation} BC^2 = AC^2 + AB^2 \end{equation}$$ 

After rearranging terms we get,

$$AB^2 = BC^2 - AC^2 \tag{1}$$ 

Given,

$$s = AB^2 + AC \tag{2}$$ 

$$BC = 2r \tag{3}$$ 

Substiting (1) in (2) we get,

$$s = BC^2 - AC^2 + AC $$ 

$$s = -AC^2 + AC + BC^2 \tag{4}$$

Let $$AC = \large x$$ and as $$BC^2$$ remains constant, let us replace it with $$\large c$$.

$$s = -x^2 + x + c$$

Differentiating $$\large s$$ w.r.t to $$\large x$$

$$\frac{ds}{dx} = -2x + 1$$

Equating  $$\frac{ds}{dx}$$ = $$\large 0$$ to get the critical points.

$$-2x + 1 = 0$$

$$x =\frac {1}{2}$$

Differentiating once again to check if the critical point gives a local maximum or minimum,

$$\frac{d^2s}{dx^2} = -2 \tag {5}$$

We know that if double differentiation of a function at critical point gives negative value then the given function has local maximum at that critical point.

From (3) we know that $$BC = \large 2r$$ and by putting the critical point from (5) in (4) 

We finally arrive at the formula,

$$\large s = -{0.5}^2 + 0.5 + 4{r^2} $$

$$\large s = 4{r^2} + 0.25\tag {6}$$

With this formula we can now finally convert the derived formula into code.

<script src="https://gist.github.com/ajish097/bac1fcb5e29b441eb6a6ef06ebf3275f.js"></script>
`NOTE : I have not used cout and cin because they are slower compared to printf and scanf.`

Happy coding!!
<hr style="height:2px;border:none;color:#ccc;background-color:#ccc;" />

