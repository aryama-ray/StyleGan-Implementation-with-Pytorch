
# End-to-end implementation of StyleGan architecture[Forward pass] based on StyleGan paper.



## Paper Reference:
Karras, T., Laine, S., & Aila, T. (2018). A Style-Based generator architecture for generative adversarial networks. arXiv (Cornell University). https://doi.org/10.48550/arxiv.1812.04948


## Dataset:

Flickr-Faces-HQ Dataset (FFHQ)
https://www.kaggle.com/datasets/arnaud58/flickrfaceshq-dataset-ffhq

# StyleGAN Pretrained Weights Image Generation

This repository contains a end-to-end implementation styleGan architecture using Pytorch framework in Jupyter notebook. Flickr-Faces-HQ Dataset (FFHQ) is used for training and pretrained model weight is being used from : https://github.com/kevinMEH/simple-stylegan/blob/main/README.md. 
The implementation focuses on loading a pretrained StyleGAN generator and sampling latent vectors to generate high-quality, realistic images.

## 🚀 Features

- ✅ Loads StyleGAN generator using PyTorch.
- ✅ Uses pre-trained weights for FFHQ dataset.- style-gan-nonsat-64
- ✅ Random latent vector generation.
- ✅ Image visualization using Matplotlib.

## 📐 Model Architecture: StyleGAN

The original **StyleGAN** architecture (proposed by NVIDIA in 2018) introduces a novel approach to generator design:

![style_gan_generator](https://github.com/user-attachments/assets/97b251d3-5195-4597-bba5-8ef4fae6eb58)

- **Mapping Network**:  
  - Maps an input latent vector (sampled from a normal distribution) to an intermediate latent space. This allows for disentangled and controllable image generation.
  - Consists of 8 multiple fully connected layers(Multi-layer perceptron).

- **Synthesis Network**:
  - Begins from a learned constant (not noise).
  - Generates the image using a series of convolutional layers.
  - Style modulation is applied at each layer using AdaIN (Adaptive Instance Normalization).
  - Each layer is modulated by the style vector w and stochastic noise. Noise is injected at every layer to add stochastic details (e.g., hair strands, skin pores).

- **Progressive Growing**:
  - Images are generated at increasing resolutions during training starting from 4 X 4, then progressive growing till 1024 X 1024
  - Helps improve training stability and image quality.





