## A Novel Connectionist System for Unconstrained Handwriting Recognition
### Authors:Alex Graves, Marcus Liwicki, Santiago Fernandez, Roman Bertolami, Horst Bunke, Jurgen Schmidhuber
## [http://people.idsia.ch/~juergen/tpami_2008.pdf](http://people.idsia.ch/~juergen/tpami_2008.pdf)

## Problem Statement
- The paper proposes a method for recognition of handwritten text using Recurrent Neural Network. 
- *Online data*, recorded from whiteboard
- *Offline data*, includes images scanned from handwritten forms. 
- The data is "Normalized" due to varying handwriting styles. Skew and Slant , delayed strokes correction is a part of the normalization step. Also a baseline is established on which the handwritten charactes rest with some adjustment to the width of the characters. 
- The normalized data is then used for "Feature Extraction". The online data contains 25 features for each point recorded and can be categorized as features based on neighboring coordinates and those based on spatial information through the offine matrix representation. The offline data uses a sliding window feature extractor  where each text image is converted to vectors containing 9 features.

## Previous Work
- Classification of isolated words on limited vocabolary (*drawback*: not scalable)
- For larger vocabolary, naive approach is to use characters from previously segmented words and map them based on a dictionary of words. (*drawback*: difficult for handwritten cursive text,results in *Sayre's Paradox*)
- Hidden Markov Models , address the "Sayre's Paradox" where segmentation and classification is done simultaneously.(*drawback*: use of context information is difficult) 
- RNNs provide a solution to HMMs context problem but they have limited to single character recognition. 

## Proposed Idea
- Using a RNN trained for sequence labeling task with CTC mapping the input sequence to the output labels directly, thus no presegmented data required. BLSTM, combined approach using BRNN and LSTM , is used to improved the flow of context information. 
- **Recurrent Neural Network**, robust model to handle distortions of input data by modulating rate of change of state while making use of the past information for context 
- **Long Short-Term Memory**, employed to improve the use of contextual information in RNNs while addressing the vanishing/exploding gradient problem using connections between "memory blocks".
- **Bi-directional RNN**, capable of accessing context in both directions since it can be useful to know the letters before and after a given letter. 
- **Connectionist Temporal Classification**, designed for sequence labelling task and doesnot require a previously segmented data as input. 

## Results
- Datasets use:
  - IAM-OnDB , acquired from whiteboard
  - IAM-DB, scanned images of handwritten forms
  
 - Performance Measure: Word Accuracy and Character Accuracy is calculated based on the following formula:
<a href="http://www.codecogs.com/eqnedit.php?latex=acc&space;=&space;100&space;*&space;\Big(1-&space;\frac{insertions&space;&plus;substitutions&space;&plus;&space;deletions}{total\:length\:of\:test\:set&space;\:trancriptions}\Big)" target="_blank"><img src="http://latex.codecogs.com/gif.latex?acc&space;=&space;100&space;*&space;\Big(1-&space;\frac{insertions&space;&plus;substitutions&space;&plus;&space;deletions}{total\:length\:of\:test\:set&space;\:trancriptions}\Big)" title="acc = 100 * \Big(1- \frac{insertions +substitutions + deletions}{total\:length\:of\:test\:set \:trancriptions}\Big)" /></a>
  
  - Results: Word Recognition Accuracy : 79.7% (online data) , 74.1%(offline data) , hence out-performs the HMM based state-of-the-art
  
  
