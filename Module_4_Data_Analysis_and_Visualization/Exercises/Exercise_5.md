### Module Title: Data Analysis and Visualization ###

### Learning Objectives ###
- Apply the concept of "Exercise 5: Split data into training and test sets" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

### User Profile ###
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements ###

#### 1. Problem Statement ####
In this exercise, you will apply the concept of splitting data into training and test sets to a scenario in the Healthcare industry. Imagine you are working with a dataset that contains patient information and their medical test results. Your task is to prepare this dataset for machine learning by splitting it into training and test sets. This will help in building predictive models that can, for instance, predict patient outcomes based on their test results.

**Problem Statement:**
You are provided with a dataset containing patient information, including features such as age, gender, blood pressure, cholesterol level, and medical test results. Your objective is to split this data into training and test sets, ensuring that the training set comprises 80% of the data and the test set consists of the remaining 20%. This split will enable you to train a machine learning model on the training set and evaluate its performance on the test set.

#### 2. Starter Code ####
Below is the starter code that sets up the basic environment for the exercise. The code includes the necessary imports and a template for splitting the dataset. Annotations are included to guide you through the process.

```python
# Starter code for splitting data into training and test sets
import pandas as pd
from sklearn.model_selection import train_test_split

# Load the dataset
# (Assume 'healthcare_data.csv' contains the columns: 'age', 'gender', 'blood_pressure', 'cholesterol', 'test_result')
data = pd.read_csv('healthcare_data.csv')

# Display the first few rows of the dataset
print(data.head())

# Define the feature columns and the target column
features = ['age', 'gender', 'blood_pressure', 'cholesterol']
target = 'test_result'

# Split the data into features (X) and target (y)
X = data[features]
y = data[target]

# Split the data into training and test sets
# Use train_test_split from sklearn with an 80-20 split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Display the shapes of the resulting datasets
print(f'Training set shape: {X_train.shape}, {y_train.shape}')
print(f'Test set shape: {X_test.shape}, {y_test.shape}')
```

#### 3. Hints ####
- **Hint 1:** Remember to import the necessary libraries, such as pandas for data manipulation and sklearn for splitting the data.
- **Hint 2:** Ensure that your dataset is loaded correctly by printing the first few rows using `data.head()`.
- **Hint 3:** Use the `train_test_split` function from sklearn, which makes it easy to split your data into training and test sets. The `test_size` parameter determines the proportion of the dataset to include in the test split.
- **Hint 4:** Setting a `random_state` in `train_test_split` ensures that your results are reproducible and consistent.

### Exercise Outcome ###
By the end of this exercise, you should be able to:
- Successfully split a dataset into training and test sets using the `train_test_split` function.
- Understand the importance of preparing data for machine learning models.
- Apply these concepts to real-world scenarios in the Healthcare industry, such as predicting patient outcomes based on medical tests.

### Integration ###
Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

### Final Notes ###
This exercise will help you understand how to handle and prepare large datasets for machine learning, an essential skill for any Python Developer. By applying these concepts to a Healthcare scenario, you will gain practical experience that can be transferred to other industries, including your specific interest in Formula 1 Racing. Keep practicing and exploring different datasets to enhance your data analysis and visualization skills.