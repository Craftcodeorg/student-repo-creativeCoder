### Module Title: Data Analysis and Visualization ###

### Learning Objectives ###
- Apply the concept of "Exercise 4: Clean a dataset by handling missing values" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.
- Leverage knowledge of data visualization techniques learned from Matplotlib and Seaborn lectures.

### User Profile ###
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements ###

#### 1. Problem Statement ####
**Scenario**: You are working as a data analyst for a healthcare organization. You have been provided with a dataset containing patient records, including information on patient IDs, age, weight, blood pressure, and cholesterol levels. However, the dataset has missing values which need to be handled before any meaningful analysis can be conducted. Your task is to clean the dataset by handling these missing values using Python and Pandas.

**Problem Statement**: 
- **Objective**: Clean the dataset of patient records by handling missing values.
- **Steps**:
  1. Load the dataset into a Pandas DataFrame.
  2. Identify and handle missing values appropriately (e.g., filling with mean/median values, forward/backward fill, or dropping rows/columns).
  3. Generate basic visualizations to understand the distribution of the data post-cleaning.

#### 2. Starter Code ####
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Step 1: Load the dataset
# For this exercise, we will simulate loading a dataset. In a real scenario, you would read from a CSV file.
data = {
    'PatientID': [1, 2, 3, 4, 5],
    'Age': [25, 30, None, 45, 50],
    'Weight': [70, None, 80, 85, None],
    'BloodPressure': [120, 130, 125, None, 140],
    'Cholesterol': [200, 220, 210, 250, None]
}
df = pd.DataFrame(data)

# Step 2: Identify missing values
print("Initial DataFrame with missing values:")
print(df)

# Step 3: Handle missing values
# Fill missing values with the mean of the column
df['Age'].fillna(df['Age'].mean(), inplace=True)
df['Weight'].fillna(df['Weight'].mean(), inplace=True)
df['BloodPressure'].fillna(df['BloodPressure'].mean(), inplace=True)
df['Cholesterol'].fillna(df['Cholesterol'].mean(), inplace=True)

print("\nDataFrame after handling missing values:")
print(df)

# Step 4: Visualize the clean data
# Visualizing the distribution of Age
plt.figure(figsize=(10, 6))
sns.histplot(df['Age'], kde=True)
plt.title('Age Distribution')
plt.xlabel('Age')
plt.ylabel('Frequency')
plt.show()
```

#### 3. Hints ####
- **Hint 1**: Use `df.isnull().sum()` to identify the number of missing values in each column.
- **Hint 2**: Consider using `df.fillna()` to fill missing values with the mean, median, or a specific value.
- **Hint 3**: Use visualizations to check if the data looks reasonable after filling missing values. For example, histograms can help you understand the distribution of a column.
- **Hint 4**: In a healthcare context, think about the implications of different methods for handling missing data. For example, filling with mean values might be more appropriate than dropping rows if the dataset is small.

### Exercise Outcome ###
- **Expected Outcome**: The user should be able to clean the dataset by handling missing values and visualize the cleaned data effectively.
- **Solution Requirements**:
  - Proper handling of missing values using appropriate methods.
  - Clear, commented code explaining the steps taken.
  - Visualizations to demonstrate the cleaned data.

### Integration ###
- **Headings and Sections**:
  - **Problem Statement**: Clearly define the objective and steps.
  - **Starter Code**: Provide annotated code to set up the environment.
  - **Hints**: Offer step-by-step guidance without giving away the solution.
  - **Expected Outcome**: Define what a successful solution looks like.
  - **Resources**: Include links to any additional resources or documentation.

### Additional Resources ###
- **Pandas Documentation**: [Pandas Handling Missing Data](https://pandas.pydata.org/pandas-docs/stable/user_guide/missing_data.html)
- **Matplotlib Documentation**: [Matplotlib Plotting](https://matplotlib.org/stable/contents.html)
- **Seaborn Documentation**: [Seaborn Tutorial](https://seaborn.pydata.org/tutorial.html)

By completing this exercise, you will gain practical experience in cleaning datasets and visualizing data, which are crucial skills for any aspiring Python Developer working in the healthcare industry.