# 04-rmd-global-opts-device
Your Name  
2017/06/27  


```r
knitr::opts_chunk$set(fig.width = 4,
                      fig.height = 5,
                      dev = c("png", "pdf", "tiff"))
```


# Tasks

- set a global option to: 
  - hide all of the code
    - hint: put `knitr::opts_chunk$set()` in a chunk and set the options
  - set the graphics device
    - hint: `dev = "png"` or even `dev = c("png", "pdf","tiff")`
  - set the DPI
    - hint: `dpi = 300`

# Introduction

This is a simple analysis of the New York Air Quality Measurements using the R statistical programming language. As stated in the helpfile `?airquality`, this dataset contains:

> Daily air quality measurements in New York, May to September 1973.

And the dataset is sourced from:

> ... the New York State Department of Conservation (ozone data) and the National Weather Service (meteorological data).

It contains the following variables

- Ozone: Mean ozone in parts per billion from 1300 to 1500 hours at Roosevelt Island.
- Solar.R: Solar radiation in Langleys in the frequency band 4000–7700 Angstroms from 0800 to 1200 hours at Central Park.
- Wind: Average wind speed in miles per hour at 0700 and 1000 hours at LaGuardia Airport.
- Temp: Maximum daily temperature in degrees Fahrenheit at La Guardia Airport.
- Month: Month (1--12)
- Day: Day of month (1--31)

We are going to explore the relationship between solar radiation and other selected variables, solar radiation, wind, and temperature.

# Method


```r
lm_fit <- lm(Ozone ~ Solar.R + Temp + Wind, 
             data = airquality)
```

$$
Ozone \sim \beta_0 + \beta_1Solar.R + \beta_2 Wind + \beta_3Temp + \epsilon
$$

# Results

We can see that there is an interesting relationship between ozone and solar radiation in figure 1 below, plotted using ggplot2.


```r
library(ggplot2)
ggplot(airquality,
       aes(x = Ozone,
           y = Solar.R)) + 
  geom_point()
```

```
## Warning: Removed 42 rows containing missing values (geom_point).
```

![](04-rmd-global-opts-device_files/figure-html/figure-1-1.png)<!-- -->

We can also see that there is an interesting relationship between Ozone and temperature.


```
## Warning: Removed 37 rows containing missing values (geom_point).
```

![](04-rmd-global-opts-device_files/figure-html/figure-2-1.png)<!-- -->



```r
knitr::kable(coef(lm_fit))
```



------------  ------------
(Intercept)    -64.3420789
Solar.R          0.0598206
Temp             1.6520929
Wind            -3.3335913
------------  ------------

0.0598206
`broom::glance(lm_fit)$r.squared`
