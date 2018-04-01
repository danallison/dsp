[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

```python
import scipy.stats

cm_per_inch = 2.54
five_ten = (5 * 12 + 10) * cm_per_inch
six_one = (6 * 12 + 1) * cm_per_inch

mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

between = dist.cdf(six_one) - dist.cdf(five_ten)

print("Approximately {0}% of U.S. males are eligible to join Blue Man Group.".format(round(between * 100, 1)))
# Approximately 34.3% of U.S. males are eligible to join Blue Man Group.
```
