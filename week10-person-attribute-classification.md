## Adaptively Weighted Multi-task Deep Network for Person Attribute Classification
### Authors: Keke He, Zhanxiong Wang, Yanwei Fu, Rui Feng, Yu-Gang Jiang, Xiangyang Xue
### Link: [http://www.yugangjiang.info/publication/17MM-PersonAttribute.pdf](http://www.yugangjiang.info/publication/17MM-PersonAttribute.pdf)

### Problem Statement
- The paper proposes a multi-task learning model for person atttribute classification with adaptive and dynamic weights for each learning task. 

### Related Work (Key Papers)
- *Multi-task Learning*, refers to [Zhang et al]()'s paper that describes a facial landmark detection problem with other correlated tasks like gender, expression, etc. However, the current paper doesnot use the auxiliary attributes for facial landmark detection. Some of the previous works namely, deep cascaded multi-task framework, multi-task cross residual networks and multi-task CNN also address the same task but donot have the dynamic and adaptive weight update mechanism. A recent [paper](https://arxiv.org/abs/1611.05377) utilized a similar adaptive weight update model by grouping similar tasks together however, the current paper performs weight optimizations on each task. 

- *Person Attribute Analysis*, useful for face detection, face alignment and face identification problems. Some previous works referenced also use person attributes as an intermediate feature for improving related task such as clothing retrieval, person re-identification, etc.

### Main Contributions
- The paper addresses 2 issues with the existing deep network frameworks:
  1. *Negative Transfer*, where sharing between 2 different  tasks may affect the performance of the other.
  2. *Static Weights*, implies that weights are not adaptive and remain fixed for each of the learning task.
  
 - *Weighted Loss Layer*: The loss calculation uses a weight term, <img src="https://latex.codecogs.com/gif.latex?\lambda_j" title="\lambda_j" />, that represents a scalar value to include the importance of the task of the learning the <img src="https://latex.codecogs.com/gif.latex?j^{th}" title="j^{th}" /> attribute. This understanding arises by eliminating the assumptions that attributes are independent and that each attribute prediction contributes equally to the loss. The authors believe that attributes are correlated with one another. 

### Assumptions and Future Work
The correlation of attributes seems like a fair assumption since a lot of attributes are co-dependent and a weighted loss would be useful. However, this may lead to stagnation of certain attributes that may not be flagged as main attributes but have properties that help enhance the main attribute. So, a weight donation strategy must be employed to ensure that these not-so-important attributes do not impact the learning in a negative way. 
