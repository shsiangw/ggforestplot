## Differences from the Original Package

The original **`ggforestplot`** package is available on GitHub:

```r
# install.packages("devtools")
devtools::install_github("NightingaleHealth/ggforestplot")
```

This fork introduces **3 additional options** to improve plot customization:

  1. Reference Line at 1 (Without Exponentiation)

     Set the reference line at 1 without exponentiating the estimates or confidence intervals.

```r
forestplot(
  df = df,
  estimate = beta,
  one = TRUE
)
```

  2. Custom Confidence Intervals

     Provide pre-computed confidence intervals instead of relying on `ggforestplot` calculation.

```r
forestplot(
  df = df,
  estimate = beta,
  ci_upper = upper,
  ci_lower = lower
)
```

  3. Highlight Significant Results

     Display statistically significant estimates using a different color for points and error bars.

```r
forestplot(
  df = df,
  estimate = beta,
  pvalue = pvalue,
  psignif = 0.05,
  psignif_colour = c("#000000", "#d62728")  # (insignificant, significant)
)

