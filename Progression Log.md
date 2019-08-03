## 1: Image Quality Metrics

A couple of functions are deined that can be used to calculate the PSNR, MSE, and SSIM. 
The structural similiarity (SSIM) index was imported directly from the scikit-image library.
However, we will have to define our own functions for the PSNR and MSE. 

Furthermore, we will wrap all three of these metrics into a single function that we can call later.

## 2: Preparing Images

The same images from the original SRCNN paper are used here as well.
The images can be downloaded from http://mmlab.ie.cuhk.edu.hk/projects/SRCNN.html.  

Now that we have some images, lower resolution versions of them are produced.
This is accomplished by resizing the images, both downwards and upwards, using OpenCV. 
There are several interpolation methods that can be used to resize images; bilinear interpolation is used in this case.  

Once the low resolution images are produced, they're saved in a new folder.

## 3: Testing Low Resolution Images

To ensure that our image quality metrics are being calculated correctly and that the images 
were effectively degraded, lets calculate the PSNR, MSE, and SSIM between our reference 
images and the degraded images that we just prepared. 

## 4: Building the SRCNN Model

Now that we have our low resolution images and with all image quality metrics functioning properly,
we can start building the SRCNN. In Keras, it's as simple as adding layers one after the other.
The achitecture and hyper parameters of the SRCNN network can be obtained from the cited publication.
