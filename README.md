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

Currently tools such as ARIBA, Resfinder and databases such as CARD, ARDB are used to analyse whether a known AMR gene is present in the sequenced data of a bacteria using various assembly and mapping algorithms. Although these tools are efficient in finding the presence of known AMR genes, the need of the hour demands tools that can predict whether a known first line drug is effective in treatment or not. Rule-based predictors exist such as Mykrobe predictor which uses De Bruijn graph representation of bacterial diversity to identify species and resistance profiles of clinical isolates<sup>3</sup>. Since genetic mechanisms that result in evolution of AMR genes are rapid, the competence of deterministic AI models should be scrutinized. A study published in 2022 Feb 14 is brought to the spotlight here<sup>2</sup>.



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
1. WGS data of 10,575 mycobacterium tuberculosis (MTB) isolates should be collected from Sequence read archive(SRA) and corresponding lineage and phenotypic drug susceptibility test (DST) data from CRyPTIC Consortium and the 100,000 Genomes project .
2. To obtain the  genetic features possibly responsible for drug resistance, ARIBA can be employed. ARIBA uses a partial assembly mode of operation to identify AMR genes<sup>4</sup>. Unassembled reads are taken as an input and only necessary parts of the DNA is assembled and mapped to a curated AMR gene database such as CARD<sup>5</sup>. 
3. Output of ARIBA  combined with the lineage data should serve as the dataset for LR and RF and thereafter CNN.
4. Both of the machine learning and the ANN models can be trained with the datasets and the quality of the predictions evaluated.
5. Mykrobe predictor can be used to predict drug resistance of these 10,575 isolates and its predictive qualities should be compared with the machine learning and CNN results.
6. Further I plan to tune the hyperparameteres of CNN and see if it brings any improvement in accuracy of the model.
7. Lastly I plan to use the same machine and deep learning pipeline to try and build a model for predicting drug susceptibility in Staphylococcus aureus.


## Goal
***
Goal is to output and compare the features such as precision,sensitivity,specificity,accuracy,F1 and G-mean of all the models as well as Mykrobe predictor for MTB and attemp hyperparameter tuning to upgrade these features if possible. Thenceforth, investigating the possibility of predicting drug resistance for Staphylococcus aureus using the same approach.


## Time Plan
***
| Month | Intended work |
| --- | --- |
| 1 | Understanding the idea and scope of Machine learning and Deep learning |
| 2 | Data collection, ARIBA implementation, Dataset preperation |
| 3 | Training models, determining significance of prediction |
| 4 | Comparison of machine learning and rule-based approach, Hyperparameter tuning |
| 5 | Testing with Staphylococcus aureus dataset, determining quality of prediction, Thesis writing |
| 6 |Thesis writing |


## References
***
1.  O'Neill, Jim. "Tackling drug-resistant infections globally: final report andrecommendations." (2016). 
2.  Kuang X, Wang F, Hernandez KM, Zhang Z, Grossman RL. Accurate and rapid prediction of tuberculosis drug resistance from genome sequence data using traditional machine learning algorithms and CNN. Sci Rep. 2022 Feb 14;12(1):2427. doi: 10.1038/s41598-022-06449-4. PMID: 35165358; PMCID: PMC8844416.
3.  Bradley, Phelim, et al. "Rapid antibiotic-resistance predictions from genome sequence data for Staphylococcus aureus and Mycobacterium tuberculosis." Nature communications 6.1 (2015): 10063.
4.  Hunt, Martin, et al. "ARIBA: rapid antimicrobial resistance genotyping directly from sequencing reads." Microbial genomics 3.10 (2017).
5.  Alcock BP, Huynh W, Chalil R, Smith KW, Raphenya AR, Wlodarski MA, Edalatmand A, Petkau A, Syed SA, Tsang KK, Baker SJC, Dave M, McCarthy MC, Mukiri KM, Nasir JA, Golbon B, Imtiaz H, Jiang X, Kaur K, Kwong M, Liang ZC, Niu KC, Shan P, Yang JYJ, Gray KL, Hoad GR, Jia B, Bhando T, Carfrae LA, Farha MA, French S, Gordzevich R, Rachwalski K, Tu MM, Bordeleau E, Dooley D, Griffiths E, Zubyk HL, Brown ED, Maguire F, Beiko RG, Hsiao WWL, Brinkman FSL, Van Domselaar G, McArthur AG. CARD 2023: expanded curation, support for machine learning, and resistome prediction at the Comprehensive Antibiotic Resistance Database. Nucleic Acids Res. 2023 Jan 6;51(D1):D690-D699. doi: 10.1093/nar/gkac920. PMID: 36263822; PMCID: PMC9825576.




