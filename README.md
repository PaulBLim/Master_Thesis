# Master Thesis Proposal
# Comparing and evaluating traditional machine learning algorithms with deep learning algorithms in the field of AMR detection.
# Author - Varun Sree Bholalayam (00807289)


## Problem Introduction
***********************
Antimicrobial Resistance (AMR) occurs when bacteria, viruses, fungi and parasites evolve over time and no longer respond to medicines making infections harder to treat and increasing the risk of disease spread, severe illness and death. AMR is a much overlooked aspect in the field of public health since the predicted mortality rate due to AMR by the year 2050 is more concerning than cancer<sup>1</sup>.

Some examples of so called 'superbugs' are,

1.Drug resistant tuberculosis. 

2.Methicillin-resistant Staphylococcus aureus.  

3.Multidrug-resistant Pseudomonas aeruginosa.  

Both genotypic and phenotypic drug susceptibility test is used clinically. Phenotypic DST have limitations including extended turnaround time for slow-growing bacteria such as Mycobacterium tuberculosis (MTB) and bias due to potential contamination<sup>2</sup>.

Currently tools such as ARIBA, Resfinder and databases such as CARD, ARDB are used to analyse whether a known AMR gene is present in the sequenced data of a bacteria using various assembly and mapping algorithms. Although these tools are efficient in finding the presence of known AMR genes, the need of the hour demands tools that can predict whether a known first line drug is effective in treatment or not. Rule based predictors exist such as Mykrobe predictor which uses De Bruijn graph representation of bacterial diversity to identify species and resistance profiles of clinical isolates<sup>3</sup>. Since genetic mechanisms that result in evolution of AMR genes are rapid, the competence of deterministic AI models should be scrutinized. A study published in 2022 Feb 14 is brought to the spotlight here<sup>2</sup>.



## Research Question
********************
Objective of this thesis is to compare and evaluate the efficiency of traditional machine learning approaches (Logistic Regression and Random Forest) and Deep Learning approach(Convolutional Neural Network) in prediction of drug resistance in tuberculosis.
The questions aimed to be answered are:
1. How does logistic regression and random forest algorithms perform compared to an artificial neural network (CNN) in predicting drug resistance in tuberculosis? 
2. How does these aforementioned machine learning approaches compare to the state-of-the-art rule-based  predictor (Mykrobe).
3. Can the ANN part of the pipeline be improved for higher accuracy by hyperparameter tuning?
4. Can the same pipeline be tweaked to predict drug resistance in Staphylococcus aureus?


## Methodology
***************
