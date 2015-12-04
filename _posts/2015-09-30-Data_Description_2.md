---
layout:     	post
title:      	Data Description 2
date:       	2015-09-30 16:00
author:     Xinyi Gong
tags:         
---

This post will show our preliminary treatment of the data: how the data looks like and what we do to clean up the data.


How big is the data?

Each data set we have includes an input file which gives information about every parameter used to simulate this specific process and an output file which contains spin (or grain id) data of the final microstructure. Every microstructure is represented by a 300 by 300 by 200 cuboid which means 18,000,000 voxels per microstructure (process).

<a data-flickr-embed="true" data-context="true"  href="https://www.flickr.com/photos/133265793@N04/21815001906/in/datetaken/" title="microstructure"><img src="https://farm6.staticflickr.com/5721/21815001906_8c887e7a27_c.jpg" width="800" height="494" alt="microstructure"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>


Upon that, since every microstructure correspond to a set of unique process parameters, every change of each parameter would lead to a new set of data.

Variable
Values simulated
(X/XY)Scan Pattern
Linear and layer-by-layer cross-hatch
(W)Melt spot width (lattice sites)
60, 70, 80, 90
(V)Velocity (sites/timestep)
2.5, 5, 7.5, 10, 15
(D)Melt spot depth (sites)
100, 125
(L)Melt spot tail length (sites)
50, 60, 70
(HAZ)Heat-affected-zone width (sites)
5, 20, 35
(T)Heat-affected-zone tail length (sites)
5, 20, 35

There are 7 different parameters in the process and each variables are listed above. This leads to 2160 combinations which means 2160 sets of microstructure data. 


Data classification (metadata) and extraction

Because we have over two thousand different combinations, the first thing we do after downloading the data is to classify all our data into systematically named folds. After some cleaning up, we have our dataset structured like this:
<a data-flickr-embed="true"  href="https://www.flickr.com/photos/133265793@N04/21841139005/in/datetaken/" title="Screen Shot 2015-09-30 at 12.25.12 PM"><img src="https://farm1.staticflickr.com/612/21841139005_88f78b6f0e_c.jpg" width="800" height="302" alt="Screen Shot 2015-09-30 at 12.25.12 PM"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>


The effort we gave to structuring the folders will also benefit us for doing further operations (digital representation and dimensionality reduction) efficiently.

Due to the large amount of data, all the files are packed and double packed to .gz files. Thanks to Ahmet, we are able to create a batch file (.bat) to unpack all our data recursively, so that we don’t have to click all week just to unpack the data. The output data from SPPARKS can not be directly used to visualize the microstructure and we also find a huge amount of redundancy in the data provided. With Eva’s help, we converted the original files to .vti files which can be read directly in ParaView and the size of data drop from about 480MB to 180MB.
<a data-flickr-embed="true" data-context="true"  href="https://www.flickr.com/photos/133265793@N04/21815001936/in/datetaken/" title="Screen Shot 2015-09-30 at 9.00.29 AM"><img src="https://farm1.staticflickr.com/577/21815001936_e3fa89c5f8_o.png" width="183" height="388" alt="Screen Shot 2015-09-30 at 9.00.29 AM"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>


<a data-flickr-embed="true" data-context="true"  href="https://www.flickr.com/photos/133265793@N04/21850734141/in/datetaken/" title="Screen Shot 2015-09-30 at 12.32.13 PM"><img src="https://farm6.staticflickr.com/5727/21850734141_51ed39302c_o.png" width="598" height="383" alt="Screen Shot 2015-09-30 at 12.32.13 PM"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

As mentioned in previous post, the experimental EBSD map from LENS manufactured material shows resemblance to the simulated data of some extent. However, I can not quantify this resemblance until we do further statistics on both images. So one of our next step will also include statistical comparison of these two kinds of data.

Although the color (spin/grain id) resembles orientation in the EBSD map, it does not necessarily have any physical meanings. So, the most useful information would be the shape of grains. In that sense, we decide to represent our microstructure at every voxel with 2 states: 1-grain boundaries, 0-grains. This representation would contain the grain boundary information which depict the shape of grains. Conventionally, one may interpret the structure by measuring and calculating the volume fraction, grain size distribution or ration of elongated and normal direction of grains. But this interpretation is mostly determined by experience which is subjective and may lose structure information.  So, instead, we do two point statistics which contains all the structural information in the images. Since we believe the grain boundary representation includes all shape information, the 2-pt statistics of such representation can capture all shape information. 

If you have any confusion about the data of our project, you are more than welcome to comment on this post.











