# MelanomaDetectionAssignment
## Problem statement: 
  To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.

## Dataset:
The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant.


The data set contains the following diseases:
 - Actinic keratosis
 - Basal cell carcinoma
 - Dermatofibroma
 - Melanoma
 - Nevus
 - Pigmented benign keratosis
 - Seborrheic keratosis
 - Squamous cell carcinoma
 - Vascular lesion

## CNN Architecture:
Custom CNN model is built to address cancer detection problem. Details of the model, and snapshot are as follows.
1. Rescaling Layer: To rescale the input images of [0..255] range to [0..1]
2. 3 Convolution +Max Pooling layers (2D): (with 3x3 filters), and increasing the number of filters for each convolution layer
  a. **Convolutional Layer** - convolution converts all the pixels in its receptive field into a single value. For example, if you would apply a convolution to an image, you will be decreasing the image size as well as bringing all the information in the field together into a single pixel.
  b. **Pooling Layer** - Pooling layers are used to reduce the dimensions of the feature maps. 
3. **Dropout Layer**:The Dropout layer randomly sets input units to 0, which helps in avoiding overfitting.
     a. Dropout is set as 40% after convolution + Maxpool before flatting input.
     b. Before the final activation, dropout is set to 25%
4. **Flatten Layer**: TO flatten inputs to 1D array to feed the input to NN
5. **Dense Layer**: Dense Layer with 128 Nuerons. Dense layer is FC (Fully Connected),  which mean each neuron receives input from all neurons of its previous layer
6. **Activation Function**:
   a. ReLU (For intermediate Layers):The rectified linear activation function or ReLU is a linear function that will output the input directly if it is positive, otherwise, it will output zero. As ReLU overcomes the vanishing gradient problem, allowing models to learn faster and perform better, it is being used for intermediate layers.
   b. softmax(for output layer):The softmax function is used as the activation function in the output layer of for multiclass classification problems. As in current case, there are 9 possible cases of output softmax is used at output layer.