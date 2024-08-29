### Module Title: Data Analysis with Pandas and Visualization with Matplotlib

### Exercise Requirements

#### 1. Problem Statement
You are tasked with analyzing stock price fluctuations for a healthcare company over the past year. Using the skills you learned in the lecture on data visualization with Matplotlib and Seaborn, you will create visualizations that help identify trends in the company's stock prices. Your analysis should focus on how the stock price has changed over time, and you should also compare it to key events in the healthcare sector that may have influenced these fluctuations.

#### 2. Fill-in-the-Blank Starter Code
Below is the starter code that you will need to complete. Fill in the blanks to implement the functionality required to analyze and visualize the stock price data.

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Sample dataset representing stock prices over time
data = {
    'Date': ['2023-01-01', '2023-02-01', '2023-03-01', '2023-04-01', '2023-05-01', 
             '2023-06-01', '2023-07-01', '2023-08-01', '2023-09-01', '2023-10-01'],
    'Stock Price': [100, 105, 102, 110, 107, 115, 120, 125, 130, 128]
}

# Convert the data into a DataFrame
df = pd.DataFrame(data)

# Convert 'Date' column to datetime format
df['Date'] = pd.to_datetime(df['Date'])

# Plotting the stock price over time
plt.figure(figsize=(10, 5))
plt.plot(df['Date'], df['Stock Price'], marker='o', label='Stock Price')
plt.title('Stock Price Fluctuations of Healthcare Company')
plt.xlabel('Date')
plt.ylabel('Stock Price (USD)')
plt.xticks(rotation=45)
plt.legend()
plt.tight_layout()
plt.show()

# Creating a bar chart to visualize average stock price per quarter
df['Quarter'] = df['Date'].dt.to_period('Q')
average_price = df.groupby('Quarter')['Stock Price'].mean().reset_index()

sns.barplot(x='Quarter', y='Stock Price', data=average_price)
plt.title('Average Stock Price per Quarter')
plt.xlabel('Quarter')
plt.ylabel('Average Stock Price (USD)')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

#### 3. Hints
- **Hint 1**: Remember to import necessary libraries at the top of your code.
- **Hint 2**: When converting dates, ensure you use the correct function from pandas.
- **Hint 3**: For the line plot, use `plt.plot()` to visualize how stock prices change over time. Make sure to label your axes clearly.
- **Hint 4**: To create a bar chart, group your data by quarter and calculate the average stock price for each quarter.

#### 4. Expected Outcome
By completing this exercise, you should be able to:
- Visualize stock price fluctuations over time using a line plot.
- Create a bar chart that shows average stock prices per quarter.
- Demonstrate an understanding of how to manipulate and visualize data using Pandas and Matplotlib.
- Provide clear labels and titles for your visualizations, enhancing their readability.

Your final solution should include well-commented code that explains each step, ensuring clarity and adherence to best practices in data visualization.