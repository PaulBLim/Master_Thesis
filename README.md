# Deep learning vs traditional ML algorithms for AMR detection

Master Thesis Proposal

Author - Varun Sree Bholalayam (00807289)


## Problem Introduction

Reinforcement learning (RL) is a branch of machine that is concerned with training agents to make progressive decisions in an environment to maximize a numerical reward signal. In RL, a learning agent senses the state of its environment and takes iterative actions to improve its policy, such that the expected reward along its trajectory is maximized <sup>2</sup>.

Unlike supervised learning which relies on labeled datasets or unsupervised learning which tries to find structure in sets of labeled data sets, in RL the learner must discover which actions yield the best reward by trial and error. These two characteristics, trial and error search, and delayed reward are the two most important distinguishing features of reinforcement learning<sup>1</sup>.

RL has found widespread success in many application areas including self-driving cars <sup>4</sup>, robotics in space exploration <sup>5</sup>, surveillance <sup>6</sup>, wearable healthcare devices <sup>7</sup>, and much more. Accelerating Reinforcement learning with FPGAs (Field-Programmable Gate Arrays) can offer a range of advantages and address specific problems associated with RL applications. Architectures consisting of a blend of CPUs and FPGAs have become a good solution for accelerating RL. A few examples include 

1. Accelerating both computation and memory-intensive AI applications <sup>8</sup>.
2. Hardware acceleration by configuring FPGAs to accelerate key operations such as a high-throughput on-chip accelerator for Prioritized Replay Buffer<sup>2</sup>.
3. Optimizing for specific RL algorithms, such as developing a high-throughput PPO accelerator by accelerating computational intensive phases <sup>3</sup>.

Proximal Policy Optimization (PPO) is a state-of-the-art policy optimization method that has been shown to achieve superior overall performance on various Reinforced Learning Benchmarks. The aim is to make the biggest possible improvement step on a policy using the data we currently have, without stepping so far that we accidentally cause performance collapse<sup>9</sup>. Each iteration of PPO includes the inference face where an agent interacts with its environment to collect data, and a Training Phase where the agent trains the policy using the collected data. 

A study <sup>3</sup> published in 2020 developed a high-throughput PPO accelerator, using a CPU_FPGA heterogenous infrastructure, by accelerating both the Inference and training Phases which are both computationally intensive. This achieved 2.1X to 30.5X improvements in throughput against state-of-the-art CPU and 2X to 27.5X improvements against CPU-GPU implementations. 


## Research Questions

The motivation for the following research questions stem from <sup>2</sup>:

1. Replicating the results obtained from the paper<sup>2</sup> which compares 4 ML algorithms. (Logistic regression, random forest, convolutional neural network and rule based machine learning). 
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

1. Richard S. Sutton and Andrew G. Barto, (2018). Reinforcement Learning: An Introduction, 2
2. Yuan Meng, Chi Zhang, Viktor Prasanna, (2022). FPGA acceleration of deep reinforcement learning using on-chip replay management. Association for Computing Machinery. https://doi.org/10.1145/3528416.3530227
3. Y. Meng, S. Kuppannagari and V. Prasanna, (2020). Accelerating Proximal Policy Optimization on CPU-FPGA Heterogeneous Platforms.  2020 IEEE 28th Annual International Symposium on Field-Programmable Custom Computing Machines (FCCM). https://doi.org/10.1109/FCCM48280.2020.00012
4. S. Shalev-Shwartz, S. Shammah, and A. Shashua (2016).Safe, multiagent, reinforcement learning for autonomous driving. arXiv preprintarXiv:1610.03295, .https://doi.org/10.48550/arXiv.1610.03295
5. P. R. Gankidi, (2016). Fpga accelerator architecture for q-learning and its applications in space exploration rovers. Ph.D. dissertation, Arizona State University.
6. P. Remagnino, A. Shihab, and G. A. Jones, (2004). Distributed intelligence for multi-camera visual surveillance. Pattern Recognition 37(4):675-689. https://doi.org/10.1016/j.patcog.2003.09.017
7. P. Hamet and J. Tremblay, (2017). Artificial intelligence in medicine. Metabolism, 69:S36–S40. https://doi.org/10.1016/j.metabol.2017.01.011
8. Andrea Damiani, Giorgia Fiscaletti, Marco Bacis, Rolando Brondolin, and Marco D Santambrogio. (2022). BlastFunction: A Full-stack Framework Bringing FPGA Hardware Acceleration to Cloud-native Applications. ACM Transactions on Reconfigurable Technology and Systems (TRETS) 15(2):1–27. https://doi.org/10.1145/3472958
9. Spinning Up (2018). Proximal Policy Optimization, Open Ai, 2.01.2024. https://spinningup.openai.com/en/latest/algorithms/ppo.html#proximal-policy-optimization


