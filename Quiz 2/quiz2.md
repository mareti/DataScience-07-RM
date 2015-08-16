# Quiz 2

Muralidhar Areti  
Aug 16, 2015  

Q1  

```r
x = c(0.61, 0.93, 0.83, 0.35, 0.54, 0.16, 0.91, 0.62, 0.62)
y = c(0.67, 0.84, 0.6, 0.18, 0.85, 0.47, 1.1, 0.65, 0.36)

f = lm(y ~ x)
summary(f)
```

```
## 
## Call:
## lm(formula = y ~ x)
## 
## Residuals:
##      Min       1Q   Median       3Q      Max 
## -0.27636 -0.18807  0.01364  0.16595  0.27143 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)  
## (Intercept)   0.1885     0.2061   0.914    0.391  
## x             0.7224     0.3107   2.325    0.053 .
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 0.223 on 7 degrees of freedom
## Multiple R-squared:  0.4358,	Adjusted R-squared:  0.3552 
## F-statistic: 5.408 on 1 and 7 DF,  p-value: 0.05296
```

Q2  
from the summary, the residual is given

Q3  
In the mtcars data set, fit a linear regression model of weight (predictor) on mpg (outcome). Get a 95% confidence interval for the expected mpg at the average weight. What is the lower endpoint?

```r
data(mtcars)

x = mtcars$wt
y = mtcars$mpg

f = lm(y ~ x)
predict(f, data.frame(x=mean(x)), interval="confidence")
```

```
##        fit      lwr      upr
## 1 20.09062 18.99098 21.19027
```

Q4

```r
summary(f)
```

```
## 
## Call:
## lm(formula = y ~ x)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -4.5432 -2.3647 -0.1252  1.4096  6.8727 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)  37.2851     1.8776  19.858  < 2e-16 ***
## x            -5.3445     0.5591  -9.559 1.29e-10 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 3.046 on 30 degrees of freedom
## Multiple R-squared:  0.7528,	Adjusted R-squared:  0.7446 
## F-statistic: 91.38 on 1 and 30 DF,  p-value: 1.294e-10
```
The estimated expected change in mpg per 1,000 lb increase in weight  

Q5
Consider again the mtcars data set and a linear regression model with mpg as predicted by weight (1,000 lbs). A new car is coming weighing 3000 pounds. Construct a 95% prediction interval for its mpg. What is the upper endpoint? 

```r
predict(f, data.frame(x=mean(3)), interval="prediction")
```

```
##        fit      lwr      upr
## 1 21.25171 14.92987 27.57355
```

Q6  
Consider again the mtcars data set and a linear regression model with mpg as predicted by weight (in 1,000 lbs). A “short” ton is defined as 2,000 lbs. Construct a 95% confidence interval for the expected change in mpg per 1 short ton increase in weight. Give the lower endpoint.

```r
f2 = lm(y ~ I(x/2))
t2 = summary(f2)$coefficients

mu = t2[2,1]
se = t2[2,2]
df = f2$df

mu + c(1,-1) * qt(0.975, df=df) * se
```

```
## [1]  -8.40527 -12.97262
```

Q7  
If my X from a linear regression is measured in centimeters and I convert it to meters what would happen to the slope coefficient?

ans: it would get multiplied by 100

```r
f3 = lm(y ~ I(x/100))
summary(f)$coefficients[2,1]
```

```
## [1] -5.344472
```

```r
summary(f3)$coefficients[2,1]
```

```
## [1] -534.4472
```

Q8  
I have an outcome, Y, and a predictor, X and fit a linear regression model with Y=β<sup>0</sup>+β<sup>1</sup>X+ϵ to obtain β^<sup>0</sup> and β^<sup>1</sup>. What would be the consequence to the subsequent slope and intercept if I were to refit the model with a new regressor, X+c for some constant, c? 

Y = beta0 + beta1 * X + epsilon
    = beta1 * (X + c) + (beta0 - beta1 * c)
    
i.e. New intercept: beta0 - c*beta1

Q9  
Refer back to the mtcars data set with mpg as an outcome and weight (wt) as the predictor. About what is the ratio of the the sum of the squared errors, ∑ni=1(Y<sup>i</sup>−Y^<sup>i</sup>)^2^ when comparing a model with just an intercept (denominator) to the model with the intercept and slope (numerator)?

```r
fit_residual = f$residuals ^ 2
fit_intercept = lm(mpg ~ 1, mtcars)
fit_intercept_residual = fit_intercept$residuals ^ 2

sum(fit_residual) / sum(fit_intercept_residual)
```

```
## [1] 0.2471672
```

Q10  
Do the residuals always have to sum to 0 in linear regression?

```r
sum(resid(f))
```

```
## [1] -1.637579e-15
```
if an intercept is included then they will sum to 0
