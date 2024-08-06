# Personalized Curriculum for "Data Analysis and Visualization"

## Module Title: Data Analysis and Visualization

### Assignment 3: Implement a Machine Learning Model that Predicts Stock Prices Based on Historical Data

#### Problem Statement:
Develop a machine learning application that reads historical stock price data, processes the data to identify key insights, and uses a machine learning model to predict future stock prices. The application should generate a summary report of the predictions and visualize the stock trends.

#### Requirements.txt:
```plaintext
pandas
numpy
scikit-learn
matplotlib
plotly
```

#### Starter Code:
```python
# Starter code for stock price prediction application
import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
import matplotlib.pyplot as plt
import plotly.express as px

def read_data(file_path):
    return pd.read_csv(file_path)

def process_data(data):
    data['Date'] = pd.to_datetime(data['Date'])
    data = data.sort_values('Date')
    data['DailyReturn'] = data['Close'].pct_change()
    data['50DayMA'] = data['Close'].rolling(window=50).mean()
    data = data.dropna()
    return data

def train_model(data):
    X = data[['DailyReturn', '50DayMA']]
    y = data['Close']
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
    model = LinearRegression()
    model.fit(X_train, y_train)
    return model, X_test, y_test

def generate_report(model, X_test, y_test):
    predictions = model.predict(X_test)
    plt.figure(figsize=(10,5))
    plt.plot(y_test.values, label='Actual Prices')
    plt.plot(predictions, label='Predicted Prices')
    plt.legend()
    plt.title('Stock Price Prediction')
    plt.xlabel('Time')
    plt.ylabel('Stock Price')
    plt.show()

# Provide the file path and call the functions
file_path = 'data/stock_prices.csv'
data = read_data(file_path)
processed_data = process_data(data)
model, X_test, y_test = train_model(processed_data)
generate_report(model, X_test, y_test)
```

#### Detailed Instructions:
**Step 1: Read the data from the provided CSV file using pandas.**
- Use the `pd.read_csv()` function to read the stock price data from `data/stock_prices.csv`.

**Step 2: Process the data to identify key insights.**
- Convert the 'Date' column to datetime format and sort the data by date.
- Calculate daily returns using the percentage change of the 'Close' column.
- Calculate the 50-day moving average of the 'Close' column.
- Drop any rows with missing values.

**Step 3: Split the data into training and testing sets.**
- Use the `train_test_split()` function from `sklearn.model_selection` to split the data into training and testing sets.
- Use 'DailyReturn' and '50DayMA' as features and 'Close' as the target variable.

**Step 4: Train a machine learning model.**
- Instantiate a `LinearRegression` model from `sklearn.linear_model`.
- Fit the model using the training data.

**Step 5: Generate a summary report and visualize the results.**
- Use the trained model to predict stock prices on the test data.
- Plot the actual vs. predicted stock prices using Matplotlib.
- Create an interactive plot using Plotly to visualize stock trends and predictions.

#### Criteria for Success and Evaluation:
**Success Criteria:**
- The application correctly reads and processes the stock price data.
- The machine learning model is trained and able to predict future stock prices with reasonable accuracy.
- The summary report includes a plot comparing actual vs. predicted stock prices.
- The interactive dashboard effectively visualizes stock trends and predictions.

**Evaluation Rubric:**
- **Data Loading and Cleaning (20%)**: Correctly reads data, handles missing values, and calculates new columns.
- **Data Transformation (20%)**: Appropriately splits data into training and testing sets.
- **Model Training (20%)**: Successfully trains a machine learning model and achieves reasonable predictions.
- **Visualization (20%)**: Generates clear and accurate plots comparing actual and predicted prices.
- **Interactivity (20%)**: Creates an interactive dashboard that effectively visualizes stock trends and predictions.

### Assignment 4: Analyzing Formula 1 Race Data

#### Problem Statement:
Create an application that reads Formula 1 race data, processes the data to uncover key performance insights, and generates a comprehensive report. The application should also visualize race results and performance trends.

#### Requirements.txt:
```plaintext
pandas
numpy
matplotlib
seaborn
```

#### Starter Code:
```python
# Starter code for F1 race data analysis application
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

def read_data(file_path):
    return pd.read_csv(file_path)

def process_data(data):
    data = data.dropna()
    data = data.rename(columns={'Driver': 'DriverName', 'Pos': 'Position'})
    return data

def analyze_performance(data):
    average_lap_times = data.groupby('DriverName')['LapTime'].mean()
    total_points = data.groupby('DriverName')['Points'].sum()
    return average_lap_times, total_points

def visualize_results(average_lap_times, total_points):
    plt.figure(figsize=(12,6))
    sns.barplot(x=average_lap_times.index, y=average_lap_times.values)
    plt.title('Average Lap Times per Driver')
    plt.xlabel('Driver')
    plt.ylabel('Average Lap Time')
    plt.show()

    plt.figure(figsize=(12,6))
    sns.barplot(x=total_points.index, y=total_points.values)
    plt.title('Total Points per Driver')
    plt.xlabel('Driver')
    plt.ylabel('Total Points')
    plt.show()

# Provide the file path and call the functions
file_path = 'data/f1_race_results.csv'
data = read_data(file_path)
processed_data = process_data(data)
average_lap_times, total_points = analyze_performance(processed_data)
visualize_results(average_lap_times, total_points)
```

#### Detailed Instructions:
**Step 1: Read the F1 race data from the provided CSV file using pandas.**
- Use the `pd.read_csv()` function to read the race results data from `data/f1_race_results.csv`.

**Step 2: Process the data to handle missing values and rename columns for clarity.**
- Drop rows with missing values using `dropna()`.
- Rename relevant columns (e.g., 'Driver' to 'DriverName', 'Pos' to 'Position').

**Step 3: Analyze the data to uncover key performance insights.**
- Calculate the average lap times for each driver using the `groupby()` and `mean()` functions.
- Calculate the total points for each driver using the `groupby()` and `sum()` functions.

**Step 4: Generate a comprehensive report and visualize the results.**
- Create bar plots visualizing the average lap times per driver using Seaborn.
- Create bar plots visualizing the total points per driver using Seaborn.

#### Criteria for Success and Evaluation:
**Success Criteria:**
- The application correctly reads and processes the F1 race data.
- The analysis provides accurate and meaningful insights into driver performance.
- The summary report includes visualizations of average lap times and total points per driver.

**Evaluation Rubric:**
- **Data Loading and Cleaning (20%)**: Correctly reads data and handles missing values.
- **Data Transformation (20%)**: Appropriately renames columns and calculates performance metrics.
- **Analysis (20%)**: Provides accurate and meaningful performance insights.
- **Visualization (20%)**: Generates clear and informative visualizations.
- **Reporting (20%)**: Creates a comprehensive report summarizing key performance insights.

These assignments are designed to challenge you to apply your knowledge of data analysis and visualization using Pandas, while aligning with your specific interests in Formula 1 Racing and Stock Market Investing. By completing these assignments, you'll gain practical experience and build a portfolio of projects to showcase to recruiters, advancing your career goals as a Python Developer.