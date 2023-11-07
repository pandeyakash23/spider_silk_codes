# spider_silk_codes
Contains code for the spider silk mechanical property prediction

Here we work on 5 mechanical properties: 1. strain at break, 2. ultimate tensile strength, 3. toughness, 4. Youngs modulus, and 5. supercontraction

Each property folder contain 3 important files and should be run in the same order as mentioned below:
1. data_<property name>.ipynb: this is to create and choose features from the L representation in the paper. This created three .npy file: a. <property_name>.features, b. <property_name>.output, and c, <property_name>.features_name
2. model_<property_name>.ipynb: this file divides the input and output data into train, valid, and test dataset. It then trains models on train data and shows the loss on the valid data to check for the overfitting. This file saves the model after very epoch in folder named "model"
3. test_<property_name>.ipynb: this tests the model on the test data set. Mention the correct epoch number by changing the value of the variable "epoch_check" for using an appropriate saved models from the "model" folder.

