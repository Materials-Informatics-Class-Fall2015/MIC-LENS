---
layout:     	post
title:      	Refinement on Linear Polynomial Regression Model
date:       	2015-12-11 12:00
author:     Xinyi Gong
---

This post will show you our trials on building an effective model to fit the first three PC scores using as many process parameters as possible.

Increasing Order of Polynomial Fit
-------
Thanks to Ahmet, we can effectively create multi-variance polynomial fit with linear regression using his matlab [function](https://github.com/ahmetcecen/MultiPolyRegress-MatlabCentral) as a very powerful tool.

To get a fit with reasonable mean average error(MAE) and R square, we decided to use all of our process variables. The following figures show goodness of fit for models using different number of terms and orders.


Due to the discrete nature of our process variables, meaning for each variable we have 3 or 4 different values, we got rank deficiency in our model if we try to fit with up to 3rd power for every process variable. To refine the model, we will have to selectively add 3rd order terms to original 2nd order model. So by exhausting all the combinations for a 3rd order fit, a more modified model was created totally with 74 terms.




About Principle Components
-------
Although as mentioned previously, the first three PCs capture over 95% variance, the choice of PCs to fit also depends on their importance in structure-property linkage - the other part of the problem. But for now, fitting the first three PCs satisfies our need to correlation process to structure information.