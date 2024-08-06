### Lecture 5: Control Structures: If Statements, Loops

#### 1. **Introduction**
Welcome to Lecture 5 of our "Introduction to Python" module. In this lecture, we will dive into control structures, specifically focusing on `if` statements and loops. Understanding control structures is crucial for any Python developer, as they enable you to dictate the flow of your code based on conditions and repetitions. This lecture will show how these concepts can be applied to automate tasks, analyze data, and build complex applications — skills essential for a budding Python developer, especially in fields like Formula 1 Racing and stock market analysis.

#### 2. **Key Concepts**

##### If Statements
- **Definition**: `If` statements allow you to execute a block of code only if a specified condition is true.
- **Syntax**:
  ```python
  if condition:
      # code to execute if condition is true
  ```
- **Example**:
  ```python
  lap_time = 72
  if lap_time < 75:
      print("Fast lap!")
  ```

##### Else and Elif
- **Else**: Provides an alternative block of code if the condition in the `if` statement is false.
  ```python
  if condition:
      # code if condition is true
  else:
      # code if condition is false
  ```
- **Elif**: Allows you to check multiple conditions.
  ```python
  if condition1:
      # code if condition1 is true
  elif condition2:
      # code if condition2 is true
  else:
      # code if both conditions are false
  ```

##### Loops
- **For Loop**: Repeats a block of code for a specified number of iterations.
  ```python
  for i in range(5):
      print(i)
  ```
- **While Loop**: Repeats a block of code as long as a condition is true.
  ```python
  count = 0
  while count < 5:
      print(count)
      count += 1
  ```

#### 3. **Real-world Examples**

##### Example 1: Automating Lap Time Analysis
- **Scenario**: Calculate average lap times for a Formula 1 driver and determine if any lap was exceptionally fast or slow.
- **Code Snippet**:
  ```python
  lap_times = [72, 74, 70, 69, 71]
  total_time = 0
  for lap in lap_times:
      total_time += lap
  average_time = total_time / len(lap_times)
  
  for lap in lap_times:
      if lap < 70:
          print(f"Lap time {lap} is exceptionally fast!")
      elif lap > 74:
          print(f"Lap time {lap} is exceptionally slow!")
      else:
          print(f"Lap time {lap} is average.")
  ```

##### Example 2: Stock Market Trend Analysis
- **Scenario**: Analyze stock prices and identify days with significant price drops.
- **Code Snippet**:
  ```python
  stock_prices = [150, 145, 148, 142, 143]
  for i in range(1, len(stock_prices)):
      if stock_prices[i] < stock_prices[i-1] * 0.95:
          print(f"Significant drop on day {i+1}: {stock_prices[i]}")
  ```

#### 4. **Interactive Exercises**

##### Exercise 1: F1 Lap Time Checker
- **Task**: Write a Python script that takes a list of lap times and identifies the fastest and slowest laps.
- **Hint**: Use `for` loops and `if` statements to compare lap times.
  
##### Exercise 2: Stock Market Analyzer
- **Task**: Create a script that analyzes a list of stock prices and prints out any days where the stock price increased by more than 5% compared to the previous day.
- **Hint**: Use a `for` loop and an `if` statement to compare the stock prices.

##### Exercise 3: Investment Portfolio Manager
- **Task**: Simulate a simple investment portfolio. Write a script that checks if the total portfolio value exceeds a certain threshold and prints a congratulatory message if it does.
- **Hint**: Use a `while` loop to simulate the portfolio value over time.

#### 5. **Summary and Next Steps**
In this lecture, we've explored the basics of `if` statements and loops, foundational tools that allow you to control the flow of your Python programs. Whether you're analyzing F1 lap times or stock prices, these control structures are instrumental in creating efficient and functional code.

**Next Steps**: In our next lecture, we will delve into functions in Python. Functions allow you to encapsulate code into reusable blocks, making your programs more modular and easier to maintain. Stay tuned as we continue to build your skills as a Python developer!

---

Incorporating multimedia elements such as diagrams to explain the flow of control structures, short video tutorials, and interactive quizzes can significantly enhance your learning experience. Make sure to use these resources to solidify your understanding. Happy coding!