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

## Summary

Below it can be seen a brief summary of the features, with the minimum and maximum value, the first and third quantile, the mean and the median for each quantitative variable. For the categorical variable (sex) it can be seen a count for each level. 

```
    HorseID           Price            Age            Height      Sex   
 Min.   :  2.00   Min.   : 1100   Min.   : 0.50   Min.   :14.25   f:20  
 1st Qu.: 43.25   1st Qu.:15000   1st Qu.: 4.00   1st Qu.:16.00   m:30  
 Median :101.50   Median :25000   Median : 6.00   Median :16.50         
 Mean   :111.88   Mean   :26840   Mean   : 7.11   Mean   :16.33         
 3rd Qu.:174.50   3rd Qu.:39750   3rd Qu.: 8.00   3rd Qu.:16.75         
 Max.   :249.00   Max.   :60000   Max.   :20.00   Max.   :17.25         
                                                  NA's   :3             
```


Plots
========================================================

## Boxplot Price 


<style>
  .p_iframe iframe {
    width:100%;
    height:300px;
}
</style>

<div class="p_iframe">
<iframe frameborder="0" seamless='seamless' scrolling=yes src="plotly1.html"></iframe>
</div>

***
## Histogram Age


<style>
  .p_iframe iframe {
    width:100%;
    height:300px;
}
</style>

<div class="p_iframe">
<iframe frameborder="0" seamless='seamless' scrolling=yes src="plotly2.html"></iframe>
</div>

Scatterplots 
========================================================

## Price vs Age
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
## Price vs Height

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

We are going to perform a multiple regression model to try to explain the price as a function of the age and the height of the horse. 
The regression model is formulated under certain assumptions that we need to
be aware off, since they need to be satisfied in order to make use of the model.

In this case the model is:  $$\hat{price_i}= \beta_0 + \beta_1 Age_i + \beta_2 Height_i$$


```
               Estimate Std. Error   t value     Pr(>|t|)
(Intercept) -172210.013 45285.9372 -3.802726 4.373692e-04
Age           -1432.837   418.6429 -3.422574 1.351502e-03
Height        12914.956  2824.8927  4.571840 3.908789e-05
```


***
## Assumptions of linear regression:

• Linearity: The mean of the response, is a linear function of the predictors,
$$E[Y|X_1 = x_1, . . . , X_k = x_k] = \beta_0 + \beta_1 x_1 + . . . + \beta_k x_k$$

• Independence: The errors are independent,
$$Cov[\epsilon_i, \epsilon_j ] = 0,   i \neq j$$

• Homocedasticity: The variance of the errors at each value of the predictor is constant.
$$Var[\epsilon_i|X_1 = x_1, . . . , X_k = x_k] = \sigma^2$$

• Normality: The errors are Normally distributed.
$$\epsilon_i ∼ N(0, \sigma^2)$$
In summary:
$$\epsilon ∼ N(0, I\sigma^2)
) ⇒ Y ∼ N(X\beta,I\sigma^2)$$




