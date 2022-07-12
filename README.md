# Telecom Churn Prediction!

In the telecommunication industry, customers tend to change operators if not provided with attractive schemes and offers. It is very important for any telecom operator to prevent the present customers from churning to other operators. In this case study our task is to build an ML model which can predict if the customer will churn or not in a particular month based on the past data.

## Project Pipeline
* [Dataset Information & Preprocessing](#dataset-information-and-preprocessing)
* [Exploratory Data Analysis](#exploratory-data-analysis)
* [Base Model](#base-model)
* [Augmentation Strategy](#augmentation-strategy)
* [Model Building](#model-building)
* [Class Imbalance](#class-imbalance)
* [Final Model](#final-model)
* [Conclusions](#conclusions)
* [Libraries Used](#libraries-used)

### Dataset Information and Preprocessing

#### Data Reading
The dataset consists of nearly 70K records with 172 features.

- ##### *Dtype*
  | float | int | obj |
  |-------|-----|-----|
  | 135   | 28  |  9  |
  
- ##### *Insignificant features*
  - 13 features are identified as insignificant as they have the same data across their entire records and so they are removed from the dataset.
    
#### Preprocessing
As the dataset is not clean, Several preprocessing are required to be done on the dataset before model building.

- ##### *Dtype Conversion*
  All the features related to the date on which recharge is done are in the object data type that has been converted to the DateTime datatype.
  
- ##### *Missing Values*
  - Columns related to the `Last recharge date` has many missing values that is because the customer hadn't recharged. Replaced the missing data     with 0 to indicate that recharge was not made by the customer.
  - Missing data from the columns related to `Total recharge data` replaced with 0 as recharge was not done.
  - Many customers were not using the internet services hence columns related to internet services has many missing values thus replaced with 0's.
  - Same above approach applies to the columns related to imcomming and outgoing calls.
  
- ##### *Derived Metrics*
  New columns are derived from the last recharge columns to date as int data type
  
- ##### *Outlier Treatment*
  we have some outliers but not very much, they may be a high value customers. So Let the feauture engineering techniques like Scaling, Hyperparemeter tuning handle those. Also tree models are not going to suffer from the outliers and we can use L1 and L2 regularization for logistic regression.
  
### Exploratory Data Analysis



