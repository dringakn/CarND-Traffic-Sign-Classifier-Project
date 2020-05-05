[Code]: https://github.com/dringakn/CarND-Traffic-Sign-Classifier-Project/blob/master/Traffic_Sign_Classifier.ipynb
[//]: # "Image References"
[image1]: ./examples/Distribution_Of_Classes_in_the_DataSet.png "Distribution Of Classes in the DataSet"
[image2]: ./examples/Distribution_Of_Taining_Testing_Validation_in_the_DataSet.png "Distribution Of Taining/Testing/Validation in the DataSet"
[image3]: ./examples/Example_Images.png "Example_Images"
[image4]: ./examples/Training.png "Training"
[image5]: ./examples/Test_Images.png "Test Images"
[image6]: ./examples/Perdicted_Class_Labels.png "Perdicted Class Labels"
[image7]: ./examples/Sample_Results.png "Sample Results"

## Traffic Sign Recognition Using Deep Learning

Overview
---
This project, uses Tensorflow, deep neural networks and convolutional neural networks, to classify road traffic signs. Training and validattion of a LeNet-5 model is performed, so that it can classify traffic sign images using the [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). There is a pickled dataset which contains training, validation and test data sets. Each image withing the data is of size 32x32x3. 

After the model is trained, it is tested on 32 unseen German traffic signs images that were found on the web. 


The Project
---
The implementation is done using python programming language. The ![code][Code] implementation consists of follwing steps:

* Loading of the data set
* Explore, summarize and visualize the data set
* Design, train and testing of LeNet-5 model architecture
* Use of the trained model to make predictions on new images
* Analyze the softmax probabilities of the new images

## Reflection

After the data file is loaded, the data set are analyzed to familarize with the data.
There are 43 types of traffic signs in the data. The following histogram figure shows the distributation of number of images in each class.

![][image1]

The distributation of images in training/testing/validation sets are as follows:

![][image2]

Here are some of the sample images from the training dataset

![][image3]

The training is performed using following parameters
`EPOCHS = 150`
`BATCH_SIZE = 256`
`rate = 0.0005`

The structure of the neural network is as follows:

* Layer-1: Convolutional. Input = 32x32x3. Output = 28x28x6
* Layer-1 Pooling: Input = 28x28x6. Output = 14x14x6
* Layer-2: Convolutional. Output = 10x10x16
* Layer-2 Pooling: Input = 10x10x16. Output = 5x5x16
* Flatten. Input: = 5x5x16. Output = 400
* Layer-3: Fully Connected. Input = 400. Output = 120
* Layer-4: Fully Connected. Input = 120. Output = 84
* Layer-5: Fully Connected. Input = 84. Output = 10

Here is the validation accuracy against the EPOCHS during the training:

![][image4]

Thirty-two images have been downloaded from internet to test the accuracy. Here are those images with the class labels:

![][image5]

The classifer is **71.88%** accurate in predicting traffic signs. Here are the predicted results.

![][image6]

The following figure shows the prediction probability for some of the sample images. The top five possible classes along with their probabilities are shown as the title.

![][image7]