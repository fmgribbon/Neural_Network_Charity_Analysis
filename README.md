# Neural Network Charity Analysis
## Purpose 
  The purpose of this study is to develop a binary classifier model using machine learning and artificial neural network given CSV file that contains metadata of 34,000 corporation. This model will predict if the corporations, that received funding in the past from Alphabet Soup Foundation, will succeed or not.  The prediction model will help the foundation decide where to allocate its funds. 
  

## Results
## Metadata
- EIN and NAME: Identification columns
- APPLICATION_TYPE: Alphabet Soup application type
- AFFILIATION: Affiliated sector of industry
- CLASSIFICATION: Government organization classification
- USE_CASE: Use case for funding
- ORGANIZATION: Organization type
- STATUS: Active status
- INCOME_AMT: Income classification
- SPECIAL_CONSIDERATIONS: Special consideration for application
- ASK_AMT: Funding amount requested
- IS_SUCCESSFUL: Was the money used effectively

## Variables used for the model
### Target Data
- IS_SUCCESSFUL

### Features
- APPLICATION_TYPE
- AFFILIATION
- CLASSIFICATION
- USE_CASE
- ORGANIZATION
- STATUS
- INCOME_AMT
- SPECIAL_CONSIDERATIONS
- ASK_AMT
### Dropped Data
- EIN 
- NAME

### Initial Model
![alt tag](https://github.com/fmgribbon/Neural_Network_Charity_Analysis/blob/main/Resources/Images/initial_model_accuracy_score.PNG)
- **Accuracy Score:** 68.68%
- **Hyperparameters Settings**

  - Input Layer: 43 Features
  
  - Hidden Layers: 2 layers
    - Activation Function
      - First Hidden layer: ReLu
      - Second Hidden Layer: ReLu
    - Number of neurons:
      - First Hidden Layer: 80
      - Second Hidden Layer: 30
  
  - Output Layer:
    - Activation Function: Sigmoid 

- **Epoch Settings**
  - Number of Epochs: 100

### OPTIMIZATION		
- Three optimization attempts were done to yield an acceptable accuracy score of 75%.
  The output layer was not modified on each attempt.
- In each attempt, the following modifications were made:  
    - Hyperparameters neuron, hidden layers and activation functions 
    - Reduced input layer features from 43 to 39. Dropped 4 features to eliminate data repetition.  
    - Converted the ASK_AMT using log10 was used to achieve absolute changes between two data points.

### First Attempt
![alt tag](https://github.com/fmgribbon/Neural_Network_Charity_Analysis/blob/main/Resources/Images/first_attempt_accuracy_score.PNG)
- **Modifications to the model settings**
  - **Neurons**
    - The first hidden layer is 10 neurons less than the model’s initial setting. 
    - The second hidden layer is 10 neurons less than the model’s initial setting.
    - The neuron settings were decreased slightly to test if the accuracy score will increase.  

- **Modification Results**
   - Accuracy Score: 67.15%
   - The accuracy score decreased by 1.5% compared to the accuracy score of the initial model.
 
 - **Hyperparameters Settings**
   - Hidden Layers: 2 layers
     - Activation Function
       - First Hidden layer: ReLu
       - Second Hidden Layer: ReLu
     - Number of neurons
       - First Hidden Layer: 70
       - Second Hidden Layer: 30

- **Epoch Settings**
  - Number of Epochs: 100
  
### Second Attempt
![alt tag](https://github.com/fmgribbon/Neural_Network_Charity_Analysis/blob/main/Resources/Images/second_attempt_accuracy_score.PNG)
- **Modifications to the model settings**
  - **Neuron**
    - The second hidden layer is 10 neurons less than the inital setting. 
    - The neuron setting was decreased slightly to test if the accuracy score will improve. 
  - **Epoch**
    - The number of Epoch was set to 30. Decreased by 70 compared to the inital eopch setting 100.  
    - The number of Epoch was decreased to test if the accuracy score will imporve. 
  - **Hidden Layers Activation Settings**
    - The activation function second hidden layer was set to Tanh. 
    - The Tanh was selected because the Tanh is identified by a characteristic S-curve like the Sigmoid function used in the output layer activation function. 

- **Modification Results**
  - Accuracy Score: 63.74%
  - The accuracy score decreased by 5% compared to the accuracy score of the initial model.

- **Hyperparameters Settings**
  - Hidden Layers: 2 layers
    - Activation Function
      - First Hidden layer: ReLu
      - Second Hidden Layer: Tanh
    -  Number of neurons
       - First Hidden Layer: 80
       - Second Hidden Layer: 20

- **Epoch Settings**
  - Number of Epochs: 30

### Third Attempt
![alt tag](https://github.com/fmgribbon/Neural_Network_Charity_Analysis/blob/main/Resources/Images/third_attempt_accuracy_score.PNG)
- **Modifications to the model settings**
  - **Neuron**
    - The first hidden layer neuron is decreased by 10 neurons less than the inital model. 
    - The second hidden layer is decreased by 20 neurons less than the first hidden layer set for this model. 
    - The third hidden layer is decreased by 20 neurons less than the second hidden layer set for this model. 
    - Decreasing the  neuron settings were slightly by an equal number of neurons may improve the accuracy score. 
  - **Hidden Layers**
    - A third hidden layer was added to the model. 
    - **Activation Settings**
      - For the third hidden layer activation, the Tanh function was selected. 
      - The Tanh was selected because the Tanh is identified by a characteristic S-curve like the Sigmoid function used in the output layer activation function. Selecting a different activation setting may imporve accuracy score. 
- **Modification Results**
   - Accuracy Score: 71.37%	  
   - The accuracy score increased by 2.7% compared to the accuracy score of the initial model. 

- **Hyperparameters Settings**
  - Hidden Layers: 3 layers
    - Activation Funtion
      - First Hidden Layer: ReLu
      - Second Hidden Layer: ReLu
      - Third Hidden Layer: Tanh
    -  Number of neurons
       - First Hidden Layer: 70
       - Second Hidden Layer: 50
       - Third Hidden Layer: 30
       
- **Epoch Settings**
  - Number of Epochs: 100
   
### SUMMARY
   The results of the initial model did not achieve the acceptable accuracy score of 75%. To achieve an acceptable accuracy score, optimization of the model was done by modifying the hyperparameters of the model, the features, and  the epoch to train the model. 
    
  After three optimization attempts the best accuracy score achieved was 71.37%. 
  

 Adding a hidden layer using tanh function and decreasing number of neurons for each hidden layer created a model that performed best. 
 
 Slightly decreasing the number of neurons in only one hidden layer and decreasing the number of epochs showed no improvement in the accuracy score. 
 
 The effects to the accuracy score of dropping 5 features and the ASK_AMT log10 conversion, could not be determined based on the results.  
 
 There are several settings could be modified to fine tune a model. Three optimization attempts may be a good starting point in fine tuning the model’s performance. Given that the input dataset is less than 50K records and the output is a binary classification, it is best to use a supervised machine learning model like Balanced Random Forrest classification. Trying other supervised machine learning model may be used to achieve better accuracy score. Deep Learning Artificial Neural Network works best for large datasets with a good amount of data available for learning. 
 

