## DRAW: A Recurrent Neural Network For Image Generation
### Authors: Karol Gregor, Ivo Danihelka, Alex Graves, Danilo Jimenez Rezende, Daan Wierstra 
### Link: [https://arxiv.org/pdf/1502.04623.pdf](https://arxiv.org/pdf/1502.04623.pdf)

### Problem Statement
- The paper proposes a combination of Convolutional Neural Network and Recurrent Neural Network. 

### Related Work (Key Papers)
- Deep Convolutional Neural Networks(DCNN) operates on inputs and outputs of fixed dimensions and is incapable of processing sequences of arbitrary lengths.  
- Recurrent Neural Network are an improvement from the DCNN since it can handle sequences but it requires some processing to generate the sequence of image features. 

### Main Contributions
- The model is end-to-end trainable  without any preprocessing required for the seequences, performs equally well on lexicon-free and lexicon-based text. 

### Assumptions and Future Work
- The model is trained on synthetic data but gives promising results when tested on real images. As an experiment, it will be interesting to try training the model with a real dataset and comparing the results with the current results. 
