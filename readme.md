#  Richter's Predictor: Modeling Earthquake Damage

## Group Name:
- what, Wen(jie), where, Hao, Collin

## Contributors:
- Wenjie Duan
- Hao Xu
- Collin Prather

## Ask and Acquire Dataset
- Link to dataset: https://www.drivendata.org/competitions/57/nepal-earthquake/page/134/
- Dataset download link(Public Data, but you need to register in this website to download data) : https://www.drivendata.org/competitions/57/nepal-earthquake/data/
- Number of observations: 260,603
- Number of raw features: 38 
- Problem to solve: predict the buildings' damage-grade after the earthquake.

## Process & Model & Deliver
- We did feature engineering to set a binary column indicating whether the buiding is in the  “accident  center”, and it's very useful in exploiting the geographic id (location) info. 
- We implemented 4 ML algorithms: 
    * Support Vector Machine (SVM)
    * Multi-layer Perceptron Classifier (MLP)
    * Rrandom Forest (RF)
    * Gradient Boosting Machine (GBM)
- We used pipeline to do the work, and tuned parameters for RF and GBM. 
- In the GBM model, we used two methods to solve the imbalanced-dataset problem:
    * SMOTE Oversample
    * Tuning Probability Threshold
- We calculated multiple evaluation metrics, like recall, precision, and f1-score. Since this dataset is imbalanced, we use micro-weighted f1-score as our main metric to evaluate our models. The final metrics for these models are:
    * GBM : 0.74 (micro-weighted f1-score)
    * RF  : 0.73 (micro-weighted f1-score)
    * MLP : 0.69 (micro-weighted f1-score)
    * SVM : 0.33 (micro-weighted f1-score)

## Summary & Takeaways
- We solved this multi-classification problem on predicting building's damage-grade, and we ranked top 10% in the Drivendata Competition. 
- According to the micro-weighted f1-score, GBM is our best model in this case. We further intepretated GBM model with confusion_matrix, feature-importance plot and shap.
- The RF and GBM models worked well in this project, and they can also be expended to the building-damage prediction in other natural disasters, like flood and wild fire. 

