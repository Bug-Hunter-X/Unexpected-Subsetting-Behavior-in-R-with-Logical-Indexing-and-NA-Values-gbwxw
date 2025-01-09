# R Subsetting Bug

This repository demonstrates a common, yet subtle, bug in R related to subsetting data frames using logical indexing, particularly when dealing with `NA` values. The issue arises from how R handles logical comparisons in the presence of missing data.

The `bug.R` file contains code that reproduces the problem. The `bugSolution.R` file provides a corrected version using `isTRUE` to handle `NA` values appropriately.

## Bug Description
When subsetting a data frame based on a logical condition, the presence of `NA` values can lead to unexpected results.  The standard `==` operator does not treat `NA` consistently, often leading to unexpected omissions or inclusion of rows with `NA` values.

## Solution
The solution involves using the `isTRUE()` function, which handles `NA` values more predictably. This ensures that only rows where the condition evaluates to explicitly `TRUE` are included in the subset.