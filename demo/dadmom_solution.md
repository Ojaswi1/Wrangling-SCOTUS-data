Tidying `dadmom`
================
Benjamin Soltoff

# Get the data

``` r
library(tidyverse)
```

    ## ── Attaching packages ───────────────────────────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.1.1     ✔ purrr   0.3.2
    ## ✔ tibble  2.1.1     ✔ dplyr   0.8.1
    ## ✔ tidyr   0.8.3     ✔ stringr 1.4.0
    ## ✔ readr   1.3.1     ✔ forcats 0.4.0

    ## ── Conflicts ──────────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(rcfss)

data("dadmom")
dadmom
```

    ## # A tibble: 3 x 5
    ##   famid named  incd namem  incm
    ##   <dbl> <chr> <dbl> <chr> <dbl>
    ## 1     1 Bill  30000 Bess  15000
    ## 2     2 Art   22000 Amy   18000
    ## 3     3 Paul  25000 Pat   50000

# Tidied data

## Using `gather()` and `spread()`

    ## # A tibble: 6 x 4
    ##   famid type    inc name 
    ##   <dbl> <chr> <int> <chr>
    ## 1     1 d     30000 Bill 
    ## 2     1 m     15000 Bess 
    ## 3     2 d     22000 Art  
    ## 4     2 m     18000 Amy  
    ## 5     3 d     25000 Paul 
    ## 6     3 m     50000 Pat

## Using `pivot_*()`

    ## # A tibble: 6 x 4
    ##   famid sex   name    inc
    ##   <dbl> <chr> <chr> <dbl>
    ## 1     1 d     Bill  30000
    ## 2     1 m     Bess  15000
    ## 3     2 d     Art   22000
    ## 4     2 m     Amy   18000
    ## 5     3 d     Paul  25000
    ## 6     3 m     Pat   50000

## Session info

``` r
devtools::session_info()
```

    ## ─ Session info ──────────────────────────────────────────────────────────
    ##  setting  value                       
    ##  version  R version 3.5.3 (2019-03-11)
    ##  os       macOS Mojave 10.14.5        
    ##  system   x86_64, darwin15.6.0        
    ##  ui       X11                         
    ##  language (EN)                        
    ##  collate  en_US.UTF-8                 
    ##  ctype    en_US.UTF-8                 
    ##  tz       America/Chicago             
    ##  date     2019-06-08                  
    ## 
    ## ─ Packages ──────────────────────────────────────────────────────────────
    ##  package     * version date       lib source        
    ##  assertthat    0.2.1   2019-03-21 [2] CRAN (R 3.5.3)
    ##  backports     1.1.4   2019-04-10 [2] CRAN (R 3.5.2)
    ##  broom         0.5.2   2019-04-07 [2] CRAN (R 3.5.2)
    ##  callr         3.2.0   2019-03-15 [2] CRAN (R 3.5.2)
    ##  cellranger    1.1.0   2016-07-27 [2] CRAN (R 3.5.0)
    ##  cli           1.1.0   2019-03-19 [1] CRAN (R 3.5.2)
    ##  codetools     0.2-16  2018-12-24 [2] CRAN (R 3.5.3)
    ##  colorspace    1.4-1   2019-03-18 [2] CRAN (R 3.5.2)
    ##  crayon        1.3.4   2017-09-16 [2] CRAN (R 3.5.0)
    ##  desc          1.2.0   2018-05-01 [2] CRAN (R 3.5.0)
    ##  devtools      2.0.2   2019-04-08 [1] CRAN (R 3.5.2)
    ##  digest        0.6.19  2019-05-20 [1] CRAN (R 3.5.2)
    ##  dplyr       * 0.8.1   2019-05-14 [1] CRAN (R 3.5.2)
    ##  evaluate      0.13    2019-02-12 [2] CRAN (R 3.5.2)
    ##  fansi         0.4.0   2018-10-05 [2] CRAN (R 3.5.0)
    ##  forcats     * 0.4.0   2019-02-17 [2] CRAN (R 3.5.2)
    ##  fs            1.3.1   2019-05-06 [1] CRAN (R 3.5.2)
    ##  generics      0.0.2   2018-11-29 [1] CRAN (R 3.5.0)
    ##  ggplot2     * 3.1.1   2019-04-07 [1] CRAN (R 3.5.2)
    ##  glue          1.3.1   2019-03-12 [2] CRAN (R 3.5.2)
    ##  gtable        0.3.0   2019-03-25 [2] CRAN (R 3.5.2)
    ##  haven         2.1.0   2019-02-19 [2] CRAN (R 3.5.2)
    ##  hms           0.4.2   2018-03-10 [2] CRAN (R 3.5.0)
    ##  htmltools     0.3.6   2017-04-28 [1] CRAN (R 3.5.0)
    ##  httr          1.4.0   2018-12-11 [2] CRAN (R 3.5.0)
    ##  jsonlite      1.6     2018-12-07 [2] CRAN (R 3.5.0)
    ##  knitr         1.22    2019-03-08 [2] CRAN (R 3.5.2)
    ##  lattice       0.20-38 2018-11-04 [2] CRAN (R 3.5.3)
    ##  lazyeval      0.2.2   2019-03-15 [2] CRAN (R 3.5.2)
    ##  lubridate     1.7.4   2018-04-11 [2] CRAN (R 3.5.0)
    ##  magrittr      1.5     2014-11-22 [2] CRAN (R 3.5.0)
    ##  memoise       1.1.0   2017-04-21 [2] CRAN (R 3.5.0)
    ##  modelr        0.1.4   2019-02-18 [2] CRAN (R 3.5.2)
    ##  munsell       0.5.0   2018-06-12 [2] CRAN (R 3.5.0)
    ##  nlme          3.1-140 2019-05-12 [2] CRAN (R 3.5.2)
    ##  pillar        1.4.1   2019-05-28 [1] CRAN (R 3.5.2)
    ##  pkgbuild      1.0.3   2019-03-20 [1] CRAN (R 3.5.3)
    ##  pkgconfig     2.0.2   2018-08-16 [2] CRAN (R 3.5.1)
    ##  pkgload       1.0.2   2018-10-29 [1] CRAN (R 3.5.0)
    ##  plyr          1.8.4   2016-06-08 [2] CRAN (R 3.5.0)
    ##  prettyunits   1.0.2   2015-07-13 [2] CRAN (R 3.5.0)
    ##  processx      3.3.1   2019-05-08 [1] CRAN (R 3.5.2)
    ##  ps            1.3.0   2018-12-21 [2] CRAN (R 3.5.0)
    ##  purrr       * 0.3.2   2019-03-15 [2] CRAN (R 3.5.2)
    ##  R6            2.4.0   2019-02-14 [1] CRAN (R 3.5.2)
    ##  rcfss       * 0.1.5   2019-04-17 [1] local         
    ##  Rcpp          1.0.1   2019-03-17 [1] CRAN (R 3.5.2)
    ##  readr       * 1.3.1   2018-12-21 [2] CRAN (R 3.5.0)
    ##  readxl        1.3.1   2019-03-13 [2] CRAN (R 3.5.2)
    ##  remotes       2.0.4   2019-04-10 [1] CRAN (R 3.5.2)
    ##  rlang         0.3.4   2019-04-07 [1] CRAN (R 3.5.2)
    ##  rmarkdown     1.12    2019-03-14 [1] CRAN (R 3.5.2)
    ##  rprojroot     1.3-2   2018-01-03 [2] CRAN (R 3.5.0)
    ##  rstudioapi    0.10    2019-03-19 [1] CRAN (R 3.5.3)
    ##  rvest         0.3.4   2019-05-15 [2] CRAN (R 3.5.2)
    ##  scales        1.0.0   2018-08-09 [1] CRAN (R 3.5.0)
    ##  sessioninfo   1.1.1   2018-11-05 [1] CRAN (R 3.5.0)
    ##  stringi       1.4.3   2019-03-12 [1] CRAN (R 3.5.2)
    ##  stringr     * 1.4.0   2019-02-10 [1] CRAN (R 3.5.2)
    ##  testthat      2.1.1   2019-04-23 [2] CRAN (R 3.5.2)
    ##  tibble      * 2.1.1   2019-03-16 [1] CRAN (R 3.5.2)
    ##  tidyr       * 0.8.3   2019-03-01 [1] CRAN (R 3.5.2)
    ##  tidyselect    0.2.5   2018-10-11 [1] CRAN (R 3.5.0)
    ##  tidyverse   * 1.2.1   2017-11-14 [2] CRAN (R 3.5.0)
    ##  usethis       1.5.0   2019-04-07 [1] CRAN (R 3.5.2)
    ##  utf8          1.1.4   2018-05-24 [2] CRAN (R 3.5.0)
    ##  vctrs         0.1.0   2018-11-29 [2] CRAN (R 3.5.0)
    ##  withr         2.1.2   2018-03-15 [2] CRAN (R 3.5.0)
    ##  xfun          0.7     2019-05-14 [1] CRAN (R 3.5.2)
    ##  xml2          1.2.0   2018-01-24 [2] CRAN (R 3.5.0)
    ##  yaml          2.2.0   2018-07-25 [2] CRAN (R 3.5.0)
    ##  zeallot       0.1.0   2018-01-28 [2] CRAN (R 3.5.0)
    ## 
    ## [1] /Users/soltoffbc/Library/R/3.5/library
    ## [2] /Library/Frameworks/R.framework/Versions/3.5/Resources/library
