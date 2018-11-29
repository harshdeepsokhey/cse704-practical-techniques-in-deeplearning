## Localizing and Recognizing Labels for Multi-Panel Figures in Biomedical Journals 
### Authors: Jie Zou, Sameer Antani and George Thoma 
### Link: [https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8270059](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8270059)

### Problem Statement & Main Contributions
- The paper combines object detection, image classification and sequence classification for understanding multi-panel figures in biomedical journals. The 3 stage model is trained on ImageCLEF2016 dataset. 
- The key contributions of the paper is combining the object detection methods (HOG, SVM) along with CNN and label sequence classificaton methods for effective recognition of labels. The paper also contributes a ground-truth figure dataset for multi-panel label recognition. 

### Related Work (Key Papers)
- Previous works include using visual features like edges to segment and classify panels. 
- The current approach uses the SOTA implementations in detection and classification to achieve desired results. 

### Asumptions and Future Work
- Due to the limited dataset and classes, the authors were constrained to use traditional methods which work well on smaller datasets. The limited dataset also implies constrained features which are evident from the rules mentioned in the paper with respect to the fonts and direction of the labels. A potential future work is to use a larger and more varied dataset and replacing the traditional methods for detection and classification with the more efficient and accurate deep learning models. 
