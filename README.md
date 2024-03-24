What is a Convolutional Neural Network?
==
Convolutional neural networks are a fundamental architecture in artificial neural networks designed for processing and analyzing visual data, such as images and videos. CNN consists of multiple layers, which includes convolutional layers that apply filters to extract features from input images, pooling layers for down-sampling, and fully connected layers for classification. These networks learn hierarchical representations of visual data by capturing low-level features like edges and textures and gradually forming more complex patterns. CNNs have revolutionized computer vision by significantly improving accuracy in various applications and have become a cornerstone of modern artificial intelligence and machine learning for visual tasks.

 <img width="602" alt="Screen Shot 2024-03-24 at 12 55 25 PM" src="https://github.com/noderdev/Binary-Image-Classification-Using-CNN/assets/29915581/6ea1a968-2aa9-4a7d-be39-0535fe1ddd79">

Problem Statement
==
This problem consists of classifying images as food and non-food images. For the first part, we will build a Convolutional Neural Network to classify the images by training our classifier on the training data set provided and tune our model’s hyperparameters by evaluating the model on the validation data set. We will tune the model’s architecture parameters like the number of convolutional layers, number of filters per layer, filter sizes by considering various possible architectures. For the second part, we will use the pre trained VGG16 model and use a dense layer with logistic regression at the end for binary classification. We will analyze the results for the transfer learning with and without image augmentations. Finally, we will compare the three model based on evaluation data and conclude our findings.

Requirements
==
1. Make sure to have tensorflow 2.0 >= installed. Install sklearn, numpy , matplotlib.
2. If the tensor board does not display, run the notebook in firefox browser.
3. The code can be run with any binary classification image dataset (slight adjustment might be required)

Dataset
==
The dataset consists of food and non-food images for binary classification. To get the dataset, download from the link below:-
```sh
https://drive.google.com/file/d/1ee6ga_Ch2luZFRKHnC1xjferdnzLFEMH/view?usp=sharing
```

Model Architecture
==
Our selected model consists of 3 convolutional layers with 112, 48 and 80 filters in each respective hidden layer. The kernel size is 3 X 3. After each convolutional layer we have maxpooling and dense layer of logistic regression at end for binary classification.
The number of parameters are 106689 which are all trainable.

Classification Using Transfer Learning
==
We will use VGG16 pre-trained model for our binary classification problem. VGG16 was developed at the University of Stanford. We will use this pre trained model and add dense layer of logistic regression at the end for binary classification of images. The only part of the model that is trained is the Logistic regression layer. We will analyze the results with augmentation and without augmentation.</br> </br>
**The Model Architecture** </br>
In VGG16, there are thirteen convolutional layers, five Max Pooling layers, and three Dense layers which sum up to 21 layers, but it has only sixteen weight layers i.e., learnable parameters layer. Our mode has a total number of 14722881 parameters, the number of trainable parameters is 8193 and non-trainable parameters are 14714688.

<img width="468" alt="Screen Shot 2024-03-24 at 1 05 32 PM" src="https://github.com/noderdev/Binary-Image-Classification-Using-CNN/assets/29915581/212c42e5-2ae6-4f19-b766-940eaeaaec92">


Results
==
Here is the comparison of 3 models by evaluation of the accuracy and f1 score on test dataset and select the best model. I have plotted the graph of test data accuracy and f1 score for each model. The following are the results: -

<img width="450" alt="Screen Shot 2024-03-24 at 1 01 47 PM" src="https://github.com/noderdev/Binary-Image-Classification-Using-CNN/assets/29915581/e289e4a4-684d-448a-862d-ab227d38e3b8">


We were able to achieve a high accuracy of 94% and an f1 score of 0.939 when we used transfer learning (VGG16) with augmentation. Similar results were achieved without augmentation, but augmentation improved the generalization of the model
