## Focal Loss for Dense Object Detection
### Authors: Tsung-Yi Lin, Priya Goyal, Ross Girshick, Kaiming He, Piotr Dollár
### Link: [https://arxiv.org/pdf/1708.02002.pdf](https://arxiv.org/pdf/1708.02002.pdf)

### Problem Statement & Main Contributions
- This paper addresses the issue of neural networks learning from an unbalanced dataset, that mostly seen in single stage object detectors, resulting in their poor performance. 
- The Focal Loss , introduced in the paper, is the main contribution of the paper, that improves the performance of single stage object detectors that dynamically scales the cross entropy loss to compensate for the imbalance. 

### Related Work (Key Papers)
- Most approaches resolve this issue by implementing OHEM, that forces the network to investigate false postives and false negative examples, ie, FG samples for which the the network predicited a BG with high probability and BG samples for which the network predicted a FG with high probability.
   
### Asumptions and Future Work
- The paper discusses the experiments related to the varying values of <img src="https://latex.codecogs.com/gif.latex?\gamma" title="\gamma" /> for the FG and BG examples and comparison of Focal Loss with OHEM, as well as speed and accuracy tradeoffs. A potential future work would be to test this model on the challenging WIDER dataset. 
