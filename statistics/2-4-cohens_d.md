[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Are first babies lighter or heavier than others?

First babies are slightly lighter on average. Cohen's D is approximately -0.089 standard deviations, which is slightly larger (in absolute value) than the effect size for pregnancy length, but still small.

```python
import numpy as np
import math

import nsfg

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

print((firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()))
# (7.201094430437772, 7.325855614973262)

# Copied from page 24
def cohens_d(group1, group2):
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d

cohens_d(firsts.totalwgt_lb, others.totalwgt_lb)
# -0.088672927072602
```
