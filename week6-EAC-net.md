## EAC-Net: A Region-based Deep Enhancing and Cropping Approach for Facial  Action  Unit  Detection
### Author: Wei Li, Farnaz Abtahi, Zhigang Zhu, Lijun Yin
## [https://arxiv.org/pdf/1702.02925.pdf](https://arxiv.org/pdf/1702.02925.pdf)

## Idea
- *Multi-task learning*, sharing representations between related task in order for the model to learn and generalize better on the task.
- *Hard Parameter Sharing*:
  - involves sharing the hidden layers while keeping the output layers task specific
  - helps in reducing overfitting
- *Soft Parameter Sharing*:
  - each task has its own separate model with with own parameters
  
- *Inductive Bias*, provided by auxiliary tasks causes the model to prefer the assumption that explains more than one task. 

## Recent Work
- *Deep Relationship Networks*, learns relationship between tasks using priors but still dependent on a pre-defined structure for sharing which can be errorenous. 
- *Fully-Adaptive Feature Sharing*, bottom-up approach which groups similar tasks. may not produce globally optimal models.
- *Cross-stitch Networks*, 2 seperate models stitched together by learning a linear combination of the output of the previous layers and make use of the knowledge of the other tasks. 
- *A Joint Many-Task Model*,utilizes several NLP based tasks in the form of a heirarchial structure for jointly performing multi-task learning. 
- *Weighting losses with uncertainty*, architecture based on adjusting the relative weights derived from a multi-task loss function, utlizing the uncertainity of the task. 
- *Sluice Networks*, learns the layers and subspaces that must be shared and the layers at which the model has learned the best representations of the input sequences. generalizes deep-learning based MTL models like cross-stitch networks, etc. 
