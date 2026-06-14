# Restaurant Review Sentiment Analysis
## Executive Summary
A visual data mining and machine learning project built using [Orange Data Mining](https://orangedatamining.com). After cleaning the original JSON file, I used Power Query, Excel, and Orange to build four models to predict star ratings based on sentiment analysis of Google reviews for Anejo, a Mexican restaurant in Calgary, and to determine the most effective and accurate model.

### Workflow Overview
The complete visual programming canvas consists of four distinct sub-pipelines tracking data exploration, multi-model cross-validation, and final out-of-sample testing:  
<img width="2178" height="1346" alt="Anejo Workflow" src="https://github.com/user-attachments/assets/f89a18c8-184c-40ac-a20f-e867cecdf9a5" />

### Data Pipeline Architecture

1. **Preliminary Analysis:** Reviews are parsed through a text preprocessing engine to tokenize words, remove stop words, and extract sentiment metrics. Rows are filtered to isolate and visualize initial trends via Data Tables and Heat Maps.
2. **Model Training & Cross-Validation:** The training corpus is evaluated across multiple structural iterations (labeled M1, M2, and M3) using `Test and Score` widgets configured for 10-fold cross-validation. Additional Test Data was evaluated using the most accurate classification model.
3. **Machine Learning Classifiers:** Three primary models are evaluated and benchmarked concurrently:
   * **Logistic Regression** (and corresponding visual Nomograms for feature weight)
   * **Random Forest**
   * **Naive Bayes**
4. **Model Predictors:**
   * **M1:** Positive, negative, neutral, and compound columns as predictors of star rating.
   * **M2:** Positive and negative columns as predictors.
   * **M3:** Used only the compound column as a predictors.
   * **M4:** Undergoes identical imputation, text preprocessing, and sentiment analysis to evaluate predictive accuracy on food, atmosphere, and service as predictors of star rating using standard Confusion Matrices.
6. **Model Evaluation:** Models were evaluated using Test and Score and Confusion Matrix analyses; additional Test Data was evaluated using the most accurate classification model. Predictors changed for each subset of models; the target was always the star rating.  
The accuracy of the models was evaluated using AUC, CA, F1, Precision, Recall, and Matthews Correlation Coefficient (MCC). This analysis specifically focuses on AUC, CA, and F1 as measures of accuracy.


## Key Results & Insights

* **Target Variable:** Google Review Star Rating (Categorical / Ordinal classification).
* **Feature Engineering:** Text-based sentiments extracted directly from local Calgary restaurant reviews.
* **Best Performing Model:** *Random Forest on M4* achieved the highest Classification Accuracy (CA) and AUC score when processing the sentiment vectors.
* **Key Discovery:** High positive sentiment polarity strongly correlates with 5-star ratings, whereas neutral-to-negative fluctuations heavily dictate the decision boundary between 1-star and 3-star ratings on the Nomograms.
