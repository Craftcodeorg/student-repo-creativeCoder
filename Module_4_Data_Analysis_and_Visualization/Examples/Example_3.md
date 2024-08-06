# Module Title: Data Analysis and Visualization

## Learning Objectives
- Understand and apply Example 3: Creating basic plots with Matplotlib in practical scenarios.
- Enhance problem-solving skills with real-world applications.

## User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Preferred Learning Method: Code-along videos, interactive tutorials, community projects

---

## Lecture 3: Data Manipulation with Pandas

### 1. Introduction
Welcome to the third lecture in the "Data Analysis and Visualization" module, titled "Data Manipulation with Pandas." This lecture will introduce you to Pandas, a powerful library in Python used for data manipulation and analysis. As an aspiring Python Developer with a strong interest in Formula 1 Racing, mastering Pandas will be crucial for you. Whether you're analyzing F1 race data to uncover performance insights, automating stock market analysis, or creating interactive finance dashboards, Pandas provides the tools you need to handle complex data efficiently.

By the end of this lecture, you'll understand the essential methods and techniques for manipulating data using Pandas, gaining the skills to transform raw data into meaningful insights.

### 2. Key Concepts
#### a. Introduction to Pandas
- **What is Pandas?**: Pandas is an open-source data manipulation and analysis library for Python.
- **Core Data Structures**:
  - **Series**: A one-dimensional labeled array capable of holding any data type.
  - **DataFrame**: A two-dimensional labeled data structure with columns of potentially different types.

#### b. Loading Data
- **Reading CSV Files**: `pd.read_csv()`
- **Reading Excel Files**: `pd.read_excel()`

#### c. Data Cleaning
- **Handling Missing Data**: `dropna()`, `fillna()`
- **Renaming Columns**: `df.rename()`
- **Changing Data Types**: `astype()`

#### d. Data Transformation
- **Filtering Data**: Using conditions to filter rows.
- **Sorting Data**: `sort_values()`
- **Grouping Data**: `groupby()`
- **Aggregating Data**: `agg()`, `sum()`, `mean()`

#### e. Merging and Joining
- **Concatenating DataFrames**: `pd.concat()`
- **Merging DataFrames**: `pd.merge()`

### 3. Real-world Examples
#### Example 1: Formula 1 Race Data Analysis
Imagine you have a dataset containing F1 race results. You can use Pandas to:
- Load race results data from a CSV file.
- Clean the data by handling missing values and renaming columns for clarity.
- Filter the data to focus on a specific driver or team.
- Group and aggregate the data to calculate average lap times, total points, etc.
- Merge datasets to combine race results with driver information.

```python
import pandas as pd

# Load data
race_results = pd.read_csv('f1_race_results.csv')

# Clean data
race_results = race_results.dropna()
race_results = race_results.rename(columns={'Driver': 'DriverName', 'Pos': 'Position'})

# Filter data
lewis_hamilton_results = race_results[race_results['DriverName'] == 'Lewis Hamilton']

# Group and aggregate data
average_lap_times = race_results.groupby('DriverName')['LapTime'].mean()

# Merge datasets
driver_info = pd.read_csv('driver_info.csv')
merged_data = pd.merge(race_results, driver_info, on='DriverID')
```

#### Example 2: Stock Market Analysis
Consider a dataset containing historical stock prices. You can use Pandas to:
- Load stock price data from a CSV file.
- Clean the data by handling missing values.
- Sort the data by date.
- Calculate daily returns and moving averages.
- Merge datasets to combine stock prices with trading volumes.

```python
# Load data
stock_prices = pd.read_csv('stock_prices.csv')

# Clean data
stock_prices = stock_prices.fillna(0)

# Sort data
stock_prices = stock_prices.sort_values('Date')

# Calculate daily returns
stock_prices['DailyReturn'] = stock_prices['Close'].pct_change()

# Calculate moving averages
stock_prices['50DayMA'] = stock_prices['Close'].rolling(window=50).mean()

# Merge datasets
trading_volume = pd.read_csv('trading_volume.csv')
merged_data = pd.merge(stock_prices, trading_volume, on='Date')
```

### 4. Interactive Exercises
#### Exercise 1: Analyzing F1 Race Data
- Load an F1 race dataset.
- Clean the data by handling missing values and renaming columns.
- Filter the data to focus on a specific race or driver.
- Group and aggregate the data to calculate key statistics (e.g., average speed, total points).
- Visualize the results using Pandas' built-in plotting capabilities or another library like Matplotlib.

#### Exercise 2: Automating Stock Market Analysis
- Load a dataset of historical stock prices.
- Clean the data by handling missing values.
- Sort the data by date.
- Calculate daily returns and moving averages.
- Merge the dataset with another dataset containing trading volumes.
- Create an interactive dashboard to visualize stock trends and trading volumes using a library like Plotly or Dash.

### 5. Summary and Next Steps
In this lecture, you've learned the fundamental concepts and techniques for data manipulation with Pandas, including loading data, cleaning data, transforming data, and merging/joining data. These skills are essential for any Python Developer working with data, especially in fields like Formula 1 Racing and Stock Market Investing.

Next, we'll dive into data visualization techniques, where you'll learn how to create compelling visualizations to communicate your data insights effectively. Stay tuned as we explore tools like Matplotlib, Seaborn, and Plotly to bring your data to life!

---

This lecture has been designed to be interactive and engaging, with real-world examples and exercises tailored to your interests and career goals. Utilize multimedia resources such as diagrams, videos, and quizzes to reinforce your learning and make the content more accessible. Happy learning!

---

## Example 3: Creating Basic Plots with Matplotlib

### Introduction
In this example, we will explore how to create basic plots using Matplotlib, a widely-used plotting library in Python. Matplotlib is essential for visualizing data, making it easier to uncover patterns, trends, and insights. For a Python Developer with a keen interest in Formula 1 Racing, visualizing race data can help in identifying performance trends and making data-driven decisions.

### Code Snippet
Below is a well-commented code snippet that demonstrates how to create basic plots with Matplotlib. The code is suitable for a beginner-level programmer and includes error handling and best practices.

```python
import matplotlib.pyplot as plt
import pandas as pd

# Sample data: F1 race results
data = {
    'Driver': ['Lewis Hamilton', 'Max Verstappen', 'Sebastian Vettel', 'Charles Leclerc'],
    'Points': [350, 320, 275, 250]
}

# Convert data to DataFrame
df = pd.DataFrame(data)

# Error handling: Check if data is empty
if df.empty:
    raise ValueError("The DataFrame is empty. Please provide valid data.")

# Create a bar plot
plt.figure(figsize=(10, 6))
plt.bar(df['Driver'], df['Points'], color='blue')

# Add title and labels
plt.title('F1 Drivers Points Comparison')
plt.xlabel('Driver')
plt.ylabel('Points')

# Display the plot
plt.show()
```

### Explanation
1. **Import Libraries**: We start by importing the required libraries: `matplotlib.pyplot` for plotting and `pandas` for data manipulation.
2. **Sample Data**: We create a dictionary containing sample F1 race results, which includes drivers' names and their points.
3. **Convert to DataFrame**: The dictionary is converted into a Pandas DataFrame for easy manipulation.
4. **Error Handling**: We check if the DataFrame is empty and raise an error if it is, ensuring that the code doesn't run with invalid data.
5. **Create Bar Plot**: We use Matplotlib to create a bar plot, setting the figure size and plotting the drivers' names against their points.
6. **Add Title and Labels**: We add a title and labels to the plot for better readability.
7. **Display Plot**: Finally, we display the plot using `plt.show()`.

### Application
#### Real-world Application in Healthcare
In healthcare, visualizing data is crucial for monitoring patient outcomes, resource allocation, and treatment efficacy. For example, a hospital can use Matplotlib to create plots that display patient recovery rates, medication effectiveness, or staff performance metrics.

Consider a scenario where you have a dataset containing patient recovery times from different treatments. Using Matplotlib, you can create a bar plot to compare the average recovery times for each treatment, helping healthcare professionals make informed decisions about patient care.

```python
import matplotlib.pyplot as plt
import pandas as pd

# Sample data: Patient recovery times
data = {
    'Treatment': ['Treatment A', 'Treatment B', 'Treatment C', 'Treatment D'],
    'Average Recovery Time (days)': [10, 15, 7, 12]
}

# Convert data to DataFrame
df = pd.DataFrame(data)

# Error handling: Check if data is empty
if df.empty:
    raise ValueError("The DataFrame is empty. Please provide valid data.")

# Create a bar plot
plt.figure(figsize=(10, 6))
plt.bar(df['Treatment