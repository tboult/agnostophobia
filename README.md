# Agnostophobia -- Deep Learning

## Introduction
This repository provides the code to incorporate center-loss in the keras based implementation of the paper titled "Reducing Network Agnostophobia" [1]. The original implementation of the paper is available [here](https://github.com/Vastlab/ObjectoSphere). This paper [1] is targeted on maximizing the entropy for unknow inputs and increasing their separation in feature space to that of the known classes. Authors proposed Entropic Open-Set and Objectosphere losses that train networks additionally on finite subset of known unknown samples in an effort to perform better on infinite set of unknown unknown examples i.e. not generating a big response for examples belonging to anything other than the targeted classes. Specifically, the objectosphere loss is targeted to generate large feature magnitudes and low entropy for known classes. Additionally, it penalizes the feature magnitude of samples from the known unknown set while maximizing entropy of such samples. This exercise/repository is focused on incorporating the center-loss [2] into existing framework of objectosphere loss with an intention of further increasing the discriminative power of deep features.


## Center-loss
Wen et al. [2] proposed center-loss to enhance the discriminative power of deep learned features specifically for face recognition application. The center loss learns a center for deep features for each class and penalizes the distances between the deep features and their respective class centers. The center-loss appears to be somewhat similar to k-means clustering where the center plays the role of cluster centroid and through learning inter-class dispension and intra-class compactness is achieved. Using MNIST dataset, authors demonstrate larger separation and compactness of deep features visualized in 2D. References [3] and [4] below provide the implementation of center-loss in PyTorch and TensorFlow Keras respectively, with [3] providing nice visualization for the training evolution on MNIST with and without using center-loss.

## Incorporating Center-loss
In this repository/exercise, I have borrowed the implementation of center-loss from [4] and have icorporated it in existing framework of objectosphere [1]. The incorporation of center-loss follows the same training setup where the command-line arguments can be used to choose between different loss functions, their respective weights and number of epochs.


## References
* [1]. A. Dhamija, M. Günther, and Terrance E. Boult: “Reducing Network Agnostophobia”, Neural Information Processing Systems (NeurIPS), 2018. [paper](https://papers.nips.cc/paper/8129-reducing-network-agnostophobia.pdf)
* [2]. Y. Wen, K. Zhang, Z. Li and Y. Qiao: “A Discriminative Feature Learning Approach for Deep Face Recognition”, ECCV, 2016. [paper](https://ydwen.github.io/papers/WenECCV16.pdf)
* [3] Center loss: [PyTorch Implementation](https://github.com/KaiyangZhou/pytorch-center-loss)
* [4] Center loss: [TensorFlow Keras Implementation](https://github.com/handongfeng/MNIST-center-loss)

