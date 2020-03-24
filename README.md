# High Frequency Component Helps Explain the Generalization of Convolutional Neural Networks 
**[H. Wang, X. Wu, Z. Huang, and E. P. Xing. "High frequency component helps explain the generalization of convolutional neural networks." CVPR 2020 (Oral).](https://arxiv.org/abs/1905.13545)**

## Highlights
|Fig. 1: The central hypothesis of our paper: within a data collection, there are correlations between the highfrequency components and the “semantic” component of the images. As a result, the model will perceive both high-frequency components as well as the “semantic” ones, leading to generalization behaviors counterintuitive to human (e.g., adversarial examples).|<img src="main.png" alt="main hypothesis of the paper" width="1600" height="whatever">  
 |:--|---|

<img src="intro.gif" alt="HFC helps explain CNN generaliation" width="1000" height="whatever">

**Fig. 2: Eight testing samples selected from CIFAR10 that help explain that CNN can capture the high-frequency image: the model (ResNet18) correctly predicts the original image (1st column in each panel) and the high frequency reconstructed image (3rd column in each panel), but incorrectly predict the low-frequency reconstructed image (2nd column in each panel). The prediction confidences are also shown. Details are in the paper.**

<details>
 <summary><b>Other Discussions in Paper</b> (click to expand)</summary>

  1. Trade-off between accuracy and robustness (Section 3)
  2. Rethinking data before rethinking generalization (Section 4)
  3. Re-evaluate the heuristics (BatchNorm seems to promote high-frequency information) (Section 5)
  4. Adversarially robust models tend to filter out high-frequency components (Section 6)
  5. Similar phenomena are observed beyond image classification (Section 7)
</details>

## Code Structures

- [scripts/resnet.py](https://github.com/HaohanWang/HFC/blob/master/scripts/resnet.py)
    - Pipeline to replicate our results on CIFAR10 data
- utility/ 
    - [attackHelper.py](https://github.com/HaohanWang/HFC/blob/master/utility/attackHelper.py)
         - main methods used to generate adversarial examples
    - [dataLoader.py](https://github.com/HaohanWang/HFC/blob/master/utility/dataLoader.py)
         - load data
    - [frequencyHelper.py](https://github.com/HaohanWang/HFC/blob/master/utility/frequencyHelper.py)
         - generate low and high frequency data
    - [pdg_attack.py](https://github.com/HaohanWang/HFC/blob/master/utility/pgd_attack.py)
         - helper for adversarial training

## Before using the code

- Install the main dependency: TensorFlow 1.x and [Foolbox](https://github.com/bethgelab/foolbox)
- Read the main script. We recommend users to skim through the script befoure usage. We use "todo" to highlight the parts that may require attention. 
- Generate data: one can generate the data with [utility/frequencyHelper.py](https://github.com/HaohanWang/HFC/blob/master/utility/frequencyHelper.py)
   
## Contact 
  
[HaohanWang](https://twitter.com/HaohanWang) 
&middot; 
[Xindi Wu](https://github.com/XindiWu) 
&middot;
[Zeyi Huang](https://github.com/Justinhzy) 
   
We also have partial implementation in pytorch, feel free to request. 
