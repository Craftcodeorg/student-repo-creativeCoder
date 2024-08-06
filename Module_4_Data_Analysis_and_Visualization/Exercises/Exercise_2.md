## Module Title: Data Analysis and Visualization

### Learning Objectives
- Apply the concept of "Exercise 2: Create a bar chart and a line plot using Matplotlib" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements

#### 1. Problem Statement

**Scenario**: As a Python Developer interested in both Formula 1 Racing and the Healthcare industry, you are tasked with analyzing patient data to visualize trends in hospital admissions and average recovery times over a year. Your goal is to create a bar chart to show the number of admissions each month and a line plot to illustrate the average recovery time.

**Problem Statement**: Utilize Matplotlib to create a bar chart and a line plot that visualize hospital admissions and average recovery times. The bar chart should display the number of admissions for each month, and the line plot should show the average recovery time for each month. This exercise will help you understand how to handle and visualize real-world data in the healthcare industry using Python.

#### 2. Starter Code

```python
# Import necessary libraries
import pandas as pd
import matplotlib.pyplot as plt

# Sample data for hospital admissions and recovery times
data = {
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
    'Admissions': [120, 135, 150, 160, 170, 180, 190, 200, 210, 220, 230, 240],
    'Avg_Recovery_Time': [5.2, 5.1, 5.0, 4.9, 4.8, 4.7, 4.6, 4.5, 4.4, 4.3, 4.2, 4.1]
}

# Convert the data into a DataFrame
df = pd.DataFrame(data)

# Create a bar chart for hospital admissions
plt.figure(figsize=(10, 6))
plt.bar(df['Month'], df['Admissions'], color='blue', alpha=0.7, label='Admissions')
plt.xlabel('Month')
plt.ylabel('Number of Admissions')
plt.title('Monthly Hospital Admissions')
plt.legend()
plt.show()

# Create a line plot for average recovery time
plt.figure(figsize=(10, 6))
plt.plot(df['Month'], df['Avg_Recovery_Time'], color='green', marker='o', label='Avg Recovery Time')
plt.xlabel('Month')
plt.ylabel('Average Recovery Time (days)')
plt.title('Monthly Average Recovery Time')
plt.legend()
plt.show()
```

#### 3. Hints

- **Hint 1**: Ensure you understand the difference between a bar chart and a line plot. Bar charts are useful for comparing quantities, while line plots are ideal for observing trends over time.
- **Hint 2**: Use the `plt.bar()` function to create bar charts and `plt.plot()` to create line plots in Matplotlib.
- **Hint 3**: Customize your plots with labels, titles, and legends to make them more informative and easier to understand.
- **Hint 4**: Review the sample data provided in the starter code to understand the structure of the DataFrame and how it can be used to create visualizations.

### Exercise Outcome
- The user should be able to solve the problem using the concepts learned, demonstrating an understanding of how these concepts apply to real-world scenarios in Healthcare.
- The solution should include best practices, error handling, and be well-commented to explain the reasoning behind each step.

### Integration
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform.
- Use markdown for formatting and include any necessary files or resources as links.

---

By completing this exercise, you will not only practice creating visualizations using Matplotlib but also gain insights into how data analysis can be applied in the Healthcare industry. This experience will be valuable in your journey to becoming a proficient Python Developer. Keep challenging yourself with real-world data and scenarios to enhance your problem-solving skills!