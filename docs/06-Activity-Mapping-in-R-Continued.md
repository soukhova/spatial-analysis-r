# Activity 2: Statistical Maps II

*NOTE*: The source files for this book are available with companion package [{isdas}](https://paezha.github.io/isdas/). The source files are in Rmarkdown format and packed as templates. These files allow you execute code within the notebook, so that you can work interactively with the notes. 

## Housekeeping Questions

Answer the following questions:

1. How many examinations are there in this course?
2. What is the date of the first examination?
3. Where is the office of your instructor?

## Learning objectives

In this activity you will:

1. Learn about patterns and processes, including random patterns.
2. Understand the general approach to retrieve a process from a pattern.
3. Discuss the importance of discriminating random patterns.

## Suggested reading

O'Sullivan D and Unwin D (2010) Geographic Information Analysis, 2nd Edition, Chapters 1-3. John Wiley & Sons: New Jersey.

## Preliminaries

it is good practice to begin with a clean session to make sure that you do not have extraneous items there when you begin your work. The best practice is to restart the `R` session, which can be accomplished for example with `command/ctrl + shift + F10`. An alternative to _only_ purge user-created objects from memory is to use the `R` command `rm` (for "remove"), followed by a list of items to be removed:

```r
rm(list = ls())
```

Note that `ls()` lists all objects currently on the workspace.

Load the libraries you will use in this activity:

```r
library(tidyverse) # Easily Install and Load the 'Tidyverse'
library(isdas) # Companion Package for Book An Introduction to Spatial Data Analysis and Statistics
```

```
## Warning: replacing previous import 'dplyr::lag' by 'stats::lag' when loading
## 'isdas'
```

```
## Warning: replacing previous import 'plotly::filter' by 'stats::filter' when
## loading 'isdas'
```

Now that your workspace is clear, you can proceed to invoke the datasets required for this activity:

```r
data("missing_df")
data("PointPattern1")
data("PointPattern2")
data("PointPattern3")
```

The datasets include the following dataframe which will be used in the first part of the activity:

* `missing_df`

This dataframe includes $n = 65$ observations (Note: text between $ characters is mathematical notation in LaTeX). These observations are geocoded using a false origin and coordinates normalized to the unit-square (the extent of their values is between zero and one). The coordinates are `x` and `y`. In addition, there are three variables associated with the locations (VAR1, VAR2, VAR3). The variables are generic. Feel free to think of them as if they were housing prices or concentrations in ppb of some contaminant. Finally, a factor variable states whether the variables were measured for a location: if the status is "FALSE", the values of the variables are missing.

The following dataframes will be used in the second part of the activity:

* `PointPattern1`
* `PointPattern2`
* `PointPattern3`

The dataframes `PointPattern*` are locations of some generic events. The coordinates `x` and `y` are also based on a false origin and are normalized to the unit-square. Feel free to think of these events as cases of flu, the location of trees of a certain species, or the location of fires.

## Activity

**NOTE**: Activities include technical "how to" tasks/questions. Usually, these ask you to practice using the software to organize data, create plots, and so on in support of analysis and interpretation. The second type of questions ask you to activate your brainware and to think geographically and statistically.

::: {.infobox .software data-latex="{software}"}
**Activity Part I**
:::

1. Create thematic maps for variables VAR1 through VAR3 in the dataframe `missing_df`. 

2. Plot all three point patterns.

::: {.infobox .brainware data-latex="{brainware}"}
**Activity Part II**
:::

3. Suppose that you were tasked with estimating the value of a variable for the locations where those were not measured. For instance, you could be a realtor, and you need to assess the value of a property, and the only information available is the published values of other properties in the region. As an alternative, you could be an environmental scientist, and you need to estimate what the concentration of a contaminant at a site, based on previous measurements at other sites in the region. Propose one or more ways to guess those missing values, and explain your reasoning. The approach does not need to be the same for all variables!

4. Imagine that you are a public health official and you need to plan services to the public. If you were asked to guess where the next event would emerge, where would be your guess in each map? Explain your answer.

