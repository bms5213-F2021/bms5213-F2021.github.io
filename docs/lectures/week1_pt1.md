# Week 1 -- Part 1

## Week 1 Learning Objectives

By the end of Week 1, you will be able to

* Describe the steps of a data analysis project
* Define the types of data analytic questions and classify examples in biology research
* Recognize biases present in data due to sampling procedure or analysis
* Distinguish between different types of data you will encounter in biology research and classify examples in the correct group
* Define and calculate descriptive statistics for central tendency and variability or dispersion.
* Compare and contrast the utility of different types of plots for summarizing data clearly and accurately.

## What are Biostatistics and Data Science?

Biostatistics as a field develops and applies statistical methods to biological questions and problems in basic and clinical research. Statistical methods are those which are used to collect, describe, analyze, interpret or display data.

Practicing biostatistics shares many similarities and is essentially linked to data science, which has [previously been defined as](https://simplystatistics.org/2015/03/17/data-science-done-well-looks-easy-and-that-is-a-big-problem-for-data-scientists/)

> the process of formulating a quantitative question that can be answered with data, collecting and cleaning the data, analyzing the data, and communicating the answer to the question to a relevant audience.

While one would likely expect that a statistics course primarily focuses on analyzing data, within this course, we will discuss and practice all aspects of this definition.

Using statistical methods to analyze data requires knowledge about distributions, estimation, hypothesis testing, etc. And in this course, we will certainly cover this material. However, the practice of analyzing data outside of the classroom, in real research environments, hardly ever starts at the analysis step.

## What do the steps of a data analysis project look like?

Data Scientists at Johns Hopkins have proposed the following [7 'discrete' stages](https://simplystatistics.org/2015/03/17/data-science-done-well-looks-easy-and-that-is-a-big-problem-for-data-scientists/) as the main steps of a data science project.

1. Define the question of interest
2. Get the data
3. Clean the data
4. Explore the data
5. Fit statistical models
6. Communicate the results
7. Make your analysis reproducible

In *The Art of Data Science: A Guide for Anyone Who Works with Data* by Roger Peng and Elizabeth Matsui, they reduce these 7 steps to just 5:

1. Stating and refining the question
2. Exploring the data
3. Building formal statistical models
4. Interpreting the results
5. Communicating the results

There is certainly overlap between these two lists, namely defining a question, exploring the data, actually applying statistical models to the data, and communicating the results.

As for how the lists differ, the first list gives a more accurate picture of how data collection and cleaning are a major part of a data analysis project (and often these take more time than any other step). The second list rightly points out the importance of interpreting the results before communicating them. And the first list stresses the importance of making sure your data analysis is reproducible. We'll discuss later what makes a data analysis replicable or reproducible (these are different things!) and why we want to strive to have all of our analyses meet this gold standard.  

While these steps are listed as discrete steps that seem to follow each other in time, as explained in *The Art of Data Science*, data science projects are often cyclical processes with iterative steps. (They actually describe the steps of a data analysis project as an epicycle, or an outer circle which turns on other inner circles -- each of which represents a step of the project.)

Why might these steps be iterative? Let's start the end of the process. Assume you've just given a presentation of your analysis to the department. Someone asks you a question or gives you feedback that causes you to re-assess an earlier stage of the analysis. Perhaps they point out that a graph which was presented isn't showing the variation in the data, and therefore you rework the plot for later presentations and a paper. Another example is that perhaps you are exploring your data and you notice that the sample size at a specific time point doesn't match the sample size for the rest of the time points, suggesting there's a time point with "missing" data. You could revisit earlier steps to see if the data wasn't transcribed or accidentally discarded at some point in data cleaning. These are just two examples, but at the end of every step within a data analysis there's the potential to need to re-assess an earlier step. This [twitter post](https://twitter.com/siminaboca/status/1298870717291917312/photo/1) has a very nice graphic showcasing the cyclical nature of a data analysis.   

## Formulating questions

The first step of a data analysis project is to define a question.

### What makes a good question?

The question should have several qualities which Peng and Matsui describe. These include characteristics such as the question being of interest to your audience. Whoever the audience is (collaborators, PI, grant awarding committees, the public), be sure to understand and communicate what question you think you want to answer with the data before performing an analysis and finding out that the answer was not in line with the audience's interest/thoughts.

Ideally, the question will also be novel, or it hasn't been answered before. Perhaps an answer has been attempted, but it wasn't a satisfactory answer and either the data that you will be analyzing or the way in which you will be analyzing it, will lead to a more satisfactory answer.

You also want a question to be plausible. A [Science paper](https://raw.githubusercontent.com/bms5213-F2021/bms5213-F2021.github.io/master/docs/resourcedev/papers/dnm_halldorsson.pdf) which you are going to read for your homework asks a very plausible question about the relation between parental age and the number of *de novo* mutations their offspring inherit. A far less plausible question might ask the relation between parental age and offspring height.

Questions should also be specific. General questions may seem appealing in that they give the researcher more leeway to refine the question as they collect and work with the data, but specificity to begin with allows researchers to be intentional and precise in the data they are collecting and analyzing. Imagine the sheer amount of work a student would have to do to collect data for a question which asked "Are *C. elegans* affected by hormones?". A lot of this work would stem from the question being inherently unclear. What is meant by "affected"? What kind of hormones: Is the question asking about treating *C. elegans* with external hormones or asking if they have a limbic system?

A final consideration should also be answerable. One reason a question may not be answerable is if the data necessary to answer it doesn't exist and cannot be generated (due to shortcomings in technology, ethical considerations, feasibility, etc.). Another reason may be that the question isn't really measurable. Essentially, one could pose a question in which there is no way to accurately measure at least one component important to the question.

Keep in mind the following saying from the [statistician responsible for box-plots](https://en.wikipedia.org/wiki/John_Tukey):

> The data may not contain the answer. The combination of some data and an aching desire for an answer does not ensure that a reasonable answer can be extracted from a given body of data. -- John Tukey

While this quote focuses on the data involved in answering a question, an important point is that the question may need to be refined in order for it to be answerable given the data. This connects to our earlier thought that data analyses are often iterative and questions may need to be re-assessed after studying the data that is collected/available.  

### What types of questions are there?

It's important to know what type of question you are asking to make sure that you interpret the results from the data analysis appropriately. The types of data analytic questions which can be asked are grouped into the following categories. These are described in detail in the paper ["What is the question?"](https://raw.githubusercontent.com/bms5213-F2021/bms5213-F2021.github.io/master/docs/resourcedev/papers/leek_peng_question_type.pdf) by Jeff Leek and Roger Peng.

* Descriptive: A descriptive question is one in which the goal is to summarize a characteristic of a set of data. This could be something like, "What is the range of expression of geneX in these cell types as assayed by qPCR?" Interpreting the results of this question is impossible as the answer is the answer. Testable hypotheses may be formed based on the result, but one would be unable to interpret why the range is small/large/etc.
* Exploratory: An exploratory question is one in which the goal is to analyze data to look for patterns or trends within the data and relationships or correlations between specific components of the data. Exploratory analyses often make discoveries which are then confirmed by other studies. As an example, we could build upon our earlier question and ask, "What is the expression and accessibility of geneX in these cell types?" We could now certainly interpret the results of this question and generate a specific, testable hypothesis that geneX's accessibility is somehow correlated to its expression. However, we would not have a cause-and-effect relationship.
* Inferential: An inferential question takes the hypothesis generated from an exploratory question and attempts to observe whether the relationship holds in a different dataset. For example, we could test different genes in different cell types and see if their expression levels are correlated with their accessibility. If the correlation stands in a representative sample of genes, this supports that the relationship may be true for all genes on average. Ideally, an inferential analysis is moving from a small sample (just geneX in a few cell types) closer to population scale (all genes in a lot of cell types).
* Predictive: A predictive question attempts to use a subset of information/measurements/features to predict an another measurement or feature (an outcome) in new data. Returning to a gene's expression and accessibility, we could pose a question such as, "Can the accessibility of a gene in cell type A be used to predict that gene's expression level in cell type A?"
* Causal: A causal question attempts to solidify a cause-and-effect relationship by asking whether changing one factor will change another factor. Suppose following along with our gene expression and accessibility analysis, we somehow changed the accessibility of genes in the population (made accessible genes unaccessible and made unaccessible genes accessible) and then asked how did the expression levels change. This would be a causal question.
* Mechanistic: What if we found that yes a change in accessibility of a gene on average led to a change in expression? Would we be able to answer *how* the change in accessibility led to the change in expression? No, because we haven't asked a mechanistic question yet. A mechanistic question looks for the mechanism by which or how a causal relationship is carried out. This is often achieved by showing that changing one measurement *always* leads to a specific, deterministic outcome rather than an on average outcome. Leek and Peng remark that this type of a question is challenging and rarely achievable outside of the field of engineering.
