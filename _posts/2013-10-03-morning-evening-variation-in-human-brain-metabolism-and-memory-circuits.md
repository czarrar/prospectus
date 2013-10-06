---
layout: post
title: "Morning evening variation in human brain metabolism and memory circuits"
description: "Paper examining changes in functional connectivity and brain metabolism from morning to evening"
category: "sleep"
tags: [sleep,functional connectivity,fMRI,PET,metabolism,diurnal,resting state]
---
{% include JB/setup %}

I was very interested in reading this paper because it took an unstudied phenomena, systematic changes in resting-state connectivity over the course of the day, and put it in the context of a larger theoretical framework related to synaptic homeostasis. The synaptic homeostasis hypothesis suggests that _"a major function of sleep is the regulation of synaptic weights: over the course of a day, learning and experience cause an increase in the brain’s synaptic density, which is pruned each night during sleep (Gilestro et al. 2009; Tononi and Cirelli 2003)"_. From this theory, the author's _"hypothesized that wake would alter the resting-state functional organization of the brain and increase its metabolic cost"_.

They found that functional connectivity differences were fairly stable between morning and evening. The most prominent differences were related to regions in the MTL, which were locally connected in the morning and then displayed more connectivity with the prefrontal, parietal, striatal, and brainstem. Surprisingly, there was no associated metabolic changes from PET scans between morning and evening in a separate and smaller set of participants.

# Highlights and Thoughts

* Authors suggest that greater interference effect for scans conducted in the evening versus morning to explain results.
* Greater degree of memory replay may occur during the evening (high degree of overlap between memory retrieval meta-analysis and evening minus morning connectivity)
* Greater degree of replay or retrieval might also lead to greater amounts of interference between multiple memories that needs to be resolved by the evening.
* Interesting that striatal connectivity goes from negative to positive by the evening. Is this possibly a greater reflection of greater memory integration going in the evening?
* Weird that metabolism the same morning vs evening. Authors suggest that metabolism changes due to learning/memory might be time-limited possibly due to local sleep during wake states. It would be interesting if such local sleep periods were more prevalent during rest periods, which might explain improvements in memory performance after an intervening rest vs task period.

I wonder if one could also quickly examine the same time of day (morning/evening) effects with currently available samples of resting-state data. Between-subjects one could compare differences in MTL functional connectivity depending on the time of day (earlier versus later) of the scan.

This is what would interest me the most if it were true:

_"One exciting, though speculative, possibility is that the evening MTL functional connectivity arises as subjects accumulate experiences and memories throughout the day and recedes as those memories are consolidated during sleep."_

I already commented on the metabolism earlier but this quote from the paper might be relevant as well.

_"Madsen et al. (1995), they were able to show that aerobic glycolysis persists for close to an hour following the performance of a difficult cognitive task without any evidence of an increase in oxygen consumption or blood flow. This observation, coupled with the metabolic measurements we report herein (i.e., no change in aerobic glycolysis either globally or regionally between morning and evening), suggests that some of the metabolic consequences of synaptic growth and strengthening may be time limited within the period of wake. Obviously, more work needs to be done that emphasizes a more comprehensive view of glucose metabolism. The idea of “local sleep” during wake (Vyazovskiy et al. 2011) should also be considered."_

# Experiments

There were two experiments.

First, they conducted a resting-state fMRI study during the morning and evening (within-subject design). Scans were counter-balanced. Some participants completed the morning scan first and evening scan second, and vice-versa. 

Second, they conducted a PET scan on a smaller sample with the same morning and evening design. I am not clear if the same counter-balancing occurred with PET. 

# Special Analysis

Special algorithm called IDEA, which given a set of ROIs will find significant univariate associations with an experimental or phenotypic variable and then take the peaks from those results and use those as ROIs, and iterating this process.

_"The algorithm is initialized by placing a number of regions into the testing set. Here, we used 36 “canonical” regions representing well-defined nodes in prominent brain networks, including the default-mode, dorsal-attention, executive-control, salience, visual, auditory, and motor networks (Raichle 2011)."_

_"The predictive ability of IDEA was tested using a leave-one-out cross-validation scheme. IDEA was run using data from 23 of the 24 subjects. Using the regions identified by IDEA, we generated a predictive model relating functional connectivity measurements to morning/evening status. We input data from the left-out subject into the model and evaluated its accuracy."_

# Results

## Functional Connectivity

Using their original set of 31 ROIs, didn't find any large differences between conditions.

_"Our analysis identified two regions with strongly altered RS-fcMRI in the left and right medial temporal lobe"_ within entorhinal cortex.

_"In the morning, the regions in left and right MTL were primarily connected locally with correlations in contralateral MTL, the surrounding area, and the temporal poles, as well as negative correlations in the striatum bilaterally (Fig. 4)."_

_"In the evening, the regions of the left and right MTL displayed functional connectivity with neocortical areas, including the retrosplenial cortex, and nearby posterior cingulate and precuneus, bilateral angular and supramarginal gyri, and dorsolateral and dorsomedial prefrontal cortex. The MTL also exhibited in the evening positive correlations with the pontine tegmentum and with bilateral basal ganglia, as well as negative correlations bilaterally with the anterior insula. The negative correlations with the striatum became positive correlations in the evening."_

They note that many correlations that develop in evening are related to memory retrieval and have a retrieval meta-analysis that is highly similar as a comparison.

## PET

They looked at glucose, oxygen, and cerebral blood flow. Across these and other measures, there were no significant differences between morning and evening.

# Relevant References

There was an important citation related to local sleep (see below) that I found and explored it's related citations.

Vyazovskiy VV, Olcese U, Hanlon EC, Nir Y, Cirelli C, Tononi G. Local sleep in awake rats. Nature 472: 443–447, 2011. 

Park B, Kim JI, Lee D, Jeong SO, Lee JD, Park HJ. Are brain networks stable during a 24-hour period? Neuroimage 59: 456–466, 2012.