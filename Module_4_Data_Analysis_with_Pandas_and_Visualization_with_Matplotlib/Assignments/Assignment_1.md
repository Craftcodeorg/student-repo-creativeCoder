# Assignment: Develop an Interactive Dashboard Displaying F1 Race Statistics Using Pandas and Matplotlib

## Problem Statement
Create an interactive dashboard that visualizes Formula 1 race statistics using the Pandas library for data manipulation and Matplotlib for data visualization. The dashboard should allow users to explore various statistics, such as average lap times, race positions of drivers, and the number of races won by each driver. This assignment will help you apply the concepts learned in the lecture about data manipulation and visualization, showcasing your skills relevant to data analysis in sports.

## Starter Code
Below is a basic framework to get you started on building your dashboard. This code sets up a simple environment to load the data and create basic visualizations.

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load data from a CSV file
df = pd.read_csv('f1_race_results.csv')

# Display the first few rows of the DataFrame
print(df.head())

# Function to calculate average lap time for each driver
def calculate_average_lap_time(df):
    return df.groupby('Driver')['LapTime'].mean()

# Function to visualize average lap time
def plot_average_lap_time(avg_lap_time):
    avg_lap_time.plot(kind='bar', title='Average Lap Time per Driver')
    plt.xlabel('Driver')
    plt.ylabel('Average Lap Time (seconds)')
    plt.show()

# Calculate average lap time
average_lap_time = calculate_average_lap_time(df)

# Visualize average lap time
plot_average_lap_time(average_lap_time)
```

### Instructions
1. **Data Preparation**: 
   - Ensure that your CSV file (`f1_race_results.csv`) contains columns for `Driver`, `LapTime`, and `Position`. You may need to clean the data by handling any missing values.

2. **Enhance the Dashboard**:
   - **Step 1**: Modify the `calculate_average_lap_time` function to also return the total number of races won by each driver. You can do this by grouping by `Driver` and counting the occurrences where `Position` equals 1.
   - **Step 2**: Create a new function `plot_races_won` that visualizes the total number of races won by each driver in a pie chart.
   - **Step 3**: Integrate user input to select which driver’s statistics to visualize. Use `input()` to allow users to specify a driver’s name and display their average lap time and races won.

3. **User Interface**:
   - Create a simple text-based menu that allows users to choose between viewing average lap times or races won.
   - Format the output neatly for better readability.

### Criteria for Success and Evaluation
- **Functionality**: The dashboard correctly calculates and displays average lap times and races won for each driver.
- **Code Quality**: The code is well-organized, follows best practices, and includes comments explaining each function and its purpose.
- **User Experience**: The dashboard is user-friendly, with clear instructions and formatted outputs that enhance readability.
- **Creativity**: Additional features such as filtering by year or race type will earn extra points.

### Submission Guidelines
- Submit your completed Python script along with any necessary data files.
- Ensure your code runs without errors and produces the expected visualizations.
- Provide a brief report (1-2 paragraphs) describing your approach and any challenges you faced during development.

This assignment not only reinforces your understanding of data manipulation with Pandas but also enhances your skills in data visualization with Matplotlib, making it a valuable addition to your portfolio as you pursue your career goals in Python development.