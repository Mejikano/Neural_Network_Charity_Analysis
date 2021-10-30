# Neural_Network_Charity_Analysis


## Overview

Alphabet Soup has been funding organizations over the years, unfortunately not all the fundings have been successful. This project analyzes and generates neural networks and deep learning models to predict whether the organization requesting funding will be successful using a 34,000 history dataset to train and test model performance.

## Results

### Data Preprocessing
- What variable(s) are considered the target(s) for your model?
    *** IS_SUCCESSFUL *** is the target variable as it states whether the money provided was effectively used. Therefore this is the variable to be predicted.
- What variable(s) are considered to be the features for your model?
    *** Model Features: *** 
    ***APPLICATION_TYPE***: Alphabet Soup application type
    ***AFFILIATION***: Affiliated sector of industry
    ***CLASSIFICATION***: Government organization classification
    ***USE_CASE***: Use case for funding
    ***ORGANIZATION***: Organization type
    ***INCOME_AMT***: Income classification
    ***ASK_AMT***: Funding amount requested
- What variable(s) are neither targets nor features, and should be removed from the input data?
    *** Dropped Variables *** below columns were dropped as they dont add any useful variance for the model.
    ***EIN*** and ***NAME***: Identification columns
    ***STATUS***: Active status
    ***SPECIAL_CONSIDERATIONS***: Special consideration for application

![Removed Columns](https://github.com/Mejikano/Neural_Network_Charity_Analysis/blob/main/Resources/Status_SpecialCons_Val.png)


### Compiling, Training, and Evaluating the Model


#### 1st Attempt
How many neurons, layers, and activation functions did you select for your neural network model, and why?
- 1st Hidden Layer: 120 neurons, "relu" activation
- 2nd Hidden Layer: 40 neurons, "relu" activation
- 3th Hidden Layer: 20 neurons, "relu" activation
- 4th Hidden Layer: 10 neurons, "relu" activation
- Output Layer: "sigmoid" activation

What steps did you take to try and increase model performance?
- Identify and remove outliers: Amount requested from some organization was too high: over 6,000,000,000
![Potential Outlier](https://github.com/Mejikano/Neural_Network_Charity_Analysis/blob/main/Resources/ASK_AMT_Outliers.png)
- Add number of neurons and hidden layers as deep learning tool
Note: relu activations were used in all hidden layers to deal with non-linnear patterns as during trial and error it yielded better results 

Were you able to achieve the target model performance? **No**, accuracy: 0.7383 in training and accuracy: 0.7216 in testing

#### 2nd Attempt
How many neurons, layers, and activation functions did you select for your neural network model, and why?
- 1st Hidden Layer: 80 neurons, "relu" activation
- 2nd Hidden Layer: 40 neurons, "relu" activation
- 3th Hidden Layer: 20 neurons, "relu" activation
- Output Layer: "sigmoid" activation

What steps did you take to try and increase model performance?
- Bucketing: INCOME_AMT feature was bucketed to reduce dimensionality
![INCOME AMT Density](https://github.com/Mejikano/Neural_Network_Charity_Analysis/blob/main/Resources/INCOME_AMT_density.png)

![INCOME AMT Contingency Table](https://github.com/Mejikano/Neural_Network_Charity_Analysis/blob/main/Resources/INCOME_AMT_contingency.png)

- Number of epochs were increased from 100 to 200
- Add number of neurons but less deep than the other attemps implementing tree  hidden layers
Note: relu activations were used in all hidden layers to deal with non-linnear patterns as during trial and error it yielded better results 

Were you able to achieve the target model performance? **No**, accuracy: 0.7413 in training and accuracy: 0.7295 in testing




#### 3rd Attempt
How many neurons, layers, and activation functions did you select for your neural network model, and why?
- 1st Hidden Layer: 80 neurons, "relu" activation
- 2nd Hidden Layer: 60 neurons, "relu" activation
- 3th Hidden Layer: 40 neurons, "relu" activation
- 4th Hidden Layer: 20 neurons, "relu" activation
- 5th Hidden Layer: 10 neurons, "relu" activation
- 6th Hidden Layer: 10 neurons, "relu" activation
- Output Layer: "sigmoid" activation

What steps did you take to try and increase model performance?
- Trying to go deeper and assess the results; number of neurons and hidden layers were added
Note: relu activations were used in all hidden layers to deal with non-linnear patterns as during trial and error it yielded better results 
- Data was not modified as in previous attemps (removing potential outliers or re-bucketing) as accuracy decreased
- Number of epochs were increased from 100 to 150

Were you able to achieve the target model performance? **No**, accuracy: 0.7405 in training and accuracy: 0.7252 in testing



## Summary

The neural network tends to overfit, this was observed during trial and error and tunning the existing model whenever  neurons or hidden layers were added or epochs increased and training accuracy improved the testing and validation accuracy dropped.

Explore other models are recommended that might be less likely to overfit and handle non-linnear patterns such as: Random Forest, Gradient Boosting Trees and Support Vector Machine.


