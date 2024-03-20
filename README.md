# spider_silk_codes
Contains code for the spider silk mechanical property prediction

Here we work on **5 mechanical properties**: 1. strain at break, 2. ultimate tensile strength, 3. toughness, 4. Young's modulus, and 5. supercontraction

Each property folder contains 3 important files and should be run in the same order as mentioned below:
1. **data_<property name>.ipynb**: this is to create and choose features from the L representation in the paper. This created three .npy file: a. **<property_name>.features** : contains the numeric value of each input feature to NN, b. **<property_name>.output** : contains the numeric value of output property, and c, **<property_name>.features_name** : : contains the name of each input feature to NN
   
3. **model_<property_name>.ipynb**: this file divides the input and output data into train, valid, and test datasets. It then trains models on train data and shows the loss on the valid data to check for overfitting. This file saves the model after every epoch in the folder named "model"
4. **test_<property_name>.ipynb**: this tests the model on the test data set. Mention the correct epoch number by changing the value of the variable "epoch_check" for using the appropriate saved model from the "model" folder.

**Mutation Study Protocol**
1. First run the model following the above protocols without any mutations and save the predicted property value for the test dataset (**p1**). 
2. Then in the **data_<property_name>_with_mutation.ipynb** file, in the last cell of the notebook input the value for *m_from* and *m_to*. 
3. Then run the **test_<property_name>_mutation.ipynb** file to get the predicted property value for the test dataset (**p2**).
4. Then quantify the effect of mutation by averaging the **100*(p1-p2)/p1**.
5. It is important to follow the above process with different **random_state** (atleast 5 different values) in cell 5 of the **model_<property_name>.ipynb**. Then average the percentage change over several different random_state.

**Note**: 
1. Before training any model, please make a folder named "model" to store the saved models during training.
2. Raw data contains the repetitive sequence of spidroins. These files are obtained from https://spider-silkome.org/



