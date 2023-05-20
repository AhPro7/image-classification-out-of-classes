# Image Classification Out-of-Classes

Hello there! Welcome to my "Image Classification Out-of-Classes" project. This repository focuses on the task of classifying lung images, specifically Chest X-Ray Images (Pneumonia) from Kaggle. You can find the dataset [here](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia).

## Project Overview

In this project, I aim to solve the image classification problem for lung images. I have designed and evaluated a classifier using the powerful Visionary Image Transformer (Vit). Additionally, I have explored two solutions for images that fall outside the designated classes.

## Getting Started

### 1. Solve imblance dataset
![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/014704d1-8316-49bd-a8a7-09c20e7e472f)

As I delve into this project, I encounter an imbalanced dataset. To address this issue, I have created a new dataset with an added class, which can be accessed [here](https://www.kaggle.com/datasets/ahmedhaytham/chest-xray-images-pneumonia-with-new-class). This new dataset introduces the classification problem of distinguishing between normal, bacterial, and viral lung images, expanding beyond the binary classification of normal and pneumonia cases. Before training the model, I augment the data

![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/b48d2fcb-bb88-4d83-80ba-1f347ca5ad26)

### 2. Classifier
For the classification task, I used the powerful Visionary Image Transformer (Vit) model. To ensure optimal performance, I implemented two different approaches using transfer learning techniques, as outlined in the book "Deep Learning for Vision Systems."

![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/51a59f2e-a7e8-431d-8f7e-ea4ee43edb44)

#### In the first model,
I created a new top layer to fine-tune the classification process. However, the results were not as promising as I had hoped. Undeterred, I decided to explore further.

![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/05ec5961-4159-43a2-990d-ad114905b65a)
![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/33918eb6-d364-4016-a50c-396daad7ce60)

#### The second model was a game-changer.
I adopted a selective approach by training only the last five layers of the Vit model. This strategic adjustment yielded significantly better results in terms of classification accuracy and performance.

![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/4930344d-d943-4486-83e1-5a562d890089)
![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/2fc328d5-6ace-4760-b023-caba7bd4c5a4)
![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/d78b2127-7816-4123-8f0c-68d6e9fb18a0)
![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/89e6b6dc-0874-4902-a02c-4b956c725433)
sure! needs improvments

### 3.Out of classes
In this project, I explore two methods for handling images that fall outside the designated classes. The first method I employed is based on cosine similarity.

### 3.1 cosine similiraty
To apply cosine similarity, I randomly selected 10 images from the dataset. I input these images into the model, excluding the top layer, to obtain the last vector that contains the extracted features. I then compared these feature vectors with each other to calculate the mean similarity threshold. <br/>

Next, when an input image is presented, I compare its feature vector with the previously obtained set of feature vectors. By calculating the mean similarity of the input image with the set of reference images, I can make a decision based on whether the mean similarity exceeds the threshold. This enables me to determine if the input image falls within one of the designated classes or if it is out of classes.<br/>

This approach allows for the identification of images that may not fit into the predefined classes. By leveraging cosine similarity and threshold comparisons, I can provide a mechanism for detecting and handling images that deviate from the expected classes.

![image](https://github.com/AhPro7/image-classification-out-of-classes/assets/39713678/51f8ee19-094d-4aec-96ac-a2974c9c00e7)
