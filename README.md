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
 - How many neurons, layers, and activation functions were selected for the neural network model, and why?

 - Was target model performance acheived?

 - What steps were taken to try and increase model performance?

## Summary
