# Lecture 4: File Handling

## Introduction

Welcome to Lecture 4 of the Advanced Python Concepts module! Today, we will explore the essential topic of File Handling in Python. As an aspiring Python Developer, mastering file handling is crucial because it allows you to read from and write to files, manage data storage, and manipulate file data efficiently. This skill is particularly important for various applications, such as automating data analysis tasks, developing applications that require data persistence, and creating dynamic web content.

By the end of this lecture, you'll understand the fundamental operations for working with files in Python, including opening, reading, writing, and closing files. You'll also learn how to handle different file types and manage file operations safely and efficiently.

## Key Concepts

### 1. Understanding File Operations

#### Opening Files
- **Syntax**: `open(filename, mode)`
- **Modes**:
  - `'r'`: Read (default mode)
  - `'w'`: Write (creates a new file or truncates an existing file)
  - `'a'`: Append (adds content to the end of the file)
  - `'b'`: Binary mode (for non-text files)
  - `'t'`: Text mode (default)
  - `'+'`: Updating (reading and writing)

#### Reading Files
- **Methods**:
  - `read()`: Reads the entire file
  - `readline()`: Reads a single line from the file
  - `readlines()`: Reads all lines into a list

#### Writing Files
- **Methods**:
  - `write()`: Writes a string to the file
  - `writelines()`: Writes a list of strings to the file

#### Closing Files
- **Syntax**: `file.close()`
- Use of `with` statement to handle files, which ensures proper closure:
  ```python
  with open('file.txt', 'r') as file:
      content = file.read()
  ```

### 2. Handling Different File Types

#### Text Files
- Common operations include reading and writing strings and handling line breaks.

#### Binary Files
- Used for non-text files like images, videos, or any file that requires binary mode.
- Example: Reading an image file
  ```python
  with open('image.png', 'rb') as file:
      binary_data = file.read()
  ```

### 3. Error Handling in File Operations
- Using `try-except` blocks to handle potential errors such as `FileNotFoundError`, `IOError`, etc.
  ```python
  try:
      with open('file.txt', 'r') as file:
          content = file.read()
  except FileNotFoundError:
      print("The file was not found.")
  ```

### 4. Efficient File Handling
- Use of `with` statement for better resource management.
- Avoiding memory overload by reading large files in chunks.

## Real-world Examples

### Automating Stock Market Analysis
Imagine you are developing a Python script to automate stock market analysis. You can use file handling to read historical stock price data from CSV files, analyze trends, and generate reports.

```python
import csv

# Reading stock data from a CSV file
with open('stock_data.csv', 'r') as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

### Analyzing F1 Race Data
You might want to analyze F1 race lap times stored in a text file. By reading the file and processing the data, you can gain insights into performance.

```python
with open('race_lap_times.txt', 'r') as file:
    lap_times = file.readlines()

# Convert lap times to float and analyze
lap_times = [float(time.strip()) for time in lap_times]
average_time = sum(lap_times) / len(lap_times)
print(f"Average Lap Time: {average_time}")
```

## Interactive Exercises

### Exercise 1: Reading and Writing Race Data
Create a program that reads F1 race data from a file, processes it, and writes the processed data to a new file.

**Task**:
1. Read lap times from `race_data.txt`.
2. Calculate the fastest lap time.
3. Write the fastest lap time to `fastest_lap.txt`.

```python
# Sample code to get you started
with open('race_data.txt', 'r') as file:
    lap_times = file.readlines()

lap_times = [float(time.strip()) for time in lap_times]
fastest_lap = min(lap_times)

with open('fastest_lap.txt', 'w') as file:
    file.write(f"Fastest Lap Time: {fastest_lap}")
```

### Exercise 2: Stock Market Data Analysis
Write a Python script that reads stock prices from a CSV file, calculates the daily percentage change, and writes the results to a new CSV file.

```python
import csv

with open('stock_prices.csv', 'r') as file:
    reader = csv.reader(file)
    header = next(reader)
    prices = [row for row in reader]

daily_changes = []
for i in range(1, len(prices)):
    previous_close = float(prices[i-1][1])
    current_close = float(prices[i][1])
    daily_change = (current_close - previous_close) / previous_close * 100
    daily_changes.append([prices[i][0], daily_change])

with open('daily_changes.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(['Date', 'Daily Change (%)'])
    writer.writerows(daily_changes)
```

## Summary and Next Steps

In this lecture, we explored the fundamentals of file handling in Python, including opening, reading, writing, and closing files. We also discussed handling different file types and managing file operations efficiently. By working through real-world examples and interactive exercises, you should now have a solid understanding of how to apply these concepts to your projects.

### What's Next?

In the next lecture, we will dive into **5. Working with APIs**, where you'll learn how to interact with web APIs to fetch and manipulate data. This is an essential skill for developing web applications and integrating third-party services into your projects. Stay tuned!

---

Remember to practice these concepts by working on the suggested exercises and exploring additional resources to deepen your understanding. Happy coding!