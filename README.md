# Semantic Segmentation

### Overview

This project contain an implementation of a Fully Convolutional Network for semantic segmentation of a road in images
Kitti data set was used for network training

### Model architecture

The network based on a pretrained VGG-16 model. The model was changed in the following way:
added 1x1 convolution of layer 7 output (tf.layers.conv2d), result of convolution upsampled (tf.layers.conv2d_transpose) and connected with 1x1 convolution of layer 4 (skip-connection),
resulted layer upsampled and connected with 1x1 convolution of layer 3, resulted layer upsampled again.

### Hyperparameters

Good performance with average loss of 0.022 was achieved with keep probability value of 0.5, 30 epochs and 0.0001 learning rate

### Results
[image1]: ./images/um_000023.png
[image2]: ./images/um_000056.png
[image3]: ./images/um_000000.png
[image4]: ./images/um_000039.png
[image5]: ./images/um_000077.png

![alt text][image1]

![alt text][image2]

![alt text][image3]

![alt text][image4]

![alt text][image5]

### Setup
##### GPU
`main.py` will check to make sure you are using GPU - if you don't have a GPU on your system, you can use AWS or another cloud computing platform.
##### Frameworks and Packages
Make sure you have the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.
