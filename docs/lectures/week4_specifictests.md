## Specific Hypothesis Tests

**This will be a dynamic resource**

### Binomial test

### t-test

An assumption of the t-test is that the observations/data or sampling distribution (in case of sample means, etc.) should be normally distributed.

### Tests for normality

There are several tests for normality, and they all use different aspects of the sample data to test for the goodness-of-fit of the sample data to a normal distribution. These tests each will have a certain *power* (the ability to detect an actual effect or difference) dependent on characteristics of the data (if the data is skewed/asymmetric or symmetric; if the data has short or long tails). Simulations and power-analyses have been done in many studies to compare these tests for types of data characteristics ([an example](https://www.jstor.org/stable/pdf/2285889.pdf?casa_token=_dU_ybc4AbcAAAAA:cOyxqZdBNzG_Ru1lIJy2ify0-lfSnRNnxx_FvKbd2--qVXIbmkYsdoh9ymiXbYmmQXrkEbtqy10nq6uXoHL8BnoGftsmmeGqYhFxF9pk4CN7IVHBdjw)).

You may astutely point out that given the Central Limit Theorem and large enough sample sizes, as well as often only having a single sample, we may not need a test the normality for samples and sample summary statistics. (However, tests for normality will be important again later for residuals in regression)

In class, we showcased one test in particular, the **Shapiro-Wilk** test is a type of an analysis of variance procedure, and tends to show high power which is why it was highlighted.

#### Shapiro-Wilk
**Shapiro-Wilk** Test for Normality is used to test if a sample is normally distributed (i.e. follows a Gaussian distribution).

The *null hypothesis* of the **Shapiro-Wilk** test is that the data set/sample is normally distributed. Rejection of the null hypothesis would suggest that the sample departs from the normal distribution.  

The assumptions of the test are

A limitation of the **Shapiro-Wilk** test is that as the dataset being evaluated gets larger, the test becomes more sensitive to small variation within the sample and with greater probability may reject the null hypothesis when it shouldn't. (This is one reason we can't use sample sizes greater than 5000 with the R function.). [Another limitation](https://www.jstor.org/stable/pdf/2333709.pdf?casa_token=ygMIq4tzDx4AAAAA:ixUNznd8CpdcAKn5DSKXxDN3Umqm88ME0ka4LognrujLGAn8Rz5Jix75eYVKRup1dwnkP6kEGJEqNik6ht3tgRETvoF0QvyUj9-5Jy3fn3BCw7QZ4N8) is that the test is sensitive to outlier values

As with all hypothesis tests, you should use some "outside" validation as well when asking if your sample is normally distributed.
  * Is it continuous data?
  * Is it independent data?
  * When plotted, does the sample visually follow a symmetric, bell-shaped curve?
  * Can you curve fit a reference normal distribution parameterized by the sample mean and standard deviation to the data?
  * Q-Q or (quantile-quantile) Plot (`qqnorm` function in R) shows a straight line
  * Is the skew of the distribution 0 or almost 0? (e.g. checking symmetry)

The R function `shapiro.test()` can be used for this.

### Kolmogorov-Smirnov test

Test for continuous distributions, specifically looking at the "distance" between two distributions (between two empirical/observed distributions of two samples; or between an empirical distribution and a cumulative distribution function for a reference continuous distribution).

This test can be performed as a one- or two-sample test. As a one- sample test, it compares a sample of data against a defined continuous distribution function. In this case, the null hypothesis is that the distribution that generated the sample data is the same distribution that is defined.

As a two-sample test, it compares two samples of data to each other. The null hypothesis is that the distribution which generated the two samples of data is the same. (e.g., the two samples are distributed according to the same continuous distribution.)

The R function `ks.test()` can be used for this.
