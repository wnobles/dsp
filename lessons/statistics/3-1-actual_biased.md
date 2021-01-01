[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

### Problem
The class size paradox problem also occurs when surveying children to determine family size. The NSFG respondent variable `numkdhh` is used to construct the actual distribution for the number of children under 18 in the respondents' households. Next, the biased distribution is computed, and the actual and biased distributions are plotted. Lastly, their means are computed.

### Solution
The inspection paradox occurs in the example of estimating the average family size when surveying children because there are more chances to survey children with more siblings. This results in a biased distribution. The goal of this exercise is to first compute the probability mass function for the number of children per household.

    pmf = thinkstats2.Pmf(resp.numkdhh, label='actual')

The PMF is then plotted.

    thinkplot.Pmf(pmf)
    thinkplot.Config(xlabel='Number of Children', ylabel='PMF')

![Image of actual PMF](https://github.com/wnobles/dsp/blob/master/lessons/statistics/CEF0D171-2722-4920-8752-5E3188F1D62E_4_5005_c.jpeg)

Again, the functions relevant in the nsfg and first files are useful for solving this problem, in addition to the files, thinkstats2 and thinkplot, which have been imported. Next, the biased PMF is calculated using the BiasPmf function and is plotted with the unbiased PMF to illustrate the various probabilities associated with the number of children in a household.

    biased_pmf = BiasPmf(pmf, label='biased')

    thinkplot.PrePlot(2)
    thinkplot.Pmfs([pmf, biased_pmf])
    thinkplot.Config(xlabel='Number of Children', ylabel='PMF')

![Image of actual/biased PMF](https://github.com/wnobles/dsp/blob/master/lessons/statistics/CFBC9A01-9B7B-42EA-BDC5-EB60F9437A5E_4_5005_c.jpeg)

Finally, the average number of children per household is calculated for the both the unbiased and biased distributions.

    print('Actual mean: ', pmf.Mean())
    print('Observed mean: ', biased_pmf.Mean())
