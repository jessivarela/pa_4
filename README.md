Programming Assignment 4
================

**Author**: Your name here
**Date**: Last update: 2020-04-18 22:57:30

Overview
========

<!-- 
  Talk brielfy about what you did here 
  Describe your hypotheses
-->
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Prep
====

``` r
## Libraries
library(tidyverse)
```

    ## ── Attaching packages ───────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.1.1       ✔ purrr   0.3.3  
    ## ✔ tibble  2.1.1       ✔ dplyr   0.8.0.1
    ## ✔ tidyr   0.8.3       ✔ stringr 1.4.0  
    ## ✔ readr   1.3.1       ✔ forcats 0.4.0

    ## ── Conflicts ──────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
bi01 <- read_csv("data/bi01.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   fileID = col_character(),
    ##   f1 = col_double(),
    ##   f2 = col_double(),
    ##   vot = col_double(),
    ##   notes = col_character()
    ## )

``` r
library(knitr)
kable(bi01[1:45, ], caption = " Bi01 table")
```

| fileID      |      f1|       f2|     vot| notes |
|:------------|-------:|--------:|-------:|:------|
| bi01\_kaka  |  650.90|  1637.02|   24.81| NA    |
| bi01\_kaka1 |  714.32|  1567.58|   25.49| NA    |
| bi01\_kaka2 |  709.19|  1560.03|   28.29| NA    |
| bi01\_keke  |  495.24|  2168.42|   31.55| NA    |
| bi01\_keke1 |  893.01|  2152.98|   32.39| NA    |
| bi01\_keke2 |  579.31|  2339.40|   32.87| NA    |
| bi01\_kiki  |  823.90|  2711.97|   18.54| NA    |
| bi01\_kiki1 |  348.26|  2632.05|   52.80| NA    |
| bi01\_kiki2 |  493.55|  2765.72|   50.48| NA    |
| bi01\_koko  |  498.60|  1049.62|   30.88| NA    |
| bi01\_koko1 |  513.35|  1012.33|   23.98| NA    |
| bi01\_koko2 |  599.63|  1095.21|   26.13| NA    |
| bi01\_kuku  |  520.29|  1085.70|   31.55| NA    |
| bi01\_kuku1 |  457.27|  1085.94|   29.56| NA    |
| bi01\_kuku2 |  231.68|  1523.96|  167.71| error |
| bi01\_paka  |  636.92|  1798.53|   10.82| NA    |
| bi01\_paka1 |  478.08|  1203.61|   26.06| NA    |
| bi01\_paka2 |  723.91|  1591.12|   18.49| NA    |
| bi01\_peke  |  480.94|  2388.24|   16.16| NA    |
| bi01\_peke1 |  538.02|  2385.35|   16.12| NA    |
| bi01\_peke2 |  586.71|  2189.72|   13.36| NA    |
| bi01\_piki  |  394.24|  2572.92|   23.80| NA    |
| bi01\_piki1 |  300.41|  2576.74|   27.74| NA    |
| bi01\_piki2 |  412.77|  2696.80|   14.36| NA    |
| bi01\_poko  |  574.84|  1182.03|   20.75| NA    |
| bi01\_poko1 |  456.21|  1060.58|   17.19| NA    |
| bi01\_poko2 |  350.93|  1039.92|   18.90| NA    |
| bi01\_puku  |  436.90|   936.48|   18.83| NA    |
| bi01\_puku1 |  438.71|   919.01|   46.71| NA    |
| bi01\_puku2 |  425.06|   979.09|   23.93| NA    |
| bi01\_taka  |  662.33|  1678.52|   10.16| NA    |
| bi01\_taka1 |  697.26|  1675.21|   16.65| NA    |
| bi01\_taka2 |  300.67|  1410.20|   17.95| NA    |
| bi01\_teke  |  518.24|  2340.06|   15.48| NA    |
| bi01\_teke1 |  669.55|  2311.48|   14.44| NA    |
| bi01\_teke2 |  514.68|  2361.35|   17.17| NA    |
| bi01\_tiki  |  298.87|  2629.78|   16.16| NA    |
| bi01\_tiki1 |  461.89|  2637.19|   18.80| NA    |
| bi01\_tiki2 |  448.42|  2666.14|   27.66| NA    |
| bi01\_toko  |  598.46|  1154.98|   16.57| NA    |
| bi01\_toko1 |  526.94|  1062.50|   16.22| NA    |
| bi01\_toko2 |  510.96|  1073.20|   19.27| NA    |
| bi01\_tuku  |  529.54|   831.24|   14.10| NA    |
| bi01\_tuku1 |  477.36|  1022.60|   22.78| NA    |
| bi01\_tuku2 |  432.98|   963.16|   15.22| NA    |

``` r
mean(bi01$vot, na.rm = TRUE)  
```

    ## [1] 26.19733

``` r
bi02 <- read_csv("data/bi02.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   fileID = col_character(),
    ##   f1 = col_double(),
    ##   f2 = col_double(),
    ##   vot = col_double(),
    ##   notes = col_logical()
    ## )

``` r
kable(bi02[1:45, ], caption = " Bi02 table")
```

| fileID      |      f1|       f2|    vot| notes |
|:------------|-------:|--------:|------:|:------|
| bi02\_kaka  |  793.30|  1574.03|  21.55| NA    |
| bi02\_kaka1 |  793.60|  1544.95|  29.60| NA    |
| bi02\_kaka2 |  526.55|  1489.58|  26.71| NA    |
| bi02\_keke  |  473.19|  2186.96|  23.96| NA    |
| bi02\_keke1 |  463.09|  2344.86|  19.74| NA    |
| bi02\_keke2 |  515.20|  2237.02|   0.41| NA    |
| bi02\_kiki  |  335.23|  2629.55|  36.06| NA    |
| bi02\_kiki1 |  348.28|  2681.40|  26.13| NA    |
| bi02\_kiki2 |  338.12|  2621.42|  26.96| NA    |
| bi02\_koko  |  617.03|   991.59|  32.00| NA    |
| bi02\_koko1 |  591.67|   962.36|  32.96| NA    |
| bi02\_koko2 |  463.70|   894.42|  38.46| NA    |
| bi02\_kuku  |  471.74|   903.69|  43.48| NA    |
| bi02\_kuku1 |  467.79|   914.34|  32.94| NA    |
| bi02\_kuku2 |  299.20|   763.95|  27.52| NA    |
| bi02\_paka  |  816.94|  1634.44|   6.85| NA    |
| bi02\_paka1 |  728.30|  1458.21|  18.85| NA    |
| bi02\_paka2 |  687.46|  1615.72|  12.42| NA    |
| bi02\_peke  |  500.98|  2264.88|  22.42| NA    |
| bi02\_peke1 |  461.54|  2349.54|  20.53| NA    |
| bi02\_peke2 |  488.10|  2344.74|  16.44| NA    |
| bi02\_piki  |  357.87|  1639.76|  26.79| NA    |
| bi02\_piki1 |  289.09|  2427.73|  20.84| NA    |
| bi02\_piki2 |  572.90|  2681.98|  29.86| NA    |
| bi02\_poko  |  582.08|   919.16|  21.15| NA    |
| bi02\_poko1 |  584.30|   951.23|  19.92| NA    |
| bi02\_poko2 |  560.81|  1054.90|  21.39| NA    |
| bi02\_puku  |  506.90|   897.91|  29.44| NA    |
| bi02\_puku1 |  461.75|   860.87|  15.98| NA    |
| bi02\_puku2 |  432.52|   808.62|  25.48| NA    |
| bi02\_taka  |  814.63|  1548.56|  13.74| NA    |
| bi02\_taka1 |  751.02|  1528.21|  17.17| NA    |
| bi02\_taka2 |  503.55|  1442.42|  19.22| NA    |
| bi02\_teke  |  530.08|  2216.71|  13.42| NA    |
| bi02\_teke1 |  465.73|  2334.47|  19.85| NA    |
| bi02\_teke2 |  401.24|  1516.55|  13.93| NA    |
| bi02\_tiki  |  643.41|  2277.45|  21.69| NA    |
| bi02\_tiki1 |  345.94|  2752.15|  19.65| NA    |
| bi02\_tiki2 |  608.91|  2211.76|  25.53| NA    |
| bi02\_toko  |  505.23|   919.97|  11.01| NA    |
| bi02\_toko1 |  543.37|   964.12|  13.03| NA    |
| bi02\_toko2 |  603.96|  1000.18|  16.56| NA    |
| bi02\_tuku  |  472.73|   962.50|  19.99| NA    |
| bi02\_tuku1 |  467.07|   929.20|  16.05| NA    |
| bi02\_tuku2 |  519.85|   833.03|  19.79| NA    |

``` r
bi03 <- read_csv("data/bi03.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   fileID = col_character(),
    ##   f1 = col_double(),
    ##   f2 = col_double(),
    ##   vot = col_double(),
    ##   notes = col_logical()
    ## )

``` r
kable(bi03[1:45, ], caption = " Bi03 table")
```

| fileID      |       f1|       f2|    vot| notes |
|:------------|--------:|--------:|------:|:------|
| bi03\_kaka  |  1050.46|  1891.33|  20.01| NA    |
| bi03\_kaka1 |   833.30|  1495.70|  23.39| NA    |
| bi03\_kaka2 |   822.12|  1659.80|  26.53| NA    |
| bi03\_keke  |   589.48|  2414.55|  26.72| NA    |
| bi03\_keke1 |   525.56|  2281.49|  19.09| NA    |
| bi03\_keke2 |   555.79|  2487.71|  21.09| NA    |
| bi03\_kiki  |   400.42|  2667.24|  25.34| NA    |
| bi03\_kiki1 |   354.83|  2690.90|  29.57| NA    |
| bi03\_kiki2 |   347.88|  2678.54|  22.49| NA    |
| bi03\_koko  |   588.65|   828.24|  28.02| NA    |
| bi03\_koko1 |   553.68|   902.57|  24.49| NA    |
| bi03\_koko2 |   749.63|  1160.73|  23.74| NA    |
| bi03\_kuku  |   393.76|   761.01|  24.37| NA    |
| bi03\_kuku1 |   299.03|  1736.22|  28.00| NA    |
| bi03\_kuku2 |   406.59|   824.67|  26.08| NA    |
| bi03\_paka  |  1131.33|  1700.92|  11.70| NA    |
| bi03\_paka1 |   758.65|  1622.58|  11.81| NA    |
| bi03\_paka2 |   644.17|  1779.18|  11.89| NA    |
| bi03\_peke  |   420.64|  1797.26|  10.31| NA    |
| bi03\_peke1 |   556.08|  2331.56|   9.43| NA    |
| bi03\_peke2 |   962.79|  2407.49|  13.58| NA    |
| bi03\_piki  |   350.61|  2644.89|  14.64| NA    |
| bi03\_piki1 |   328.39|  2856.40|  18.75| NA    |
| bi03\_piki2 |  1810.90|  2941.83|  16.73| NA    |
| bi03\_poko  |   533.99|   886.22|  28.45| NA    |
| bi03\_poko1 |   623.13|  1865.05|   7.94| NA    |
| bi03\_poko2 |   515.64|   870.68|  17.12| NA    |
| bi03\_puku  |   442.39|   576.83|  20.85| NA    |
| bi03\_puku1 |   669.95|  1715.70|  34.17| NA    |
| bi03\_puku2 |   422.74|   814.15|  16.83| NA    |
| bi03\_taka  |   785.94|  1640.76|  16.84| NA    |
| bi03\_taka1 |   846.52|  1640.57|  16.45| NA    |
| bi03\_taka2 |   863.61|  1532.93|  14.99| NA    |
| bi03\_teke  |   460.82|  2349.24|  13.11| NA    |
| bi03\_teke1 |   452.67|  2406.16|  15.93| NA    |
| bi03\_teke2 |   433.16|  2440.39|  18.17| NA    |
| bi03\_tiki  |   356.85|  2505.49|  15.40| NA    |
| bi03\_tiki1 |   888.72|  2237.48|  13.34| NA    |
| bi03\_tiki2 |   417.91|  1905.22|  19.95| NA    |
| bi03\_toko  |   795.19|   973.48|  18.77| NA    |
| bi03\_toko1 |   751.12|  1142.44|  13.79| NA    |
| bi03\_toko2 |   773.87|  1061.37|  13.12| NA    |
| bi03\_tuku  |   660.47|   811.96|  11.37| NA    |
| bi03\_tuku1 |   386.71|   731.36|   5.97| NA    |
| bi03\_tuku2 |   395.01|   737.97|   7.81| NA    |

``` r
ne01 <- read_csv("data/ne01.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   fileID = col_character(),
    ##   f1 = col_double(),
    ##   f2 = col_double(),
    ##   vot = col_double(),
    ##   notes = col_logical()
    ## )

``` r
kable(ne01[1:45, ], caption = " ne01 table")
```

| fileID      |       f1|       f2|    vot| notes |
|:------------|--------:|--------:|------:|:------|
| ne01\_kaka  |   888.07|  1648.85|  14.80| NA    |
| ne01\_kaka1 |   950.47|  1769.28|  17.74| NA    |
| ne01\_kaka2 |  1074.88|  1758.22|  17.38| NA    |
| ne01\_keke  |   470.99|  2484.59|  35.66| NA    |
| ne01\_keke1 |   603.90|  2474.00|  20.00| NA    |
| ne01\_keke2 |   491.90|  2646.25|  23.70| NA    |
| ne01\_kiki  |   355.74|  2845.27|  18.26| NA    |
| ne01\_kiki1 |   958.08|  2261.88|  28.98| NA    |
| ne01\_kiki2 |   438.62|  2781.91|  29.37| NA    |
| ne01\_koko  |   665.11|  1080.23|  16.82| NA    |
| ne01\_koko1 |   577.69|  1062.39|  14.30| NA    |
| ne01\_koko2 |   649.28|  1103.05|  17.67| NA    |
| ne01\_kuku  |   487.75|  1103.41|  22.44| NA    |
| ne01\_kuku1 |   441.46|  1007.64|  17.16| NA    |
| ne01\_kuku2 |  1086.29|  2129.31|  12.18| NA    |
| ne01\_paka  |   757.50|  1498.19|  11.51| NA    |
| ne01\_paka1 |   797.88|  1525.88|   5.87| NA    |
| ne01\_paka2 |   847.54|  1650.43|   8.14| NA    |
| ne01\_peke  |   394.63|  2670.13|   4.37| NA    |
| ne01\_peke1 |   382.44|  2669.54|  14.15| NA    |
| ne01\_peke2 |   548.79|  2518.09|   6.29| NA    |
| ne01\_piki  |   400.48|  2849.75|   4.90| NA    |
| ne01\_piki1 |   419.54|  2873.08|   6.15| NA    |
| ne01\_piki2 |   372.17|  2932.67|   4.62| NA    |
| ne01\_poko  |   517.01|  1082.60|  19.72| NA    |
| ne01\_poko1 |   575.73|  1155.71|  13.20| NA    |
| ne01\_poko2 |   509.17|  1056.30|   4.98| NA    |
| ne01\_puku  |   422.51|  1061.70|   8.68| NA    |
| ne01\_puku1 |   449.86|  1061.17|  13.08| NA    |
| ne01\_puku2 |   438.81|  1011.47|  22.90| NA    |
| ne01\_taka  |   884.77|  1702.06|   9.19| NA    |
| ne01\_taka1 |  1210.37|  1786.24|   6.77| NA    |
| ne01\_taka2 |   925.35|  1737.58|   4.31| NA    |
| ne01\_teke  |   518.10|  2460.10|   8.70| NA    |
| ne01\_teke1 |   549.96|  2475.07|   6.28| NA    |
| ne01\_teke2 |   748.88|  2500.86|   3.69| NA    |
| ne01\_tiki  |   372.27|  2875.39|   4.80| NA    |
| ne01\_tiki1 |   384.19|  2838.28|   4.32| NA    |
| ne01\_tiki2 |   362.28|  3006.21|  14.66| NA    |
| ne01\_toko  |   580.28|   981.00|   2.69| NA    |
| ne01\_toko1 |   439.56|  1082.48|   5.82| NA    |
| ne01\_toko2 |   557.98|  1063.93|   6.03| NA    |
| ne01\_tuku  |   422.39|  1065.90|  19.29| NA    |
| ne01\_tuku1 |   414.20|  1071.89|   9.04| NA    |
| ne01\_tuku2 |  1051.79|  1650.95|  11.54| NA    |

``` r
ne02 <- read_csv("data/ne02.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   fileID = col_character(),
    ##   f1 = col_double(),
    ##   f2 = col_double(),
    ##   vot = col_double(),
    ##   notes = col_logical()
    ## )

``` r
kable(ne02[1:45, ], caption = " ne02 table")
```

| fileID      |       f1|       f2|    vot| notes |
|:------------|--------:|--------:|------:|:------|
| ne02\_kaka  |   590.84|  1437.68|  22.35| NA    |
| ne02\_kaka1 |   870.48|  2209.19|  62.94| NA    |
| ne02\_kaka2 |    77.98|  1503.08|  49.22| NA    |
| ne02\_keke  |   464.15|  2408.32|  26.46| NA    |
| ne02\_keke1 |   424.21|  2481.53|  43.16| NA    |
| ne02\_keke2 |   500.85|  2243.07|  25.40| NA    |
| ne02\_kiki  |   356.70|  2691.05|  56.36| NA    |
| ne02\_kiki1 |   343.97|  2779.35|  82.37| NA    |
| ne02\_kiki2 |   318.82|  2783.60|  48.37| NA    |
| ne02\_koko  |   553.42|  1041.25|  29.83| NA    |
| ne02\_koko1 |   404.32|  1026.42|  26.71| NA    |
| ne02\_koko2 |   529.08|  1076.27|  34.17| NA    |
| ne02\_kuku  |   892.95|  1113.98|  52.04| NA    |
| ne02\_kuku1 |   336.99|  1143.45|  55.40| NA    |
| ne02\_kuku2 |   481.30|  1141.18|  47.83| NA    |
| ne02\_paka  |   761.80|  1680.30|  19.46| NA    |
| ne02\_paka1 |   863.92|  1521.54|  17.04| NA    |
| ne02\_paka2 |  1055.36|  1785.00|  15.66| NA    |
| ne02\_peke  |   544.66|  2393.68|  40.68| NA    |
| ne02\_peke1 |   525.19|  2456.19|   8.64| NA    |
| ne02\_peke2 |   529.60|  2469.49|  34.95| NA    |
| ne02\_piki  |   346.27|  2627.83|   5.52| NA    |
| ne02\_piki1 |   380.97|  2710.23|   6.70| NA    |
| ne02\_piki2 |   445.66|  2643.52|   7.25| NA    |
| ne02\_poko  |   578.32|  1034.92|  16.34| NA    |
| ne02\_poko1 |  1021.82|  2160.31|  21.65| NA    |
| ne02\_poko2 |   616.31|  1564.72|  19.21| NA    |
| ne02\_puku  |   436.62|  1053.90|  22.98| NA    |
| ne02\_puku1 |   493.96|  1209.62|  31.07| NA    |
| ne02\_puku2 |   449.36|  1261.87|  21.68| NA    |
| ne02\_taka  |   449.36|  1261.87|  21.68| NA    |
| ne02\_taka1 |   828.28|  1591.14|  11.83| NA    |
| ne02\_taka2 |   807.68|  1661.53|  21.70| NA    |
| ne02\_teke  |   518.18|  2397.23|  22.75| NA    |
| ne02\_teke1 |   479.72|  2481.82|  27.88| NA    |
| ne02\_teke2 |   665.31|  1854.87|  28.77| NA    |
| ne02\_tiki  |   299.92|  2860.63|  31.38| NA    |
| ne02\_tiki1 |   314.76|  2752.52|  28.48| NA    |
| ne02\_tiki2 |   291.64|  2705.72|  28.00| NA    |
| ne02\_toko  |   500.19|   994.39|  27.27| NA    |
| ne02\_toko1 |   595.35|  1155.93|  45.13| NA    |
| ne02\_toko2 |   536.02|  1020.34|  28.51| NA    |
| ne02\_tuku  |   469.89|  1304.34|  32.55| NA    |
| ne02\_tuku1 |   441.39|  1121.08|  36.65| NA    |
| ne02\_tuku2 |   732.00|  1468.51|  32.44| NA    |

``` r
ne03 <- read_csv("data/ne03.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   fileID = col_character(),
    ##   f1 = col_double(),
    ##   f2 = col_double(),
    ##   vot = col_double(),
    ##   notes = col_logical()
    ## )

``` r
kable(ne03[1:45, ], caption = " ne03 table")
```

| fileID      |      f1|       f2|    vot| notes |
|:------------|-------:|--------:|------:|:------|
| ne03\_kaka  |  770.42|  1803.00|  27.03| NA    |
| ne03\_kaka1 |  815.85|  1737.43|  25.44| NA    |
| ne03\_kaka2 |  882.82|  1656.87|  31.88| NA    |
| ne03\_keke  |  687.94|  2637.73|  26.18| NA    |
| ne03\_keke1 |  566.40|  1749.11|  29.82| NA    |
| ne03\_keke2 |  562.00|  2547.78|  32.45| NA    |
| ne03\_kiki  |  509.97|  2714.88|  33.47| NA    |
| ne03\_kiki1 |  401.15|  2158.23|  66.23| NA    |
| ne03\_kiki2 |  372.92|  2810.92|  53.59| NA    |
| ne03\_koko  |  507.19|  1070.28|  39.55| NA    |
| ne03\_koko1 |  556.76|  1214.75|  30.81| NA    |
| ne03\_koko2 |  570.59|  1092.01|  31.42| NA    |
| ne03\_kuku  |  516.12|   991.68|  39.03| NA    |
| ne03\_kuku1 |  464.95|  1071.73|  26.57| NA    |
| ne03\_kuku2 |  413.13|  1060.30|  33.55| NA    |
| ne03\_paka  |  841.04|  1790.54|   8.12| NA    |
| ne03\_paka1 |  725.57|  1837.30|   9.90| NA    |
| ne03\_paka2 |  731.69|  1941.48|   6.07| NA    |
| ne03\_peke  |  548.20|  1502.00|   6.66| NA    |
| ne03\_peke1 |  728.73|  2485.13|  26.57| NA    |
| ne03\_peke2 |  600.49|  2290.92|   8.54| NA    |
| ne03\_piki  |  363.86|  2615.63|  17.61| NA    |
| ne03\_piki1 |  379.52|  1967.79|  29.98| NA    |
| ne03\_piki2 |  392.12|  2239.25|  14.28| NA    |
| ne03\_poko  |  638.10|  1121.61|   5.95| NA    |
| ne03\_poko1 |  585.17|  1183.71|  30.16| NA    |
| ne03\_poko2 |  594.74|  1101.79|  28.74| NA    |
| ne03\_puku  |  825.77|  1297.54|  19.64| NA    |
| ne03\_puku1 |  428.63|   971.71|  43.50| NA    |
| ne03\_puku2 |  485.17|   984.51|  60.72| NA    |
| ne03\_taka  |  739.66|  1834.87|  14.64| NA    |
| ne03\_taka1 |  857.38|  1750.11|  19.78| NA    |
| ne03\_taka2 |  726.39|  1405.64|  12.05| NA    |
| ne03\_teke  |  577.16|  1511.80|  31.71| NA    |
| ne03\_teke1 |  575.33|  1878.78|  26.18| NA    |
| ne03\_teke2 |  564.86|  1675.94|  17.49| NA    |
| ne03\_tiki  |  387.65|  2787.01|  39.62| NA    |
| ne03\_tiki1 |  376.63|  1570.68|  70.08| NA    |
| ne03\_tiki2 |  412.79|  1718.48|  25.72| NA    |
| ne03\_toko  |  613.76|  1098.71|  25.44| NA    |
| ne03\_toko1 |  619.15|  1193.41|  30.11| NA    |
| ne03\_toko2 |  528.31|  1043.78|  18.33| NA    |
| ne03\_tuku  |  445.61|  1096.95|  30.49| NA    |
| ne03\_tuku1 |  428.53|  1051.32|  51.04| NA    |
| ne03\_tuku2 |  474.86|  1125.31|  35.00| NA    |
