---
layout:     	post
title:      	Data Description
date:       	2015-09-30 10:45
author:     Xinyi Gong
tags:         
---

This post is created to specify the data of our project. It will clarify the meaning of each data file with an idea of how the data is generated.

The data is acquired at Materials Science and Engineering Data Challenge Dataverse under the project Exploration of Process-Structure Linkages in Simulated Additive Manufacturing Microstructures (https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/KJMK9Z)  As mentioned in the previous post, this data simulates the LENS-type process and generates final 3D microstructure with different processing parameters.

Data Generation
	
The tool used to generate the data is SPPARKS (http://spparks.sandia.gov/) which stands for Stochastic Parallel PARticle Kinetic Simulator. It utilizes a parallel Monte Carlo code for on-lattice and off-lattice models. “In a generic sense, the solvers catalog a list of "events", each with an associated probability, choose a single event to perform, and advance time by the correct amount. Events may be chosen individually at random, or by sweeping over sites in a more ordered fashion.” This method offers a wealth of adjustable variables to tune simulation behavior to reflect that of experiments.

To simulate the LENS-type additive manufacturing process, the code has been specifically modified.

Firstly, an initial 3D microstructure is created with randomly distributed grains. This structure is to represent the powder upon the substrate before laser melting. Each color corresponds to a specific spin which does not necessarily related to certain orientation of the grains but serves well as an identification of each grain. Although the simulation uses simple cubic lattice, similar methods can be applied to other types of lattice.

![figure1 Initial Microstructure](https://www.flickr.com/photos/133265793@N04/21650496310/in/dateposted-public/)

Secondly, a melt pool is generated and described by 5 spatial parameters. Although the LENS-type additive manufacturing involves many different physical parameters such as laser power density, powder feeding rate and material thermal resistance, when it comes to simulating the structure evolvement, the primary parameters that directly influences this process would come down to: melt spot tail length, melt spot width, melt spot depth, heat-affected-zone tail length and heat-affected-zone width. Illustration of each parameter is show below.

![figure 2 Melt Pool Illustration](https://www.flickr.com/photos/133265793@N04/21848127251/in/dateposted-public/)

Thirdly, the manufacturing process is simulated in a bar-after-bar and layer-by-layer fashion. As we explained in our last post, when the substrate moves under the stationary deposition nozzle from one end to another, a trace of this process can be left behind. So the simulation proceeds on bars (which represent one trace line created by the melt pool) and in a serpentine, bar-after-bar manner. Due to the characteristics of LENS technique, the layer-by-layer process can have different scan pattern: 1. All layers are produced in one direction (X); 2. Layers are produced in two directions and each layer has a different direction than its neighbors(XY).  One should notice that another 2 parameters play an important role: velocity (how fast the melt pool/beam moves) and the scan pattern (whether it’s in a “XY” manner or “X” manner).
 
 ![figure 3 Sweep Process](https://www.flickr.com/photos/133265793@N04/21848125651/in/dateposted-public/)

This project will be focused on the linkage between process and final microstructure rather than the evolution of microstructures. So the data we acquire is the final microstructure from the simulation.











