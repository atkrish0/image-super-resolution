## 1: Image Quality Metrics

Functions are created to calculate the PSNR(Peak Signal-to-Noise Ratio) and the MSE(Mean Squared Error). 
The Structural Similiarity(SSIM) index was imported directly from the scikit-image library.

We then wrap all three metrics into a single function that can be called later.

## 2: Preparing Images

The same images from the original SRCNN paper are used here as well.
The images can be downloaded from http://mmlab.ie.cuhk.edu.hk/projects/SRCNN.html.  

Now that we have some images, lower resolution versions of them are produced.
This is accomplished by resizing the images, both downwards and upwards, using OpenCV. 
There are several interpolation methods that can be used to resize images; Bilinear Interpolation is used in this case.  

Once the low resolution images are produced, they're saved in a new folder.

## 3: Testing Low Resolution Images

To ensure that our image quality metrics are being calculated correctly and that the images 
were effectively degraded, we calculate the PSNR, MSE, and SSIM between our reference 
images and the degraded images that we just prepared. 

## 4: Building the SRCNN Model

Now that we have our low resolution images and with all image quality metrics functioning properly,
we can start building the SRCNN. In Keras, it's as simple as adding layers one after the other.
The achitecture and hyper parameters of the SRCNN network can be obtained from the cited publication.

## 5: Deploying the SRCNN Model

Now, we will need to define a couple of image processing functions. 
It will be necessary to preprocess the images extensively before using them as inputs to the network. 
This processing will include cropping and color space conversions.

To save us the time it takes to train a deep neural network, we will be loading pre-trained weights for the SRCNN. 
These weights can be found at the following GitHub page: https://github.com/MarkPrecursor/SRCNN-keras

Once we have tested our network, we can perform single-image super-resolution on all of our input images. 
Furthermore, after processing, we can calculate the PSNR, MSE, and SSIM on the images that we produce. 
