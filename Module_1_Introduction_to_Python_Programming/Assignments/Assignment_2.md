### Assignment: Create a Program that Simulates a Stock Price Tracker with User-Defined Inputs

#### Problem Statement:
As a beginner Python programmer interested in stock market analysis, your task is to create a simple program that simulates a stock price tracker. This program will allow users to input stock prices for a specific company and track the changes over time. The goal is to help users understand how to manipulate data and visualize trends, which is essential for making informed investment decisions in the healthcare industry.

#### Starter Code:
Below is a basic framework for your stock price tracker program. Your task is to expand upon this code by implementing the necessary functionalities.

```python
# Starter code for a stock price tracker

# Import necessary libraries
import matplotlib.pyplot as plt

def track_stock_prices():
    # Step 1: Initialize an empty list to hold stock prices
    stock_prices = []
    days = int(input("Enter the number of days you want to track: "))

    # Step 2: Gather stock prices from the user
    for day in range(1, days + 1):
        price = float(input(f"Enter the stock price for day {day}: "))
        stock_prices.append(price)

    # Step 3: Calculate average price
    average_price = sum(stock_prices) / len(stock_prices)
    
    # Step 4: Identify days where the price exceeded the average
    above_average_days = [i + 1 for i, price in enumerate(stock_prices) if price > average_price]

    # Step 5: Display results
    print(f"\nAverage Stock Price: {average_price:.2f}")
    print(f"Days with prices above average: {above_average_days}")

    # Step 6: Plotting the stock prices
    plt.plot(range(1, days + 1), stock_prices, marker='o')
    plt.axhline(y=average_price, color='r', linestyle='--', label='Average Price')
    plt.title('Stock Price Tracker')
    plt.xlabel('Days')
    plt.ylabel('Stock Price')
    plt.xticks(range(1, days + 1))
    plt.legend()
    plt.grid()
    plt.show()

# Call the function to run the tracker
track_stock_prices()
```

#### Detailed Instructions:
1. **User Input**: Modify the program to allow users to input the name of the stock they are tracking. Store this information and display it in the output.
   
2. **Enhance Data Collection**: Add functionality to allow users to input whether each day's price is higher or lower than the previous day. Store this information and display it alongside the prices.

3. **Calculate Percentage Change**: Implement a feature that calculates the percentage change in stock prices from one day to the next and display this information.

4. **Output Formatting**: Enhance the output to show a clear summary of the stock's performance over the tracked days, including:
   - The average price.
   - Days where prices were above average.
   - Percentage changes between consecutive days.

5. **Error Handling**: Add error handling to ensure that user inputs are valid (e.g., non-negative numbers for stock prices).

#### Criteria for Success and Evaluation:
- **Functionality**: The program should correctly collect and display stock prices, calculate averages, and identify days above average.
- **Code Quality**: The code should be clean, well-structured, and include comments explaining each section.
- **User Experience**: The output should be formatted clearly and provide useful insights to the user.
- **Error Handling**: The program should gracefully handle invalid inputs without crashing.

By completing this assignment, you will not only reinforce your understanding of Python basics but also gain practical experience in data manipulation and visualization, which are valuable skills in both healthcare and finance sectors.