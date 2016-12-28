---
layout: single
title: Catching Fish with Neural Nets
author_profile: true
read_time: true
comments: true
share: true
---

Illegal fishing poses a major threat to our marine ecosystems and global seafood supplies. It is reported that as much as 33% of the total fish caught in the world happens through unreported and illegal means. The Nature Conservancy, a charitable environmental organization, is seeking to installing cameras on fisherman's boats to monitor their activities. However, the amount of raw data produced by these cameras is enormous making it cumbersome and expensive to monitor manually. In order to combat this problem, The Nature Conservancy created a competition on Kaggle where they seek help to automate the monitoring process. I found this competition particularly interesting because the work done in this competition can make a true difference in the conservation of the environment. Therefore, I decided to participate in this competition.

## The Data

The data provided in the competition included 3777 photos of fisherman catching various types of fish such as Albacore Tuna, sharks, Moonfish, Dolphinfish, and other species. There are 7 classes of fish and another class where there would be no fish in the picture. The following image shows some of the classes of fish in the data.

![alt text]({{ site.baseurl }}/images/fish_data.PNG)

## Methodology

My goal is to use machine learning and computer vision to classify which fish species is caught in an image. There are many techniques in computer vision that I could've used to tackle this problem. I decided to use deep learning mainly because all the major recent breakthroughs in computer vision have been due to the use of convolutional neural networks (CNNs). CNNs are great at finding patterns and using them to classify images which makes it perfect for this competition. Neural networks are notoriously known for requiring a gigantic amount of data that makes it extremely difficult for individuals to collect. The amount of data needed can only be achieved by companies that have access to big data such as Google and Amazon. My data set of 3777 images isn't nearly enough to train a neural network from scratch even with image augmentation. Therefore, I used a method called transfer learning which leverages a pretrained CNN to classify my images. Google has released several pretrained CNNs such as VGG-16 and InceptionV3 which have different architectures and weights. I used transfer learning because it took siginificantly less time to train the model and I didn't need as many training images.

A CNN is normally made up of a few layers. The procedure to achieve transfer learning follows these steps:

1. Build the CNN using the same architecture and parameters as the pretrained CNN
2. Load the weights of the pretrained CNN
3. Freeze the CNN
4. Delete the final layer of the CNN
5. Rebuild the final layer of the CNN to classify your images
6. Feed your dataset into the CNN

I spent most of my time experimenting with the parameters on step 6. There are multiple optimizers that could be used to classify my images such as Stochastic Gradient Descent (SGD), RMSprop, Adagrad, Adadelta, and many more. In each of these optimizers, I could tune many different parameters such as the learning rate, momentum, learning decay, and many more. I achieved my best results when I used RMSprop with a learning rate of 0.0001 on the InceptionV3 model which gave me a 95% validation accuracy and a loss of 0.99. My best results from the VGG-16 model was a 90% validation accuracy and a loss of 1.5. The VGG-16 model still performed fairly well, but the InceptionV3 model had a higher accuracy and a lower loss. The following slide visualizes my results. It compares the InceptionV3 model with the baseline model which predicts the most frequent class for every image. 

![alt text]({{ site.baseurl }}/images/fish_model.PNG)

## Future Work

My results from using the raw data with augmentation are exceptional. However, there are improvements that can be made. The following slide illustrates my next steps to improve my results.

![alt text]({{ site.baseurl }}/images/future_work_fish.PNG)

Notice in the top left image that the fish only takes up a tiny part of the image. This part of the image is what we need in order to accurately classify the fish. Thus, everything surrounding the fish such as the boat, fisherman, and ocean are just random noise that we don't care about. In the future, I would like to:

1. Train a CNN to detect where the fish is in the image
2. Crop out everything surrounding the fish
3. Feed the new refined image into my original model

## Final Thoughts

The implications of my results show that deep learning can make a true difference in the environment. By automating the monitoring process, millions of dollars can be saved and reallocated to the enforcement and management of conservation. 
