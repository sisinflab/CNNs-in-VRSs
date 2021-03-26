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
 
 1. Extract visual features from item images. You can refer to this GitHub [repository](https://github.com/danielemalitesta/ExplainableFeatureExtractor).
 2. Train and evaluate the visual-based recommenders through [this extension](https://github.com/danielemalitesta/elliot_expl) of [Elliot](https://github.com/sisinflab/elliot), a Python framework for reproducible recommender systems.
 3. Evaluate the *visual diversity* (**VisDiv**). Again, you can refer to this GitHub [repository](https://github.com/danielemalitesta/ExplainableFeatureExtractor).
