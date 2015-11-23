---
layout:     	post
title:      	Data Organization and Metadata Collection
date:       	2015-10-11 21:34
author:     	Andriy Dotsenko
tags:         
---

The organization and folder architecture of the SPPARKS data poses a small challenge to automated data processing. There are 2160 microstructures with identical or similar names. The process parameter combination associated with a particular microstructure is derived by observing the unique folder path of the data as illustrated below.
![enter image description here](/MIC-LENS/img/Data Structure Post/data_tree.png)
**Fig.1.** Data folder architecture.

A Matlab script was written to automatically navigate the branches of the folder tree, accessing the data and collecting metadata which identifies the data's parameter combination.

**File address:**
…Home\T20W60\T20-X-V10-60\D100\L50\HAZ20\dump.additive4.4

**Metadata collected:** 
T20-X-V10-W60-D100-L50-HAZ20

A significantly more difficult challenge proved to be navigating around the exceptions and anomalies in the structure scattered throughout the folder tree. Some parameter combinations were found to be missing from the data set, while other accessible files had miscellaneous other problems. A concise summary of the documented anomalies is as follows: 

 1. Missing parameter combinations
 2. Miscellaneous files with unknown extensions of unkown purpose
 3. Corrupted files  
 4. Missing structure files 
 5. Unpredictable variations in name 

Over all 1799 microstructures were successfully gathered. A meeting with the domain expert from Sandia National Labs is scheduled to determine if this is a reasonable number compared to the original estimate of 2160 microstructures. The set of 1799 is stored in one folder in .mat format with unique numerical names (1.mat-1799.mat). The .mat file holds the metadata parameter information and an already segmented brain boundary data arrays 300x300x200.
 