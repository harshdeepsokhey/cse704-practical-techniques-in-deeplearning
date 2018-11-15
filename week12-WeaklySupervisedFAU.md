## Weakly Supervised Facial Action Unit Recognition through Adversarial Training
### Authors: Guozhu Peng, Shangfei Wang
### Link: [http://openaccess.thecvf.com/content_cvpr_2018/papers/Peng_Weakly_Supervised_Facial_CVPR_2018_paper.pdf](http://openaccess.thecvf.com/content_cvpr_2018/papers/Peng_Weakly_Supervised_Facial_CVPR_2018_paper.pdf)

### Problem Statement & Main Contributions
- The paper promotes the use of a weakly annotated AU dataset against a fully annotated AU dataset by utlizing the relationship between facial expressions and action units(domain knowledge). The paper employs an adversarial approach to train an AU classifier using domain knowledge and annotated facial expressions. 

- The main contribution of the paper is the recognition(R)-discrimination(D) model. The R model trains for the AU classifiers where as the D model determines the probability that the labels came from the domain knowledge or were determined by the R model during classification. The goal is to close the gap between labels generated from domain knowledge and those determined by the Recognizer model. 

### Related Work (Key Papers)
- Most of the earlier work is focused on utilizing a fully annotated AU dataset. Song et al proposed an approach that uses a  weakly annotated AU dataset and was based on Bayesian model. 
- Another paper closely related to the current paper, by Ruiz et al, proposed and utilized both AU and expressions for performing classifications. However, it used extra large scale facial images for improving the performance.

### Asumptions and Future Work
- With fully supervised and semi-supervised methods already in place and performing well, the next logical approach to experiment is related to a fully unsupervised model for AU recognition. 
