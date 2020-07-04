---
title: Deep Learning with OpenCV
tags:
  - open-cv
  - deep-learning
category: 'Deep Learning'
---

Deep learning with OpenCV using its inbuilt `dnn` module

## Introduction to `dnn` module

The [`dnn module`](https://github.com/opencv/opencv/tree/master/modules/dnn) of OpenCV was included in the main repository in v3.3.

With OpenCV 3.3 _or later_, we can utilize pre-trained networks with popular deep learning frameworks. The fact that they are _pre-trained_ implies that we don't need to spend many hours training the network - rather we can complete a forward pass and utilize the output to make a decision within our application.

<!--more-->

For more information about supported frameworks and networks, follow this [link](https://github.com/opencv/opencv/wiki/Deep-Learning-in-OpenCV)

## OpenCV deep learning functions and frameworks

Using OpenCV 3.3 we can load images from disk using the following functions inside `dnn`:

+ `cv2.dnn.blobFromImage`
+ `cv2.dnn.blobFromImages`

Use "read" methods to load serialized model from disk directly:

+ `cv2.dnn.readNetFromCaffe`
+ `cv2.dnn.readNetFromTensorFlow`
+ `cv2.dnn.readNetFromTorch`

Once we have loaded model from disk, the `.forward` method is used to forward-propogate our image and obtain the actual classification.

We'll take a look at how to load model and classify images using pre-trained model.

## Image classification

For this example, we'll use:

+ Caffe framework
+ GoogleLeNet _or [Inception](https://arxiv.org/abs/1409.4842)_ (pre-trained on ImageNet) network

To learn more about how we load a pre-trained Caffe model and use it to classify an image using OpenCV, follow [this]({{ site.baseurl }}{% link _posts/2020-06-13-image-classification-opencv.md %}).

## Object Detection

[Image classification](#image-classification){: .scrolly} just classify an image into one of ImageNet's 1000 separate class labels, but it could not tell us where an object resides in image.
In order to obtain the bounding box (x, y) co-ordinates for an object in an image, we need to apply **Object Detection**.

When it comes to deep learning based object detection, there are following methods primarily:

+ [Faster R-CNNs](https://arxiv.org/abs/1506.01497) (Girshick et al., 2015)
+ [You Only Look Once (YOLO)](https://arxiv.org/abs/1506.02640) (Redmon and Farhadi, 2015)
+ [Single Shot Detectors (SSDs)](https://arxiv.org/abs/1512.02325) (Liu et al., 2015)

### Faster R-CNNs

This technique can be difficult to understand, hard to implement, and challenging to train. The algorithm is quite slow, on the order of 7 FPS.

### YOLO

This technique is faster, capable of processing 40-90 FPS on a Titan X GPU. The super fast variant of YOLO can even get upto 155 FPS.
But the problem with YOLO is the _accuracy_, which is not very good.

### SSDs

This technique is balance between above twos. The algorithm is straight forward to understand, implement. It gives comparable faster FPS throughput at 22-46 FPS depending on which variant of the network we use. SSDs also tend to be more accurate than YOLO.

### MobileNets: Efficient (deep) neural networks

When building object detection networks, we normally use an existing network architecture, such as VGG or ResNet, and then use it inside the object detection pipeline. But the problem is that these networks can be very large in the order of 200-500 MB.  
These networks are unsuitable for resource constrained devices due to their sheer size and resulting number of computations.

But, we can use [MobileNets](https://arxiv.org/abs/1704.04861) (Howard et al., 2017), another paper by Google researchers. These networks are designed for resource constrained devices such as smartphones, IOT devices, etc. These networks use _depthwise separable convolution_ compared to traditional CNNs.  
The general idea behind depthwise separable convolution is to split convolution into 2 stages:

+ A 3x3 depthwise convolution
+ Followed by a 1x1 pointwise convolution

This allows us to reduce the number of parameters in out network.

But we loose accuracy in MobileNets.

To overcome the shortcoming, we combine MobileNets and SSDs for fast, efficient deep learning based object detection.

For this example, we'll use:

+ Caffe framework [original TensorFlow implementation](https://github.com/Zehaos/MobileNet). Caffe version trained by [_chuanqi305_](https://github.com/chuanqi305/MobileNet-SSD)
+ MobileNet SSD pre-trained model

The MobileNet SSD was first trained on the [COCO dataset](http://cocodataset.org/) (Common Objects in COntext) and then fine-tuned on PASCAL VOC reaching 72.7% mAP (mean Average Precision).

We can therefore detect 20 objects in images (+1 for the background class), including _airplanes_, _bicycles_, _birds_, _boats_, _bottles_, _buses_, _cars_, _cats_, _chairs_, _cows_, _dining tables_, _dogs_, _horses_, _motorbikes_, _people_, _potted plants_, _sheep_, _sofas_, _trains_, and _tv monitors_.
