# Deep learning vs traditional ML algorithms for AMR detection

Master Thesis Proposal

Author - Varun Sree Bholalayam (00807289)


## Problem Introduction

Reinforcement learning (RL) is a branch of machine that is concerned with training agents to make progressive decisions in an environment, to maximize a numerical reward signal. In RL, a learning agent senses the state of its environment and takes iterative actions to improve its policy, such that the expected reward along its trajectory is maximized <sup>2</sup>.

Unlike supervised learning which relies on labeled datasets or unsupervised learning which tries to find structure in sets of unlabeled data, in RL the learner must discover which actions yield the best reward by trial and error. These two characteristics: trial-and-error search, and delayed reward, are the two most important distinguishing features of reinforcement learning<sup>1</sup>.

RL has found widespread success in many application areas including self-driving cars <sup>4</sup>, robotics in space exploration <sup>5</sup>, surveillance <sup>6</sup>, wearable healthcare devices <sup>7</sup>, and much more. Accelerating Reinforcement learning with FPGAs (Field-Programmable Gate Arrays) can offer a range of advantages and address specific problems associated with RL applications. Architectures consisting of a blend of CPUs and FPGAs have become a good solution for accelerating RL. A few examples include 

1. Accelerating both computation and memory-intensive AI applications <sup>8</sup>.
2. Hardware acceleration by configuring FPGAs to accelerate key operations such as a high-throughput on-chip accelerator for Prioritized Replay Buffer<sup>2</sup>.
3. Optimizing for specific RL algorithms, such as developing a high-throughput PPO accelerator by accelerating computational intensive inference and training phases <sup>3</sup>.

Proximal Policy Optimization (PPO) is a state-of-the-art policy optimization method that has been shown to achieve superior overall performance on various Reinforced Learning Benchmarks<sup>10</sup>. The aim is to make the biggest possible improvement step on a policy using the data we currently have, without stepping so far that we accidentally cause performance collapse<sup>9</sup>. Each iteration of PPO includes the inference face where an agent interacts with its environment to collect data, and a Training Phase where the agent trains the policy using the collected data. 

A study <sup>3</sup> published in 2020 developed a high-throughput PPO accelerator, using a CPU_FPGA heterogenous infrastructure, by accelerating both the Inference and training Phases which are both computationally intensive. This achieved 2.1X to 30.5X improvements in throughput against state-of-the-art CPU and 2X to 27.5X improvements against CPU-GPU implementations. 


## Research Questions

The motivation for the following research questions stems from <sup>3</sup> :

1. Integrating the Alveo board with the Gymnasium environment in a convenient way for the development and testing of acceleration algorithms for RL.
2. Recreating the results obtained from the paper<sup>3</sup> which accelerates Proximal Policy Optimization on CPU-FPGA Heterogenous platforms. 
3. Compare my results to that of the paper <sup>3</sup> and suggest improvements to the methods used in the paper. 


## Methodology

1. <strong>Literature Review and Paper Understanding</strong>
<ul>
  <li>Thoroughly studying <sup>3</sup> and related papers on accelerating PPO on CPU-FPGA Heterogeneous Architecture.</li>
  <li>Studying and familiarizing myself with the Gymnasium environment and how to modify an existing Gym environment if I need to.</li>  
</ul>
2.<strong>Eniroment Intergration</strong>
  <ul>
    <li>Developing an interface or wrapper that connects the Alveo board functionalities with Gymnasium's environment interface.</li>
    <li>Validateing the integration by running simple tests to ensure that the Gym environment properly interacts with the Alveo board and that the agent can learn within this environment.</li>
  </ul>
3. <strong>Recreating of Accelerator</strong>
  <ul>
     <li>Recreating the design of a systolic, array-based FPGA accelerator to enable parallel inferences and high-throughput training of neural networks representing value and policy functions.</li>
     <li>Designing a systolic array compute sharing-based load-balancing technique that shares the compute units between the value network and policy network to deal with potential load imbalances in       training as in the paper.</li>
  </ul>
4. <strong>Testing and and Comparison</strong>
   <ul>
      <li>Testing the resultant performance and comparing it to state-of-the-art CPU only and CPU-GPU implementations.</li>
      <li> exploring and suggesting possible improvements./li>
    </ul>


## Research Goal

The goal is to reproduce the high-throughput PPO accelerator on a CPU-FPGA Heterogenous architecture as done in the paper <sup>3</sup>, to compare my results to those in the paper and propose possible improvements.  


## Time Plan

| Month | Intended work |
| --- | --- |
| 1 | Understanding Pappers on PPO implementation and familiarization with Gymnasium|
| 2 | Conveniently Integrating the Alveo board with the Gymnasium environment |
| 3 & 4| Recreating the architecture in the paper <sup>3</sup> |
| 5 | Testing Evaluation and Optimization of PPO Accelerator  |
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
10. John Schulman, Filip Wolski, Prafulla Dhariwal, Alec Radford, and Oleg Klimov, (2016). Proximal Policy Optimization Algorithms, arXiv preprint arXiv. https://doi.org/10.48550/arXiv.1707.06347


