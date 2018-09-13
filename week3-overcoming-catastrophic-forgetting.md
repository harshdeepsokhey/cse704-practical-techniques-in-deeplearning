## Overcoming Catastropic Forgetting with Hard Attention to the Task 
### Authors: Joan Serra, Didac Suris, Marius Miron, Alexandros Karatzoglou
## [https://arxiv.org/pdf/1801.01423.pdf](https://arxiv.org/pdf/1801.01423.pdf)

## Problem Statement

- Neural networks trained for performing one task lose information when trained for performing a different task. This is known as *Catastrophic Forgetting*. This paper proposes a mechanism to prevent loss of information during sequential/lifelong learning. 

- For example, Task #1 can classify category-A and category-B while Task #2 can classify category-C and category-D. But since there is no way to way the information learnt previously, the Task #2 method may not work for Task #1. 

## Related Work

1. Use of Memory , also known as *Rehersal* : Explicitly storing information and using it to not forget what was previously learnt. 

2. Pseudo-Rehersal, also known as *Dreamy Methods*: Using generative approach to  generate the memory of the previously performed task. The generated example is expected to be similar to the task seen earlier. When learning the new task , we use generative modesls to replay these tasks or *dreams* of the past.
- **Drawback**: We need to replay the information multiple times. 

3. Reduce Representation overlap in the task: Another proposed solution is using learning models that are *orthogonal* to each other: 

- *Freezing parts of the network*, in order to preserve information contained by those parts of the network. 

- Example: 
	- **Progressive Neural Network**, trains seperate networks/neuron columns and ensure the flow of information from the previous network to the network trained for the new task. (**Drawback**- lot of space)
	- **PathNet** , uses generative models to learn different paths for tasks. (**Drawback**- time consuming and involves lots of parameters)
	- **PackNet**, represents independent units and trains the full network with pruning and compressing. (**Drawback**- need to set threshold for pruning)


## Proposed Idea

- Need of an task-based model that maintains information from previous tasks while learning new task. For example, when learning to classify brown and black animals after learning to classify dogs and birds, the change is only in the task while the training data is the same. 

- The **proposed method** uses task number as an identifier, and learns embeddings for each task. These embeddings are used to condition the network in the learning phase. The task number and the embedding change as the task changes while ensuring no overlap between embeddings. So we identify the units that are important for the embeddings in the first task, we freeze these units when we learn new units for the embeddings in the next task, such that they dont overlap. 

- Attention($${a_l}^{t}$$) is a Gated function of the embedding. The output of every layer's unit is conditioned and used to keep some units and discard other units. This is possible since the attention is a sigmoid that provides binary resuls for large values. 

- Accumalate attention vectors across tasks by taking the maximum over each task sequence. For the backpropagation stage, the input($$ {a_{l-1,j}^{\le t}} $$) and the outputs($$ {a_{l,i}^{\le t}} $$) are used along with the original gradient, $$g_{l,i,j}$$. 

- To train the attention mechanism, epoch-based  linear annealing is used. For the b=1, the slope, $$ s  = \frac{1}{s_{max}}$, whereas for the last batch, $$ s= s_{max}$$. Annealing results in some gradient at the start of the epoch with a sigmoid gate, which gradually changes to no gradient observed at the end of the batch with the gate transformed into a step function. (**Drawback**- introduction of poor gradients due to annealing, thus need *gradient compensation*).

- *Gradient Compensation* boosts the gradient of the gates. The gradient is normalized by the derivative of the current sigmoid with current slope,$$s$$ along with the derivative of the normal sigmoid multiplied by the $$s_max$$ factor. 
 
- L1 regularization over the attention vectors is used to prevent dedicating all units to one task. Thus, actiavting the minimum amount of units for the first task so that there is enough for the other tasks. 
 
## Results

- Trained with the minimal overhead using SGD. 

- Tested against the following datasets: 
	- CIFAR 10/100
	- MNIST
	- NotMNIST
	- FashionMNIST
	- SVHN
	- FaceScrub
	- TrafficSigns


- *Hard Attention Task(HAT)* registers a 55% improvement from the previous state-of-the-art ,*Progressive Neural Network (PNN)*. PNN has 11% forgetting ratio whereas HAT results in only 6% forgetting. 

- HAT also has lesser hyperparameters namely, $$s_max$$, maximum slope allowed in the gated function and $$c$$, amount of compressibility to be applied when learning a task. 