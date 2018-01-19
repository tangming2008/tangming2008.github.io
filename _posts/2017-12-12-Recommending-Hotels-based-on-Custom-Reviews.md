---
published: true
categories: [Classification]
title: Applying Deep Learning to Detect Blurry Images
---
[comment]: <comment out>

## Abstract
This blog is based on my final passion project at Metis/Chicago. In this project, I applied CNN (convolutional neural network) to train the model for classification analysis: to predict whether an image is blurry or not.

## Introduction
Have you got any notice and significant storage in the phone ?


<center><img src="/files/fig/proj5/1.png" width="700"></center>
<p><center>Figure 1. Storage full in the phone?.</center></p>


If your answer is yes, or you want to prevent this from happen in the future, then you may want to continue looking.

Such topic & blog was inspired by my personal experience when using the cell-phone. I enjoyed testing new features, playing with fun apps, and taking nice images. However, after some time, you may get an alert like this and need to free some space. We may find that photos would take a significant amount of storage (see screenshot below) and only a few high-quality or clear images are worth keeping in the phone. The most efficient way to get around this is to buy a new phone with a larger storage. Besides, we can delete blurry files.


<center><img src="/files/fig/proj5/2.png" width="700"></center>
<p><center>Figure 2. Storage distribution in the phone.</center></p>


To solve this, we can manually delete some files. For examples of following two images of my cat, we could manually check them, and keep the clear one and delete the blurry one. However, this manual check is time-consuming. To solve this issue, I applied deep learning for image analysis, and the objective of this work to find blurry images automatically.


<center><img src="/files/fig/proj5/3.png" width="700"></center>
<p><center>Figure 3. My lovely cat.</center></p>


## Analysis Approach
### OpenCV
Before using deep learning, I applied OpenCV, an image analysis package as a baseline prediction. In this project, I have 1000 clear images and 1000 blurry images with labels, downloaded from a research database. I import these images and estimate the score with OpenCV, and separate result with a threshold of 100. All images with a score higher than 100 are predicted as clear, otherwise blurry. Overall, we could get an accuracy of 85% for 2000 images.


<center><img src="/files/fig/proj5/4.png" width="700"></center>
<p><center>Figure 4. XXX.</center></p>

### CNN
Then I spent most time on the prediction with deep learning. // First, I applied Pillow and OpenCV to process the images to a uniform size of 200 x 200 pixels. Then, I converted the image to a matrix with 3 color channels, including red, green and blue. After these steps, I fed the image into the CNN for feature learning and classification analysis, which were implemented in TensorFlow and the wrapper of Keras. This is a classification problem and the output result is the label for each image, which is either clear or blurry.

<center><img src="/files/fig/proj5/5.png" width="700"></center>
<p><center>Figure 5. XXX.</center></p>


## Results & Discussion
### Trained CNN model
Here is an evaluation image of the nice bay with beautiful boats, the model correctly predicted that the left one is clear and right one is blurry, which makes sense that, in this left image, we could see the boats inside the bay and clear boundaries of the mountain in the background.
The trained model has an accuracy of 95%, which outperformed the prediction with OpenCV.


<center><img src="/files/fig/proj5/6.png" width="700"></center>
<p><center>Figure 6. XXX.</center></p>


### Blurry algorithms
Besides the simple cut-off between clear and blurry images, I was wondering whether the neural network model can distinguish the images blurred with various methods. To test this, 1000 clear images were artificially blurred by various approaches, such as Gaussian, Motion and Minfilter. For example, the motion blur would randomly shift the pixels to left or right side. Besides, I also include a research database with 1000 images with focused center and blurry background. This technique is also called out-of-focus, which is used by professional photographer. After training, the neural network is able to have a 90% accuracy when classifying images based on blurring algorithms.


<center><img src="/files/fig/proj5/7.png" width="700"></center>
<p><center>Figure 7. XXX.</center></p>


### Further Applications
The main idea of this project is image classification, and here are two examples of possible application. First, we could apply this technology to examine images of crashed cars, so that we could rate the damage, estimate auto-part supplies and total repair cost. Besides, we could also import the images of pre-portioned ingredients and predict the total calories, which might be helpful for the customers.

<center><img src="/files/fig/proj5/8.png" width="700"></center>
<p><center>Figure 8. XXX.</center></p>

## Conclusions
* It is feasible to use machine learning algorithm to predict whether a team is top 4 based on the goals scored and goals lost.
* Although soccer is a team sports, with 11 players, an outstanding individual would have a significant effect on the team, even the league.


## Image credits
* [Phone storage alert](https://www.anysoftwaretools.com/fix-iphone-storage-almost-full/)
