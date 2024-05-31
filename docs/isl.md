ISL_Class
================

``` r
library(ISLR2)
```

    ## Warning: package 'ISLR2' was built under R version 4.3.3

``` r
default <- as.data.frame(Default)

str(default)
```

    ## 'data.frame':    10000 obs. of  4 variables:
    ##  $ default: Factor w/ 2 levels "No","Yes": 1 1 1 1 1 1 1 1 1 1 ...
    ##  $ student: Factor w/ 2 levels "No","Yes": 1 2 1 1 1 2 1 2 1 1 ...
    ##  $ balance: num  730 817 1074 529 786 ...
    ##  $ income : num  44362 12106 31767 35704 38463 ...

``` r
summary(default)
```

    ##  default    student       balance           income     
    ##  No :9667   No :7056   Min.   :   0.0   Min.   :  772  
    ##  Yes: 333   Yes:2944   1st Qu.: 481.7   1st Qu.:21340  
    ##                        Median : 823.6   Median :34553  
    ##                        Mean   : 835.4   Mean   :33517  
    ##                        3rd Qu.:1166.3   3rd Qu.:43808  
    ##                        Max.   :2654.3   Max.   :73554

``` r
glm.fits <- glm(
  default ~ balance + income,
  data = default, family = binomial
)
summary(glm.fits)
```

    ## 
    ## Call:
    ## glm(formula = default ~ balance + income, family = binomial, 
    ##     data = default)
    ## 
    ## Coefficients:
    ##               Estimate Std. Error z value Pr(>|z|)    
    ## (Intercept) -1.154e+01  4.348e-01 -26.545  < 2e-16 ***
    ## balance      5.647e-03  2.274e-04  24.836  < 2e-16 ***
    ## income       2.081e-05  4.985e-06   4.174 2.99e-05 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 2920.6  on 9999  degrees of freedom
    ## Residual deviance: 1579.0  on 9997  degrees of freedom
    ## AIC: 1585
    ## 
    ## Number of Fisher Scoring iterations: 8
