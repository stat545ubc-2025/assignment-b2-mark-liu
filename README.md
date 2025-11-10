
<!-- README.md is generated from README.Rmd. Please edit that file -->

# STAT545.Assignment.Package

<!-- badges: start -->

<!-- badges: end -->

STAT545.Assignment.Package aims to provide users with a function, the
“count_all_missing_by_group” function. This function ought to return the
number of missing observations with respect to under-specified groupings
within a given data frame or tibble by way of a another tibble.

## Installation

You can install the in-development version of STAT545.Assignment.Package
from [GitHub](https://github.com/) with the following command:

> devtools::install_github(“<https://github.com/stat545ubc-2025/assignment-b2-mark-liu>”,
> ref = “1.0.0”)

## Example

This is a basic example which shows how the “count_all_missing_by_group”
function is intended to work:

``` r
library(STAT545.Assignment.Package)

count_all_missing_by_group(iris)
#> # A tibble: 1 × 5
#>   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
#>          <int>       <int>        <int>       <int>   <int>
#> 1            0           0            0           0       0
count_all_missing_by_group(penguins, island)
#> # A tibble: 3 × 8
#>   island    species bill_len bill_dep flipper_len body_mass   sex  year
#>   <fct>       <int>    <int>    <int>       <int>     <int> <int> <int>
#> 1 Biscoe          0        1        1           1         1     5     0
#> 2 Dream           0        0        0           0         0     1     0
#> 3 Torgersen       0        1        1           1         1     5     0
count_all_missing_by_group(airquality, Month)
#> # A tibble: 5 × 6
#>   Month Ozone Solar.R  Wind  Temp   Day
#>   <int> <int>   <int> <int> <int> <int>
#> 1     5     5       4     0     0     0
#> 2     6    21       0     0     0     0
#> 3     7     5       0     0     0     0
#> 4     8     5       3     0     0     0
#> 5     9     1       0     0     0     0
count_all_missing_by_group(airquality, Month, .groups = "keep")
#> # A tibble: 5 × 6
#> # Groups:   Month [5]
#>   Month Ozone Solar.R  Wind  Temp   Day
#>   <int> <int>   <int> <int> <int> <int>
#> 1     5     5       4     0     0     0
#> 2     6    21       0     0     0     0
#> 3     7     5       0     0     0     0
#> 4     8     5       3     0     0     0
#> 5     9     1       0     0     0     0
```
