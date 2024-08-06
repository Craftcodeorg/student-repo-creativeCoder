### Personalized Curriculum for "Introduction to Python"

#### Module Title: Introduction to Python

---

### Assignment 1: Basic Age Program

**Problem Statement:**

Write a program that asks the user for their age and prints whether they are a minor or an adult.

**Requirements.txt:**

```
No external libraries required
```

**Starter Code:**

```python
# Starter code for the age program
def check_age():
    # Ask the user for their age
    age = int(input("Please enter your age: "))
    
    # Determine if they are a minor or an adult
    if age < 18:
        print("You are a minor.")
    else:
        print("You are an adult.")

# Call the function to execute the program
check_age()
```

**Detailed Instructions:**

1. **Step 1:** Create a function named `check_age`.
2. **Step 2:** Inside the function, use the `input()` function to ask the user for their age and convert it to an integer.
3. **Step 3:** Use an `if-else` statement to determine if the age is less than 18. If it is, print "You are a minor." Otherwise, print "You are an adult."
4. **Step 4:** Call the `check_age()` function to run the program.

**Criteria for Success and Evaluation:**

- The program should correctly ask the user for their age.
- It should accurately determine and print whether the user is a minor or an adult based on the input age.
- Code should be clean, well-commented, and easy to understand.

---

### Assignment 2: Analyzing F1 Race Data

**Problem Statement:**

Develop a Python application that reads Formula 1 race data from a CSV file, processes the data to identify key insights, and generates a summary report.

**Requirements.txt:**

```
pandas
matplotlib
```

**Starter Code:**

```python
# Starter code for F1 race data analysis application
import pandas as pd
import matplotlib.pyplot as plt

def read_data(file_path):
    return pd.read_csv(file_path)

def process_data(data):
    # Calculate the average speed of each driver
    average_speed = data.groupby('driver')['speed'].mean()
    return average_speed

def generate_report(data):
    # Plot the average speed of each driver
    data.plot(kind='bar')
    plt.title('Average Speed of Each Driver')
    plt.xlabel('Driver')
    plt.ylabel('Average Speed')
    plt.show()

# Provide the file path and call the functions
file_path = 'f1_race_data.csv'
data = read_data(file_path)
processed_data = process_data(data)
generate_report(processed_data)
```

**Detailed Instructions:**

1. **Step 1:** Read the data from the provided CSV file using `pandas`.
2. **Step 2:** Process the data to calculate the average speed of each driver.
3. **Step 3:** Generate a bar plot using `matplotlib` to visualize the average speed of each driver.
4. **Step 4:** Ensure the plot includes appropriate titles and labels.

**Criteria for Success and Evaluation:**

- The application should correctly read the race data from the CSV file.
- It should accurately calculate and display the average speed of each driver.
- The generated report should be clear, well-labeled, and visually informative.

---

### Assignment 3: Creating a Stock Market Dashboard

**Problem Statement:**

Create a simple stock market dashboard that fetches historical stock prices using a financial API, processes the data, and visualizes stock trends.

**Requirements.txt:**

```
pandas
matplotlib
requests
```

**Starter Code:**

```python
# Starter code for stock market dashboard
import pandas as pd
import matplotlib.pyplot as plt
import requests

def fetch_stock_data(symbol, api_key):
    url = f'https://www.alphavantage.co/query?function=TIME_SERIES_DAILY&symbol={symbol}&apikey={api_key}'
    response = requests.get(url)
    data = response.json()
    return data

def process_data(data):
    # Convert the JSON data to a DataFrame
    df = pd.DataFrame(data['Time Series (Daily)']).T
    df = df.astype(float)
    return df

def visualize_data(df, symbol):
    # Plot the stock prices
    df['4. close'].plot()
    plt.title(f'Stock Prices for {symbol}')
    plt.xlabel('Date')
    plt.ylabel('Closing Price')
    plt.show()

# Fetch and process stock data
symbol = 'AAPL'
api_key = 'your_api_key_here'
data = fetch_stock_data(symbol, api_key)
df = process_data(data)
visualize_data(df, symbol)
```

**Detailed Instructions:**

1. **Step 1:** Fetch historical stock prices using `requests`.
2. **Step 2:** Process the data to convert it into a `pandas` DataFrame.
3. **Step 3:** Visualize the closing stock prices over time using `matplotlib`.
4. **Step 4:** Ensure the plot includes appropriate titles and labels.

**Criteria for Success and Evaluation:**

- The application should correctly fetch stock data from the API.
- It should accurately process the data into a usable format.
- The generated visualization should be clear, well-labeled, and provide insightful information about stock trends.

---

### Assignment 4: Automating Stock Market Analysis

**Problem Statement:**

Build an application that automates the analysis of stock market data, identifying key trends and generating alerts for significant price changes.

**Requirements.txt:**

```
pandas
matplotlib
requests
```

**Starter Code:**

```python
# Starter code for automating stock market analysis
import pandas as pd
import matplotlib.pyplot as plt
import requests

def fetch_stock_data(symbol, api_key):
    url = f'https://www.alphavantage.co/query?function=TIME_SERIES_DAILY&symbol={symbol}&apikey={api_key}'
    response = requests.get(url)
    data = response.json()
    return data

def process_data(data):
    # Convert the JSON data to a DataFrame
    df = pd.DataFrame(data['Time Series (Daily)']).T
    df = df.astype(float)
    return df

def analyze_data(df):
    # Identify significant price changes
    df['Price Change'] = df['4. close'].diff()
    significant_changes = df[df['Price Change'].abs() > 5]
    return significant_changes

def generate_alerts(changes):
    for index, row in changes.iterrows():
        print(f"Significant price change on {index}: {row['Price Change']}")

# Fetch and process stock data
symbol = 'AAPL'
api_key = 'your_api_key_here'
data = fetch_stock_data(symbol, api_key)
df = process_data(data)
changes = analyze_data(df)
generate_alerts(changes)
```

**Detailed Instructions:**

1. **Step 1:** Fetch historical stock prices using `requests`.
2. **Step 2:** Process the data into a `pandas` DataFrame.
3. **Step 3:** Identify significant price changes (e.g., changes greater than $5).
4. **Step 4:** Generate alerts for significant price changes by printing messages to the console.

**Criteria for Success and Evaluation:**

- The application should correctly fetch and process stock data.
- It should accurately identify significant price changes.
- The generated alerts should be clear and informative.

---

### Summary and Next Steps

In this personalized curriculum, you have been provided with assignments that integrate real-world applications, particularly focusing on Formula 1 Racing and relevant practices in Healthcare. These assignments encourage the practical application of concepts covered in the lecture, challenging you to solve problems or create projects that reflect real-world scenarios.

Next, we will dive deeper into Python's syntax and control structures, setting the foundation for writing more complex programs. We will also explore more advanced applications in web development, data analysis, and automation.

Stay tuned, and get ready to unlock the full potential of Python in the upcoming lectures!

---

**Note:**

For all assignments requiring an API key (e.g., Alpha Vantage), ensure you sign up and obtain your own API key to replace the placeholder `'your_api_key_here'`.