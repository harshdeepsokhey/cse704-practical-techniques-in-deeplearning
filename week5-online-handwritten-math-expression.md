## ICFHR 2016 CROHME: Competition on Recognition of Online Handwritten Mathematical Expressions
### Authors: Harold Mouchère,Richard Zanibbi, Utpal Garain, Christian Viard-Gaudin
## [https://www.cs.rit.edu/~rlaz/files/icfhr_crohme2016.pdf](https://www.cs.rit.edu/~rlaz/files/icfhr_crohme2016.pdf)

## Problem Statement
- The competition identifies the following tasks:
  - Task 1: Formula Recognition, classification of isolated symbols.
  - Task 2: Symbol Recognition, including classifying symbols into valid and invalid domain, allowing only valid symbols as input.
  - Task 3: Structure Recognition, parsing formula for valid handwritten symbols.
  - Task 4: Matrix Recognition, parsing expressions with matrices .
 
## Proposed Ideas
1. *MyScript*: Defines 3 engines to achieve the 4 tasks:
  - *Segmentation*,
  - *Recognition*, 
  - *Interpretation*, 
2. *RIT*: Uses a histogram based model combined with k-means clustering to create a word dictionary.
3. *Tokyo University of Agriculture and Technology*: uses a combination of CNN and LSTM based models for math symbol classification. A context-free grammar based algorithm (CYK) is used to address Task 3. 
4. *University of Nantes*: Applies a graph based approach by utilizing temporal and spatial information for strokes. This approach doesnot use any language models.
5. *University at Sao Paulo*: Also uses 2 stage graph parsing pipeline, where a "hypotheses graph" defines relationship between symbols followed by a top-down paser scans the graph and identifies a subgraph containing the best interpretation with respect to graph grammar. 
6. *WIRIS math*: uses a grammar based recognition stage with the statistical language model being estimated using both expression and formulae in the dataset. The system also employs special methods including symbol segmentation and classification. The above results in a generic task based recognition engine that can be trainied for different tasks like matrices and formula structure.   

## Result:
- For all 4 task,  MyScript, WIRIS perform the best, with MyScript being declared the winner of CROHME 2016. 
