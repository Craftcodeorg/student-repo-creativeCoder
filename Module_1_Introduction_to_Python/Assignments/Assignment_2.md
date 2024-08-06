### Assignment Creation Guidelines ###

Based on the comprehensive coverage of the "Introduction to Python" module, including topics such as those covered in the lectures:

### Module Information ###
- **Module Title**: Introduction to Python
- **Lecture Title**: 2. Setting up Python environment and tools
- **Lecture Description**: This lecture covers 2. Setting up Python environment and tools

### User Profile ###
- **Interest**: Formula 1 Racing, Stock Market Investing, Web Development for Finance, Data Analysis in Sports, Creating Interactive Dashboards, Automating Stock Market Analysis, Building F1 Race Track Simulators, Developing Investment Portfolio Apps, Visualizing Stock Market Trends, Analyzing F1 Race Data
- **Career Goal**: Python Developer

### Previous Lectures ###
1. Introduction to Python and its applications

---

## Lecture: 2. Setting up Python environment and tools

### 1. Introduction
Welcome to the second lecture of the "Introduction to Python" module. In this lecture, we will guide you through the essential steps of setting up your Python environment and tools. A well-configured environment is crucial for any Python Developer as it forms the foundation for writing, testing, and running your Python code efficiently.

By the end of this lecture, you'll be equipped with the knowledge to set up Python on your machine, understand the use of Integrated Development Environments (IDEs), and manage packages using tools like pip. This setup is particularly important if you're aiming to develop Python applications in areas such as Formula 1 Racing data analysis or automating stock market analysis.

### 2. Key Concepts
#### Installing Python
- **Downloading Python**: Visit the official Python website (https://www.python.org/) and download the latest version compatible with your operating system (Windows, macOS, Linux).
- **Installation Process**: Follow the on-screen instructions to install Python. Ensure to check the box that says "Add Python to PATH" for ease of use from the command line.

#### Integrated Development Environments (IDEs)
- **IDEs Overview**: An IDE is a software application that provides comprehensive facilities to programmers for software development. Popular Python IDEs include PyCharm, VS Code, and Jupyter Notebook.
- **Choosing an IDE**: For beginners, VS Code is highly recommended due to its versatility and extensive community support. For data analysis and visualization, Jupyter Notebook is ideal.

#### Setting up VS Code
- **Installing VS Code**: Download and install Visual Studio Code from https://code.visualstudio.com/.
- **Python Extension**: Install the Python extension for VS Code, which provides rich support for Python including IntelliSense (autocompletion), linting, debugging, and more.

#### Setting up Jupyter Notebook
- **Installing Jupyter Notebook**: You can install Jupyter Notebook via pip by running `pip install notebook`.
- **Launching Jupyter Notebook**: Open a terminal or command prompt and type `jupyter notebook` to launch the interface in your web browser.

#### Package Management with pip
- **pip Overview**: pip is the package installer for Python. You can use pip to install and manage additional libraries and dependencies that are not part of the standard library.
- **Basic pip Commands**:
  - To install a package: `pip install package_name`
  - To upgrade a package: `pip install --upgrade package_name`
  - To list installed packages: `pip list`

### 3. Real-world Examples
#### Example 1: Setting up an Environment for Data Analysis in Formula 1 Racing
- **Scenario**: You want to analyze historical race data to predict future race outcomes.
- **Steps**:
  1. Install Python and ensure it's added to PATH.
  2. Install VS Code and the Python extension.
  3. Install necessary packages using pip: `pip install pandas numpy matplotlib seaborn`.
  4. Set up a Jupyter Notebook environment to visualize data interactively.

#### Example 2: Automating Stock Market Analysis
- **Scenario**: Automate retrieval and analysis of stock market data to make informed investment decisions.
- **Steps**:
  1. Install Python and add it to PATH.
  2. Install VS Code and the Python extension.
  3. Install necessary packages using pip: `pip install yfinance pandas`.
  4. Set up a script in VS Code to fetch and analyze stock data.

### 4. Interactive Exercises
#### Exercise 1: Setting up Python and VS Code
- **Task**: Follow the steps outlined to install Python and VS Code on your machine. Then, write a simple Python script in VS Code to print "Hello, Python!".
- **Objective**: Ensure you have a functioning Python environment and are comfortable using VS Code.

#### Exercise 2: Installing and Using Jupyter Notebook
- **Task**: Install Jupyter Notebook via pip and launch it. Create a new notebook and write a Python script to load a sample CSV file and display its contents.
- **Objective**: Get hands-on experience with Jupyter Notebook and loading data.

#### Exercise 3: Installing Packages with pip
- **Task**: Use pip to install the `pandas` and `matplotlib` packages. Create a simple script to load a dataset and plot a graph.
- **Objective**: Practice using pip and get familiar with basic data analysis and visualization.

### 5. Summary and Next Steps
In this lecture, you have learned how to set up your Python environment, choose and configure an IDE, and manage packages with pip. These skills are foundational for any Python Developer and will enable you to start building and running Python applications efficiently.

#### Key Takeaways:
- How to install Python and add it to PATH.
- The importance of IDEs and how to set up VS Code and Jupyter Notebook.
- Using pip for package management.

### Teaser for Next Lecture:
In the next lecture, we will dive into Python syntax and basic programming constructs. You'll learn about variables, data types, and control structures, which are essential building blocks for any Python application.

Stay tuned and keep practicing! The journey to mastering Python is just beginning.

---

### Assignment Components ###

#### Assignment 1: Formula 1 Race Data Analysis Application

**Problem Statement**: 
Develop a Python application that reads historical Formula 1 race data from a CSV file, processes the data to identify key insights (such as fastest laps and winning teams), and generates a summary report. 

**Requirements.txt**:
```
pandas
numpy
matplotlib
seaborn
```

**Starter Code**:
```python
# Starter code for F1 race data processing application
import pandas as pd

def read_data(file_path):
    return pd.read_csv(file_path)

def process_data(data):
    # Example processing: Calculate the average lap time
    data['average_lap_time'] = data['lap_times'].mean()
    return data

def generate_report(processed_data):
    # Example report generation: Print summary statistics
    print("Average Lap Time:", processed_data['average_lap_time'])
    # Add more report generation code here

# Provide the file path and call the functions
file_path = 'f1_race_data.csv'
data = read_data(file_path)
processed_data = process_data(data)
generate_report(processed_data)
```

**Detailed Instructions**:
1. **Step 1**: Read the data from the provided CSV file using pandas.
2. **Step 2**: Process the data to calculate insights such as average lap times, winning teams, and fastest laps.
3. **Step 3**: Generate a summary report that includes these key insights.
4. **Hint**: Use pandas' built-in functions like `mean()`, `groupby()`, and `describe()` to facilitate data processing.

**Criteria for Success and Evaluation**:
- **Success Criteria**: The application should correctly read and process the data, identify key insights, and generate an accurate summary report.
- **Evaluation Rubric**:
  - Correctly reads data from CSV: 20%
  - Accurate data processing and insight calculation: 40%
  - Comprehensive and clear report generation: 30%
  - Code readability and documentation: 10%

---

#### Assignment 2: Stock Market Analysis Automation

**Problem Statement**:
Create a Python script that automates the retrieval of stock market data, processes the data to identify trends, and visualizes the trends in a graphical format.

**Requirements.txt**:
```
pandas
yfinance
matplotlib
```

**Starter Code**:
```python
# Starter code for stock market analysis automation
import pandas as pd
import yfinance as yf
import matplotlib.pyplot as plt

def fetch_stock_data(ticker):
    stock_data = yf.download(ticker)
    return stock_data

def process_data(data):
    # Example processing: Calculate moving averages
    data['20_MA'] = data['Close'].rolling(window=20).mean()
    data['50_MA'] = data['Close'].rolling(window=50).mean()
    return data

def plot_data(data, ticker):
    plt.figure(figsize=(10, 5))
    plt.plot(data['Close'], label='Close Price')
    plt.plot(data['20_MA'], label='20 Day MA')
    plt.plot(data['50_MA'], label='50 Day MA')
    plt.title(f'{ticker} Stock Price and Moving Averages')
    plt.legend()
    plt.show()

# Provide the stock ticker and call the functions
ticker = 'AAPL'
data = fetch_stock_data(ticker)
processed_data = process_data(data)
plot_data(processed_data, ticker)
```

**Detailed Instructions**:
1. **