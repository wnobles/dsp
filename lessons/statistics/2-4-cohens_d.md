[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

### Problem
The variable `totalwgt_lb` is used to investigate whether first babies are lighter or heavier than others, and then Cohen’s effect size computed to quantify the difference between the groups. Lastly, the difference in pregnancy length is observed.

### Solution
The author provides two files, nsfg and first, which are imported and provide methods for solving the problem. The variable, `totalwgt_lb` can be found in the nsfg.py file and is a transformation of two other values regarding birth weight. Also, a function in first.py that the author has provided reads in pregnancy data, partitions the data into firstborn babies and others, and returns a dataframe, so the variable `totalwgt_lb` is used along with methods in the Pandas library to determine which group of babies is lighter or heavier on average.


```python
{
firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()
}
```

The difference in birth weight (in pounds) is then calculated by subtracting the two values.

    firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean()

The negative result indicates that firstborn babies are slightly lighter than others. Cohen's *d* takes into account the standard deviation, and the author provides a function in the Jupyter Notebook to calculate the effect size. Both values for average birth weight are passed into the function, and the standard deviation is returned.

    CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)

The negative result means that the "others" group is slightly heavier at birth than the "firsts" group. This can also be related to the difference in pregnancy length by observing that a longer pregnancy seems to correlate with a slightly lower birth weight. However, the Cohen Effect Size is very small in both cases and is usually considered not statistically significant.
