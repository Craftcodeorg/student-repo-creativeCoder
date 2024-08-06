### Module Title: Advanced Python Concepts

---

### Learning Objectives

- Understand and apply Example 1: Creating and accessing lists, tuples, and dictionaries in practical scenarios.
- Enhance problem-solving skills with real-world applications.

### User Profile

- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Preferred Learning Method: Project-based learning, interactive tutorials, and code-along videos

---

### Advanced Python Concepts - Lecture 1: Lists, Tuples, and Dictionaries

---

#### 1. Introduction

Welcome to the first lecture of the "Advanced Python Concepts" module. Today, we will delve into the fundamental data structures in Python: Lists, Tuples, and Dictionaries. These structures are crucial for any Python developer, providing the foundations for data manipulation and storage. Understanding these concepts is essential for tasks such as automating stock market analysis, building race track simulators, and developing investment portfolio apps. By the end of this lecture, you will be well-equipped to use these data structures in your projects, particularly in the realms of Formula 1 racing data analysis and healthcare applications.

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

**Example 3: Healthcare Data Management**

- **Lists**: Track daily patient counts in a hospital.
  ```python
  patient_counts = [50, 55, 60, 53, 49]
  ```
- **Tuples**: Store immutable patient data (e.g., patient IDs).
  ```python
  patient_ids = (12345, 12346, 12347, 12348, 12349)
  ```
- **Dictionaries**: Store patient details.
  ```python
  patient_details = {
      12345: {"name": "John Doe", "age": 45, "condition": "Diabetes"},
      12346: {"name": "Jane Smith", "age": 30, "condition": "Hypertension"},
      12347: {"name": "Alice Brown", "age": 25, "condition": "Asthma"}
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

**Exercise 4: Healthcare Data Management**

1. Create a list to track daily patient counts in a hospital over a week.
2. Convert this list into a tuple to represent immutable patient data.
3. Create a dictionary to store the details (name, age, condition) of at least 3 patients.

---

#### 5. Summary and Next Steps

In this lecture, we covered the basics of Lists, Tuples, and Dictionaries in Python. These data structures are foundational for storing and manipulating data efficiently. We explored practical examples from Formula 1 racing, stock market analysis, and healthcare data management to illustrate their applications.

**Next Steps**: In the upcoming lecture, we will explore more advanced data structures, such as sets and custom objects, and how they can be used for more complex data manipulation tasks. Stay tuned to learn how to leverage Python's full potential in your projects!

---

#### Multimedia Elements

- **Diagrams**: Include diagrams illustrating the structure of lists, tuples, and dictionaries.
- **Videos**: Short video tutorials explaining each data structure.
- **Quizzes**: Interactive quizzes to test understanding of lists, tuples, and dictionaries.

---

Thank you for joining this lecture. Happy coding!