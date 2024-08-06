## Personalized Curriculum: Advanced Python Concepts

**Module Title:** Advanced Python Concepts

**Assignment Description:** 
Assignment 1: Write a program that reads a text file and counts the frequency of each word.

---

### Lecture Content: Advanced Python Concepts - Lecture 1: Lists, Tuples, and Dictionaries

---

#### 1. Introduction

Welcome to the first lecture of the "Advanced Python Concepts" module. Today, we will delve into the fundamental data structures in Python: Lists, Tuples, and Dictionaries. These structures are crucial for any Python developer, providing the foundations for data manipulation and storage. Understanding these concepts is essential for tasks such as automating stock market analysis, building race track simulators, and developing investment portfolio apps. By the end of this lecture, you will be well-equipped to use these data structures in your projects, particularly in the realms of Formula 1 racing data analysis and financial applications.

---

#### 2. Key Concepts

**Lists**

- **Definition**: A list is an ordered collection of items that are changeable (mutable). Lists are defined using square brackets `[]`.
- **Characteristics**:
  - Ordered
  - Mutable
  - Allows duplicates
- **Example**:
  ```python
  f1_racers = ["Hamilton", "Verstappen", "Leclerc"]
  ```

**Tuples**

- **Definition**: A tuple is an ordered collection of items that are immutable. Tuples are defined using parentheses `()`.
- **Characteristics**:
  - Ordered
  - Immutable
  - Allows duplicates
- **Example**:
  ```python
  f1_podium = ("Hamilton", "Verstappen", "Leclerc")
  ```

**Dictionaries**

- **Definition**: A dictionary is an unordered collection of key-value pairs. Dictionaries are defined using curly braces `{}` with a mapping of unique keys to values.
- **Characteristics**:
  - Unordered
  - Mutable
  - Keys must be unique
- **Example**:
  ```python
  f1_driver_stats = {
      "Hamilton": {"wins": 95, "team": "Mercedes"},
      "Verstappen": {"wins": 20, "team": "Red Bull"},
      "Leclerc": {"wins": 2, "team": "Ferrari"}
  }
  ```

---

#### 3. Real-world Examples

**Example 1: Analyzing F1 Race Data**

Let's say you want to analyze the positions of drivers in a race:

- **Lists**: Store the order of drivers as they finish the race.
  ```python
  race_results = ["Hamilton", "Verstappen", "Leclerc", "Norris", "Ricciardo"]
  ```
- **Tuples**: Store unchangeable start positions of drivers.
  ```python
  start_positions = ("Hamilton", "Verstappen", "Leclerc", "Norris", "Ricciardo")
  ```
- **Dictionaries**: Store detailed statistics for each driver.
  ```python
  driver_stats = {
      "Hamilton": {"wins": 95, "team": "Mercedes"},
      "Verstappen": {"wins": 20, "team": "Red Bull"},
      "Leclerc": {"wins": 2, "team": "Ferrari"},
      "Norris": {"wins": 0, "team": "McLaren"},
      "Ricciardo": {"wins": 8, "team": "McLaren"}
  }
  ```

**Example 2: Automating Stock Market Analysis**

- **Lists**: Track daily closing prices of a stock.
  ```python
  closing_prices = [150.0, 152.5, 153.0, 151.5, 150.0]
  ```
- **Tuples**: Store historical stock prices (immutable).
  ```python
  historical_prices = (148.0, 149.5, 150.0, 150.5, 151.0)
  ```
- **Dictionaries**: Store stock details.
  ```python
  stock_details = {
      "AAPL": {"price": 150.0, "volume": 1200000},
      "TSLA": {"price": 700.0, "volume": 800000},
      "AMZN": {"price": 3300.0, "volume": 500000}
  }
  ```

---

#### 4. Interactive Exercises

**Exercise 1: Track F1 Race Results**

Create a list to store the results of the top 5 drivers in the latest F1 race. Then, convert this list into a tuple to represent the start positions (which should not change).

**Exercise 2: Driver Statistics Dictionary**

Create a dictionary to store the number of wins and the team name for the top 3 drivers in the current F1 season.

**Exercise 3: Stock Market Analysis**

1. Create a list of closing prices for a stock over the past week.
2. Convert this list into a tuple to represent immutable historical data.
3. Create a dictionary to store the details (price and volume) of at least 3 different stocks.

---

#### 5. Summary and Next Steps

In this lecture, we covered the basics of Lists, Tuples, and Dictionaries in Python. These data structures are foundational for storing and manipulating data efficiently. We explored practical examples from Formula 1 racing and stock market analysis to illustrate their applications. 

**Next Steps**: In the upcoming lecture, we will explore more advanced data structures, such as sets and custom objects, and how they can be used for more complex data manipulation tasks. Stay tuned to learn how to leverage Python's full potential in your projects!

---

#### Multimedia Elements

- **Diagrams**: Include diagrams illustrating the structure of lists, tuples, and dictionaries.
- **Videos**: Short video tutorials explaining each data structure.
- **Quizzes**: Interactive quizzes to test understanding of lists, tuples, and dictionaries.

---

Thank you for joining this lecture. Happy coding!

---

### Assignments

---

### Assignment 1: Formula 1 Race Data Analyzer

**Problem Statement:**

Develop a program that reads a text file containing Formula 1 race results and counts the frequency of each driver's name. The program should then display the results in a sorted manner.

**Requirements.txt:**
```
pandas
```

**Starter Code:**
```python
import pandas as pd

def read_data(file_path):
    with open(file_path, 'r') as file:
        data = file.read()
    return data.split()

def count_frequencies(data):
    frequency = {}
    for word in data:
        if word in frequency:
            frequency[word] += 1
        else:
            frequency[word] = 1
    return frequency

def display_results(frequency):
    sorted_frequency = dict(sorted(frequency.items(), key=lambda item: item[1], reverse=True))
    for driver, count in sorted_frequency.items():
        print(f"{driver}: {count}")

# Provide the file path and call the functions
file_path = 'race_results.txt'
data = read_data(file_path)
frequency = count_frequencies(data)
display_results(frequency)
```

**Detailed Instructions:**

1. **Step 1**: Read the race results from the provided text file using the `read_data` function.
2. **Step 2**: Process the data to count the frequency of each driver's name using the `count_frequencies` function.
3. **Step 3**: Display the results in descending order of frequency using the `display_results` function.

**Criteria for Success and Evaluation:**

- The program correctly reads and processes the data from the text file.
- The program accurately counts the frequency of each driver's name.
- The results are displayed in descending order of frequency.

---

### Assignment 2: Stock Market Data Processor

**Problem Statement:**

Create a Python program that reads a CSV file containing stock market prices and volumes, processes the data to calculate daily changes, and generates a summary report.

**Requirements.txt:**
```
pandas
numpy
```

**Starter Code:**
```python
import pandas as pd
import numpy as np

def read_stock_data(file_path):
    return pd.read_csv(file_path)

def calculate_daily_changes(data):
    data['Change'] = data['Close'] - data['Open']
    return data

def generate_summary_report(data):
    summary = data.describe()
    print(summary)

# Provide the file path and call the functions
file_path = 'stock_data.csv'
data = read_stock_data(file_path)
data = calculate_daily_changes(data)
generate_summary_report(data)
```

**Detailed Instructions:**

1. **Step 1**: Read the stock data from the provided CSV file using the `read_stock_data` function.
2. **Step 2**: Process the data to calculate daily changes in stock prices using the `calculate_daily_changes` function.
3. **Step 3**: Generate a summary report that includes key statistics using the `generate_summary_report` function.

**Criteria for Success and Evaluation:**

- The program correctly reads and processes the stock data from the CSV file.
- The program accurately calculates daily changes in stock prices.
- The summary report includes key statistics and provides valuable insights.

---

### Assignment 3: Healthcare Data Dashboard

**Problem Statement:**

Develop an interactive dashboard that reads healthcare data from a CSV file, processes the data to provide key insights, and visualizes the results using plots and charts.

**Requirements.txt:**
```
pandas
matplotlib
dash
```

**Starter Code:**
```python
