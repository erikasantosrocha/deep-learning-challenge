# Deep Learning Challenge

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. Use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Data Attributes (34,000 entries)
* `EIN` and `NAME`—Identification columns
* `APPLICATION_TYPE`—Alphabet Soup application type
* `AFFILIATION`—Affiliated sector of industry
* `CLASSIFICATION`—Government organization classification
* `USE_CASE`—Use case for funding
* `ORGANIZATION`—Organization type
* `STATUS`—Active status
* `INCOME_AMT`—Income classification
* `SPECIAL_CONSIDERATIONS`—Special considerations for application
* `ASK_AMT`—Funding amount requested
* `IS_SUCCESSFUL`—Was the money used effectively

## Instructions

### Preprocess the Data

1. Use pd.get_dummies() to encode categorical variables.
2. Splite the data into training and testing dataset with train_test_split function.
3. Scale the training and testing features datasets by creating a StandardScaler instance, fitting it to the training data, then using the transform function.

### Compile, Train, and Evaluate the Model

1. Create a neural network model by assigning the number of input features and nodes for each layer using TensorFlow and Keras.
2. Create the hidden and output layers and choose an appropriate activation function.
3. Evaluate the model using the test data to determine the loss and accuracy.
4. Save and export your results to an HDF5 file: `AlphabetSoupCharity.h5`

### Optimize the Model

1. Optimize the model to achieve a target predictive accuracy higher than 75%.
2. Save and export your results to an HDF5 file: `AlphabetSoupCharity_Optimization.h5`.

## Report

Using bulleted lists and images to support your answers, address the following questions:

### Data Preprocessing
* What variable(s) are the target(s) for your model?
    * `IS_SUCCESSFUL`—Was the money used effectively
* What variable(s) are the features for your model?
    * `APPLICATION_TYPE`—Alphabet Soup application type
    * `AFFILIATION`—Affiliated sector of industry
    * `CLASSIFICATION`—Government organization classification
    * `USE_CASE`—Use case for funding
    * `ORGANIZATION`—Organization type
    * `STATUS`—Active status
    * `INCOME_AMT`—Income classification
    * `SPECIAL_CONSIDERATIONS`—Special considerations for application
    * `ASK_AMT`—Funding amount requested
* What variable(s) should be removed from the input data because they are neither targets nor features?
    * `EIN` and `NAME`—Identification columns

### Compiling, Training, and Evaluating the Model
* How many neurons, layers, and activation functions did you select for your neural network model, and why?
    * Hidden layer 1: 8 neurons, 'relu' activation function
    * Hidden layer 2: 6 neurons, 'relu' activation function
    * Output layer:  1 neurons, 'sigmoid' activation function
* Were you able to achieve the target model performance?
    * No, since the accuracy is 0.739 and the loss 0.542.
* What steps did you take in your attempts to increase model performance?
    * To enhance the model performance, changes were made to the cutoff values of certain variables, increased the number of nodes in the layers, and by adding a third hidden layer.

### Summary
Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.

* The initial neural network model had an accuracy of 0.739 and a loss of 0.542, while using two hidden layers.
* The optimization of the model was done by the following changes:
    - The `name` variable was cutoff for counts < 5
    - The `classification` variable was cutoff for counts < 1200
    - A third hidden layer was added:
        hidden_nodes_layer1 =  15
        hidden_nodes_layer2 = 8
        hidden_nodes_layer3 = 5

The optimization improved the accuracy of the model to 0.801 and a loss of 0.447. 