### Module Title: Advanced Python Concepts ###

### Learning Objectives ###
- Apply the concept of "Exercise 2: Write a list comprehension to filter even numbers" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Formula 1 Racing.

### User Profile ###
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, code-along videos

### Exercise Requirements ###

#### Problem Statement
You work for a healthcare analytics company that is developing a dashboard to monitor patient vitals. One of the metrics tracked is the number of steps taken by patients each day. The data is collected from wearable devices and stored in a list. Your task is to write a list comprehension that filters out the even-numbered step counts from a week's worth of data for each patient. This will help identify anomalies in the data, as even-numbered step counts over a period may indicate a malfunctioning device.

#### Starter Code
Here's some starter code to help you get started. This code sets up a list of step counts for a week and includes a placeholder for your list comprehension.

```python
# List of daily step counts for a patient over a week
weekly_step_counts = [1203, 1344, 1456, 1509, 1678, 1789, 1902]

# Write a list comprehension to filter out even-numbered step counts
even_step_counts = [_________ for _________ in _________ if _________]

# Print the result to verify your solution
print(even_step_counts)  # Output should be: [1344, 1456, 1678, 1902]
```

#### Hints
1. **Understand the Requirement**: The goal is to filter out step counts that are even numbers. Remember that an even number is divisible by 2 with no remainder.
2. **Syntax of List Comprehension**: Use the list comprehension syntax: `[expression for item in iterable if condition]`.
3. **Applying the Condition**: Use the modulo operator `%` to check if a number is even. For example, `x % 2 == 0` checks if `x` is even.
4. **Real-World Insight**: In healthcare, filtering data is crucial for identifying anomalies and ensuring the accuracy of patient monitoring systems.

#### Exercise Outcome
By the end of this exercise, you should be able to:
- Use list comprehensions to filter data based on specific conditions.
- Understand how to apply these concepts to real-world scenarios in Healthcare.
- Write clean, efficient, and well-commented code that adheres to best practices.

### Integration ###
Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

```markdown
# Exercise 2: Write a List Comprehension to Filter Even Numbers

## Problem Statement
You work for a healthcare analytics company that is developing a dashboard to monitor patient vitals. One of the metrics tracked is the number of steps taken by patients each day. The data is collected from wearable devices and stored in a list. Your task is to write a list comprehension that filters out the even-numbered step counts from a week's worth of data for each patient. This will help identify anomalies in the data, as even-numbered step counts over a period may indicate a malfunctioning device.

## Starter Code
```python
# List of daily step counts for a patient over a week
weekly_step_counts = [1203, 1344, 1456, 1509, 1678, 1789, 1902]

# Write a list comprehension to filter out even-numbered step counts
even_step_counts = [count for count in weekly_step_counts if count % 2 == 0]

# Print the result to verify your solution
print(even_step_counts)  # Output should be: [1344, 1456, 1678, 1902]
```

## Hints
1. **Understand the Requirement**: The goal is to filter out step counts that are even numbers. Remember that an even number is divisible by 2 with no remainder.
2. **Syntax of List Comprehension**: Use the list comprehension syntax: `[expression for item in iterable if condition]`.
3. **Applying the Condition**: Use the modulo operator `%` to check if a number is even. For example, `x % 2 == 0` checks if `x` is even.
4. **Real-World Insight**: In healthcare, filtering data is crucial for identifying anomalies and ensuring the accuracy of patient monitoring systems.

## Expected Outcome
By the end of this exercise, you should be able to:
- Use list comprehensions to filter data based on specific conditions.
- Understand how to apply these concepts to real-world scenarios in Healthcare.
- Write clean, efficient, and well-commented code that adheres to best practices.
```

Happy coding!