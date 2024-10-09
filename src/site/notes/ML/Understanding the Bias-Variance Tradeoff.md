---
{"dg-publish":true,"permalink":"/ML/Understanding the Bias-Variance Tradeoff/","created":"2024-10-09T14:47:07.868+08:00","updated":"2024-10-09T15:21:27.370+08:00"}
---

Webpage: [Understanding the Bias-Variance Tradeoff (fortmann-roe.com)](https://scott.fortmann-roe.com/docs/BiasVariance.html)

## Introduction

>When we discuss prediction models, prediction errors can be decomposed into two main subcomponents we care about: error due to "bias" and error due to "variance". There is a tradeoff between a model's ability to minimize bias and variance. Understanding these two types of error can help us diagnose model results and avoid the mistake of over- or under-fitting.

在模型拟合中，会出现error，而error的主要原因主要是这两个：
1. bias
2. variance
对这两个的理解才能明白over/under fitting

### bias：太偏了（偏移值）
 The error due to bias is taken as the difference between the expected (or average) prediction of our model and the correct value which we are trying to predict.

### variance：太散了（方差）
 The error due to variance is taken as the variability of a model prediction for a given data point.

<div>			<!--块级封装-->
    <center>	<!--将图片和文字居中-->
    <img src="https://blog-1327458544.cos.ap-guangzhou.myqcloud.com/New/20241009150716.png"
         alt="无法显示图片时显示的文字"
         style="zoom:0.5"/>
    <br>		<!--换行-->
    	<!--标题-->
    </center>
</div>

## Mathematical Definition

假设需要预测的随机变量 Y 和 协变量 X 满足如下关系：
$$
Y = f(X) + \epsilon
$$

其中，$\epsilon$ 满足正态分布$N(0,\sigma_E)$

我们在评估中使用以下函数作为损失函数：

$$
Err(x) = E[(Y-\hat f(x))^2]
$$

This error may then be decomposed into bias and variance components:

$$
Err(x) = (E[\hat f(x)]-f(x))^2 + E[(\hat f(x) - E[\hat f(x)])^2] + \epsilon_e ^ 2
$$

  which is:
$$Bias^2+Variance+Irreducible Error$$


That third term, irreducible error, is the noise term in the true relationship that cannot fundamentally be reduced by any model. Given the true model and infinite data to calibrate it, we should be able to reduce both the bias and variance terms to 0. However, in a world with imperfect models and finite data, there is a tradeoff between minimizing the bias and minimizing the variance.

##  Example: Voting Intentions

