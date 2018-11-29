## Generating Handwritten Chinese Characters using CycleGAN
### Authors: Bo Chang,Qiong Zhang,Shenyi Pan,Lili Meng
### Link: [https://arxiv.org/pdf/1801.08624.pdf](https://arxiv.org/pdf/1801.08624.pdf)

### Problem Statement & Main Contributions
- The paper proposes CycleGAN to generate handwritten-styled chinese characters using printed chinese font characters. 

### Related Work (Key Papers)
- Previous works include hierarchial representation of strokes(Eg. StrokeBank), generating a template of the character followed by separating into strokes. 
- Some recent works include Image Style transfer using noth descriptive and generative models. However, these models can be time-consuming(descriptive) and may yield poor/blurry results(generative).
- GAN models like pix2pix, zi2zi have also been used as an approach for transforming chinese character images to generate newer representations. Some of these models require a paired dataset which is an added overhead. Using **cycleGAN**, eliminates the requirement of a paired dataset. 

### Asumptions and Future Work
- From the results mentioned in the paper, we can conclude that the model generally performs well with some exceptions related to subtle differences in characters and generates better quality results than neural style transfer. From the unsupervised task standpoint, the current model performs well. However, its performance with respect to the supervised learning model is low. The original cycleGAN paper mentions some of the failures including small differences between classes and unbalanced dataset. A potential future work could be using this model for generating arabic and indic handwritten characters. 
