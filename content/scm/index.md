+++
title = "Sign consistency methods to reason over the transitional behavior of dynamic systems"
date = 2016-06-01

[taxonomies]
tags = ["sign-consistency"]
+++

**`This is work in progress! The content is still incomplete and changing.`**

In this series I want to explain how interaction graph models and sign consistency methods are used to model the behavior of dynamical systems. The focus lies on modeling the behavior of biological systems, although the application to artificial systems is possible. In particular, I want to show how certain sign consistency methods work, under which assumption they operate, which biological questions they allow us to answer, and what problems exist. My aim is to be very beginner friendly with lots of examples. OK, let’s dive into it! Here is a table of content that list the covered topics from which you can cherry pick.

## CONTENTS

[**Interaction graphs and signed system changes**](/scm/scm1) \
[**Predicting system responses to perturbations**](/scm/scm2) \
[**Minimum and maximum level constraints**](/scm/scm3) \
[**Predicting effects on downstream regulated variables**](/scm/scm4) \
[**Predicting effects on cooperatively regulated variables**](/scm/scm5) \
[**Excluding unfounded changes in feedback loops**](/scm/scm6) \
**Model consistency wrt. measurement data** \
**Consistency index and data repair** \
**Model repair and network inference** \
**Dependency matrix** \
**Experiment design** \
**Relation to Boolean Networks**

## References

1.    S. Thiele, L. Cerone, J. Saez-Rodriguez, A. Siegel, C. Guziołowski, and S. Klamt. [Extended notions of sign consistency to relate experimental data to signaling and regulatory network topologies](http://dx.doi.org/10.1186/s12859-015-0733-7), *BMC Bioinformatics*, 16(345), 2015.

2.    I. N. Melas, R. Samaga, L. G. Alexopoulos, and S. Klamt. [Detecting and Removing Inconsistencies between Experimental Data and Signaling Network Topologies Using Integer Linear Programming on Interaction Graphs](http://dx.doi.org/10.1371/journal.pcbi.1003204), *PLoS Computational Biology*, 9(9):e1003204, 09 2013. 

3.    R. Samaga and S. Klamt. [Modeling approaches for qualitative and semi-quantitative analysis of cellular signaling networks](http://dx.doi.org/10.1186/1478-811X-11-43), *Cell Communication and Signaling*, 11(43), 2013.

4.    M. Gebser, T. Schaub, S. Thiele, and P. Veber. [Detecting inconsistencies in large biological networks with answer set programming](http://dx.doi.org/10.1017/S1471068410000554), *Theory and Practice of Logic Programming*, 11(2-3):323–360, 2011.

5.    M. Gebser, C. Guziołowski, M. Ivanchev, T. Schaub, A. Siegel, S. Thiele, and P. Veber. [Repair and prediction (under inconsistency) in large biological networks with answer set programming](http://aaai.org/ocs/index.php/KR/KR2010/paper/view/1334), *Proceedings of the Twelfth International Conference on the Principles of Knowledge Representation and Reasoning (KR’10)*, AAAI Press, 2010.

6.    J. Saez-Rodriguez, L. G. Alexopoulos, J. Epperlein, R. Samaga, D. A. Lauffenburger, S. Klamt, and P. K. Sorger. [Discrete logic modelling as a means to link protein signalling networks with functional analysis of mammalian signal transduction](http://dx.doi.org/10.1038/msb.2009.87), *Molecular systems biology*, 5(331), 2009.

7.    S. Klamt, J. Saez-Rodriguez, J. Lindquist, L. Simeoni, and E. Gilles. [A methodology for the structural and functional analysis of signaling and regulatory networks](http://dx.doi.org/10.1186/1471-2105-7-56), *BMC Bioinformatics*, 7(1):56, 2006.
