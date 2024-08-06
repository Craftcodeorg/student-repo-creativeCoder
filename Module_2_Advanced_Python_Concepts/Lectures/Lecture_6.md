### Module Information ###
- **Module Title**: Advanced Python Concepts
- **Lecture Title**: 6. Decorators and Context Managers

---

### Lecture: Decorators and Context Managers ###

#### 1. Introduction ####
Welcome to Lecture 6 of our Advanced Python Concepts module! Today, we will delve into the powerful features of Python known as Decorators and Context Managers. As a Python Developer, mastering these concepts will greatly enhance your ability to write more efficient, readable, and maintainable code. In this lecture, we’ll explore how these tools can simplify complex operations, manage resources effectively, and add functionality to existing code with ease.

Understanding Decorators and Context Managers is crucial for any advanced Python developer. They are widely used in various applications, including web development, data analysis, and automation—areas directly aligned with your interests in creating interactive dashboards, automating stock market analysis, and developing investment portfolio apps.

#### 2. Key Concepts ####

**Decorators:**
- **Definition**: A decorator is a function that takes another function and extends its behavior without explicitly modifying it.
- **Syntax**: The `@decorator` syntax is used to apply a decorator to a function.
- **Use Cases**: Logging, access control, caching, and validation.
- **Example**:
  ```python
  def log_execution(func):
      def wrapper(*args, **kwargs):
          print(f"Executing {func.__name__}...")
          result = func(*args, **kwargs)
          print(f"{func.__name__} executed.")
          return result
      return wrapper

  @log_execution
  def analyze_stock_data(data):
      # Simulate data analysis
      return sum(data) / len(data)
  
  analyze_stock_data([100, 200, 300])
  ```

**Context Managers:**
- **Definition**: A context manager is a construct that allows for the setup and teardown of resources, ensuring that resources are properly managed.
- **Syntax**: The `with` statement is used to implement a context manager.
- **Use Cases**: Managing file operations, database connections, and network calls.
- **Example**:
  ```python
  class FileManager:
      def __init__(self, filename, mode):
          self.filename = filename
          self.mode = mode
      
      def __enter__(self):
          self.file = open(self.filename, self.mode)
          return self.file
      
      def __exit__(self, exc_type, exc_value, traceback):
          self.file.close()

  with FileManager('data.txt', 'w') as f:
      f.write('Hello, Formula 1 Data Analysis!')
  ```

#### 3. Real-world Examples ####

**Example 1: Logging in Web Development for Finance**
- **Scenario**: You are developing a web application for financial portfolio management. You need to log user activities to track their actions and debug issues.
- **Code Snippet**:
  ```python
  def log_activity(func):
      def wrapper(*args, **kwargs):
          user = args[0]  # Assume the first argument is the user
          print(f"User {user} is performing {func.__name__}")
          result = func(*args, **kwargs)
          print(f"User {user} completed {func.__name__}")
          return result
      return wrapper

  @log_activity
  def update_portfolio(user, portfolio, changes):
      # Perform portfolio update
      return portfolio.update(changes)
  
  update_portfolio('Alice', {'stocks': 100}, {'stocks': 150})
  ```

**Example 2: Managing Database Connections in Automating Stock Market Analysis**
- **Scenario**: You are automating stock market analysis and need to ensure that the database connections are managed correctly to prevent resource leaks.
- **Code Snippet**:
  ```python
  import sqlite3

  class DatabaseConnection:
      def __init__(self, db_name):
          self.db_name = db_name
      
      def __enter__(self):
          self.conn = sqlite3.connect(self.db_name)
          return self.conn
      
      def __exit__(self, exc_type, exc_value, traceback):
          self.conn.close()

  with DatabaseConnection('stocks.db') as conn:
      cursor = conn.cursor()
      cursor.execute('SELECT * FROM stock_prices')
      for row in cursor.fetchall():
          print(row)
  ```

#### 4. Interactive Exercises ####

**Exercise 1: Create a Decorator for Execution Time Measurement**
- **Objective**: Write a decorator that measures and prints the execution time of a function.
- **Instructions**:
  1. Define a decorator named `measure_time`.
  2. Apply this decorator to a function that simulates analyzing F1 race data.
  3. Print the execution time.

**Exercise 2: Implement a Context Manager for File Operations**
- **Objective**: Write a context manager that manages file reading operations for a large dataset (e.g., F1 race lap times).
- **Instructions**:
  1. Create a context manager class named `LargeFileReader`.
  2. Use the context manager to read and print the first 10 lines of a large file.

**Exercise 3: Combine Decorators and Context Managers**
- **Objective**: Combine a decorator and a context manager to log and manage resources in a stock market analysis script.
- **Instructions**:
  1. Define a decorator to log function calls.
  2. Implement a context manager for database connections.
  3. Use both in a script that fetches and processes stock data.

#### 5. Summary and Next Steps ####

In this lecture, we explored the powerful concepts of Decorators and Context Managers, learning how they can enhance code functionality and manage resources effectively. We looked at their theoretical foundations, practical implications, and real-world applications relevant to your interests in finance and Formula 1 racing.

**Key Takeaways**:
- Decorators allow you to extend and modify the behavior of functions without changing their code.
- Context Managers ensure resources are properly managed, using the `with` statement for setup and teardown.

**Next Steps**: 
In the next lecture, we will dive into **Advanced Iterators and Generators**, where you'll learn how to handle large datasets efficiently and create custom iterators. This knowledge will be particularly useful for your interests in data analysis and building interactive dashboards.

Stay tuned and keep coding!