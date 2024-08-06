### Module Title: Introduction to Python ###

### Learning Objectives ###
- Apply the concept of "Exercise 6: Read user input and print output" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Formula 1 Racing and Healthcare.

### User Profile ###
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements ###

#### 1. Problem Statement ####
You are tasked with developing a simple Python program to calculate the Body Mass Index (BMI) of a patient. The program will read the patient's weight in kilograms and height in meters from the user input, then calculate and print the BMI along with a health status message. This exercise will help you practice reading user input and printing output, and it will also introduce you to a basic application of Python in the healthcare industry.

**Problem Statement:**
Create a Python program that:
- Reads the user's weight in kilograms.
- Reads the user's height in meters.
- Calculates the BMI using the formula: `BMI = weight / (height ** 2)`.
- Prints the calculated BMI.
- Prints a health status message based on the BMI value:
  - Underweight: BMI < 18.5
  - Normal weight: 18.5 ≤ BMI < 24.9
  - Overweight: 25 ≤ BMI < 29.9
  - Obesity: BMI ≥ 30

#### 2. Starter Code ####
```python
# Function to calculate BMI
def calculate_bmi(weight, height):
    """
    Calculate BMI given weight (in kg) and height (in meters).
    """
    bmi = weight / (height ** 2)
    return bmi

# Function to determine health status based on BMI
def health_status(bmi):
    """
    Determine the health status based on BMI value.
    """
    if bmi < 18.5:
        return "Underweight"
    elif 18.5 <= bmi < 24.9:
        return "Normal weight"
    elif 25 <= bmi < 29.9:
        return "Overweight"
    else:
        return "Obesity"

# Read user input
weight = float(input("Enter your weight in kilograms: "))
height = float(input("Enter your height in meters: "))

# Calculate BMI
bmi = calculate_bmi(weight, height)

# Print BMI and health status
print(f"Your BMI is: {bmi:.2f}")
print(f"Health Status: {health_status(bmi)}")
```

#### 3. Hints ####
- **Hint 1**: Make sure to convert the input values to `float` because user input in Python is read as a string by default.
- **Hint 2**: Use the `**` operator in Python for exponentiation (raising to the power).
- **Hint 3**: Test your program with different values to ensure it handles all health status categories correctly.
- **Hint 4**: Remember to include error handling to manage invalid input, such as negative values or non-numeric input.

### Exercise Outcome ###
- The user will be able to read user input, process it, and print the output, demonstrating an understanding of basic Python programming concepts.
- The solution will include best practices such as clear function definitions, appropriate variable naming, and comprehensive comments explaining each step.
- The user will gain confidence in applying Python to solve practical problems in the healthcare industry.

### Integration ###
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

**Exercise Content:**

```markdown
# Exercise: Calculate BMI and Determine Health Status

## Problem Statement

You are tasked with developing a simple Python program to calculate the Body Mass Index (BMI) of a patient. The program will read the patient's weight in kilograms and height in meters from the user input, then calculate and print the BMI along with a health status message.

## Starter Code

```python
# Function to calculate BMI
def calculate_bmi(weight, height):
    """
    Calculate BMI given weight (in kg) and height (in meters).
    """
    bmi = weight / (height ** 2)
    return bmi

# Function to determine health status based on BMI
def health_status(bmi):
    """
    Determine the health status based on BMI value.
    """
    if bmi < 18.5:
        return "Underweight"
    elif 18.5 <= bmi < 24.9:
        return "Normal weight"
    elif 25 <= bmi < 29.9:
        return "Overweight"
    else:
        return "Obesity"

# Read user input
weight = float(input("Enter your weight in kilograms: "))
height = float(input("Enter your height in meters: "))

# Calculate BMI
bmi = calculate_bmi(weight, height)

# Print BMI and health status
print(f"Your BMI is: {bmi:.2f}")
print(f"Health Status: {health_status(bmi)}")
```

## Hints

- **Hint 1**: Make sure to convert the input values to `float` because user input in Python is read as a string by default.
- **Hint 2**: Use the `**` operator in Python for exponentiation (raising to the power).
- **Hint 3**: Test your program with different values to ensure it handles all health status categories correctly.
- **Hint 4**: Remember to include error handling to manage invalid input, such as negative values or non-numeric input.

## Outcome

By completing this exercise, you will:
- Understand how to read user input and print output in Python.
- Gain experience in applying Python to solve practical problems in the healthcare industry.
- Develop a better understanding of function definitions, variable naming, and commenting practices in Python.

Let's get started and build something amazing!
```