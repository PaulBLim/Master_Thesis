# Master Thesis Proposal
# Comparing and evaluating traditional machine learning algorithm with deep learning algorithm in the field of AMR detection.
# Author - Varun Sree Bholalayam (00807289)


## Problem Introduction
***********************
Antimicrobial Resistance (AMR) occurs when bacteria, viruses, fungi and parasites change over time and no longer respond to medicines making infections harder to treat and increasing the risk of disease spread, severe illness and death. AMR is a much overlooked aspect in the field of public health since the predicted mortality rate due AMR by the year 2050 is more concerning than cancer<sup>1</sup>.
Drug resistant tuberculosis, Methicillin-resistant Staphylococcus aureus,Multidrug-resistant Pseudomonas aeruginosa are examples for the AMR acquired pathogens or more popularly known as 'superbugs'.
Currently tools such as ARIBA, Resfinder and databases such as CARD, ARDB are used to analyse whether a known AMR gene is present in the sequenced data of a bacteria using various assembly and mapping algorithms. Although these tools are efficient in finding the presence of known AMR genes, the need of the hour demands tools that can predict AMR genes from WGS data. Rule based predictors exist such as Mykrobe predictor which uses De Bruijn graph representation of bacterial diversity to identify species and resistance profiles of clinical isolates<sup>2</sup>. Since genetic mechanisms that result in evolution of AMR genes are rapid, the competence of deterministic AI models should be scrutinized.
