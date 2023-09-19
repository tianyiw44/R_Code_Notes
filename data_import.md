Notes on Codes
================

output: html_document: toc: true toc_float: true

# Loarding packages

- load all pacakges in the begining so anybody opening the document
  would have a clear idea on which packages are used.

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
library(readxl)
library(haven)
```

# Data Import

- `read_csv`
- `read_excel`
- `read_sas`

# Data Export

- `write_csv`

# Look at Data and Clean Name

- `janitor::clean_names(litters_df)`
- `head(litters_df)`
- `tail(litters_df)`
- `skimr::skim(litters_df)`

## Data Import Example

### read_csv

``` r
litters_df = read_csv("./data/FAS_litters.csv")
litters_df = janitor::clean_names(litters_df) 
```

``` r
litters_df = read_csv("./data/Fas_litters.csv", skip = 10, col_names = FALSE)
```

``` r
litters_df = read_csv("./data/Fas_litters.csv", na = c("","NA", 999))
```

### read_excel

``` r
mlb_df = read_excel("./data/mlb11.xlsx")
mlb_df
```

``` r
mlb_df = read_excel("./data/mlb11.xlsx", range = "A1:F7")
mlb_df
```

### read_sas.

``` r
pulse_df = read_sas("./data/public_pulse_data.sas7bdat")
pulse_df
```

## Data Export Example

### Export the mlb sub-table.

``` r
mlb_df
```

``` r
write_csv(mlb_df, "./data/mlb_subtable.csv")
```
