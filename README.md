# A Study on the Relative Importance of Convolutional Neural Networks in Visually-Aware Recommender Systems

This is the official implementation repository of our paper ***A Study on the Relative Importance of Convolutional Neural Networks in Visually-Aware Recommender Systems*** (under review).

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
2. Train and evaluate the visual-based recommenders through [this fork](https://github.com/danielemalitesta/elliot_expl) of [Elliot](https://github.com/sisinflab/elliot) (**TO BE MERGED INTO THE MASTER BRANCH SOON**).
3. Evaluate the *visual diversity* (**VisDiv**). Again, you can refer to this GitHub [repository](https://github.com/sisinflab/Image-Feature-Extractor#evaluate-visual-recommendations).

## Datasets

|       Dataset      |    ***k-cores***   | # Users   | # Products   |  # Feedbacks   |
| ------------------ | ------------------ | ------------------ | ------------------ | ------------------ |
|     Amazon Baby*     |      5 | 606 | 1,761 | 3,882  |
|    Amazon Boys & Girls*    |   5 | 600 | 2,760 | 3,910  |

\* https://jmcauley.ucsd.edu/data/amazon/

## Parameters for Image Feature Extractors

|       Convolutional Neural Network      |    Output Layer   | Output Shape  | 
| ------------------ | ------------------ | ------------------ | 
|     [AlexNet](https://papers.nips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf)     | | |
|    [VGG19](https://arxiv.org/pdf/1409.1556.pdf)    | a | a |
|    [ResNet50](https://arxiv.org/pdf/1512.03385.pdf) | a | a |


## Visual Recommenders


## The Authors
* Yashar Deldjoo (yashar.deldjoo@poliba.it)
* Tommaso Di Noia (tommaso.dinoia@poliba.it)
* Daniele Malitesta (daniele.malitesta@poliba.it)
* Felice Antonio Merra (felice.merra@poliba.it)
