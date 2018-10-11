## Conditional Image Synthesis with Auxiliary Classifier GANs
### Authors: Augustus Odena, Christopher Olah, Jonathon Shlens
### [https://arxiv.org/pdf/1610.09585.pdf](https://arxiv.org/pdf/1610.09585.pdf)

### Problem Statement
- The paper introduces a improved version of GANs, *AC-GANS*, that are capable of producing high resolution samples using specialized cost function.

### Recent Work
- VAEs have been used in the past as they are easier to train and maximize the bound on log-liklihood of the training data. (*drawbacks*- restricion on posterior distribution approximation)
- Auto-regressive models may be used as they can directly model over the distribution (*drawback*- costly to sample with no latent representation)

### Proposed Idea
- *Auxiliary Classifier GANs* - The generator uses class labels ,<img src="http://latex.codecogs.com/gif.latex?c" border="0"/>, along with the noise <img src="http://latex.codecogs.com/gif.latex?z" border="0"/> to get images using <img src="http://latex.codecogs.com/gif.latex?$X_{fake}=G(c,z)$" border="0"/>. The objective function also calculates 2 log-liklihood scores for correct source,<img src="http://latex.codecogs.com/gif.latex?$L_S$" border="0"/>, correct class <img src="http://latex.codecogs.com/gif.latex?$L_c$" border="0"/>. 

### Results
- The models were trained on Imagenet dataset, where 2 variants of the models are trained, a 128x128 generated image model and a 64x64 generated image model, over all the 1000 classes. 84.7% of the classes are claimed to have samples with diversity comparable to the real Imagenet data. 
