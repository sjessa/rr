---
title: "01 - Analysis 1"
author: "Selin Jessa"
date: "23 May, 2020"
output:
  html_document:
    theme: flatly
    css: include/style.css
    toc: yes
    toc_depth: 4
    number_sections: true
    df_print: paged
    keep_md: yes
---

<!-- FRONT MATTER -->

<!-- Load custom CSS/JS for code folding -->
<link rel="stylesheet" type="text/css" href="include/hideOutput.css">
<script src="include/hideOutput.js"></script>

***

# Configuration

Configuration of project directory & analysis outputs:

<details><summary>Show full config</summary>




```r
library(here)
```

```
## here() starts at /Users/selinjessa/Repos/rr
```

```r
# Set up outputs

# ...determines the name of the cache folder
project_id <- "rr"

# ...determines name of the subfolder of `outputs` and `figures`
doc_id     <- "01"

# ...specify where to save outputs
out        <- here("output", doc_id); dir.create(out, recursive = TRUE)
figout     <- here("figures", doc_id, "/")
cache      <- paste0("~/tmp/", project_id, "/", doc_id, "/")
```

</details>

The root directory of this project is:


```
## /Users/selinjessa/Repos/rr
```

Outputs and figures will be saved at these paths, relative to project root:


```
## rr/output/01
```

```
## rr/figures/01//
```



<!-- END OF FRONT MATTER -->

***

# Overview

This is an example of the first analysis in a project.

# Libraries


```r
library(ggplot2)
library(tidyverse)
```


Here is a note to self. This markdown code is contained in a check, 
with visibility controlled by the `echo` chunk option.

Change echo to TRUE or FALSE to display/hide this chunk.



# Analysis

## Part 1

This part of the analysis generates a figure; we can use the chunk option
`echo_fig = TRUE` to print its output path.


```r
mtcars %>% 
    ggplot(aes(x = mpg, y = cyl)) +
    geom_point() +
    theme_bw()
```

![](/Users/selinjessa/Repos/rr/figures/01//pressure-1.png)<!-- --><br><span style="color:#0d00ff">~[figure @ *rr/figures/01//pressure...*]~</span>

## Part 2

This part of the analysis saves the `mtcars` dataset from R as a TSV.
By matching the chunk name to the output file name, we can then use
the `echo_out = TRUE` chunk option to show the path to the fil.


```r
head(mtcars)
```

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":[""],"name":["_rn_"],"type":[""],"align":["left"]},{"label":["mpg"],"name":[1],"type":["dbl"],"align":["right"]},{"label":["cyl"],"name":[2],"type":["dbl"],"align":["right"]},{"label":["disp"],"name":[3],"type":["dbl"],"align":["right"]},{"label":["hp"],"name":[4],"type":["dbl"],"align":["right"]},{"label":["drat"],"name":[5],"type":["dbl"],"align":["right"]},{"label":["wt"],"name":[6],"type":["dbl"],"align":["right"]},{"label":["qsec"],"name":[7],"type":["dbl"],"align":["right"]},{"label":["vs"],"name":[8],"type":["dbl"],"align":["right"]},{"label":["am"],"name":[9],"type":["dbl"],"align":["right"]},{"label":["gear"],"name":[10],"type":["dbl"],"align":["right"]},{"label":["carb"],"name":[11],"type":["dbl"],"align":["right"]}],"data":[{"1":"21.0","2":"6","3":"160","4":"110","5":"3.90","6":"2.620","7":"16.46","8":"0","9":"1","10":"4","11":"4","_rn_":"Mazda RX4"},{"1":"21.0","2":"6","3":"160","4":"110","5":"3.90","6":"2.875","7":"17.02","8":"0","9":"1","10":"4","11":"4","_rn_":"Mazda RX4 Wag"},{"1":"22.8","2":"4","3":"108","4":"93","5":"3.85","6":"2.320","7":"18.61","8":"1","9":"1","10":"4","11":"1","_rn_":"Datsun 710"},{"1":"21.4","2":"6","3":"258","4":"110","5":"3.08","6":"3.215","7":"19.44","8":"1","9":"0","10":"3","11":"1","_rn_":"Hornet 4 Drive"},{"1":"18.7","2":"8","3":"360","4":"175","5":"3.15","6":"3.440","7":"17.02","8":"0","9":"0","10":"3","11":"2","_rn_":"Hornet Sportabout"},{"1":"18.1","2":"6","3":"225","4":"105","5":"2.76","6":"3.460","7":"20.22","8":"1","9":"0","10":"3","11":"1","_rn_":"Valiant"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>
</div>

```r
write.table(mtcars, file.path(out, "mtcars.tsv"))
```

<br><span style="color:#0d00ff">~[output @ *rr/output/01/mtcars.tsv*]~</span>



***

# Reproducibility


This document was last rendered on:


```
## 2020-05-23 20:06:02
```

Session info:
<details>


```
## ─ Session info ───────────────────────────────────────────────────────────────
##  setting  value                                   
##  version  R version 4.0.0 beta (2020-04-12 r78209)
##  os       macOS Catalina 10.15.3                  
##  system   x86_64, darwin17.0                      
##  ui       X11                                     
##  language (EN)                                    
##  collate  en_CA.UTF-8                             
##  ctype    en_CA.UTF-8                             
##  tz       America/Montreal                        
##  date     2020-05-23                              
## 
## ─ Packages ───────────────────────────────────────────────────────────────────
##  package     * version date       lib source        
##  assertthat    0.2.1   2019-03-21 [1] CRAN (R 4.0.0)
##  backports     1.1.6   2020-04-05 [1] CRAN (R 4.0.0)
##  broom         0.5.5   2020-02-29 [1] CRAN (R 4.0.0)
##  callr         3.4.3   2020-03-28 [1] CRAN (R 4.0.0)
##  cellranger    1.1.0   2016-07-27 [1] CRAN (R 4.0.0)
##  cli           2.0.2   2020-02-28 [1] CRAN (R 4.0.0)
##  codetools     0.2-16  2018-12-24 [1] CRAN (R 4.0.0)
##  colorspace    1.4-1   2019-03-18 [1] CRAN (R 4.0.0)
##  crayon        1.3.4   2017-09-16 [1] CRAN (R 4.0.0)
##  DBI           1.1.0   2019-12-15 [1] CRAN (R 4.0.0)
##  dbplyr        1.4.2   2019-06-17 [1] CRAN (R 4.0.0)
##  desc          1.2.0   2018-05-01 [1] CRAN (R 4.0.0)
##  devtools      2.3.0   2020-04-10 [1] CRAN (R 4.0.0)
##  digest        0.6.25  2020-02-23 [1] CRAN (R 4.0.0)
##  dplyr       * 0.8.5   2020-03-07 [1] CRAN (R 4.0.0)
##  ellipsis      0.3.0   2019-09-20 [1] CRAN (R 4.0.0)
##  evaluate      0.14    2019-05-28 [1] CRAN (R 4.0.0)
##  fansi         0.4.1   2020-01-08 [1] CRAN (R 4.0.0)
##  farver        2.0.3   2020-01-16 [1] CRAN (R 4.0.0)
##  forcats     * 0.5.0   2020-03-01 [1] CRAN (R 4.0.0)
##  fs            1.4.1   2020-04-04 [1] CRAN (R 4.0.0)
##  generics      0.0.2   2018-11-29 [1] CRAN (R 4.0.0)
##  ggplot2     * 3.3.0   2020-03-05 [1] CRAN (R 4.0.0)
##  glue        * 1.4.0   2020-04-03 [1] CRAN (R 4.0.0)
##  gtable        0.3.0   2019-03-25 [1] CRAN (R 4.0.0)
##  haven         2.2.0   2019-11-08 [1] CRAN (R 4.0.0)
##  here        * 0.1     2017-05-28 [1] CRAN (R 4.0.0)
##  hms           0.5.3   2020-01-08 [1] CRAN (R 4.0.0)
##  htmltools     0.4.0   2019-10-04 [1] CRAN (R 4.0.0)
##  httr          1.4.1   2019-08-05 [1] CRAN (R 4.0.0)
##  jsonlite      1.6.1   2020-02-02 [1] CRAN (R 4.0.0)
##  knitr         1.28    2020-02-06 [1] CRAN (R 4.0.0)
##  labeling      0.3     2014-08-23 [1] CRAN (R 4.0.0)
##  lattice       0.20-41 2020-04-02 [1] CRAN (R 4.0.0)
##  lifecycle     0.2.0   2020-03-06 [1] CRAN (R 4.0.0)
##  lubridate     1.7.8   2020-04-06 [1] CRAN (R 4.0.0)
##  magrittr      1.5     2014-11-22 [1] CRAN (R 4.0.0)
##  memoise       1.1.0   2017-04-21 [1] CRAN (R 4.0.0)
##  modelr        0.1.6   2020-02-22 [1] CRAN (R 4.0.0)
##  munsell       0.5.0   2018-06-12 [1] CRAN (R 4.0.0)
##  nlme          3.1-145 2020-03-04 [1] CRAN (R 4.0.0)
##  pillar        1.4.3   2019-12-20 [1] CRAN (R 4.0.0)
##  pkgbuild      1.0.6   2019-10-09 [1] CRAN (R 4.0.0)
##  pkgconfig     2.0.3   2019-09-22 [1] CRAN (R 4.0.0)
##  pkgload       1.0.2   2018-10-29 [1] CRAN (R 4.0.0)
##  prettyunits   1.1.1   2020-01-24 [1] CRAN (R 4.0.0)
##  processx      3.4.2   2020-02-09 [1] CRAN (R 4.0.0)
##  ps            1.3.2   2020-02-13 [1] CRAN (R 4.0.0)
##  purrr       * 0.3.3   2019-10-18 [1] CRAN (R 4.0.0)
##  R6            2.4.1   2019-11-12 [1] CRAN (R 4.0.0)
##  Rcpp          1.0.4.6 2020-04-09 [1] CRAN (R 4.0.0)
##  readr       * 1.3.1   2018-12-21 [1] CRAN (R 4.0.0)
##  readxl        1.3.1   2019-03-13 [1] CRAN (R 4.0.0)
##  remotes       2.1.1   2020-02-15 [1] CRAN (R 4.0.0)
##  reprex        0.3.0   2019-05-16 [1] CRAN (R 4.0.0)
##  rlang         0.4.5   2020-03-01 [1] CRAN (R 4.0.0)
##  rmarkdown     2.1     2020-01-20 [1] CRAN (R 4.0.0)
##  rprojroot     1.3-2   2018-01-03 [1] CRAN (R 4.0.0)
##  rstudioapi    0.11    2020-02-07 [1] CRAN (R 4.0.0)
##  rvest         0.3.5   2019-11-08 [1] CRAN (R 4.0.0)
##  scales        1.1.0   2019-11-18 [1] CRAN (R 4.0.0)
##  sessioninfo   1.1.1   2018-11-05 [1] CRAN (R 4.0.0)
##  stringi       1.4.6   2020-02-17 [1] CRAN (R 4.0.0)
##  stringr     * 1.4.0   2019-02-10 [1] CRAN (R 4.0.0)
##  testthat      2.3.2   2020-03-02 [1] CRAN (R 4.0.0)
##  tibble      * 3.0.0   2020-03-30 [1] CRAN (R 4.0.0)
##  tidyr       * 1.0.2   2020-01-24 [1] CRAN (R 4.0.0)
##  tidyselect    1.0.0   2020-01-27 [1] CRAN (R 4.0.0)
##  tidyverse   * 1.3.0   2019-11-21 [1] CRAN (R 4.0.0)
##  usethis       1.6.0   2020-04-09 [1] CRAN (R 4.0.0)
##  vctrs         0.2.4   2020-03-10 [1] CRAN (R 4.0.0)
##  withr         2.1.2   2018-03-15 [1] CRAN (R 4.0.0)
##  xfun          0.13    2020-04-13 [1] CRAN (R 4.0.0)
##  xml2          1.3.1   2020-04-09 [1] CRAN (R 4.0.0)
##  yaml          2.2.1   2020-02-01 [1] CRAN (R 4.0.0)
## 
## [1] /Library/Frameworks/R.framework/Versions/4.0/Resources/library
```

</details>

<!-- FOOTER -->

***

<center>
<img src="/Users/selinjessa/Repos/rr/include/kleinman_lab_logo.png" width="20%" height="20%" />
</center>

<!-- Add icon library -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

<p style="text-align: center;">
A project of the Kleinman Lab at McGill University.
<br>
<a href="https://functionalgenomics.ca/" class="fa fa-home"></a>
<a href="https://github.com/fungenomics/" class="fa fa-github"></a>
</p>


<br>
