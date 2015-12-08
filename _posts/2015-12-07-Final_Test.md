---
layout:     	post
title:      Process-Structure Linkages in Simulated LENS-type Additive Manufacturing Microstructures: Final Post
date:       2015-12-07 18:30
author:     	Materials Innovation
tags:         result
---
::::Work in Progress::::
----------------

Intro/Bacground
---------------
The LENS additive manufacturing process creates fully-dense alloy components with process parameter-dependent microstructure. In this project we investigate the morphology of the microstructure crystal grains and it's dependence on process parameters using a Materials Knowledge Systems (MKS) approach. A simulated dataset shared with us through Harvard's Dataverse was subjected to the MKS approach. The dataset's creator Theron Rogers of Sandia National Labs has been our collaborator and domain expert, guiding the direction of the project. More detail can be found [here](http://materials-informatics-class-fall2015.github.io/MIC-LENS/2015/09/24/Intro_LENS/).

Motivation:
-----------
The project is an effort to understand LENS fabricated materials as a function of LENS process parameters. The LENS process creates metal/alloy deposits with a tightly controlled chemistry but the microstructure also plays a large part in the material's mechanical properties. The Process-Structure link we create is the first step to 

With the extracted Process-Structure linkages this work will pave the way for deep uderstanding of LENS microstructure control but also make suggestions towards LENS-simulations and LENS-systems developments.  



The grand vision of MKS is to create material engineering and discovery techniques 

create linkages between material Process Structure and Properties, . In this project process-structure linkages are sought using MKS


 

Objective:
----------
The objective of this project was to extract process-structure linkages from the simulated dataset. The grain size- and shape-distribution was specified as an important structure metric. The general direction of the project became extraction of grain evolution patterns with respect to simulation process parameters. The 

Approach/Workflow:
------------------
The dataset represents 1799 unique 3D digital microstructures created by SPPARKS monte carlo simulations. Each structure occupies a 300x300x200 unit volume and is associated with a unique set of processing parameters listed below:

 1. (X/XY)Scan Pattern	Linear and layer-by-layer cross-hatch
 2. (W)Melt spot width
 3. (V)Velocity
 4. (D)Melt spot depth
 5. (L)Melt spot tail length
 6. (HAZ)Heat-affected-zone width
 7. (T)Heat-affected-zone tail length

The 1799 unique microstructures have a variety of grain size and shape distributions, and example of which is shown below. The pseudo-periodic nature present in all these structures owes itself to the linear-serpentine scan pattern of the heat source in the simulation which mimics the movement of the LENS deposition nozzle and deposit formation.

![SPPARKS simulated structure](/MIC-LENS/img/GB_post/Full_structure.png)
**Fig.1.** Example microstructure with parameter combination: T=20, X, V=2.5, W=60, D=100, L=50, HAZ=5

The data was organized in a folder tree, each branch of which defined a microstructure with a unique parameter combination. A code was written to navigate these branches, access the microstructure, and collect metadata (the process parameter combinations). A detailed explanation [here](http://materials-informatics-class-fall2015.github.io/MIC-LENS/2015/10/11/Data_org_folder_crawl/).

The journey to extract the Process-Structure linkage is summarized in the worklfow diagram below:

![Workflow](/MIC-LENS/img/Final_Post/Latest_Workflow.png)
**Fig.1.** Workflow

In the Digital Representation step the data is processed and transformed into a computationally-convenient form, after which the microstructure is subjected to grain-boundary segmentation. The Spatial Correlations within the microstructure can be interpreted in different ways but we selected 2-point statistics and Chord-Length-Distributions (CLD) in this step. Details [here](http://materials-informatics-class-fall2015.github.io/MIC-LENS/2015/09/29/Data_Process_GB_2Pt/) and [here](http://materials-informatics-class-fall2015.github.io/MIC-LENS/2015/10/25/One_Kind_of_Statistics_Describing_the_Structures/) and [here](http://materials-informatics-class-fall2015.github.io/MIC-LENS/2015/10/26/The_Weighted_Chord_Length_Distribution/). Both 2pt-statistics and CLDs are different statistical descriptions of microstructure. The 1799 microstructures are interpreted with a set of 1799 2-pt statistics and a set of 1799 CLDs. Before a linkage is built, the variance in each set is quantified and reduced in dimensionality using Principal Component Analysis (PCA). The PC space is truncated to a handful of PCs immensely reducing complexity yet capturing most of the variance. 

Results:
--------
The CLD statistics were more appropriate to the structure information we wish to quantify. The 1799 structures are plotted below in PC space, along with an accumulated variance plot. 

![CLD PCA](/MIC-LENS/img/Final_Post/CLD_PCA_and_Var.png)
**Fig.1.** The CLD variance in PC space and corresponding accumulated variance plot

The separation of structures with respect to process parameters is immediately evident by visual inspection. The plot is color coded for different parameter values of V and W below.

  ![CLD PCA](/MIC-LENS/img/Final_Post/CLD_PCA_Vprm.png)
**Fig.1.** Color coded structures show visual separation in PC space (2 views shown) as a function of V


  ![CLD PCA](/MIC-LENS/img/Final_Post/CLD_PCA_Wprm.png)
**Fig.1.** Color coded structures show visual separation in PC space (2 views shown) as a function of W

The V and W parameter-microstructure correlation is displayed as an example but other parameters also display correlation. 

Modeling the linkages for the entire dataset
Model

Outliers: 


  ![CLD PCA Outliers](/MIC-LENS/img/Final_Post/Outliers.png)
**Fig.1.** Outliers in the CLD PCA space

Model without outliers



Conclusions:
------------
summary


Future Work:
------------
Future work may include the 2pt statistics PCA. The 2-point statistics showed promising results during preliminary tests. A subset of 72 structures was selected and PCA showed reasonable separation of microstructures as shown below.

![72 structure PCA](/MIC-LENS/img/Final_Post/72_2pt_PCA.png)
**Fig.1.** On the left, the PCs -1,-2, and -3 of a 72 structure subset showing separation. An accumulated variance plot is shown on the right. 

Though the method seems to show promise it became impossible to carry out using our limited computational power. The PCA computations of the entire set required over 200GB of RAM while the most powerful nodes at our disposal were 128GB. Because we could not justify reducing the dataset to a computable subset we decided to pursue the non-memory-intensive CLD PCA while searching for a more powerful computing node for 2-pt statistics PCA.

Acknowledgements/References:
----------------------------
more stuff