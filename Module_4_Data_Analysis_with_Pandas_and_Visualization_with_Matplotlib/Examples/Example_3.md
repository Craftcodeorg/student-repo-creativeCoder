# Module Title: Data Analysis with Pandas and Visualization with Matplotlib

## Example 3: Plotting Stock Prices Over Time with Matplotlib

### 1. Introduction
In the context of healthcare, visualizing stock prices over time can provide valuable insights into the financial health of pharmaceutical companies, biotech firms, and healthcare providers. Understanding stock trends can inform investment decisions, helping stakeholders make educated choices about where to allocate resources. This example builds upon the key concepts discussed in the lecture on visualizing data with Matplotlib and Seaborn, focusing on how these techniques can be applied to analyze financial data relevant to the healthcare industry.

### 2. Code Snippet
Here’s a simple code snippet that demonstrates how to plot stock prices over time using Matplotlib. This code is designed for beginner-level programmers and includes error handling and best practices.

```python
import matplotlib.pyplot as plt
import pandas as pd

# Sample Data: Simulated stock prices for a healthcare company over a week
data = {
    'Date': ['2023-10-01', '2023-10-02', '2023-10-03', '2023-10-04', '2023-10-05', '2023-10-06', '2023-10-07'],
    'Stock Price': [150, 152, 153, 149, 155, 157, 158]
}

# Create a DataFrame
try:
    df = pd.DataFrame(data)
    df['Date'] = pd.to_datetime(df['Date'])  # Convert to datetime format
except Exception as e:
    print(f"Error creating DataFrame: {e}")

# Plotting the stock prices
try:
    plt.figure(figsize=(10, 5))
    plt.plot(df['Date'], df['Stock Price'], marker='o', color='blue', label='Stock Price')
    plt.title('Healthcare Company Stock Prices Over Time')
    plt.xlabel('Date')
    plt.ylabel('Stock Price (USD)')
    plt.xticks(rotation=45)  # Rotate date labels for better readability
    plt.legend()
    plt.grid()
    plt.tight_layout()  # Adjust layout to prevent clipping of labels
    plt.show()
except Exception as e:
    print(f"Error plotting data: {e}")
```

### 3. Explanation
1. **Import Libraries**: The code begins by importing the necessary libraries, `matplotlib.pyplot` for plotting and `pandas` for data manipulation.
   
2. **Sample Data**: A dictionary containing simulated stock prices for a healthcare company over a week is created. This data is then converted into a Pandas DataFrame for easier manipulation.

3. **Error Handling**: The code includes try-except blocks to catch any potential errors when creating the DataFrame or plotting the data. This ensures that if something goes wrong, the program will output a meaningful error message instead of crashing.

4. **Plotting**: 
   - A figure is created with a specified size.
   - The `plot` function is used to create a line graph of stock prices over time, marking each data point with circles.
   - Titles and labels are added for clarity.
   - The x-ticks (dates) are rotated for better readability.
   - A legend and grid are added to enhance the visualization.
   - Finally, `plt.show()` displays the plot.

### 4. Application
In healthcare, analyzing stock prices can help stakeholders identify trends that may impact investment decisions. For example, if a pharmaceutical company announces promising clinical trial results, its stock price may rise significantly. By visualizing this data over time, investors can observe patterns and make informed decisions regarding buying or selling stocks.

Moreover, healthcare organizations can use such visualizations to monitor their own financial performance or that of their partners. This can lead to more strategic planning and resource allocation, ultimately improving operational efficiency and patient care.

### Integration
This content is structured with clear headings and sections for easy parsing and integration into the learning platform. The use of markdown formatting ensures that the information is presented in an organized manner, making it accessible for learners at all levels. By applying these concepts in real-world scenarios within healthcare, learners can develop practical skills that enhance their understanding of both data analysis and the industry itself.