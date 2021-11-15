## Transformation, Correlation, & Regression

**These are still being updated**

## Transformations

We've briefly talked about some data cleaning, specifically related to missing data. We've also mentioned that removal of outliers can be part of data cleaning. (We will formally discuss identifying outliers at a later time.) Another part of data cleaning is *transforming* data.

Sometimes we need to add or *modify* variables in our dataset. These modifications may involve a single variable (like taking an absolute value), or multiple variables (like computing a rate from distance and a time interval). At other times, we may make a new column summing values from several different columns; this is called *aggregating* or collapsing multiple values into a single value.

Sometimes we need to *filter* data where we subset or remove observations based on a specific condition.

Some common transformations:

* Take an absolute value - `abs(x)`
* Take a square root - `sqrt(x)`
* Ceiling  (round up to nearest integer) - `ceiling(x)`
* floor (round down to nearest integer) - `floor(x)`
* round to a decimal; specific digit - `round(x, digits=n)`
* Natural logarithm (ln) - `log(x)`
* log base 10 - `log10(x)`
* log base 2 - `log2(x)`
* e^x, or exponentiating the data - `exp(x)`

Sometimes if raw data isn't normally distributed, transforming the data can make it fit a normal distribution. For skewed data with a long tail, try taking the natural logarithm of the data.

### Correlation
A linear correlation occurs when both variables increase or decrease concurrently (in the same direction, monotonic) at a constant rate (or slope).
  * A Pearson correlation coefficient is greater than or equal to negative 1 and less than or equal to 1.
  * Perfectly correlated data has a coefficient of 1 or -1.
  * Data with no correlation has a correlation coefficient of 0 or essentially 0.
  * Correlation may be weak or strong. Weak correlation will have lower (absolute) coefficient values while strong correlation will have higher (absolute) coefficient values.
  * A positive correlation has a correlation coefficient greater than 0. A positive linear relationship exists when both variables increase or decrease concurrently at the same rate.  
  * A negative correlation has a correlation coefficient less than 0. A negative linear relationship exists when one variable increases while the other variable decreases, but at a constant rate.

A non-linear correlation occurs when the data shows a relationship, but a non-linear relationship. This may be non-linear either because the rate of increase or decrease is non-constant; or perhaps the data is not monotonic increasing or decreasing (like a parabola), not moving in the same direction.


### Refereces
* [Tidy Data](http://vita.had.co.nz/papers/tidy-data.pdf)
* [Data Cleaning](http://jtleek.com/jhsph753and4/lectures/04_01_cleaningData/#1)
* [Correlation](https://support.minitab.com/en-us/minitab/19/help-and-how-to/statistics/basic-statistics/supporting-topics/basics/linear-nonlinear-and-monotonic-relationships/)
