### Module Title: Introduction to Python ###

### Learning Objectives ###
- Apply the concept of "Exercise 2: Implement basic arithmetic operations" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

### User Profile ###
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise: Implement Basic Arithmetic Operations in Healthcare ###

#### Problem Statement
Develop a problem statement that challenges the user to apply "Exercise 2: Implement basic arithmetic operations" to a scenario relevant to Healthcare. The problem should encourage critical thinking and be solvable with the concepts covered in "Introduction to Python".

#### Scenario: Calculating BMI (Body Mass Index)
In the healthcare industry, calculating the Body Mass Index (BMI) is a common practice to assess whether a patient has a healthy body weight for a person of their height. The formula for BMI is:

\[ \text{BMI} = \frac{\text{weight (kg)}}{\text{height (m)}^2} \]

Your task is to write a Python function that calculates the BMI given a patient's weight and height. The function should also categorize the BMI based on the following ranges:
- Underweight: BMI < 18.5
- Normal weight: 18.5 ≤ BMI < 24.9
- Overweight: 25 ≤ BMI < 29.9
- Obesity: BMI ≥ 30

#### Starter Code
```python
# Function to calculate BMI and categorize it
def calculate_bmi(weight, height):
    """
    Calculate BMI using the formula: BMI = weight (kg) / height (m)^2
    Categorize the BMI based on standard ranges
    """
    # Calculate BMI
    bmi = weight / (height ** 2)
    
    # Determine BMI category
    if bmi < 18.5:
        category = "Underweight"
    elif 18.5 <= bmi < 24.9:
        category = "Normal weight"
    elif 25 <= bmi < 29.9:
        category = "Overweight"
    else:
        category = "Obesity"
    
    return bmi, category

# Test the function with example values
weight_example = 70  # kg
height_example = 1.75  # meters
bmi_value, bmi_category = calculate_bmi(weight_example, height_example)
print(f"BMI: {bmi_value:.2f}, Category: {bmi_category}")
```

#### Hints
- **Hint 1**: Ensure you use the correct units for weight (kilograms) and height (meters).
- **Hint 2**: Use the `**` operator to compute the square of height.
- **Hint 3**: Use conditional statements to categorize the BMI based on the calculated value.
- **Hint 4**: Remember to format the BMI value to two decimal places for better readability.

### Exercise Outcome ###
- The user should be able to solve the problem using the concepts learned, demonstrating an understanding of how these concepts apply to real-world scenarios in Healthcare.
- The solution should include best practices, error handling, and be well-commented to explain the reasoning behind each step.

### Integration ###
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

### Summary and Next Steps ###
In this exercise, you have applied basic arithmetic operations to solve a practical problem in the healthcare industry. You have written a Python function to calculate BMI and categorized it based on standard ranges. This hands-on experience will be valuable as you continue to learn Python and tackle more complex problems.

#### Teaser for Next Exercise:
In the next exercise, we will further explore Python's capabilities by working with data structures like lists and dictionaries. You'll learn how to store, manipulate, and retrieve data efficiently, which is essential for any aspiring Python Developer.

Stay tuned and keep practicing! The journey to mastering Python is just beginning.