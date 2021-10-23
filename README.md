# Neural Network Charity Analysis
# Overview
With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, Beks received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. 

# What You're Creating
Deliverable 1: Preprocessing Data for a Neural Network Model \
Deliverable 2: Compile, Train, and Evaluate the Model \
Deliverable 3: Optimize the Model 


# Data Preprocessing
What variable(s) are considered the target(s) for your model?
- IS_SUCCESSFUL - Was the money used effectively

What variable(s) are considered to be the features for your model?
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special consideration for application
- ASK_AMT—Funding amount requested 

What variable(s) are neither targets nor features, and should be removed from the input data? 
- EIN and NAME—Identification columns 

# Compiling, Training, and Evaluating the Model
For our input layer, we must add the number of input features equal to the number of variables in our feature DataFrame. (43 inputs) 
In our hidden layers, our deep learning model structure will be slightly different—we'll add two hidden layers with neurons in each layer. To create the second hidden layer, we'll add another Keras Dense class while defining our model. All of our hidden layers will use the relu activation function to identify nonlinear characteristics from the input values. (80 neurons in layer 1 and 30 in layer 2.) 
In the output layer, we'll use the same parameters from our basic neural network including the sigmoid activation function. The sigmoid activation function will help us predict the probability that the money was used effectively.

# Results 
![OGModel](https://github.com/cfusco77/Neural_Network_Charity_Analysis/blob/main/Resources/OG_Model.png)


## Optimization 1 
Adjusting the input data to ensure that there are no variables or outliers that are causing confusion in the model. In addition to binning application type and classification, I also chose to apply a binning technique to the ask_amt data. 

![Optimization1](https://github.com/cfusco77/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization1.png)

## Optimization 2
Adding more neurons to a hidden layer. Some of the reason we might chose to add additonal nerons are: 
- There is a distributed effort to find optimal weights—faster.
- Each neuron can focus on different features to identify nonlinear effects—smarter.
- It is less likely to fixate on complex variables—more robust.

Instead of choosing 80 neurons for the first hidden layer (roughly 2x the number of inputs), I chose 120 neurons (roughly 3x the number of inputs). 

![Optimization2](https://github.com/cfusco77/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization2.png) 

## Optimization 3
Adding or reducing the number of epochs to the training regimen. Each epoch is a complete pass through the training data. I increased the number of epochs from 100 in our original model to 1000 in this optimization effort. 

![Optimization](https://github.com/cfusco77/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization3.png) 


Despite making three atempts at optimizations, I was unable to clear the 75% accuracy threshold.  When a neural network model does not meet performance expectations, it is usually due to one of two causes: inadequate or inappropriate model design for a given dataset, or insufficient or ineffective training data.

# Recommendations for enhancement
While it may not always be finanically or logistically possibly adding more training data might improve the accuracy of our model. The first way to increase training data is to collect more data, using the same tactics as the primary data, to add to our input dataset. 
