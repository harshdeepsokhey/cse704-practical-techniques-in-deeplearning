## An End-to-End Trainable Neural Network for Image-based Sequence Recognition and Its Application to Scene Text Recognition
### Authors: Baoguang Shi, Xiang Bai and Cong Yao
### Link: [https://arxiv.org/pdf/1507.05717.pdf](https://arxiv.org/pdf/1507.05717.pdf)

### Problem Statement & Main Contributions
- The paper presents a sequential VAE with each cell as an LSTM, with the decoder incrementally adding the outputs with a attention update mechanism for restricting the input area by the encoder and the output update area by the decoder. 

- The model is tested on MNIST ,SVHN and CIFAR0-10 dataset.

### Related Work (Key Papers)
- Previously proposed ideas are based either on VAEs or on generative modelling approach which generate images in a single pass. 

### Assumptions and Future Work
- The model could have been tested against the performance of GANs and other generative models available. Also, the model when tested against the CIFAR-10 dataset doesnot seem to perform upto mark. These could be some of the potential areas for future work. 
