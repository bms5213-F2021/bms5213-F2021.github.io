# Week 1 -- Part 2

## Week 1 Learning Objectives

By the end of Week 1, you will be able to

* Describe the steps of a data analysis project
* Define the types of data analytic questions and classify examples in biology research
* Recognize biases present in data due to sampling procedure or analysis
* Distinguish between different types of data you will encounter in biology research and classify examples in the correct group
* Define and calculate descriptive statistics for central tendency and variability or dispersion.
* Compare and contrast the utility of different types of plots for summarizing data clearly and accurately.

## Data

Data are collections of observations, measurements, variables, or characteristics for a group of individuals (people, animals, plants, cells, molecules, etc.) where this group is a sample or subset of individuals from a larger population (or the entire group of individuals of interest).

Within the field of biology, data sets are often very *high-dimensional* meaning that there are many variables which can be measured or observed and which may interact with each other. Additionally, each measurement is taken at a specific time point and perhaps within a specific location or cell type; this adds further dimensionality to data such that not only can multiple variables be measured, but each variable could be measured across a *temporal range* and across complex *spatial contexts*. Also, biological data sets often are *heterogeneous* containing variables which are different from each other -- including, but not limited to nucleic acid and protein sequences, counts, phenotypic images or classifications, batch factors, relative fluorescence units, rates, spatial coordinates, interaction partners or networks, etc. Another consideration of biological data is that data are *noisy* as measurements are acquired by imperfect instruments and susceptible to random and systemic errors. For example, sequencing technologies have associated sequencing error rates; machines have to be calibrated and may be susceptible to drift in readings over time; air currents or humidity affects readings from an analytical balance, etc. Further, the *size of biological data sets* ranges from very small samples to very large samples which have vastly increased over the years as technologies improve and allow for faster, more efficient, and less costly generation of "big data". So depending on the specific data, the dataset may have many individuals or may have very few individuals, complicating downstream analysis. Finally, data may be *sparse or missing* and require researchers to take steps to exclude certain variables or impute/infer the missing values from other information and models.

### Types of data

There are two main general types of data. These are **numerical data** and **categorical data**.

**Numerical** variables are those which quantitatively represent some count or measurement and for which arithmetic operations such as addition or averaging would be appropriate.

Numerical data are further subdivided into *discrete* and *continuous* data. Count data are discrete data or values which only take on integer/whole number values. Examples of count data may be number of individuals in a study sample, the number of colonies on a microbiology plate, the number of interaction partners observed for a specific protein following co-IP and mass spec. Continuous data are data for which the value may be any real numerical value contained in some range, including decimal values. Examples of continuous data include heights, relative fluorescence units, or the binding affinity between interacting proteins.   

**Categorical** variables are those which qualitatively characterize, categorize, or group individuals based on names, labels, or some attribute. Note categorical variables may take on numerical values, but not be numerical data. Consider the proband IDs from the [Halldorsson et al study](https://raw.githubusercontent.com/bms5213-F2021/bms5213-F2021.github.io/master/docs/resourcedev/papers/dnm_halldorsson.pdf); these proband IDs were numerical values but just as easily could have been represented by combinations of letters or names of fruits or some other non-numerical label. Further, in phenotypic studies, sequencing, or surveys, often numerical labels may be assigned to a specific phenotype, allele (0 = Reference allele, 1 = Alternate allele), or response (0 = "No", 1 = "Yes"). Again, these numbers serve as labels, not true numerical variables. We will often care about the distribution of categorical variables, but this looks like a list, table, pie chart, etc. reporting each category and the count or percent of individuals represented in each category.  

Categorical data are further subdivided into *nominal* and *ordinal* data. Nominal data are purely qualitative data consisting of names, labels, or categories which cannot be reasonably arranged in some order (such as low to high). Examples include flower petal color or yes/no/undecided responses. Ordinal data are data which can be ranked or arranged in some order, but they are not true quantitative variables. Additionally, intervals between consecutive ranks are not necessarily identical and therefore use of subtraction to compare differences in responses to try to find a magnitude in difference would be meaningless. Only relative, qualitative comparisons are appropriate. Examples of this include A,B,C, grades, review stars, or scales such as "strongly disagree", "disagree", "agree", "strongly agree".  

Understanding the differences in data types and identifying the correct type for a given variable is important for describing the data, visualizing the data, applying statistical models or analyses to the data, picking probability distributions applicable to the data, or interpreting patterns observed within data.  

### Collecting data

As mentioned earlier, data are collections of observations for a group of individuals or a sample which is just a subset of a larger population (or the full set of individuals). A census is used to collect data from every member of the population, but especially in biostatistics, researchers work with sample data originating from the subset of individuals who were selected from the larger population. Collecting data is the process of sampling or selecting these individuals and obtaining the appropriate variable measurements/observations.  

Data may be collected through *observational* studies or *experiments*. In *observational* studies, individuals are observed and data collected but these individuals are disturbed as little as possible and those collecting the data do not attempt to influence the outcomes or responses. What data analysis question types are appropriate for observational studies? *Experiments* deliberately impose some treatment on individuals in order to observe the outcomes or responses. This data may be compared to control or purely observational data. What data analysis question types are appropriate for experimental data? A third study design is a *meta-analysis* which considers related but independent studies together in order to better estimate the strength of a relationship or more precisely state a conclusion, based on the previous research. An example of a meta-analysis is [this study from Jeff Leek and Leah Jager](https://github.com/bms5213-F2021/bms5213-F2021.github.io/raw/master/docs/resourcedev/papers/metaanalysis.pdf) where they considered and summarized previous studies which aimed to estimating the number of false discoveries in published medical research.   

#### Sampling Design
Because it would be intractable to perform both observational studies and experiments on entire populations, sampling schemes or designs are required to choose the sample from the population which will be observed or experimented on. Then **statistical inference** will be used to reach or infer conclusions about a population based on what is known from the sample. Poor sampling may lead to incorrect conclusions about the population.

* *Simple random sample*: Every possible size n combination of individuals in the population has an equal chance of being chosen, and a single combination is chosen at random. This gives every individual an equal chance of being chosen and every combination of individuals an equal chance of being chosen.
* *Random sample*: Every member of the population has an equal chance of being selected and n individuals are chosen.
* *Systematic sample*: Order individuals in the population. Select some starting point and then select every kth element in the population. For example, in a neighborhood, the first house is chosen by random number generator, and then every 4 houses down the row is also visited.
* *Convenience sample*: Utilizes data which are very easy to get. For example, an internet poll. (This example is a *voluntary response sample* which lets individuals choose whether to participate or not.)
* *Stratified sample*: The population is stratified or subdivided into groups based on some characteristic, and then within each group, individuals are randomly sampled. For example, individuals may be stratified by race or ethnic group.
* *Cluster sample*: Divide the population into clusters (based on some characteristic or location), randomly choose some k number of clusters, and then every individual within that cluster is chosen. For example,

#### Observational Design
*Observational* studies are often further classified as (1) *Descriptive or case-series*, (2) *Case-control or retrospective studies*, (3) *Cross-sectional or prevalence studies*, or (4) *Cohort or prospective studies*.

1. *Descriptive or case-series* studies are related to descriptive data science questions in that all that is being done is describing an observed phenomena or characteristics without attempting to interpret the observation.
2. Within a *Case-control or retrospective* study, data are collected from a **past time point** through examining medical records, conducting interviews, etc. These studies often begin with the absence or presence of some outcome and look backward in time attempting to identify possible causes or risk factors indicated in the records of individuals with the outcome but not indicated in the records of individuals without the outcome (controls).
3. Within a *Cross-sectional* study, data are observed, measured, and collected at a **single point in time**, not over a period of time. These studies are often designed to ask "What is happening right now?".
4. Within a *Cohort or prospective* study, data are collected **in the future** from groups of individuals enrolled in the study and who share common factors. These groups are termed cohorts and remain in the study for an extended period of time. Individuals are selected based on having some defining characteristic and are followed over a certain period of time to observe the effect of the characteristic. These studies are often designed to ask "What will happen?"

#### Experimental Design

Good experimental design utilizes *replication*, *blinding*, and *randomization*. *Replication* is the process of carrying out the experiment on more than one individual. *Blinding* keeps an individual from knowing whether they are part of the treatment or control groups. *Double blinding* means that whoever is dispensing of the treatment also doesn't know to which group the individual belongs.

There are 4 experimental design methods utilized to *randomize* which individual is a control and which individual is "treated". These designs aim to reduce or eliminate the effect of *confounder variables*. *Confounders* are variables which are more likely to be present in one group than another (potentially due to chance or study design) and if the variable is related to the outcome of interest, its presence potentially confuses or confounds the results and interpretations. Is it the presence of this variable or the presence of treatment that causes the difference between control and treatment? To what extent is it contributing to the difference? While statistical methods do control for known confounders to an extent (by considering the variable as a covariate which we will discuss in detail later), eliminating or majorly reducing their effect in study design is preferable.

1. *Completely randomized* designs use randomness or random selection to assign subjects to treatment groups.
2. *Randomized block* designs form blocks or groups of subjects who exhibit some similar characteristic (for example: men vs women). Then, within each block, random selection is used to assign subjects to treatment groups. Whatever characteristic is used to form the blocks controls for that variable, eliminating it as a confounder of the results.
3. *Matched pairs* designs may get measurements from the same subjects before and after some treatment, using the before measurement as a baseline; matched pairs may alternatively match a control participant with a treatment participant based on a broad list of characteristics or utilize twins and give each twin a different treatment. Generally, in some way, the data is "matched" so as to eliminate possible confounders.  

### Biases in data or a statistical study

A statistical study is biased if its design systematically favors certain outcomes over others.

#### From collection/sampling

* *Random sampling error*: occurs when the sample has been selected with a random sample, but there is a discrepancy between the sample and the overall population completely by chance.
* *Nonsampling error*: occurs as the result of human error such as incorrect data entry, computation errors, false data was provided
  * *Response bias* , a non-sampling error, occurs when an individual responds in the way that they think would be more favorable to the researcher, rather than offering the truth.
  *Nonresponse* occurs when a selected individual cannot be contacted or refuses to cooperate or fails to answer/measure some subset of questions/variables. Besides in surveys, this may occur in biology if a mouse keeps biting a researcher or refuses to participate certain phenotypic studies.
* *Nonrandom sampling error*: occurs as the result of using a sampling method that is not random, such as a convenience sample or a voluntary response sample
  * An internet poll which allows participants to opt-in will likely be biased because people with strong opinions are most likely to respond and may not be representative of the entire population.
  * *Undercoverage* occurs when some groups in the population are left out of the process of choosing the sample. This could be the result of a convenience sample. Consider a screening study where mutations were randomly generated in a fly population and then the phenotypic effects were assessed. Any lethal mutations or recessive mutations may not be included in the sampling process. In surveys, this may occur if you visit a mall and survey people there. Systematically, poorer individuals will be under-covered in the survey.

#### From analysis

* *Nonsampling error*: Again, a result of human error. Examples include applying incorrect statistical methods to the data or neglecting to consider a confounder or improperly handlign missing data (potentially from non-response).

#### Missing data

How to handle missing data within a dataset is largely an unsolved issue as appropriate steps differ based on why data may be missing. *Missing completely at random* data is data for which the likelihood of its being missing is independent of its value or any of the other values of other variables in the data set (we can drop "completely" here if we allow for considering the likelihood after controlling for another variable). Ignoring such missing data (or deleting individuals with missing data from the analysis) is not likely to bias results given it's missing completely at random. However, *missing not at random* data will potentially bias analysis and lead to misleading results because the missing value is related to the reason that it is missing. Therefore, we don't want to just ignore missing not at random data. How may we handle missing data in general?  

* Delete cases/individuals with any missing values. Note this reduces the sample size, and will probably be fine for *missing completely at random* data as remaining samples should still be representative of the population, but will almost surely bias results if data is *missing not at random*
* Impute missing values by substituting values in
  * Use the mean from the known values
  * Using a randomly selected value from individuals with similar data profiles
  * Use a statistical model to calculate a value


Note that a researcher may not realize any data is missing until after they've started to explore, describe, and visualize their collected dataset.

### Describing data

We've discussed types of data and how to collect data for samples. After collecting the data, the next logical step is to explore and describe the data. For *numerical data*, we're often interested in *summary statistics* which describe central tendency and the spread of the data. In general, other characteristics which we want to describe for any type of data include the distribution, outliers (or values which are very "far" from the vast majority of data), and potentially changes over time.

#### Central Tendency

A measure of center is a value at the center or middle of a data set, essentially describing common or expected values observed in the sample. (But how might these values relate to the population?).

* *Mean*
  * This is the sum of all values / number of values
  * Sensitive to extreme values or skewed distributions
  * A weighted mean can be calculated by summing the values which are first multiplied by their weights and then dividing this sum by the sum of the weights. An example of this is often grade-point-average (GPA)
* *Median*
  * Middle value when the original data are arranged in increasing magnitude order.
    * If odd number of values, exact middle
    * If even number of values, mean of the two middle values
  * Resistant to extreme values
* *Mode*
  * This is the most frequently occurring value.
  * A dataset may have no mode or more than one mode.
  * This is also applicable to categorical data.
* *Midrange*
  * This is (max value + min value)/ 2.
  * This stat is highly sensitive to extreme values
  * Not used very often

#### Dispersion, Spread, or Variation

A measure of variation is very important for statistics as it tells you more about the distribution of the data than just the central value. Measures of variation report on how the values vary amongst themselves and can tell you if the data are spread out or concentrated; what the maximum and minimum observed values are; and measures of variation are very important for statistical tests. There are cases where datasets can have the same measures of central tendency, but have vastly different variation.

* *Range*
  * This is the max - min.
  * Alternatively, some instead report this as [min, max]
  * Very sensitive to extreme values
  * Doesn't reflect the variation among all the data values, primarily used to emphasize extreme values
* *Quartiles*
  * Arrange data in increasing magnitude order and locate the median.
  * The first quartile (Q1) is the median of the observations whose positions in the ordered list is to the left of the location of the overall median
    * The first quartile is larger than 25% of the observations
  * The third quartile is the median of the observations whose positions in the ordered list is to the right of the location of the overall median
    * The third quartile (Q3) is larger than 75% of the observations
  * the second quartile (Q2) is the median (M) and is larger than 50% of the observations
  * Many report 5 numbers: min Q1 M Q3 max
  * An interquartile range is Q3 - Q1 and contains the central 50% of the observations.
  * Good to use if looking at the median or communicating the central 50%
* *Standard Deviation*
  * A measure of how much data values deviate away from the mean.
  * The square root of (sum of the squares of the differences of each data value from the sample mean) / (number of samples - 1)
  * Never negative and only zero if all values equal each other
  * Direct relationship with the concept of variation (as one increases, so does the other)
  * Very sensitive to outliers
  * Same units as the original dataset
  * Good to use if looking at the mean
* *Variance*
  * The square of the standard deviation.
  * Therefore the units of the variance are the square of the units of the original data
  * Never negative and only zero if all values equal each other
  * Very sensitive to outliers
* *Coefficient of variation*
  * If wanting to compare the variation of two samples who have different means or with different scales, this metric should be used
  * The sample standard deviation / sample mean * 100%

## Lecture Note Resources

* Basic & Clinical Biostatistics (5th Edition), by Susan White, published by McGraw Hill
* Biostatistics for the Biological and Health Sciences (2nd Edition), by Marc Triola, Mario F. Triola, & Jason Roy, published by Pearson
* Modern Statistics for Modern Biology (2019), by Susan Holmes & Wolfgang Huber, published by Cambridge University Press
* Data Visualization: A Practical Introduction (2019), by Kieran Healy, published by Princeton University Press
* The Practice of Statistics in the Life Sciences (3rd Edition), by Brigitte Baldi & David S. Moore, Published by W.H. Freeman and Company
