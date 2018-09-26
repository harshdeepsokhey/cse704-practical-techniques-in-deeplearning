## ChartSense: Interactive Data Extraction from Chart Images
### Authors: Daekyoung Jung, Wonjae Kim, Hyunjoo Song, Jeong-in Hwang, Bongshin Lee, Bohyoung Kim, Jinwook Seo
## [https://www.microsoft.com/en-us/research/wp-content/uploads/2017/02/ChartSense-CHI2017.pdf](https://www.microsoft.com/en-us/research/wp-content/uploads/2017/02/ChartSense-CHI2017.pdf)

## Problem Statement
- The paper proposes a method to classify charts and extract data from charts. 
- Challenges: 
  - Large number of varying chart styles , hence difficult to use a simple data extraction approach
  - Work around for data items that are hidden/occluded, differentiating between 2 different trends represented in the chart
  - Image to Text conversion ie. extracting data from image and convert to appropriate text. Character recognition could be a viable option however, the existing methods have low accuracy. 

## Related Work
- **ReVision**, a tool used for automatic chart data extraction uses a 2 stage pipeline, ie. chart classification followed by data extraction (**Drawbacks**: low extraction accuracy for practical use of data)
- **Mixed Initiative Interfaces**, enables effective collaboration with intelligent agents and incorporates feedback based system to handle uncertainity in user input. 
- **Chart Data Extraction**, utilizing edge detection/vectorization for extracting data from chart images using ML and image processing. This work is partly utilized by *ChartSense* as well. 
- **iVoLVER**, another web-based tool for data extraction in chart images which allows users to classify the type of data to be extracted. (**Drawbacks**: large number of user inputs required for improving data extraction accuracy)
- Other tools like **DataThief** extract data from line charts and is dependent on user input for identifying region from where data needs to be extracted.

## Proposed Idea
- Uses a deep learning based chart classifier and extracts data with mixed-initiative interaction. 
- Uses user feedback based mixed-initiative interaction combined with image processing methods for data extraction with improved accuracy and efficiency of data extraction.
- **Network Architecture**: 
    - *Classification Task*: Uses simple CNN structure for image classification, called [GoogLeNet](https://arxiv.org/abs/1409.4842)
    - *Data Extraction Task*: Uses a user interaction based model ("mixed initiative interface") to assist data extraction. For eg. asking users to identify colors representing graphs to improve accuracy. 

## Results:
- Dataset: 
  - *Classification*: Input: 256x256x3 with the dataset split into training and validation as 80% and 20%. 
  - *Data Extraction*: 
