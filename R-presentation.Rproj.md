
<style>
body {
    overflow: scroll;
}
</style>


PRICE OF HORSES  
========================================================
author: Juan Miguel Rodriguez Lago 
date: 2th March 2021
autosize: true
font-import: https://fonts.googleapis.com/css2?family=Indie+Flower&display=swap"
font-family: 'Indie Flower';
css: css_style.css

Data Tidying and Reporting 

Master in Statistics for Data Science


========================================================
incremental: true
transition:fade
## Description
Price and related characteristics of horses listed for sale on the internet format.
## Details
Undergraduate students at Cal Poly collected data on prices of 50 horses advertised for sale on the internet. Predictor variables of price include the age and height of the horse (in hands), as well as its sex.

A data frame with 50 observations on the following 5 variables.
- HorseID: ID code for each horse
- Price: Price (in dollars)
- Age: Age of the horse (in years)
- Height: Height of the horse (in hands)
- Sex: f=female m=male


========================================================
incremental: true
transition:fade
type:exclaim
## Summary

Below it can be seen a brief summary of the features, with the minimum and maximum value, the first and third quantile, the mean and the median for each quantitative variable. 

- Summary of Price

```
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   1100   15000   25000   26840   39750   60000 
```

- Summary of Age

```
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   0.50    4.00    6.00    7.11    8.00   20.00 
```

- Summary of Height

```
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
  14.25   16.00   16.50   16.33   16.75   17.25       3 
```



Plots
========================================================
incremental: true
transition:fade

- Boxplot Price 


<style>
  .p_iframe iframe {
    width:100%;
    height:300px;
}
</style>

<div class="p_iframe">
<iframe frameborder="0" seamless='seamless' scrolling=no src="plotly1.html"></iframe>
</div>

***
- Histogram Age


<style>
  .p_iframe iframe {
    width:100%;
    height:300px;
}
</style>

<div class="p_iframe">
<iframe frameborder="0" seamless='seamless' scrolling=no src="plotly2.html"></iframe>
</div>


***
- Boxplot Height


<style>
  .p_iframe iframe {
    width:100%;
    height:300px;
}
</style>

<div class="p_iframe">
<iframe frameborder="0" seamless='seamless' scrolling=no src="plotly5.html"></iframe>
</div>


Scatterplots 
========================================================
incremental: true
transition:fade
- Price vs Age

In the following scatter plot we can see the relationship beteween the age of the horse and his price. 



<style>
  .p_iframe iframe {
    width:100%;
    height:500px;
}
</style>

<div class="p_iframe">
<iframe frameborder="0" seamless='seamless' scrolling=no src="plotly.html"></iframe>
</div>

***
- Price vs Height

In the following scatter plot we can see the relationship beteween the height of the horse and his price. 



<style>
  .p_iframe iframe {
    width:100%;
    height:500px;
}
</style>

<div class="p_iframe">
<iframe frameborder="0" seamless='seamless' scrolling=no src="plotly4.html"></iframe>
</div>


Multiple regression model  
========================================================
incremental: true
transition:fade
We are going to perform a multiple regression model to try to explain the price as a function of the age and the height of the horse. 
The regression model is formulated under certain assumptions that we need to
be aware off, since they need to be satisfied in order to make use of the model.

## Assumptions of linear regression:

- Linearity: The mean of the response, is a linear function of the predictors,
$$E[Y|X_1 = x_1, . . . , X_k = x_k] = \beta_0 + \beta_1 x_1 + . . . + \beta_k x_k$$

- Independence: The errors are independent,
$$Cov[\epsilon_i, \epsilon_j ] = 0,   i \neq j$$

- Homocedasticity: The variance of the errors at each value of the predictor is constant.
$$Var[\epsilon_i|X_1 = x_1, . . . , X_k = x_k] = \sigma^2$$

- Normality: The errors are Normally distributed.
$$\epsilon_i \sim N(0, \sigma^2)$$
In summary:
$$\epsilon \sim N(0, I\sigma^2)
) \Rightarrow Y \sim N(X\beta,I\sigma^2)$$

In this case the model is:  $$\hat{price_i}= \beta_0 + \beta_1 Age_i + \beta_2 Height_i$$

Results of the model  
========================================================
incremental: true
transition:fade

It can be seen that the coefficients are significant (p-value very low), which means that the coefficients of each of the predictors can be interpreted as follows, if we increase the age unit keeping the height constant, the price decreases by 1432 units. In the same way, the height coefficient can be interpreted.

We can see in the adjusted R squared that this model with the predictor variables age and height explains 33.6% of the variance of the horse price.


```

Call:
lm(formula = Price ~ Age + Height, data = HorsePrices)

Residuals:
   Min     1Q Median     3Q    Max 
-22842  -8606   -180   7360  34511 

Coefficients:
             Estimate Std. Error t value Pr(>|t|)    
(Intercept) -172210.0    45285.9  -3.803 0.000437 ***
Age           -1432.8      418.6  -3.423 0.001352 ** 
Height        12915.0     2824.9   4.572 3.91e-05 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 12010 on 44 degrees of freedom
  (3 observations deleted due to missingness)
Multiple R-squared:  0.3653,	Adjusted R-squared:  0.3365 
F-statistic: 12.66 on 2 and 44 DF,  p-value: 4.529e-05
```

![](https://github.com/juanmiRL/R-presentation/blob/main/american-quarter-horse.jpg?raw=true)



