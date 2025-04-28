# Stroke-Prediction

Mina Davoudi, Brandon Cheung, Pranay Chalasani

Link to Dataset: https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset

Introduction:
A stroke occurs when blood vessels that carry oxygen and nutrients to the brain are blocked. This can be due to blood clots or ruptures, which prevent blood and oxygen from reaching the brain, causing brain cells to die. Stroke is a leading cause of death and long-term disability worldwide, and early detection and prevention are crucial in reducing its impact. To explore this important issue, our project uses machine learning to predict stroke risk. Our goal is to use predictive models that can help identify at-risk individuals, potentially allowing for early detection. 

Data Analysis Summary:
We sourced the stroke prediction Dataset from Kaggle, which comprises 5,110 patient records with 12 attributes. These included demographics (age, gender, and marital status), health indicators (Hypertension, heart disease, BMI, average glucose level), and lifestyle factors (smoking status, work type, residence type). Before we begin our analysis, we created graphs to see the distribution of our data and its correlation. 

We then processed the data by separating the numerical and categorical variables. The dataset was then split into a train and test set using an 80/20 split. We then scaled the numeric variables by removing the mean and scaling to unit variance to prevent features with larger scales from dominating. The categorical features were converted into binary columns using one‑hot encoding via get_dummies. We evaluated three machine learning models: Random Forest Classifier, Logistic Regression, and Decision Tree Classifier, and assessed them based on ROC AUC, recall, precision, and confusion matrix metrics.

The Random Forest Classifier showed the highest ROC AUC score of 0.873, indicating that it's the best at distinguishing between stroke and non-stroke cases. The precision score is 0.82, meaning that 82% of patients it identified as having a stroke actually did not, but it only catches 50% of actual strokes. However, despite the high precision, the model failed to correctly predict any true stroke cases, resulting in zero true positives. 

The Logistic Regression model did a little better. It had an ROC AUC of 0.810 with a precision of 0.72 and a recall of 0.45. It correctly predicted 40 out of 50 stroke cases and also had 250 false positives. Although it predicted a lot of false positives compared to the Random Forest model. It also detected most of its actual stroke cases. With that said, this model is faster to train and easier to interpret coefficients (each “x” increase in BMI raises the predicted stroke probability by “y” percentage points).

The Decision Tree Classifier model had the worst performance, with an ROC AUC of 0.754. It only identified 6 true stroke cases and had a recall of 0.37, meaning that only 37% of actual strokes are caught, and one in three predicted strokes is a false alarm. As a result, this model tends to overfit on some branches and underfit on others.

Conclusion: 
Even though the Random Forest Model had a better ROC AUC, Precision, and Recall, the Logistic Regression Model is the better choice since the Random Forest Model calls zero true positives. Looking at the Confusion Matrix for the Logistic Regression Model, it correctly rules out stroke in 722 healthy individuals, and even though there were 250 false positives, this is acceptable in a medical context where early caution can save lives and false positives are not necessarily bad. Integration into healthcare systems can support personalized care, public health, and early detection by enabling real-time stroke risk alerts in clinical settings, tailoring prevention plans, and informing community health strategies.

References: 
About stroke. www.stroke.org. (n.d.). https://www.stroke.org/en/about-stroke#:~:text=Stroke%20is%20a%20disease%20that,or%20bursts%20(or%20ruptures). 


