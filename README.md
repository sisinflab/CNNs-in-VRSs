# A Study on the Relative Importance of Convolutional Neural Networks in Visually-Aware Recommender Systems

This is the official implementation of our paper [**A Study on the Relative Importance of Convolutional Neural Networks in Visually-Aware Recommender Systems**](https://openaccess.thecvf.com/content/CVPR2021W/CVFAD/html/Deldjoo_A_Study_on_the_Relative_Importance_of_Convolutional_Neural_Networks_CVPRW_2021_paper.html) published in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR) Workshops.

**Authors:** Yashar Deldjoo, Tommaso Di Noia, Daniele Malitesta*, Felice Antonio Merra.
<br>\**corresponding author*

<p float="left">
  <figure>
    <img src="https://github.com/sisinflab/The-Importance-of-CNNs-in-Visual-Recommenders/blob/main/alexnet.png" width="300" />
    <figcaption>(a) AlexNet</figcaption>
  </figure>
  <figure>
    <img src="https://github.com/sisinflab/The-Importance-of-CNNs-in-Visual-Recommenders/blob/main/resnet50.png" width="300" />
    <figcaption>(b) ResNet50</figcaption>
  </figure>
 </p>
 
 **Table of Contents:**
- [Requirements](#requirements)
- [Run and evaluate recommendations](#run-and-evaluate-recommendations)
- [Datasets](#datasets)
- [Parameters for Image Feature Extractors](#parameters-for-image-feature-extractors)
- [Visual Recommenders](#visual-recommenders)
- [Configuration Files](#configuration-files)
- [The Authors](#the-authors)

## Requirements

To begin with, please make sure your system has these installed:

* Python 3.6.8
* CUDA 10.1
* cuDNN 7.6.4

Then, install all required Python dependencies with the command:
```
pip install -r requirements.txt
```
Finally, you are supposed to structure the dataset folders in the following way:
```
./data
  amazon_baby_vgg19/
    original/
       images/
        0.jpg
        1.jpg
        ...
  amazon_boys_girls_alexnet/
    original/
      images/
        0.jpg
        1.jpg
        ...
```
**N.B.** The dataset folder structure requires the notation ```<dataset_name>_<cnn_name>```, even though the different dataset folders contain the exact same files. This is due to the fact that, when training and evaluating state-of-the-art visual-based recommender systems on these datasets through [Elliot](https://github.com/sisinflab/elliot), they need to be recognized as different datasets.

## Run and evaluate recommendations
To reproduce the results discussed in the paper, please follow these three steps:

1. Extract visual features from item images. You can refer to this GitHub [repository](https://github.com/sisinflab/Image-Feature-Extractor#extract-features).
2. Train and evaluate the visual-based recommenders through this [version](https://github.com/danielemalitesta/Elliot-Reproducible-VRSs) of [Elliot](https://github.com/sisinflab/elliot) (**TO BE MERGED INTO THE MAIN BRANCH SOON**).
3. Evaluate the *visual diversity* (**VisDiv**). Again, you can refer to this GitHub [repository](https://github.com/sisinflab/Image-Feature-Extractor#evaluate-visual-recommendations).

## Datasets

|       Dataset      |    ***k-cores***   | # Users   | # Products   |  # Feedbacks   |
| ------------------ | ------------------ | ------------------ | ------------------ | ------------------ |
|     Amazon Baby*     |      5 | 606 | 1,761 | 3,882  |
|    Amazon Boys & Girls*    |   5 | 600 | 2,760 | 3,910  |

\* https://jmcauley.ucsd.edu/data/amazon/

## Parameters for Image Feature Extractors

**Fully-connected layers**

|       CNN      |  Output Layer ([script](https://github.com/sisinflab/Image-Feature-Extractor/blob/main/src/classify_extract.py)) | Output Shape  | 
| ------------------ | ------------------ | ------------------ | 
|     [AlexNet](https://papers.nips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf)     | 5 | (1, 4096) |
|    [VGG19](https://arxiv.org/pdf/1409.1556.pdf)    | fc2 | (1, 4096) |
|    [ResNet50](https://arxiv.org/pdf/1512.03385.pdf) | avg_pool | (1, 2048) |

**Convolutional layers (e.g., ACF)**

|       CNN      |  Output Layer ([script](https://github.com/sisinflab/Image-Feature-Extractor/blob/main/src/classify_extract.py)) | Output Shape  | 
| ------------------ | ------------------ | ------------------ | 
|    [AlexNet](https://papers.nips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf)     | Not necessary | (36, 256) |
|    [VGG19](https://arxiv.org/pdf/1409.1556.pdf)    | block5_pool | (49, 512) |
|    [ResNet50](https://arxiv.org/pdf/1512.03385.pdf) | avg_pool | (49, 2048) |


## Visual Recommenders

|       Model      |    Paper  |
| ------------------ | ------------------ |
|     Visual Bayesian Personalized Ranking (VBPR)     | [He and McAuley](https://arxiv.org/pdf/1510.01784.pdf) |
|     Deep Style   | [Liu et al.](http://www.shuwu.name/sw/DeepStyle.pdf) |
|     Attentive Collaborative Filtering (ACF) | [Chen et al.](https://www.comp.nus.edu.sg/~xiangnan/papers/sigir17-AttentiveCF.pdf) | 
|     Visual Neural Personalized Ranking (VNPR) | [Niu et al.](https://people.engr.tamu.edu/caverlee/pubs/niu18wsdm.pdf) |

## Configuration Files
- Amazon Baby
  - [AlexNet](https://github.com/danielemalitesta/Elliot-Reproducible-VRSs/blob/master/config_files/baselines_amazon_baby_alexnet.yml)
  - [VGG19](https://github.com/danielemalitesta/Elliot-Reproducible-VRSs/blob/master/config_files/baselines_amazon_baby_vgg19.yml)
  - [ResNet50](https://github.com/danielemalitesta/Elliot-Reproducible-VRSs/blob/master/config_files/baselines_amazon_baby_resnet50.yml)
- Amazon Boys & Girls
  - [AlexNet](https://github.com/danielemalitesta/Elliot-Reproducible-VRSs/blob/master/config_files/baselines_amazon_boys_girls_alexnet.yml)
  - [VGG19](https://github.com/danielemalitesta/Elliot-Reproducible-VRSs/blob/master/config_files/baselines_amazon_boys_girls_vgg19.yml)
  - [ResNet50](https://github.com/danielemalitesta/Elliot-Reproducible-VRSs/blob/master/config_files/baselines_amazon_boys_girls_resnet50.yml) 

## The Authors
* Yashar Deldjoo (yashar.deldjoo@poliba.it)
* Tommaso Di Noia (tommaso.dinoia@poliba.it)
* Daniele Malitesta* (daniele.malitesta@poliba.it)
* Felice Antonio Merra (felice.merra@poliba.it)

\**corresponding author*
