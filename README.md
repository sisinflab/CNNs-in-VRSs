# A Study on the Relative Importance of Convolutional Neural Networks in Visually-Aware Recommender Systems

This is the repository of the official implementation of our paper *A Study on the Relative Importance of Convolutional Neural Networks in Visually-Aware Recommender Systems*.

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
 
 To reproduce the results discussed in the paper, please follow these three steps:
 
 1. Extract visual features from item images. You can refer to this GitHub [repository](https://github.com/sisinflab/Image-Feature-Extractor).
 2. Train and evaluate the visual-based recommenders through [this fork](https://github.com/danielemalitesta/elliot_expl) of [Elliot](https://github.com/sisinflab/elliot) (**TO BE MERGED INTO THE MASTER BRANCH SOON**).
 3. Evaluate the *visual diversity* (**VisDiv**). Again, you can refer to this GitHub [repository](https://github.com/sisinflab/Image-Feature-Extractor).

### The Authors
* Yashar Deldjoo (yashar.deldjoo@poliba.it)
* Tommaso Di Noia (tommaso.dinoia@poliba.it)
* Daniele Malitesta (daniele.malitesta@poliba.it)
* Felice Antonio Merra (felice.merra@poliba.it)
