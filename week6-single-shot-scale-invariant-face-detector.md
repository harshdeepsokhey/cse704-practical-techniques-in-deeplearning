## Single Shot Scale-invariant Face Detector
### Author: Shifeng Zhang, Xiangyu Zhu, Zhen Lei, Hailin Shi, Xiaobo Wang, Stan Z. Li
## [https://arxiv.org/pdf/1708.05237.pdf](https://arxiv.org/pdf/1708.05237.pdf)

## Problem Statement
- Previously, proposed anchor based methods are not scale-invariant hence, unable to detect small objects. 
- The paper proposes a scale invariant face detector that resolved the issue with anchor-based models for smaller faces. 
## Previous Work
- Anchor-based object detection methods that perform binary classification with class prediction scores and bounding-box regressions as output. Using Hard Negative Mining further boosts performance.(*Drawbacks*: reduced speed when dealing with smaller faces)
- Object detection with context information has been used in models like CMS-RCNN
- Multi-scale SSD model that serves as an inspiration for the current paper. 

## Proposed Idea
- *Scale Compensation Anchor Matching* : distinct anchor scales that improves the recall rate for smaller faces. 
- *Scale Equitable Model* : varying anchor scales for appropriate face detection , improving the detection rate that usually drops in the previous models when detecting small faces. 
- *Maxout Background label*: reduces the high false positive rate of small faces by predicting N_m scores for the background label and choosing the "Max" as the final scores.  
   
## Results
- The dataset used for the training/testing:
  - **AFW** , 205 images with 473 labeled faces
  - **FDDB**, 5171 faces in 2845 images
  - **Pascal Faces**, 1335 labeled faces in 851 images with large face appearance and pose variations.
  - **WIDER faces** , ~32K images with ~400K annotations of varying scales and poses. 

- The dataset is split into easy, medium and hard subsets. 
