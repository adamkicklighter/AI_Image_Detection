# AI_Image_Detection
Applying Computer Vision to Detect Authentic Photographs from Generative AI

## Hypothesis

AI diffusion models will leave artifactual noise undetectable to the human eye but detectable to machine learning algoritms, enabling detection from authentic images.

## Findings

Both "White Box" models and "Black Box" models are able to distinguish authentic photographs from AI images. However, these approaches fail to generalize well to either authentic photographs or AI generated images that are out of the distribution of the training data. These findings counter those of Bird and Lofti, who demonstrated that convolutional neural networks can detect the provenance of images. While their work demonstrates that a CNN *can* correctly label an AI generated image as being produced by a diffusion model, their model labels *all* images not found in the "REAL" dataset as Fake, including other authentic photographs that have different distributions from the CIFAR-10 data. This explains their network's ability to label an AI generated image as "FAKE" - it has overtrained on the specific features in their "REAL" dataset.

## Contributions

My work evaluated whether changes to the CNN architecture would help a model better generalize to out of distribution images. All of the CNN designs and methods tried were unable to overcome these limitations, including changes to data augmentation, network regularization, and activation functions. In the case of the "White Box" model, while pixel intensity was a good discriminator for images within the training data distribution, 

## Dataset

The description below and the CIFAKE image dataset are sourced from and available in the repository here: https://github.com/2spi/ai-v-real

The dataset used for training and evaluation consists of two categories of images:

<b>REAL images:</b> These images are sourced from the Krizhevsky & Hinton's CIFAR-10 dataset, which is a widely-used benchmark dataset for image classification tasks.<br>

<b>FAKE images:</b> These images were generated using the equivalent of CIFAR-10 with Stable Diffusion version 1.4.

The combined dataset provides a diverse set of real and AI-generated images for training the classification model.

## References

Bird, J.J., Lotfi, A. (2023). CIFAKE: Image Classification and Explainable Identification of AI-Generated Synthetic Images. arXiv preprint arXiv:2303.14126.
