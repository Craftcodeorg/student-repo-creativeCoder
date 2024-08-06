### Module Title: Advanced Python Concepts

### Learning Objectives
- Understand and apply Example 3: Try-except block for error handling in practical scenarios.
- Enhance problem-solving skills with real-world applications.

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Preferred Learning Method: Project-based learning, interactive tutorials, and code-along videos

### Lecture Title: 3. Error and Exception Handling

#### 1. Introduction
Welcome to Lecture 3 of our Advanced Python Concepts module: Error and Exception Handling. As you aim to become a proficient Python Developer, mastering error and exception handling is crucial. This skill ensures your applications are robust, user-friendly, and maintainable. Whether you’re developing an F1 Race Track Simulator, automating stock market analysis, or building investment portfolio apps, understanding how to gracefully manage errors will significantly enhance the reliability of your projects.

In this lecture, we will explore how to identify, handle, and resolve errors and exceptions in Python. We’ll also look at best practices for implementing error handling in your code, ensuring your applications can handle unexpected situations without crashing.

#### 2. Key Concepts
**a. Understanding Errors and Exceptions**
- **Syntax Errors**: Occur when the Python parser detects a syntactical issue.
  - Example: `if True print("Hello")`
- **Exceptions**: Raised when an error is detected during execution.
  - Example: `1 / 0` raises a `ZeroDivisionError`.

**b. The try-except Block**
- **Basic Structure**:
  ```python
  try:
      # Code that might raise an exception
  except ExceptionType:
      # Code that runs if an exception occurs
  ```
- **Example**:
  ```python
  try:
      result = 10 / 0
  except ZeroDivisionError:
      print("You can't divide by zero!")
  ```

**c. Catching Multiple Exceptions**
- Using multiple except blocks to handle different exceptions:
  ```python
  try:
      # Code that might raise multiple exceptions
  except ZeroDivisionError:
      print("Division by zero error!")
  except ValueError:
      print("Value error!")
  ```

**d. The else and finally Clauses**
- **else**: Runs if no exceptions are raised.
  ```python
  try:
      result = 10 / 2
  except ZeroDivisionError:
      print("You can't divide by zero!")
  else:
      print("Division successful!")
  ```
- **finally**: Always runs, regardless of exceptions.
  ```python
  try:
      result = 10 / 2
  except ZeroDivisionError:
      print("You can't divide by zero!")
  finally:
      print("This block always runs")
  ```

**e. Custom Exceptions**
- Creating your own exception classes for specific situations.
  ```python
  class CustomError(Exception):
      pass

  try:
      raise CustomError("An error occurred")
  except CustomError as e:
      print(e)
  ```

#### 3. Real-world Examples
To illustrate these concepts, let’s explore how error and exception handling can be applied in areas like Formula 1 Racing and stock market investing.

**Example 1: Automating Stock Market Analysis**
- **Scenario**: You’re fetching stock data from an API. Sometimes, the API might be down or return invalid data.
  ```python
  import requests

  try:
      response = requests.get("https://api.stockmarket.com/data")
      response.raise_for_status()
      data = response.json()
  except requests.exceptions.HTTPError as http_err:
      print(f"HTTP error occurred: {http_err}")
  except requests.exceptions.RequestException as req_err:
      print(f"Error fetching data: {req_err}")
  except ValueError:
      print("Invalid JSON response")
  else:
      print("Data fetched successfully")
  finally:
      print("End of data fetch attempt")
  ```

**Example 2: F1 Race Track Simulator**
- **Scenario**: You’re simulating race conditions, and a division by zero might occur if the lap time is zero.
  ```python
  lap_times = [90, 85, 0, 75]

  for lap in lap_times:
      try:
          speed = 500 / lap
      except ZeroDivisionError:
          print("Lap time cannot be zero!")
      else:
          print(f"Speed: {speed} km/h")
      finally:
          print("Lap processed")
  ```

#### 4. Interactive Exercises
**Exercise 1: Stock Market Data Fetching**
- Write a script to fetch stock prices from a mock API. Implement error handling for network issues and invalid data.
  ```python
  # Fetch stock prices from a mock API
  import requests

  def fetch_stock_prices():
      try:
          response = requests.get("https://mockapi.com/stock_prices")
          response.raise_for_status()
          data = response.json()
          return data
      except requests.exceptions.HTTPError as http_err:
          print(f"HTTP error occurred: {http_err}")
      except requests.exceptions.RequestException as req_err:
          print(f"Error fetching data: {req_err}")
      except ValueError:
          print("Invalid JSON response")

  # Call the function
  stock_data = fetch_stock_prices()
  if stock_data:
      print(stock_data)
  ```

**Exercise 2: Race Data Analysis**
- Develop a function that calculates the average speed from a list of lap times. Ensure to handle cases where lap times might be zero.
  ```python
  def calculate_average_speed(lap_times):
      total_speed = 0
      count = 0
      for lap in lap_times:
          try:
              speed = 500 / lap
              total_speed += speed
              count += 1
          except ZeroDivisionError:
              print("Lap time cannot be zero!")
      if count > 0:
          return total_speed / count
      else:
          return 0

  lap_times = [90, 85, 0, 75]
  average_speed = calculate_average_speed(lap_times)
  print(f"Average Speed: {average_speed} km/h")
  ```

#### 5. Summary and Next Steps
In this lecture, you’ve learned about the importance of error and exception handling in Python. We covered key concepts such as syntax errors, exceptions, try-except blocks, and custom exceptions. You’ve also seen how these concepts can be applied in real-world scenarios related to stock market analysis and F1 racing simulations.

Next, we’ll dive into the topic of **4. File Handling and Data Persistence**, where you’ll learn how to work with files and store data efficiently. This knowledge will be essential as you continue to build more complex and robust Python applications.

Stay tuned and keep coding!

---

### Multimedia Elements
- **Diagrams**: Flowcharts illustrating the try-except block execution.
- **Videos**: Short clips explaining each key concept.
- **Quizzes**: Interactive MCQs to test your understanding after each section.

This comprehensive approach ensures you grasp the intricacies of error and exception handling, setting you up for success as a Python Developer.