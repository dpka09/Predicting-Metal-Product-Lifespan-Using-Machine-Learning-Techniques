### Predicting Metal Product Lifespan Using Machine Learning Techniques

### Overview ###
This project which focuses on predicting the lifespan of metal products manufactured with a new metal alloy. By leveraging supervised and unsupervised learning techniques, the project aims to assist the metal parts manufacturing company in refining their production process and addressing defects efficiently.

---

### Key Objectives
- Estimate the lifespan of metal parts using processing parameters.
- Avoid costly and destructive lifespan measurement techniques.
- Improve production quality by identifying and addressing defects.
---

### Machine Learning Methods
The following techniques were applied:
### Regression ###

***1. Linear Regression***
   
Investigates the linear relationship between the dependent and independent variables.



***2. Support Vector Regressor (SVR)***

Hyperparameter tuning via Grid Search Cross Validation:

          Kernel options: ‘rbf’ and ‘linear’
          
          C parameter: 1, 10, 20
          
          Best parameters: C=1, Kernel='linear'



***3. Random Forest Regressor***

An ensemble learning method for regression. Hyperparameter tuning via Grid Search Cross Validation:
          
          n_estimators: 100, 500
          
          Best parameters: n_estimators=500
          
          ***Achieved 97.82% R² score***, making it the best model for predicting lifespan.


---

## Evaluation Metrics ##

***R² Score***

A statistical measure to evaluate model performance.
     Indicates how much variation in the dependent variable is explained by the independent variables.
          
          Formula: $$R² = 1 - \frac{\text{Sum Squared Regression}}{\text{Total Sum of Squares}}$$

---
## Model Comparison ##

![image](https://github.com/user-attachments/assets/4e6507b7-1c42-437c-8d6c-5763c20cc770)


---

## Binary Classification ##

***1. Logistic Regression***

A model that calculates probabilities and classifies data based on a logistic function.

Hyperparameter tuning:
          
          C parameter: Values 1, 10
          
          Low C prioritizes complexity over data fitting, while high C focuses on fitting training data.


***2. Support Vector Classifier***
A classification model that separates data points using a hyperplane.

***3. Random Forest Classifier***
An ensemble algorithm composed of multiple decision trees.
Introduces additional randomness to enhance accuracy and reduce overfitting.

Hyperparameter tuning:

          n_estimators: Values 100, 500

## Model Comparison ##


![image](https://github.com/user-attachments/assets/d4d28057-d5db-45d9-9a2d-75b06b464413)

Random Forest Classifier emerged as the best model, achieving an accuracy score of 94.5%.

### Evaluation Metrics ###
**1. Accuracy Score**
Measures the percentage of correct predictions:
          
          $$\text{Accuracy} = \frac{\text{Number of Correct Predictions}}{\text{Total Number of Predictions}}$$

**2. Confusion Matrix**

Evaluates the model using combinations of actual and predicted values:

True Positive (TP): Positive examples correctly classified.

True Negative (TN): Negative examples correctly classified.

False Positive (FP): Negative examples misclassified as positive.

False Negative (FN): Positive examples misclassified as negative.

          Formula for accuracy: $$\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}$$

---
## Why Use Accuracy and Confusion Matrix? ##


***Sensitivity and Specificity:***

Sensitivity measures the model's ability to identify instances with longer lifespans.

Specificity evaluates the accuracy in predicting shorter lifespans.

***Precision and Recall:***

Precision focuses on the accuracy of positive predictions.

Recall captures all positive instances accurately.

---


## Clustering ##

## KMeans Clustering: ##

K-means divides a dataset of 'n' points into 'k' clusters by evaluating the mean distance of each data point to its respective cluster centroid.
The optimal number of clusters (k) is determined using the Elbow Method, where the inertia (sum of squared errors, SSE) is analyzed.

## Implementation Details ##

1. Initially, k=3 was selected arbitrarily, representing the number of centroids or cluster centers.

2. Each data point was assigned to the closest cluster based on its distance from the centroids.

3. After assignment, the cluster centers were recalculated by computing the average position of assigned points.

4. The process iteratively repeated for 10 iterations, with the inertia at each step computed and stored in an array (sse).

## Elbow Plot for Determining Optimal Clusters ##

- The Elbow Plot visualized the inertia values for various numbers of clusters.

- The graph showed a significant change in inertia starting at k=4.

- Hence, the value of k=4 was chosen and implemented in the K-means algorithm.

![image](https://github.com/user-attachments/assets/344092df-5f54-4ffc-9aa3-45d989ea4cf2)

## Results ##
The K-means clustering effectively grouped data points into four clusters, based on similarities in features.



## How to Use ##

1. Clone the repository:

         git clone https://github.com/dpka09/Predicting-Metal-Product-Lifespan-Using-Machine-Learning-Techniques.git


2. Navigate to the project directory:

          cd repo-name

3. Install dependencies:


        pip install -r requirements.txt


4. Run the models:

        python main.py
