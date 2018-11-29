## Scan, Attend and Read: End-to-End Handwritten Paragraph Recognition with MDLSTM Attention
### Authors: Theodore Bluche, Jerome Louradour, Ronaldo Messina
### Link: [https://arxiv.org/pdf/1604.03286.pdf](https://arxiv.org/pdf/1604.03286.pdf)

### Problem Statement & Main Contributions
- The paper proposes an end-to-end multiline handwriting recognition model without the need to segment the paragraph. The current model also doesnot need the previous character as an input for predicting the next character. 
- The model is tested on the IAM database and is not limited to one particular script but performs well for Arabic text as well. 

### Related Work (Key Papers)
- Prevoiusly proposed models require segmentation of the input image providing sequential predictions along the width of the image. 

### Asumptions and Future Work
- Unlike an generic RNN model, this implementation doesnot utilize the previous input to predict the next one. The authors suggest using this as a key feature to enchance the decoder. The authors also acknowledge that the model computationally slower than the previous approaches which limits its industrial application. However, given the added advantage of skipping the segmentation step is something that can be investigated in the future work. 
