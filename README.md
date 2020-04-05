# Alphanumeric-OCR
Create a alphanumeric OCR with tensorflow deep learning

## Objective
This is an attempt to mix MNIST digit dataset and A-Z alphabeet dataset from kaggle and create a alphanumeric dataset.

## Data Prepration
* Collect both datasets in code and shuffle A-Z dataset as it is in order 
  * A-Z from Kaggle - Add 10 to all the labels, i.e. from 11-36
  * MNIST - Keep labels as is i.e. from 1-10 (label for image for `0` is 10)
* Divide both datasets in train and test models
* Combine both train and both test datasets

## Models
* First Model: Sequential
  * Test Accuracy: 83.5%
  * Test Loss: 2.79
  * Epochs: 10
* Second Model: Sequential with MaxPooling
  * Epochs: 10
  * Test Accuracy: 82.8%
  * Test Loss: 2.82
* Third Model: Sequential with Conv1D
  * Epoch: 10
  * Test Accuracy: 86.8%
  * Test Loss: 2.76
* Keras Model: Conv1D, Flatten, 2 * Dense
  * Epoch: 5
  * Test Accuracy: 98.2%
  * Test Loss: 0.087
  
## Save Model
Tried many approaches but was not able to load, under section `Save the Learnings` you will find lot of errors and stack traces, but since this is lesson learned for me I am not removing those failed approaches.
Following approach worked for me:
* Used `save` method of `keras` model
* Used `load_path` method from `tf.keras.models`
* Compared both models, summary was different, as input shape and layers were different
* When you scroll down to the bottom, you will find solution to above problem
* Shapes and layers were given explicitly after model was loaded using `load_model`
