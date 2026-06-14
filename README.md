# Restaurant Review Sentiment Analysis
## Executive Summary
A visual data mining and machine learning project built using [Orange Data Mining](https://orangedatamining.com). After cleaning the original JSON file, I used Power Query, Excel, and Orange to build four models to predict star ratings based on sentiment analysis of Google reviews for Anejo, a Mexican restaurant in Calgary, and to determine the most effective and accurate model.

### Workflow Overview
The complete visual programming canvas consists of four distinct sub-pipelines tracking data exploration, multi-model cross-validation, and final out-of-sample testing:  
<img width="2178" height="1346" alt="Anejo Workflow" src="https://github.com/user-attachments/assets/f89a18c8-184c-40ac-a20f-e867cecdf9a5" />

### Data Pipeline Architecture

1. **Preliminary Analysis:** Reviews are parsed through a text preprocessing engine to tokenize words, remove stop words, and extract sentiment metrics. Rows are filtered to isolate and visualize initial trends via Data Tables and Heat Maps.
2. **Model Training & Cross-Validation:** The training corpus is evaluated across multiple structural iterations (labeled M1, M2, and M3) using `Test and Score` widgets configured for 10-fold cross-validation.
3. **Machine Learning Classifiers:** Three primary models are evaluated and benchmarked concurrently:
   * **Logistic Regression** (and corresponding visual Nomograms for feature weight)
   * **Random Forest**
   * **Naive Bayes**
4. **Validation Pipelines (M4):** An isolated testing dataset undergoes identical imputation, text preprocessing, and sentiment analysis to evaluate true predictive accuracy on unseen data using standard Confusion Matrices.
