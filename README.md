# Neural Network Charity Analysis
## Overview and Purpose
The purpose of this project was to create a binary classifier using a neural network that would predict whether organizational applicants will be successful or not when funded by this organization.  Based on metadata of more than 34,000 organizations that received prior funding from "Alphabet Soup", a neural network model was created then optimized for the dataset.  

Data were preprocessed and an initial model was compiled, trained, and evaluated.  Attempts to optimize the model were made to increase its performance above 75% accuracy.

## Resources
- Data Sources: charity_data.csv
- Software and Programming Languages: Jupyter Notebook v. 6.4.6; Python v. 3.8.3 :: Anaconda, Inc.; conda v. 4.11.0; scikit-learn v. 0.23.1:: Anaconda, Inc.; tensorflow v. 2.8.0:: Anaconda, Inc.; keras 2.8.0:: Anaconda, Inc.

## Results
### **Data Preprocessing**
 - What variable(s) were considered targets for the model?  The target variable was represented by the column "IS_SUCCESSFUL" and was a binary response.

 - What variable(s) were considered to be the features for your model?  The final working dataframe, "application_df", contained 44 columns of data.   43 columns of data were used to build the initial neural network model because the "IS_SUCCESSFUL" column was dropped as it was the target variable.

 - What variable(s) were neither targets nor features, and should be removed from the input data?  The initial dataset contained column headings for "EIN" and organization "NAME".  These two columns were dropped during preprocessing because they were neither targets nor features.


### **Compiling, Training, and Evaluating the Model**
 - How many neurons, layers, and activation functions were selected for the neural network model, and why?  The initial model contained two hidden layers.  The first contained 14 neurons and the second contained 7.  These were selected given the size of the dataset and that there were 43 columns used as features.  The "ReLU" activation feature was used for both hidden layers because it is a good first default activation function to employ as it is computationally efficient.  The "Sigmoid" activation function was selected for the output layer because the response was binary (Fig. 1).  Additionally, 100 epochs were used to train the initial model (Fig. 2). 

![compileinitialmodel](https://user-images.githubusercontent.com/95387273/165788113-52c79335-2ab2-4bfd-8679-da51c7bbd889.png)

**Fig. 1.** Compilation of initial model for deep neural network.

![epochsinitialmodel](https://user-images.githubusercontent.com/95387273/165788916-ed49cd2e-c4c6-4215-a08c-9ee9c5a0c86c.png)

**Fig. 2.** Epochs (100) used in training initial model.

______________________________________________________________________________________________________________________________________________________________________

 - Was target model performance acheived?  Target model performance was not achieved in the initial model where accuracy was 0.7237 (Fig. 3).  Target model performance of 75% was also not achieved when the model was optmized and showed an accuracy score of 0.7275.

![accuracyinitialmodel](https://user-images.githubusercontent.com/95387273/165790022-b2904c5a-5fea-49e2-8ffd-42dc3050bc54.png)

**Fig. 3.** Accuracy for initial model.

![accuracyoptimization](https://user-images.githubusercontent.com/95387273/165790817-712514b0-7436-452c-8f88-f0088d2f9529.png)

**Fig. 4.** Accuracy for optimized model.

______________________________________________________________________________________________________________________________________________________________________

 - What steps were taken to try and increase model performance? Optimization was performed by dropping several columns as features, increasing the number of neurons, changing the activation of the hidden layers to "Leaky ReLU," and increasing the number of epochs to 200.

**Dropped Features:**  "ASK_AMT" was dropped as a feature because the amount of funding requested would have no bearing on whether an organization is successful. The amount requested is likely a product of the type of organization and the project to be completed. An overwhelming majority of organizations were also active, so "STATUS" was also dropped as a feature.  Likewise, most organizations had no special considerations, so columns "SPECIAL_CONSIDERATIONS_Y" and "SPECIAL_CONSIDERATIONS_N" were removed from the analysis (Fig. 5).

![featuresdroppedoptimization](https://user-images.githubusercontent.com/95387273/165794371-2ba52b2c-7197-4476-971e-bf88915c1f17.png)

**Fig. 5.** Features dropped from model during optimization.

**Increasing Numbers of Neurons and Changing Activation Function:**  The number of nodes in the first hidden layer was increased to 24 during optimization, up from 14 in the initial model, and increased to 12 in the second layer, up from 7 in the initial model (Fig. 6).  Additionally, the activation function was changed to "Leaky ReLU" in both hidden layers.  This dataset has has a lot of zeros, so could impact the activation of a node when using ReLU as the activation function.  Switching to a Leaky ReLU activation function could help correct for this (Fig. 6).

![hiddenlayersoptimization](https://user-images.githubusercontent.com/95387273/165799576-c72fdf45-d87a-49ea-b910-6d9c1ae6e578.png)

**Fig. 6.**  Compilation of optimized model for deep neural network showing increases in the number of nodes in both hidden layers and a change in activation function to "Leaky ReLU."

**Increasing Number of Epochs to 200:**  The number of epochs in the optimized model were increased to 200, up from 100 in the initial model (Fig. 7)

![epochsoptimization](https://user-images.githubusercontent.com/95387273/165799982-9cdb8e37-50be-4db1-bf30-260c16362218.png)

**Fig. 7.**  Number of epochs (200) in optimized model.


## Summary
Neither the initial model nor the optimized model achieved target model performance of 75%, even though there was a slight increase of 0.004.  It is recommended that the data be subjected to a logistic regression model for comparison because the output is binary.  Additionally, it would be beneficial to run this as a basic neural network model with a single hidden layer.  In retrospect, this would have been the most appropriate first analysis.  Adding multiple hidden layers and nodes to a neural network can add confusion to a model.  It would have been beneficial to compare these two neural network models to a basic model.
