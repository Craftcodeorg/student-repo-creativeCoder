### Module Title: Advanced Python Concepts

### Learning Objectives
- Apply the concept of "Exercise 3: Handle exceptions for invalid user inputs" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise 3: Handle Exceptions for Invalid User Inputs

#### Problem Statement
In Healthcare, accurate data entry is crucial for patient safety. Imagine you are developing a Python application for a hospital to calculate the Body Mass Index (BMI) of patients. The BMI is calculated using the formula:

\[ \text{BMI} = \frac{\text{weight (kg)}}{\text{height (m)}^2} \]

Your task is to write a function that takes the patient's weight and height as inputs and calculates their BMI. However, you need to ensure that the inputs are valid numbers and handle any exceptions that might occur due to invalid inputs, such as non-numeric values or zero height.

**Objective:** Implement error handling to manage invalid user inputs and ensure the application does not crash.

#### Starter Code
```python
def calculate_bmi(weight, height):
    """
    Calculate BMI using the formula: weight (kg) / height (m)^2
    :param weight: float - the weight of the patient in kilograms
    :param height: float - the height of the patient in meters
    :return: float - the calculated BMI
    """
    try:
        # Ensure weight and height are converted to float
        weight = float(weight)
        height = float(height)
        
        # Calculate BMI
        bmi = weight / (height ** 2)
        return bmi
    
    except ValueError:
        # Handle the case where input values are not numeric
        print("Error: Weight and height must be numbers.")
    except ZeroDivisionError:
        # Handle the case where height is zero
        print("Error: Height cannot be zero.")
    except Exception as e:
        # General exception handling for any other unexpected errors
        print(f"An unexpected error occurred: {e}")

# Test the function with example values
print(calculate_bmi(70, 1.75))  # Valid input
print(calculate_bmi('seventy', 1.75))  # Invalid weight input
print(calculate_bmi(70, 0))  # Invalid height input
```

#### Hints
1. **Hint 1:** Remember to use the `try` block to wrap the code that may raise an exception. This is where you will attempt to convert the inputs to floats and perform the BMI calculation.
2. **Hint 2:** Use multiple `except` blocks to catch specific exceptions like `ValueError` and `ZeroDivisionError`. This will help you provide clear error messages to the user.
3. **Hint 3:** Consider adding a general `except` block to catch any other unexpected exceptions that might occur. This will make your program more robust and user-friendly.
4. **Hint 4:** Think about edge cases such as very large or very small numbers and how they might affect your calculations.

### Exercise Outcome
By completing this exercise, you should be able to:
- Implement error handling for invalid user inputs.
- Ensure the application can handle unexpected input values gracefully.
- Apply these concepts to real-world scenarios in Healthcare, making your applications more reliable and user-friendly.

### Integration
Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

---
**Note:** This exercise can be integrated with multimedia elements such as:
- **Diagrams:** Flowcharts illustrating the try-except block execution.
- **Videos:** Short clips explaining each key concept.
- **Quizzes:** Interactive MCQs to test your understanding after each section.

This comprehensive approach ensures you grasp the intricacies of error and exception handling, setting you up for success as a Python Developer.