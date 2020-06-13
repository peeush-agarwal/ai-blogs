---
title: Image classification using OpenCV
images:
  - url: assets/images/img_classification/eagle_result.png
    caption: Eagle result
  - url: assets/images/img_classification/bottle_result.png
    caption: Bottle result
tags:
  - open-cv
  - deep-learning
  - image-classification
---

In [Deep Learning with OpenCV]({{ site.baseurl }}{% link _posts/2020-06-01-deep-learning-with-opencv.md %}) blog, we talked about using pre-trained model provided in OpenCV 3.3 to classify images or even videos(real-time webcams, video files, etc.). In this blog, we'll deep-dive into image classification using OpenCV and GoogleLeNet (pre-trained on ImageNet) using the Caffe framework.

<!--more-->

The GoogleLeNet architecture (now known as "Inception" after the novel micro-architecture) was introduced by Szegedy et al. in their 2014 paper. [Going deeper with convolutions](https://arxiv.org/abs/1409.4842)

## Import required libraries

{% highlight python linenos %}
# import required libraries
import cv2
import numpy as np
import argparse
import time
{% endhighlight %}

Above **Line 2-5** imports required packages for this tutorial.

+ `cv2`: OpenCV library
+ `numpy`: Python numerical computation library
+ `argparse`: Required to parse command line arguments
+ `time`: Use to track time spent on specific code

## Parse command line arguments

{% highlight python linenos %}
# Parse command-line arguments
ap = argparse.ArgumentParser()
ap.add_argument('-i', '--image', help="Path to input image", required=True)
ap.add_argument('-p', '--prototxt', help="Path to Caffe 'deploy' prototxt file", required=True)
ap.add_argument('-m', '--model', help="Path to Caffe pre-trained model", required=True)
ap.add_argument('-l', '--labels', help="Path to ImageNet labels (i.e. syn-sets)")
args = vars(ap.parse_args())
{% endhighlight %}

Above **Line 3-6** parses required command line arguments:

+ `image`: Path to image for classification
+ `prototxt`: Path to Caffe "deploy" prototxt file
+ `model`: Path to Caffe pre-trained model's weights
+ `labels`: Path to ImageNet labels

## Load input image and class labels

{% highlight python linenos %}
# Read image from argument
image = cv2.imread(args["image"])

# Load class data for ImageNet
rows = open(args["labels"]).read().strip().split("\n")
classes = [r[r.find(" ") + 1:].split(",")[0] for r in rows]
{% endhighlight %}

**Line 2** loads image from path to memory

**Line 5-6** loads class labels for ImageNet into memory. `rows` will contain rows like this:

{% highlight plaintext %}
n01440764 tench, Tinca tinca
n01443537 goldfish, Carassius auratus
n01484850 great white shark, white shark, man-eater, man-eating shark, Carcharodon carcharias
n01491361 tiger shark, Galeocerdo cuvieri
n01494475 hammerhead, hammerhead shark
n01496331 electric ray, crampfish, numbfish, torpedo
n01498041 stingray
n01514668 cock
n01514859 hen
n01518878 ostrich, Struthio camelus
{% endhighlight %}

And, `classes` contains following classes processed from above raw rows:

{% highlight plaintext %}
tench
goldfish
great white shark
tiger shark
hammerhead
electric ray
stingray
cock
hen
ostrich
{% endhighlight %}

## Using `dnn` module from OpenCV library

### Load `blob` from image in memory

{% highlight python linenos %}
# Our CNN requires fixed spatial dimensions for our input image(s), 
# so we need to ensure it is resized to 224x224 pixels while performing
# mean subtraction (104, 117, 123) to normalize the input; after executing 
# this command, our "blob" now has the shape: (1, 3, 224, 224)
blob = cv2.dnn.blobFromImage(image, 1, (224, 224), mean=(104, 117, 123))
{% endhighlight %}

### Load `model` from disk using `args`

{% highlight python linenos %}
# Load serialized model from disk
print("[INFO] Loading model from disk")
net = cv2.dnn.readNetFromCaffe(args["prototxt"], args["model"])
{% endhighlight %}

### Make a `forward` pass with image blob into model

{% highlight python linenos %}
# Forward propagate image through the network
net.setInput(blob)
start = time.time()
preds = net.forward()
end = time.time()
print("[INFO] Classification took {:.5} seconds".format(end - start))
{% endhighlight %}

In **Line 2**, we set the input to be passed in model and in **Line 4**, we make a forward pass through the network.

### Fetch top-5 predictions

{% highlight python linenos %}
# Sort the indexes of the probabilities in descending order (higher probability first) and grab the top-5 predictions
idxs = np.argsort(preds[0])[::-1][:5]
{% endhighlight %}

Above **Line 2** will give us top-5 predictions out of all predictions from the model.

### Display predictions onto the input image using OpenCV

{% highlight python linenos %}
# Display top prediction
for (i, idx) in enumerate(idxs):
    # draw the top prediction on the input image
    if i == 0:
        text = "Label: {}, {:.2f}".format(classes[idx], preds[0][idx]*100)
        cv2.putText(image, text, (5, 25), cv2.FONT_HERSHEY_SIMPLEX, 0.7, (0, 0, 255), 2)

    # display the predicted label + associated probability to the console
    print("[INFO] {}.label: {}, probability: {:.5}".format(i+1, classes[idx], preds[0][idx]))

cv2.imshow("Image", image)
cv2.waitKey(0)
{% endhighlight %}

Above **Lines** will take top prediction and then draw text on the input image using OpenCV's `imshow`.

## Run python script to classify any image

{% highlight console linenos %}
python image_classification.py --image {Path to image} --prototxt {Path to .prototxt} -m {Path to .caffemodel} -l {Patht to synset_words.txt}
{% endhighlight %}

### Results

<div class="card-group">
    {% for img in page.images %}
    <div class="card">
        <div class="card-header">
            <small class="text-muted">{{ img.caption }}</small>
        </div>
        <img src="{{ site.baseurl }}/{{ img.url }}" class="card-img-top" alt="{{ img.caption }}">
    </div>
    {% endfor %}
</div>

## Github repo link

Find the complete Python script in [Github repo]({{ site.github.url }}/OpenCV-Tutorials/blob/master/DeepLearning/image_classification.py)
