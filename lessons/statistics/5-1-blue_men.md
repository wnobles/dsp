[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

### Problem
In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters µ = 178 cm and σ = 7.7 cm for men, and µ = 163 cm and σ = 7.3 cm for women. In order to join Blue Man Group, you have to be male between 5’10” and 6’1” (see http://bluemancasting.com). What percentage of the U.S. male population is in this range? Hint: use scipy.stats.norm.cdf.

### Solution
The author imports the `scipy.stats` library and provides the values for σ and µ, which are arguments for `scipy.stats.norm`

```python
import scipy.stats
    
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)
```

This returns a "frozen" random variable object, which can be used to calculate the CDF. The given heights are converted to centimeters since the parameters for the scipy function are given in those units and corresponding CDFs are generated. The two values are then subtracted to show the percentage between the range of given heights.

```python
low = dist.cdf(177.8)
high = dist.cdf(185.4)
percent_between = round((high - low) * 100, 2)
print("Percent between 5'10\" and 6'1\": ", percent_between)
```

The percentage of males in the U.S. between 5'10" and 6'1" is 34.2%.
