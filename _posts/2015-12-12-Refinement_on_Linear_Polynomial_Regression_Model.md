---
layout:     	post
title:      	Refinement on Linear Polynomial Regression Model
date:       	2015-12-11 12:00
author:     Xinyi Gong
---

This post will show you our trials on building an effective model to fit the first three PC scores using as many process parameters as possible.

Increasing Order of Polynomial Fit
-------
Thanks to Ahmet, we can effectively do with multi-variance polynomial fit with linear regression using his matlab [function](https://github.com/ahmetcecen/MultiPolyRegress-MatlabCentral) as a very powerful tool. 



About Principle Components
-------
Although as mentioned previously, the first three PCs capture over 95% variance, the choice of PCs to fit also depends on their importance in structure-property linkage - the other part of the problem. But for now, fitting the first three PCs satisfies our need to correlation process to structure information.