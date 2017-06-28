# 03-rmd-lm-tables-inline-eqn
Your Name  
2017/06/27  

# Tasks

  - fit a linear model of Ozone ~ Temp + Wind + Solar.R 
    - (hint: use `lm`)
  - Make a table of the coefficients from the linear model 
    - (hint: use `coef` and `knitr::kable`)
  - Make some inline code chunks that describe the single values of the R-squared or a coefficient
  - Make an equation describing the relationship


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

![](03-rmd-lm-tables-inline-eqn_files/figure-html/figure-1-1.png)<!-- -->

We can also see that there is an interesting relationship between Ozone and temperature.


```
## Warning: Removed 37 rows containing missing values (geom_point).
```

![](03-rmd-lm-tables-inline-eqn_files/figure-html/figure-2-1.png)<!-- -->

- fit a linear model of Ozone ~ Temp + Wind + Solar.R 
    - (hint: use `lm`)
    

```r
lm_fit <- lm(Ozone ~ Temp + Wind + Solar.R,
             airquality)

lm_fit_coef <- coef(lm_fit)

lm_fit_coef
```

```
##  (Intercept)         Temp         Wind      Solar.R 
## -64.34207893   1.65209291  -3.33359131   0.05982059
```

    
  - Make a table of the coefficients from the linear model 
    - (hint: use `coef` and `knitr::kable`)
    


```r
library(knitr)

kable(lm_fit_coef)
```



------------  ------------
(Intercept)    -64.3420789
Temp             1.6520929
Wind            -3.3335913
Solar.R          0.0598206
------------  ------------

```r
kable(as.data.frame(lm_fit_coef))
```

               lm_fit_coef
------------  ------------
(Intercept)    -64.3420789
Temp             1.6520929
Wind            -3.3335913
Solar.R          0.0598206


  - Make some inline code chunks that describe the single values of the R-squared or a coefficient
  

```r
lm_fit_coef[1]
```

```
## (Intercept) 
##   -64.34208
```

We see that the intercept of the model is at -64.3420789

  - Make an equation describing the relationship
  
One could describe this linear model as:

$$
Ozone \sim \beta_0 + ...
$$
