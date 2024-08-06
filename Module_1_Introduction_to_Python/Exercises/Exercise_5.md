### Module Title: Introduction to Python ###

---

### Learning Objectives ###
- Apply the concept of "Exercise 5: Define and call a function with parameters" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

### User Profile ###
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

---

### Exercise Requirements ###

#### 1. Problem Statement ####
Develop a Python function to calculate the Body Mass Index (BMI) for patients in a healthcare setting. The BMI is a measure of body fat based on height and weight that applies to adult men and women. The formula to calculate BMI is:
\[ \text{BMI} = \frac{\text{weight (kg)}}{\text{height (m)}^2} \]

You need to define a function `calculate_bmi` that takes two parameters: `weight` and `height`. The function should return the BMI value and classify the BMI into categories such as 'Underweight', 'Normal weight', 'Overweight', and 'Obese'. 

**Problem Statement:**
Write a Python script that:
1. Defines a function `calculate_bmi(weight, height)` that calculates the BMI using the given weight and height.
2. Classifies the BMI into categories:
   - BMI < 18.5: Underweight
   - 18.5 <= BMI < 24.9: Normal weight
   - 25 <= BMI < 29.9: Overweight
   - BMI >= 30: Obese
3. Prompts the user to enter their weight (in kg) and height (in meters).
4. Calls the `calculate_bmi` function with the user-provided inputs and prints the BMI and its category.

#### 2. Starter Code ####
```python
# Function to calculate BMI
def calculate_bmi(weight, height):
    # Calculate BMI using the formula
    bmi = weight / (height ** 2)
    
    # Determine the BMI category
    if bmi < 18.5:
        category = "Underweight"
    elif 18.5 <= bmi < 24.9:
        category = "Normal weight"
    elif 25 <= bmi < 29.9:
        category = "Overweight"
    else:
        category = "Obese"
    
    return bmi, category

# Prompt the user to enter weight and height
weight = float(input("Enter your weight in kg: "))
height = float(input("Enter your height in meters: "))

# Call the function and get the result
bmi, category = calculate_bmi(weight, height)

# Print the BMI and its category
print(f"Your BMI is {bmi:.2f}, which is considered {category}.")
```

#### 3. Hints ####
- **Hint 1**: Ensure that the `calculate_bmi` function correctly applies the BMI formula: weight divided by the square of height.
- **Hint 2**: Use conditional (`if`, `elif`, `else`) statements to classify the BMI into the correct category.
- **Hint 3**: To prompt user input, use the `input` function and remember to convert the input strings to floats for numerical calculations.
- **Hint 4**: Test the function with different values to ensure it correctly calculates and classifies the BMI.

---

### Exercise Outcome ###
- The user should be able to solve the problem using the concepts learned, demonstrating an understanding of how these concepts apply to real-world scenarios in Healthcare.
- The solution should include best practices, error handling, and be well-commented to explain the reasoning behind each step.

---

### Integration ###
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

**Example:**
```markdown
# Introduction to Python: Exercise 5

## Problem Statement
Develop a Python function to calculate the Body Mass Index (BMI) for patients in a healthcare setting. The BMI is a measure of body fat based on height and weight that applies to adult men and women. The formula to calculate BMI is:
\[ \text{BMI} = \frac{\text{weight (kg)}}{\text{height (m)}^2} \]

Write a Python script that:
1. Defines a function `calculate_bmi(weight, height)` that calculates the BMI using the given weight and height.
2. Classifies the BMI into categories:
   - BMI < 18.5: Underweight
   - 18.5 <= BMI < 24.9: Normal weight
   - 25 <= BMI < 29.9: Overweight
   - BMI >= 30: Obese
3. Prompts the user to enter their weight (in kg) and height (in meters).
4. Calls the `calculate_bmi` function with the user-provided inputs and prints the BMI and its category.

## Starter Code
```python
# Function to calculate BMI
def calculate_bmi(weight, height):
    # Calculate BMI using the formula
    bmi = weight / (height ** 2)
    
    # Determine the BMI category
    if bmi < 18.5:
        category = "Underweight"
    elif 18.5 <= bmi < 24.9:
        category = "Normal weight"
    elif 25 <= bmi < 29.9:
        category = "Overweight"
    else:
        category = "Obese"
    
    return bmi, category

# Prompt the user to enter weight and height
weight = float(input("Enter your weight in kg: "))
height = float(input("Enter your height in meters: "))

# Call the function and get the result
bmi, category = calculate_bmi(weight, height)

# Print the BMI and its category
print(f"Your BMI is {bmi:.2f}, which is considered {category}.")
```

## Hints
- **Hint 1**: Ensure that the `calculate_bmi` function correctly applies the BMI formula: weight divided by the square of height.
- **Hint 2**: Use conditional (`if`, `elif`, `else`) statements to classify the BMI into the correct category.
- **Hint 3**: To prompt user input, use the `input` function and remember to convert the input strings to floats for numerical calculations.
- **Hint 4**: Test the function with different values to ensure it correctly calculates and classifies the BMI.

## Expected Outcome
By completing this exercise, you will:
- Understand how to define and call a function with parameters.
- Apply conditional statements to classify data based on calculated values.
- Gain practical experience in developing a healthcare-related Python script.
```

---

Incorporating multimedia elements such as diagrams, short video tutorials, and interactive quizzes can significantly enhance your learning experience. Make sure to use these resources to solidify your understanding. Happy coding!