## Joint Line Segmentation and Transcriptiopn for End-to-End Handwritten Paragraph Recognition
### Authors: Théodore Bluche
### [https://arxiv.org/pdf/1604.08352.pdf](https://arxiv.org/pdf/1604.08352.pdf)

### Problem Statement
- Earlier methods recognise sequence of characters in an image of handwritten text. But annotations and transcription is expensive for train and recognition stage. 
- The existing models need segmented text lines or need automated line segmentation algorithms for complete document text extraction. 
- This paper improves the existing Multi-dimensional LSTM RNN model for end-to-end processing of complete handwritten paragraphs. 

### Previous Work
- Classical methods include image processing techniques and statistical models. 
- *Attention-based* models, used for recognition of small pieces of handwriting as well as predicting the next set of sequences. 
- Computer Vision based techniques based on localization and object recognition were also employed but was limited to only to large text. 

### Proposed Idea
- *MDLSTM-RNN*, contains LSTM layers scanning in 4 directions and summing the feature maps with character predictions obtained from softmax normalization. 
- *Connectionist Temporal Classification (CTC)*, uses all possible labellings of the sequence to recognise text lines. 
- *Iterative Weighted Collapse*, contains a neural network to predict the weights of a weighted sum.

### Result
- The datasets used are:
  - *IAM* dataset, contains handwritten english text copied from LOB corpus.
  - *Rimes* database, contains handwritten letters in French.
- The performance is measured as *Character(or Word) error rate(CER %)*, corresponds to edit distance between recognition and ground-truth. 
