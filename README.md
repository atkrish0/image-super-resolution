# Image-Super-Resolution

The goal of super-resolution (SR) is to recover a high resolution image from a low resolution input.

To accomplish this goal, we will be deploying the super-resolution convolution neural network (SRCNN) using Keras.  This network was published in the paper, "Image Super-Resolution Using Deep Convolutional Networks" by Chao Dong, et al. in 2014.  

Original Paper: [Learning a Deep Convolutional Network for Image Super-Resolution](https://arxiv.org/abs/1501.00092)

<p align="center">
  <img src="https://github.com/MarkPrecursor/SRCNN-keras/blob/master/SRCNN.png" width="800"/>
</p>

As the title suggests, the SRCNN is a deep convolutional neural network that learns end-to-end mapping of low resolution to high resolution images.  As a result, we can use it to improve the image quality of low resolution images.  To evaluate the performance of this network, three image quality metrics are used, namely, Peak Signal to Noise Ratio (PSNR), Mean Squared Error (MSE), and the Structural Similarity (SSIM) Index.  

Furthermore, OpenCV is used to pre and post process our images. The images will frequently be converted back and forth between the RGB, BGR, and YCrCb color spaces. This is necessary because the SRCNN network was trained on the luminance (Y) channel in the YCrCb color space.  

Objectives:

* Use the PSNR, MSE, and SSIM image quality metrics
* Process images using OpenCV
* Convert between the RGB, BGR, and YCrCb color spaces
* Build Deep Neural Networks in Keras
* Deploy and evaluate the SRCNN network
