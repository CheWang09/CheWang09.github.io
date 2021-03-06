---
layout:     post
title:      Logistic Regression
author:     CHENEY WANG
tags: 		MachineLearning Review
header-img:  "img/manhanton.jpg"
subtitle:  	Logistic Regression Review
category:  project
---
<!-- Start Writing Below in Markdown -->


# 逻辑回归回顾
<br > 这篇分享，我仅从频率学学派派去推导逻辑回归。后期会加上从贝叶斯学派进行的逻辑回归推导
        This post, I'm gonna introduce logistic regression from frequentist perspective, and I will add conduction of logistic regression from bayes perspective.
## Logistic Regression Summary
Logistic regression is the appropriate regression analysis to conduct when the dependent variable is dichotomous (binary).  Like all regression analyses, the logistic regression is a predictive analysis.  Logistic regression is used to describe data and to explain the relationship between one dependent binary variable and one or more nominal, ordinal, interval or ratio-level independent variables.
![image](/img/Post_image/2018-11-17-15-09-09.png)
## Mathmatical function of LR:
### Base function( hypothesis fucntion of linear regression )
$$ 
\begin{align}
\text{Hypothesis:} \quad H_w(X) = W_1+W_1X_2+ ... + W_nX_n 
\end{align}
$$
### Sigmoid Function of LR:
Sigmoid function is implemented to compress predict value into {0,1}, which can help us to do classification.
$$ 
\begin{align}
\text{Sigmoid} & = \frac{1}{1+e^{-θ^{T}x}}  \\
θ^{T}x = H_{\theta}(X) &\quad \text{which is base function}
\end{align}
$$

### Hypothesis function of LR:
$$
\begin{align}
\text{Hypothesis of LR} = \frac{1}{1+e^{-w^{T}x}}  
\end{align}
$$
And different from linear regression, the graph of this function is not a bowl-shaped funciton . Therefore, it would be hard to get a global minimum. So loss function of logistic regression is different from linear regression.
### Cost function of LR:
If we use least square as our loss function, the cost function would be a non-convex function that we can not get global minimum.  
$$
\begin{align}
J(\theta) = (y^i - H_\theta(X^{i}))
\end{align}
$$
![imgae](/img/Post_image/2018-11-17-15-22-06.png)

In order to overcome this issue, we use logistic loss as our loss function and cross-entry as our cost function.
$$
\begin{align}
J(\theta) & =  \frac{1}{m} \sum_{i=1}^{m} \text{Cost}
(h_\theta(x^i), y^i) \\
 &= -\frac{1}{m} \sum_{i=1}^{m} [y^ilog \ h_\theta(x^i) + (1 - y^i) \ log \ (1 - h_\theta(x^i)]  \\
To \ fit \ parameter \ \theta : \\
& min_\theta J(\theta)
\end{align}
$$
![image](/img/Post_image/2018-11-17-15-37-25.png)
$$ 
\begin{align}
&\text{Cost} = -log(h_\theta(x)) \quad &if \ \  y = 1 \\
&Cost = 0 \ \ &if  \ y =1 , h_\theta = 1 \\ 
&But\ as \ h_\theta \rightarrow 0, & cost \rightarrow \infty
\end{align}
$$
![aas](/img/Post_image/2018-11-17-15-37-39.png)
$$ 
\begin{align}
&\text{Cost} = -log(1-h_\theta(x)) \quad &if \ \  y = 0 \\
&Cost = 0 \ \ &if  \ y =0 , h_\theta = 0 \\ 
&But\ as \ h_\theta \rightarrow 1, & cost \rightarrow \infty
\end{align}
$$
Therefore, it will penalize learning algorithm by a large cost if y is not equal to $h_\theta(x)$

### Regularization
Same as regularization in linear regression, here we always use L2-norm as our penality item.

$$
\begin{align}
J(\theta) & =  \frac{1}{m} \sum_{i=1}^{m} \text{Cost}
(h_\theta(x^i), y^i) \\
 &= -\frac{1}{m} \sum_{i=1}^{m} [y^ilog \ h_\theta(x^i) + (1 - y^i) \ log \ (1 - h_\theta(x^i)]  + \frac{\lambda}{2m} \sum_{j=1}^{m}\theta_j^{2}
\end{align}
$$

## Overfitting 
There are several options to deal with overfitting:
1. Reduce number of features
2. Regularization
3. Enlarger the data set

















