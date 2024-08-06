# Module Title: Data Analysis and Visualization

## Learning Objectives
- Apply the concept of "Exercise 6: Train a simple regression model" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Formula 1 Racing.

## User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

## Exercise Requirements

### Problem Statement
Develop a problem statement that challenges you to apply "Exercise 6: Train a simple regression model" to a scenario relevant to Healthcare. The problem should encourage critical thinking and be solvable with the concepts covered in "Data Analysis and Visualization."

**Problem Statement: Predicting Patient Recovery Time**

Using historical patient data, develop a regression model to predict the number of days a patient will take to recover from a specific type of surgery. This exercise will involve data preprocessing, feature selection, model training, and evaluation.

**Dataset Description:**
- `age`: Age of the patient
- `bmi`: Body Mass Index
- `smoking_status`: Whether the patient smokes (1 for Yes, 0 for No)
- `surgery_type`: Type of surgery performed (1, 2, 3, or 4)
- `recovery_days`: Number of days taken for recovery (Target variable)

### Starter Code
The following starter code sets up the basic environment for the exercise. Annotations are provided to guide you through the process.

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error

# Load dataset
# Note: Replace 'patient_data.csv' with the path to your dataset file
data = pd.read_csv('patient_data.csv')

# Display the first few rows of the dataset
print(data.head())

# Select features and target variable
# Features: age, bmi, smoking_status, surgery_type
# Target: recovery_days
X = data[['age', 'bmi', 'smoking_status', 'surgery_type']]
y = data['recovery_days']

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize the regression model
model = LinearRegression()

# Train the model on the training data
model.fit(X_train, y_train)

# Make predictions on the testing data
predictions = model.predict(X_test)

# Evaluate the model using Mean Squared Error
mse = mean_squared_error(y_test, predictions)
print(f'Mean Squared Error: {mse}')

# Print sample predictions vs actual recovery days
for i in range(5):
    print(f'Predicted: {predictions[i]}, Actual: {y_test.iloc[i]}')
```

### Hints
1. **Data Preprocessing**: Ensure your dataset does not have missing values. Use techniques like mean imputation or remove rows with missing values.
2. **Feature Scaling**: Standardize or normalize your features to improve model performance.
3. **Model Evaluation**: Besides Mean Squared Error, consider using other metrics like R² Score to evaluate the model's performance.
4. **Understanding the Output**: Compare the predicted recovery days with the actual values to understand how well your model is performing.

### Exercise Outcome
- You should be able to solve the problem using the concepts learned, demonstrating an understanding of how these concepts apply to real-world scenarios in Healthcare.
- The solution should include best practices, error handling, and well-commented code to explain the reasoning behind each step.

## Integration
Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

### Summary and Next Steps
In this exercise, you applied machine learning concepts to predict patient recovery time using a simple regression model. This practical application helps bridge the gap between theoretical knowledge and real-world problem-solving in Healthcare.

**Next Steps**:
- Explore more advanced regression techniques such as Ridge Regression or Lasso Regression.
- Investigate feature engineering and how it can improve model accuracy.
- Implement hyperparameter tuning to optimize your model.

By completing this exercise, you are building a strong foundation in data analysis and visualization, which is crucial for your career goal as a Python Developer.