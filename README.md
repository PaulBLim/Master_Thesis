# Deep learning vs traditional ML algorithms for AMR detection

Master Thesis Proposal

Author - Varun Sree Bholalayam (00807289)


## Problem Introduction

Antimicrobial Resistance (AMR) occurs when bacteria, viruses, fungi and parasites evolve over time and no longer respond to medicines making infections harder to treat and increasing the risk of disease spread, severe illness and death. AMR is a much overlooked aspect in the field of public health since the predicted mortality rate due to AMR by the year 2050 is more concerning than cancer<sup>1</sup>.

Some examples of dangerous organisms with a high AMR potential are:

1. Drug resistant tuberculosis
2. Methicillin-resistant Staphylococcus aureus
3. Multidrug-resistant Pseudomonas aeruginosa.

Drug susceptibility tests (DST) is a typical method to determine whether the pathogen has evolved to resist the antimicrobial drug. Two well-known clinical DST methods are genotypic and phenotypic DST. Phenotypic DST have limitations including extended turnaround time for slow-growing bacteria such as Mycobacterium tuberculosis (MTB) and bias due to potential contamination<sup>2</sup>. Genotypic DST employs WGS to detect the presence of genes that can cause AMR against a given drug<sup>3</sup>.

An example of a genotypic DST tool is Mykrobe predictor, which uses De Bruijn graph representation of bacterial diversity to identify species and resistance profiles of clinical isolates<sup>4</sup>. Mykrobe employs a rule based machine learning algorithm for prediction. However since genetic mechanisms that result in evolution of AMR genes are rapid, the competence of deterministic ML methods like RBML is questionable. 

A recent study published in 2022 compared traditional ML,CNN,RBML and reported that CNN had higher F1 score with room for improvement if hyperparameters are tuned<sup>2</sup>.

However <sup>2</sup> was not replicated nor applied on other bacteria.

## Research Questions

The motivation for the following research questions stem from <sup>2</sup>:

1. Replicating the results obtained from the paper<sup>2</sup> which compares 4 ML algorithms. ( Logistic regression, random forest, convolutional neural network and rule based machine learning. 
2. Can the CNN part of the pipeline be improved for higher accuracy by hyperparameter tuning?
3. Can the same pipeline be tweaked to predict drug resistance in Staphylococcus aureus?


## Methodology

1. WGS data of 10,575 mycobacterium tuberculosis (MTB) isolates will be collected from Sequence read archive (SRA) and corresponding lineage and phenotypic DST data from CRyPTIC Consortium and the 100,000 Genomes project.
2. To obtain the  genetic features possibly responsible for drug resistance, ARIBA will be employed. ARIBA uses a partial assembly mode of operation to identify AMR genes<sup>5</sup>. Unassembled reads are taken as an input and only necessary parts of the DNA are assembled and mapped to a curated AMR gene database such as CARD<sup>6</sup>. 
3. Output of ARIBA  combined with the lineage data should serve as the dataset for LR and RF and thereafter CNN.
4. Both of the machine learning and the CNN models will be trained with the datasets and the quality of the predictions will be evaluated.
5. Mykrobe predictor can be used to predict drug resistance of these 10,575 isolates and its predictive qualities will be compared with the machine learning and CNN results.
6. Further I plan to tune the hyperparameters of CNN and see if it brings any improvement in accuracy of the model.
7. Lastly I plan to use the same machine and deep learning pipeline to try and build a model for predicting drug susceptibility in Staphylococcus aureus.


## Research Goal

Goal is to output and compare the features such as precision, sensitivity, specificity, accuracy, F1 and G-mean of all the models as well as Mykrobe predictor for MTB and attempt hyperparameter tuning to improve these features if possible. Thenceforth, this work can pave the way for a more efficient DST for Staphylococcus aureus.


## Time Plan

| Month | Intended work |
| --- | --- |
| 1 | Understanding the idea and scope of machine learning and deep learning in DST prediction|
| 2 | Data collection, ARIBA implementation, dataset preparation |
| 3 | Training models, determining significance of prediction |
| 4 | Comparison of machine learning and rule-based approach, hyperparameter tuning |
| 5 | Testing with Staphylococcus aureus dataset, determining quality of prediction, thesis writing |
| 6 | Thesis writing |


## References

1. Shankar, Pr. (2016). Book review: Tackling drug-resistant infections globally. Archives of Pharmacy Practice, 7(3), 110. https://doi.org/10.4103/2045-080x.186181
2. Kuang, X., Wang, F., Hernandez, K. M., Zhang, Z., & Grossman, R. L. (2022). Accurate and rapid prediction of tuberculosis drug resistance from genome sequence data using traditional machine learning algorithms and CNN. Scientific Reports, 12(1). https://doi.org/10.1038/s41598-022-06449-4
3. Aung, W. W., Ei, P. W., Nyunt, W. W., Swe, T. L., Lwin, T., Htwe, M. M., Kim, K. J., Lee, J. S., Kim, C. K., Cho, S. N., Song, S. D., & Chang, C. L. (2015). Phenotypic and genotypic analysis of anti-tuberculosis drug resistance in Mycobacterium tuberculosis isolates in Myanmar. Annals of laboratory medicine, 35(5), 494–499. https://doi.org/10.3343/alm.2015.35.5.494
4. Bradley, P., Gordon, N. C., Walker, T. M., Dunn, L., Heys, S., Huang, B., Earle, S., Pankhurst, L. J., Anson, L., de Cesare, M., Piazza, P., Votintseva, A. A., Golubchik, T., Wilson, D. J., Wyllie, D. H., Diel, R., Niemann, S., Feuerriegel, S., Kohl, T. A., … Iqbal, Z. (2015). Rapid antibiotic-resistance predictions from genome sequence data for Staphylococcus aureus and Mycobacterium tuberculosis. Nature Communications, 6(1). https://doi.org/10.1038/ncomms10063
5. Hunt, M., Mather, A. E., Sánchez-Busó, L., Page, A. J., Parkhill, J., Keane, J. A., & Harris, S. R. (2017). ARIBA: rapid antimicrobial resistance genotyping directly from sequencing reads. Microbial Genomics, 3(10). https://doi.org/10.1099/mgen.0.000131
6. Alcock, B. P., Huynh, W., Chalil, R., Smith, K. W., Raphenya, A. R., Wlodarski, M. A., Edalatmand, A., Petkau, A., Syed, S. A., Tsang, K. K., Baker, S. J. C., Dave, M., McCarthy, M. C., Mukiri, K. M., Nasir, J. A., Golbon, B., Imtiaz, H., Jiang, X., Kaur, K., … McArthur, A. G. (2022). CARD 2023: expanded curation, support for machine learning, and resistome prediction at the Comprehensive Antibiotic Resistance Database. Nucleic Acids Research, 51(D1), D690–D699. https://doi.org/10.1093/nar/gkac920

