# Week 2 -- Part 1

## Week 2 Learning Objectives

By the end of Weeks 2 & 3, you will be able to

* Compare and contrast discrete and continuous distributions
* Describe the characteristics of and graphical appearance of probability distributions important for biology.
* Determine what probability distribution satisfies the necessary requirements given information and assumptions about data/processes.
* Use sample data to find actual results and use probabilities to find expected results.
* Describe the relation between population-based and sample-based information.
* Use estimation to infer or estimate the value of a population parameter given sample data.
* Differentiate between unbiased and biased estimators.
* Construct confidence intervals for estimated parameters.
* Describe the difference between the non-parametric and parametric bootstrap. Apply the bootstrap in confidence interval estimation and to compare two data sets.
* Determine minimum sample sizes necessary for estimation.
* Develop the ability to identify the null and alternative hypotheses when given some claim about a population
* Use sample data to test hypotheses or claims made about population parameters and state the conclusions in both technical terms (of rejecting or failing to reject the null hypothesis) and simple terms.
* Use hypothesis testing to test whether real and expected results differ significantly.
* Employ multiple hypothesis testing correction when appropriate.
* Accurately define, use, and compare p-values.

## Sample vs Population

### Why Sample?
Last week, we discussed that in biology data analysis projects, we are often, if not all the time, working with sample data rather than population data. There are several reasons why we use sample data rather than population data.
* Samples can be studied more quickly than populations. Consider as an example the clinical trials for the COVID-19 vaccines. Also consider that it may be impossible within finite time to observe every organism within a given species.
* A study of a sample is less expensive than studying an entire population.
* A census, or a study of entire populations, is often impossible. This could be due to a destructive experiment that depletes materials or sacrifices animal models; another potential example of this would be cohort/prospective observational studies. i.e. a prospective study of men with prostate cancer will select individuals based on same risk factor, but has no way of knowing or observing every man ever who will develop prostate cancer.
* Sample results may be more accurate than population-studies because more time and resources can be spent on training individuals who perform observations or experiments in sample studies or higher-quality procedures may be used since fewer procedures overall are needed.
* Sample studies allow for the use of probability methods to estimate the error or confidence intervals in statistical findings.
* Sampling can be used to select individuals in a way that reduces heterogeneity. Consider a lab who studies Diabetes. Type I and II have different causes, mechanisms, management, etc. and therefore are separated when studied. If combined, the sample would be heterogenous and specific inferences/conclusions would be more difficult.

### Target vs Sampled Populations
There are also two types of populations which we did not distinguish from each other last week, but we will now. Target populations are the overall population to which we wish to generalize, but we often sample/select/draw individuals from sampled populations.

A sample is *representative* of the *target population* if the distribution of important characteristics in the *sampled population* is the same as that in the *target population*.

So while ideally, we would wish to sample from the *target distribution* at all times, due to the nature of clinical research (especially for rare diseases), often patients donate samples to a hospital system and are randomly selected from the hospital system, not according to what a specific investigator wishes to study; Their inclusion isn't determined by their inclusion in the target population, but rather because the patient was part of the hospital system, donated at a specific time point, and then met some entry criteria for the study. So in such an example, an individual is selected from a  *sampled population*.  In this way, *sampled populations* may differ from *target populations* as it is difficult to list or prioritize all the important characteristics, unless a lot is known about a disease/process being studied. These judgments are clinical, not statistical. And while statistically we may be able to compare or quantify the similarity of distributions, again, a lot has to be known about the *target population* to actually do this.

### Parameters vs Statistics

Any numerical measurement describing some characteristic of a population, such as measures of central tendency and variation, is a fixed, invariant characteristic true of that population and is called a *parameter*. There are many parameters for each population because there are multiple numerical measurements for each characteristic and because there are lots of characteristics for a population.

Any numerical measurement describing some characteristic of a sample is called a *statistic*, and while fixed for any given or observed sample, a statistic will likely vary among all possible samples. For every parameter a population has, there is a corresponding statistic in the sample that will be used to make inferences about the population.

## Random Variables and Probability Distributions
A characteristic of interest is a *variable*. The value of the characteristic is likely to vary from one individual to another due to inherent biological variation as well as errors made in measuring or recording the value of the characteristic. Due to this variation, in studies where samples are randomly selected, we call variables *random variables*. By technical definition, a *random variable* is a variable that has a single numerical value, determined by chance, for each outcome of a procedure.  We can summarize the values of a random variable in a frequency distribution called a *probability distribution*. We previously saw *frequency distributions* when we discussed summarizing the values of an observed categorical variable, where for every value, you have the corresponding number of times (or a normalized ratio) that that value occurred. In a probability distribution, we now provide a probability that the random variable will take on any given value or range of values. By technical definition, a *probability distribution* is a description that gives the probability for each value of the random variable, expressed as a table, formula, or graph. For example, if 8505 US high school students are surveyed and asked to report how many times they took the bus to school in the previous month, the value that this random variable can take on is a number from 0 to 31, and each instance or outcome for each student is one of these numbers only, but not any other value. If 7200 report at least once, what is the probability of a high school student in the sample taking the bus at least once? What is the probability of a high school student in the sample taking the bus 0 times? What is the probability distribution?

### Requirements of every probability distribution

1.  There is a *numerical* (not categorical) random variable and its number values are associated with corresponding probabilities
2.  The sum of the probabilities for every value that the random variable can take on is 1.
3.  0 is less than or equal to the probability of every value that the random variable can take on. Additionally, 1 is greater than or equal to the probability of every value that the random variable can take on.


### Discrete vs Continuous
There are two major types of (univariate) random variables and probability distributions. These are *discrete* and *continuous*.

A *discrete* random variable has a collection of values that is finite or countable, and *discrete* probability distributions are used to summarize the values for a *discrete* random variable.

A *continuous* random variable has infinitely many values, and the collection of values is not countable, and *continuous* probability distributions are used to summarize the values for a *continuous* random variable.


### PMF vs PDF vs CDF

A *probability mass function* (PMF) returns the probability that a random variable is equal to a specific value for discrete distributions.

A *probability distribution function* (PDF) defines the probability distribution for a continuous distribution.

A *cumulative distribution function* (CDF) returns the probability that a random variable is less than or equal to a specific value, for both discrete and continuous distributions.


## Lecture Note Resources

* Basic & Clinical Biostatistics (5th Edition), by Susan White, published by McGraw Hill
* Biostatistics for the Biological and Health Sciences (2nd Edition), by Marc Triola, Mario F. Triola, & Jason Roy, published by Pearson
* Modern Statistics for Modern Biology (2019), by Susan Holmes & Wolfgang Huber, published by Cambridge University Press
