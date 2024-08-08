# Neural-Network-Challenge-2

Training a neural network model using Keras to predict two outputs: department and attrition within a dataset.

## Project Summary
This project involves creating, compiling, and training a neural network model using Keras to predict two outputs: department and attrition within a dataset. 

## Requirements
- Python 3.x
- TensorFlow 2.x
- Keras
- Pandas
- NumPy
- Scikit-learn

###  Results Interpretation

**Department Accuracy (0.8207):** This means your model correctly predicts the department of an employee about 82.07% of the time. 
This is a relatively high accuracy, suggesting that the model is performing well in classifying the department.

**Attrition Accuracy (0.6087):** This indicates that the model accurately predicts whether an employee will leave the company (attrition) approximately 60.87% of the time. 
This accuracy is lower compared to the department prediction, which might suggest that predicting attrition is more challenging for your model.

### Answering Further Questions:

**Is accuracy the best metric to use on this data? Why or why not?** 

Answer: When the dataset is not balanced, accuracy metric may not be the best. While accuracy measures the proportion of correctly predicted instances out of all instances, it can be misleading in imbalanced datasets. For example, in this dataset, 83.8% of people do not leave, while only 16% leave the organization. 
```
Attrition Summary Table:
  Attrition  Count  Percentage
0        No   1233   83.877551
1       Yes    237   16.122449
```

If the attrition data is imbalanced (e.g., very few people leave the company), accuracy might give a misleading impression of the model's performance. 
In such cases, metrics like precision, recall, or the F1 score could provide a more nuanced understanding of the model's effectiveness.

It's important to take into consideration other metrics in order to get a better picture such as Precision-Recall Curve, Confusion Matrix, ROC Curve, and AUC. 

2. **What activation functions did you choose for your output layers, and why?**

Answer: The softmax activation function was chosen for the department output because it handles multi-class classification by producing probabilities that sum to 1 across the classes. There is a total of 3 departments. 
```
Department Summary Table:
               Department  Count  Percentage
0  Research & Development    961   65.374150
1                   Sales    446   30.340136
2         Human Resources     63    4.285714
```

The sigmoid activation function was chosen for the attrition output (e.g. left the company or not) because it is suitable for binary classification, outputting a probability between 0 and 1.

3. **Can you name a few ways that this model might be improved?**

Answer:
- **Handling Imbalanced Data:** If the attrition data is imbalanced, techniques such as oversampling the minority class, undersampling the majority class, or using weighted loss functions could help.
    - For example, in this case, the ratio of employees who leave and stay is imbalanced at approximately 8:2. In this case, we can undersample the majority by reducing the sample of people who leave. 

    - We can also use a weight loss function. This approach assigns a higher penalty for misclassifying the minority class. It helps the model focus more on getting the minority class correct.
    Weighted Loss Functions are a good choice if you want to keep all your data without duplication or deletion but still make sure the model doesn’t ignore the minority class.

- **Feature Engineering:** Another way to improve the model is by creating more meaningful features that can improve the accuracy.
