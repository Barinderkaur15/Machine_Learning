# Machine_Learning
## Purpose : 
In this project, we are building anf evaluating several machine learning models to assess credit risk.<BR>

### objective 

**1.** :  Implement machine learning models.<BR>
**2** :  Use resampling to attempt to address class imbalance.<BR>
**3.**  Evaluate the performance of machine learning models.<BR>

### Various Models  and Alogorithms used 
**1.** Oversample the data using the RandomOverSampler and SMOTE algorithms.<BR>
**2.** Undersample the data using the cluster centroids algorithm.<BR>
**3.** A combination approach with the SMOTEENN algorithm.<BR>

**BalancedRandomForestClassifier** and **EasyEnsembleClassifier** Models were used to predict loan risk

### Process 
**1.** Split the datasets.<BR>
**2.** Create a Model .<BR>
**3.** Train the Model<BR>
**4**  Create Predictions <BR>
**5**  Validate the Model<BR>


### Analysis
**Oversampling** 
Class imbalance refers to a situation in which the existing classes in a dataset aren’t equally represented.one strategy to deal with class imbalance is to use appropriate metrics to evaluate a model’s performance, such as precision and recall.
Another strategy is to use oversampling. The idea is simple and intuitive: If one class has too few instances in the training set, we choose more instances from that class for training until it’s larger.


### Naive Random Oversampling 
Accuracy Score : 65.03%
It is the ratio of number of correct predictions to the total number of input samples.It works well only if there are equal number of samples belonging to each class.Accuracy Score of 65.03% s not a good score, but An accuracy score is not always an appropriate or a meaningful performance metric.<BR>
  
  ### Confusion Matrix:
  Confusion Matrix as the name suggests gives us a matrix as output and describes the complete performance of the model. 
  
  A Classification report is used to measure the quality of predictions from a classification algorithm.<BR>
 ***1. Precision***: Precision is the ability of a classifier not to label an instance positive that is actually negative. 
  In The case of oversampling model  the precision value  is case of Low risk is perfect 1.0 where is in case of high risk is 0.01 which is  very low , which is indicative of lots of false negative <BR>
  
 ***2.Recall*** - Recall is the ratio of correctly predicted positive observations to the all observations in actual class . We have got recall of 0.631 which is good for this model as it’s above 0.5.<BR>
  
 ***F1 score*** - F1 Score is the weighted average of Precision and Recall. Therefore, this score takes both false positives and false negatives into account. Intuitively it is not as easy to understand as accuracy, but F1 is usually more useful than accuracy, especially if you have an uneven class distribution. Accuracy works best if false positives and false negatives have similar cost. If the cost of false positives and false negatives are very different, it’s better to look at both Precision and Recall. In our case, F1 score is 0.75 which states some what balance between precision and sesitivity 
 
![Capture_part1](https://user-images.githubusercontent.com/55926650/74115442-163b0180-4b64-11ea-8886-2d8ac1134fc2.PNG)  
While precisioand recall are high for the majority class, precision is low for the minority class.  <BR>


**Synthetic Minority Oversampling Technique** <BR>
The synthetic minority oversampling technique (SMOTE) is another oversampling approach to deal with unbalanced datasets. In SMOTE, like random oversampling, the size of the minority is increased.
  
Although SMOTE reduces the risk of oversampling, it does not always outperform random oversampling. Another deficiency of SMOTE is its vulnerability to outliers

**Cluster Centroid Undersampling** <BR>
  Cluster centroid undersampling is akin to SMOTE. The algorithm identifies clusters of the majority class, then generates synthetic data points, called centroids, that are representative of the clusters. 
  
 By undersampling, we solved the class imbalance issue, and increased the sensitivity of our models.
 However the Results in this case het more worse then random sampling .
  
A reason could indeed be that we trained our classifiers using few samples. In general, the more imbalanced the dataset the more samples will be discarded when undersampling, therefore throwing away potentially useful information.
![Capture_undersampling](https://user-images.githubusercontent.com/55926650/74115443-16d39800-4b64-11ea-9021-614805119d17.PNG)
**SMOTEENN ** <BR>
  SMOTEENN combines the SMOTE and Edited Nearest Neighbors (ENN) algorithms. SMOTEENN is a two-step process:<BR>
  1.Oversample the minority class with SMOTE
  2. Clean the resulting data with Undersampling strategy
  ![combination](https://user-images.githubusercontent.com/55926650/74115444-16d39800-4b64-11ea-81de-83f000fa80bc.PNG)
 Combining these two stargies help in improving the metrices .This model may not be the best one for preventing  fraudulent loan applications, but combining both obr sampling and undersampling techniqies gives us better represntation about the risk 
 <BR>
 ==================================================================
### Ensemble Learning
The concept of ensemble learning is the process of combining multiple models, like decision tree algorithms, to help improve the accuracy and robustness, as well as decrease variance of the model, and therefore increase the overall performance of the model.
<BR>

***BalancedRandomForestClassifier** <BR>
A balanced random forest randomly under-samples each boostrap sample to balance it.
 After using this model  the accuracy score increases to 78% and F1 is 94% which is nearly perfect and  states very strong balance between precision and sesitivity 
