## Lifelong Learning with Dynamically Expandable Networks
### Authors: Jaehong Yoon, Eunho Yang, Jeongtae Lee, Sung Ju Hwang
## [https://arxiv.org/pdf/1708.01547.pdf](https://arxiv.org/pdf/1708.01547.pdf)

## Problem Statement
- The task of *LifeLong Learning* focuses on utilizing knowledge from previously learned tasks for training of new tasks that may or may not be correlated.

- The paper tackles this problem by using *Dynamically Expandable Networks*, that are capable of deciding capacity of the network dynamically and proficient in utlizing the overlapping knowledge sharing framework between tasks. This model prevents forgetting, , overhead of retraining the network for each new task as well as limiting use of the neurons per task. 

## Related Work
1. Naive approach of **retraining the network** with new training data (*Drawback*- degraded performance if the new task is very different from the old task, so no use of the previously learned features in the new task learning.).

2. Lifelong learning based on **online multi-task learning**, removes dependencies on previously learned tasks and thus, prevents retraining previous task predictors. (*Drawback*- catastrophic forgetting)

3. **Regularization** can prevent catastrophic forgetting, by preventing any deviation in the model learned for the new task.  (*Drawback*- suboptimal performance due to restricted learning of new knowledge for the model)

4. **Elastic Weight Consolidation(EWC)** , **online per-synapse consolidation** provide a solution for the restricted learning. Treating the previously learned network as *static* may also prevent forgetting, while expanding the network at each stage by adding neurons that help preserve information for the new task if it significantly differs from the previous task and reusing if the tasks are similar. (*Drawbacks*- increase in the number of neurons per layer)

## Proposed Idea

- *Selective Retraining*, performs model retraining only for weights that are affected by the new task. It provides a computationally low overhead. 

- *Dynamic Network Expansion* occurs when the new task and the old task differ significatly and require new/additional knowledge for understanding the task. This is done by addtional neurons added to the network to represent the new features of the new task that were not present in the previous tasks. The number of neurons needed is decided dynamically using *group sparse regularization*. In other scenario, where the new and the old tasks share relevance,*selective retraining* is sufficiant to understand the new task.

- *Network split/duplication* performs splitting the neuron optimally for 2 different tasks. Post-regularization, the semantic drift is compared for change in the features between time <img src="https://latex.codecogs.com/gif.latex?t" title="t" />, <img src="https://latex.codecogs.com/gif.latex?t-1" title="t-1" /> above a threshold, <img src="https://latex.codecogs.com/gif.latex?\sigma" title="\sigma" />. If true, we register change to be significant and split the neuron into two copies, performing a retraining on the overall structure. 

## Results

- Tested against the following datasets:
  - MINIST-Variation (MNIST with rotated, noisy background)
  - CIFAR-100
  - AWA (Animal with Atttributes)
  
- Significant reduction in the parameters used during training (~ 11% - 60%)


