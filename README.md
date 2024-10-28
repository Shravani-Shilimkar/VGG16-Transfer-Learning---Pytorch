# VGG16-Transfer-Learning---Pytorch

Using a Pretrained VGG16 to classify retinal damage from OCT Scans¶
Motivation and Context
Transfer learning turns out to be useful when dealing with relatively small datasets; for examples medical images, which are harder to obtain in large numbers than other datasets. Instead of training a deep neural network from scratch, which would require a significant amount of data, power and time, it's often convenient to use a pretrained model and just finetune its performance to simplify and speed up the process.

If you are new to convolutional neural networks (CNNs) be sure to check out the wikipedia page on CNNs for a more detailed description

In short, convolutional networks are used on (but not only) images instead of fully-connected feedforward networks because they would require a very high number of neurons - i.e. at least one per pixel in the input layer - and that would make them inconvenient.

We can identify two main blocks inside of a typical CNN:

Feature extraction
Classification
The feature extraction is made of a series of convolutional and pooling layers which extract features from the image, increasing in complexity in each layer (i.e. from simpler features in the first layers as points, to more complex ones in the last layers like edges and shapes; see more at Link #1 and Link #2).

These features are then fed to a fully connected network (classifier), which learns to classify them.

Read more about CNNs at http://cs231n.github.io/convolutional-networks/

So, what we'll do here is using a model (VGG-16) which is already capable of extracting features from an image and train its fully connected network in order to classify different types of retinal damage instead of objects.

The model we'll use is a VGG-16- convolutional network, trained on ImageNet dataset.

This work will use PyTorch as deep learning framework and CUDA for GPU acceleration.

About Retinal OCT¶
Quoted from https://www.kaggle.com/paultimothymooney/kermany2018

Retinal optical coherence tomography (OCT) is an imaging technique used to capture high-resolution cross sections of the retinas of living patients. Approximately 30 million OCT scans are performed each year, and the analysis and interpretation of these images takes up a significant amount of time (Swanson and Fujimoto, 2017).


(A) (Far left) choroidal neovascularization (CNV) with neovascular membrane (white arrowheads) and associated subretinal fluid (arrows). (Middle left) Diabetic macular edema (DME) with retinal-thickening-associated intraretinal fluid (arrows). (Middle right) Multiple drusen (arrowheads) present in early AMD. (Far right) Normal retina with preserved foveal contour and absence of any retinal fluid/edema.
