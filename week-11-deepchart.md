## DeepChart: Combining deep convolutional networks and deep belief networks in chart classification
### Authors: Binbin Tang , Xiao Liu , Jie Lei , Mingli Song , Dapeng Tao, Shuifa Sun, Fangmin Dong
### Link: [https://www.sciencedirect.com/science/article/pii/S0165168415003291](https://www.sciencedirect.com/science/article/pii/S0165168415003291)

### Problem Statement
- The paper addresses the problem of classifying charts using CNN and DBN. This implementation provides a comparison result between 5-chart classes[bar, flow, line, scatter, pie] and is trained on over 5K chart images. 

### Related Work (Key Papers)
- Previous approachs include use of Hough Transforms, Line-detection, Hidden Markov Models
- More recent approaches have been known to perform better than its predecessors, namely, HD-MSL, Hypergraph, multimodal hypergraph method. 
- The propsed paper combines CNN and DBN to perform the classification of charts instead of pre-crafted features. 

### Main Contributions
- *Convolution Neural Network* : The CNN used in the implementation is based on Alex Krizhevsky's CNN model, with a 5 class output for the 5 chart categories. The extracted features are then pushed through a DBN for dimensionality reduction. 

- *Deep Belief Network*: DBN is a generative model and provides the final softmax predictions for the 5-chart categories. 

### Assumptions and Future Work
- The model currently trains on limited dataset of 5K images and compares the results only against models that use handcrafted features. It would be interesting to see the performance of this model compared against Chartsense and other similar models. Moreover, this paper only addresses the chart classification problem and doesnot talk about the problem of chart data understanding. Training the model on more chart categories and ultimately compiling a larger dataset of different chart types would be a potential extension of the work.  
