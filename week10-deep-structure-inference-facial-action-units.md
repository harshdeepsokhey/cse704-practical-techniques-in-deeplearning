## Deep Structure Inference Network for Facial Action Unit Recognition
### Author: Ciprian Corneanu,Meysam Madadi, and Sergio Escalera
### Link: [http://openaccess.thecvf.com/content_ECCV_2018/papers/Ciprian_Corneanu_Deep_Structure_Inference_ECCV_2018_paper.pdf](http://openaccess.thecvf.com/content_ECCV_2018/papers/Ciprian_Corneanu_Deep_Structure_Inference_ECCV_2018_paper.pdf)

### Problem Statement
- The paper builds an Inference Network for combining local and global reprentations. It utilizes patch learning methods and structure learning methods for Action Unit Recognition.

### Related Work (Key Papers)
- *Patch Learning models*, proposes ideas like patch selection, use of domain knowledge to select face region mapping to an AU using Bi-LSTM and CNNs. Also uses multi-task sparse learning framework for learning patches for different expressions.

- *Structure Learning models*, include CRFs to detect multiple AUs, RBM based approaches for capturing high order AU interactions,some combining patch learning also. 

### Main Contributions
The main contributions in this paper are :
 - *Patch Prediction(PP)* and  *Fusion(F)*: The model learns local features for the face patch and then identifies the structure between these face patches for mapping with particular action units
 - *Structure Inference* :The correlated AUs are captured and replicated using an inference network using Bidirectional LSTM model.

### Assumptions and Future Work
Most of the key ideas/assumptions have been addressed by the authors in the *Ablation Study* section of the paper. One such idea is about balancing classes. The idea of ensuring that the network learns features corresponding to almost every AU in the training is important and is widely adapted while training most networks. Additionally, the model learns local features between classes: some AUs work best for some patches while other work for different patches. Locality and Patch Prediction ensures that the model learns the correlation between classes. A potential addition to this work could include trying a different RNN model or employing a Sequence to Sequence GAN model to experiment the performance. 
