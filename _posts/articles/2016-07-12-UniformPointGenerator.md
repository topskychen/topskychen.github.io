---
layout: post
title: Generate Points in a Circle with Uniform Distribution
excerpt: "Generate Points in a Circle with Uniform Distribution."
modified: 2015-04-24
categories: articles
tags: [uniform distribution, points generator]
comments: true
mathjax: true
<!-- share: true -->
---

One naive but wrong idea is to randomly pick the degree and then the radius. We can find out the probability for a point located at $$(\alpha, r)$$ in a circle is $$p(\alpha, r) = \frac{1} {2\pi R}$$, where R is the circle radius, which is different from the uniform probability $$\frac{1} {\pi R^2}$$.

Instead, we can regard a circle composed of infinite triangles. Since we can easily generate uniform-distributed points in a triangle, it is easy to find the correct solution for a circle. See this [answer](http://stackoverflow.com/questions/5837572/generate-a-random-point-within-a-circle-uniformly) for ref.

As a conclusion, the pseudocode of generator is listed as follows:

```python
# assume the circle is centered at (0, 0) with radius 1
from math import pi, sin, cos
from random import random

def generator():
    d = 2*pi*random()
    r = random()+random()
    if r > 1:
    	r = 2-r
    return (r*cos(d), r*sin(d))

for i in range(10):
    print generator()    
    
```