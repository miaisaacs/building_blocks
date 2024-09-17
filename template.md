Simple document
================
Mia Isaacs
2024-09-10

Loaded necessary packages (e.g. `tidyverse`).

I’m an R Markdown document!

# Section 1

Here’s a **code chunk** that samples from a *normal distribution*:

``` r
samp = rnorm(100)
length(samp)
```

    ## [1] 100

# Section 2

I can take the mean of the sample, too! The mean is 0.0875682.

# Learning Assessment

The chunk below creates a dataframe containing a sample of size 500 from
a random normal variable, constructs the specified logical vector, takes
the absolute value of each element of that sample,and produces a
histogram of the absolute value. The code chunk also finds the median of
the sample and stores it for easy in-line printing.

``` r
library(tidyverse)

la_df = 
  tibble(
   norm_samp = rnorm(500, mean = 1),
   samp_g0 = norm_samp > 0,
   abs_v_samp = abs(norm_samp)
 )


ggplot(la_df, aes(x = abs_v_samp)) + 
  geom_histogram()
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](template_files/figure-gfm/learning_assessment_1-1.png)<!-- -->

``` r
median_samp = median(pull(la_df, norm_samp))
```

The median of the variable containing absolute values is 1.

## \# Text formatting

*italic* or *italic* **bold** or **bold** `code` superscript<sup>2</sup>
and subscript<sub>2</sub>

## Headings

# 1st Level Header

## 2nd Level Header

### 3rd Level Header

## Lists

- Bulleted list item 1

- Item 2

  - Item 2a

  - Item 2b

1.  Numbered list item 1

2.  Item 2. The numbers are incremented automatically in the output.

## Tables

| First Header | Second Header |
|--------------|---------------|
| Content Cell | Content Cell  |
| Content Cell | Content Cell  |
