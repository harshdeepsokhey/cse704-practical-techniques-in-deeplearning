## Multi-Task Curriculum Transfer Deep Learning of Clothing Attributes
### Authors: Qi Dong, Shaogang Gong and Xiatian Zhu
## [https://arxiv.org/pdf/1610.03670.pdf](https://arxiv.org/pdf/1610.03670.pdf)

## Problem Statement
- The paper focuses on using domain transfer learning for understanding multi-label clothing attributes, with limited labled training data available. 

## Related Work
- Learning visual attributes based of using a small pre-defined set of attributes and relying heavily on manual labeling of training data. (Drawback: inconsistencies and inaccuracies of the meta-data labels as compared to the manually labeled attribites)

- Using deep transfer learning for cross-domain adaptation , where large amounts of data is present for training. (Drawback: "domain-drift problem", tranfering knowledge learnt on easy sources(shop) to difficult targets(street)). 

## Proposed Idea

- Multi-Task Deep Learning (MTN): Branched model for learning details of each category, along with shared learning of generic features in convolution layers. Due to the small set of learning parameters, overfitting may not occur. However, it needs large amount of training data. 

- Curriculum Transfer Learning (MTCT):The CT method is used to tranfer annotation knowledge from the source to the weakly labelled target domain. It is motivated from the fact that learning things for people and animals starts with easier task incrementally grows towards learning difficult tasks, rather than by blind random acquisition of knowledge. The paper proposes 2 stages to model clothing attaributes. 
  - Stage 1: Shop domain (clean) , where learning is performed using simpler source images + attribute labels only
  - Stage 2: Street domain (wild) , where inorder to learn harder cross-domain information, we build on top of stage-1 and perform incremental learning for difficult target data. 

## Results

- Dataset used : Cross-domain clothing attribute dataset containing 9 fine grained clothing attributes. 
- MTCT performs better that the existing state-of-the-art ,FashionNet, by 4.51% in mAP (mean average precision). 

