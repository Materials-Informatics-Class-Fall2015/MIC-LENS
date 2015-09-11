---
layout:     	post 
title:      	Introduction
date:       	2015-09-09 00:33
author:     	Andriy Dotsenko, Xinyi Gong
tags:         
---

Process-Microstructure Relationships in Polyethylene Under Uniaxial Strain
------------------------------------------------------------------------

Team Members
------------

Andriy Dotsenko
Xinyi Gong

Project Goals
-------------

 - Find process-structure evolution linkages in polyetylene under appied uniaxial strain using Wide Angle X-ray Scattering (WAXS) data  as well as reveal the effects of thickness and density variations.
 - Find correlations between WAXS and linkages found in [previous work](http://phelpsforpresident.github.io/MIC-XRD-Polymer/about/) using the Small Angle X-ray Scattering (SAXS) data.

Process: Applied strain 
Structure: Captured by XRD images at different length scales

Source of Datasets
----------------------------
The tools used to generate the datasets are described [here](http://pubs.acs.org/doi/abs/10.1021/ma020771i).  The SAXS, and WAXS image sets and the accompanying strain data collected at Argonne National Lab. Representative images shown below.
![SAXS image scaled in previous work by Abhiram Kannan and David Brough](/MIC-XRD-WAXS-polymers/img/SAXS_representative_photo_scaled.jpg)
SAXS image scaled in previous work by Abhiram Kannan and David Brough
![WAXS image scaled in previous work by Abhiram Kannan and David Brough](/MIC-XRD-WAXS-polymers/img/Abhirams WAXs picture.jpg)
WAXS image scaled in previous work by Abhiram Kannan and David Brough

Workflow
------------------------------

 - Scale the WAXS images
 - Extract the spatial statistics(2-point statistics) of polyethylene of
   one single time step from WAXS.
 - Reduce dimension using techniques like PCA to get representation of structures.
 - Build the linkage between process and structure with the trajectories showing structure evolution.
