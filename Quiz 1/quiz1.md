# Quiz 1

Muralidhar Areti  
Aug 9, 2015  

Q1  

```r
x = c(0.18, -1.54, 0.42, 0.95)
w = c(2, 1, 3, 1)

weighted.mean(x, w)
```

```
## [1] 0.1471429
```

Q2  

```r
x <- c(0.8, 0.47, 0.51, 0.73, 0.36, 0.58, 0.57, 0.85, 0.44, 0.42)
y <- c(1.39, 0.72, 1.55, 0.48, 1.19, -1.59, 1.23, -0.65, 1.49, 0.05)

fit = lm(y ~ x - 1)
summary(fit)
```

```
## 
## Call:
## lm(formula = y ~ x - 1)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -2.0692 -0.2536  0.5303  0.8592  1.1286 
## 
## Coefficients:
##   Estimate Std. Error t value Pr(>|t|)
## x   0.8263     0.5817   1.421    0.189
## 
## Residual standard error: 1.094 on 9 degrees of freedom
## Multiple R-squared:  0.1831,	Adjusted R-squared:  0.09238 
## F-statistic: 2.018 on 1 and 9 DF,  p-value: 0.1892
```

Q3

```r
data(mtcars)
fit = lm(mpg ~ wt, mtcars)
summary(fit)
```

```
## 
## Call:
## lm(formula = mpg ~ wt, data = mtcars)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -4.5432 -2.3647 -0.1252  1.4096  6.8727 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)  37.2851     1.8776  19.858  < 2e-16 ***
## wt           -5.3445     0.5591  -9.559 1.29e-10 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 3.046 on 30 degrees of freedom
## Multiple R-squared:  0.7528,	Adjusted R-squared:  0.7446 
## F-statistic: 91.38 on 1 and 30 DF,  p-value: 1.294e-10
```

Q4

```r
corr_XY = 0.5
sd_XY = 2

beta = corr_XY * sd_XY
```

Q5

```r
corr_XY = 0.4
q1 = 1.5
q2 = q1 * corr_XY * 1 + 0

q2
```

```
## [1] 0.6
```

Q6

```r
x <- c(8.58, 10.46, 9.01, 9.64, 8.86)

mu = mean(x)
sd = sd(x)

first_value = (x[1] - mu)/sd
first_value
```

```
## [1] -0.9718658
```

Q7  

```r
x <- c(0.8, 0.47, 0.51, 0.73, 0.36, 0.58, 0.57, 0.85, 0.44, 0.42)
y <- c(1.39, 0.72, 1.55, 0.48, 1.19, -1.59, 1.23, -0.65, 1.49, 0.05)

fit = lm(y ~ x)
summary(fit)
```

```
## 
## Call:
## lm(formula = y ~ x)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -2.1640 -0.5818  0.2010  0.6669  1.1928 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)
## (Intercept)    1.567      1.252   1.252    0.246
## x             -1.713      2.105  -0.814    0.439
## 
## Residual standard error: 1.061 on 8 degrees of freedom
## Multiple R-squared:  0.07642,	Adjusted R-squared:  -0.03903 
## F-statistic: 0.662 on 1 and 8 DF,  p-value: 0.4394
```

Q8

```r
# it must be identically 0
```

Q9

```r
x <- c(0.8, 0.47, 0.51, 0.73, 0.36, 0.58, 0.57, 0.85, 0.44, 0.42)

mean(x)
```

```
## [1] 0.573
```

Q10

```r
# var(y)/var(x)
```
