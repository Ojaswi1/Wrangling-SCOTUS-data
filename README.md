# Homework 03: Exploring and wrangling data

**Ojaswi Malik** 
- First Commit: Making sure Setup works

See detailed instructions for this homework assignment [here](https://cfss.uchicago.edu/homework/wrangle-data/).

## Required packages

You should have the following packages installed:

```r
library(tidyverse)
library(gapminder)
library(rcfss)
```

[`rcfss`](https://github.com/uc-cfss/rcfss) can be installed from GitHub using the command:

```r
if (packageVersion("devtools") < 1.6) {
  install.packages("devtools")
}

devtools::install_github("uc-cfss/rcfss")
```

## Assignment submission

Your assignment should be submitted as three RMarkdown documents. Make sure you've read the chapter on [R Markdown](http://r4ds.had.co.nz/r-markdown.html) so you understand how to properly use these files.

For your benefit, I have provided starter RMarkdown documents for each part of the homework. You should not need to modify the starter code, merely add on to it. In the [`demo`](demo/) folder I have included some example solutions:

* [Tidying `dadmom` solution](demo/dadmom_solution.md)
* [`gapminder` solution](demo/gapminder_solution.md)
* [SCOTUS solution](demo/scotus_solution.md)

These files do not contain any of the code necessary to complete the homework, but do show you output from R for potential solutions. Your solutions do not need to perfectly replicate these tables and graphs, but are a good starting point.

Follow instructions on [homework workflow](https://cfss.uchicago.edu/faq/homework-guidelines/#homework-workflow) to submit your homework. As part of the pull request, you're encouraged to reflect on what was hard/easy, problems you solved, helpful tutorials you read, etc.
