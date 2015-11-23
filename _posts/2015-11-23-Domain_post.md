---
layout:     	post
title:      	Meeting with Sandia National Labs Domain Expert
date:       	2015-10-27 00:09
author:     	Andriy Dotsenko
tags:         
---
We were lucky to have a teleconference with the domain expert and the creator of the SPPARKS LENS data set Theron Rogers of Sandia National Labs. We discussed the details of the data set and the state of our project.

The number of extracted files (1799) was confirmed to be accurate. The missing parameter combinations are a result of upload issues and not all 2160 combinations were uploaded. Some anomalies in the folder trees were addressed  as well. The mystery files of unknown origin and extension were added automatically by the Harvard's Dataverse repository where the data set was uploaded for public use. These files were safely discarded, however the implication is the necessity of data filtering and cleanup considerations for anyone using Dataverse.

Theron also discussed the physical coupling between process parameters that is empirically observed. The scan velocity V is directly linked to melt spot tail length L and inversely to melt spot width W and melt spot depth D.  The data set does not express this coupling because for a variety of V values the ranges of L,W,D are the same. This leads to the conclusion that some of these microstructures are not physically achievable. An improvement to the project will be limiting the microstructure space to only the physically achievable parameter combinations. The current data set describes a LENS-like process but without considerations of physical parameter coupling the final process-structure linkages will be describing a 'generalized LENS' system.

Further discussion revealed model limitaitons and current and future work including efforts to model oddly shaped parts, unrestricted melt spot trajectory, CFD-based meltpool shape and evolution, and porosity considerations in the deposit.