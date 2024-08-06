### Module Title: Introduction to Python

### Learning Objectives
- Understand and apply Example 5: Defining and calling a function in practical scenarios.
- Enhance problem-solving skills with real-world applications.

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Preferred Learning Method: Project-based learning, interactive tutorials, and code-along videos

### Example 5: Defining and Calling a Function

#### 1. **Introduction**
Welcome to Example 5 of our "Introduction to Python" module. In this example, we will learn how to define and call functions in Python, a fundamental skill that enables you to create reusable blocks of code. Functions help in organizing code, making it more modular and easier to maintain, which is particularly important in complex fields like Healthcare.

#### 2. **Code Snippet**

Below is a simple Python function that calculates the Body Mass Index (BMI) based on weight and height. This example includes error handling to ensure the function can handle incorrect inputs gracefully.

```python
def calculate_bmi(weight, height):
    """
    Calculate the Body Mass Index (BMI) given a weight in kilograms and height in meters.
    
    Parameters:
    weight (float): The weight of the person in kilograms.
    height (float): The height of the person in meters.
    
    Returns:
    float: The BMI of the person.
    """
    try:
        if weight <= 0 or height <= 0:
            raise ValueError("Weight and height must be positive numbers.")
        
        bmi = weight / (height ** 2)
        return round(bmi, 2)
    
    except TypeError:
        return "Invalid input type. Please enter numbers for weight and height."
    except ValueError as ve:
        return str(ve)

# Example of calling the function
weight = 70  # in kilograms
height = 1.75  # in meters
bmi = calculate_bmi(weight, height)
print(f"The BMI is: {bmi}")
```

#### 3. **Explanation**

Let's break down the code step-by-step to understand how it works:

- **Function Definition**: We define a function named `calculate_bmi` that accepts two parameters: `weight` and `height`.
- **Docstring**: The docstring provides a brief description of what the function does, its parameters, and its return value.
- **Error Handling**: 
  - A `try` block is used to attempt the execution of the code.
  - We check if `weight` and `height` are positive numbers. If not, a `ValueError` is raised with a descriptive message.
  - The BMI is calculated using the formula `weight / (height ** 2)` and rounded to two decimal places.
  - The `except TypeError` block catches errors related to incorrect input types (e.g., if a string is passed instead of a number).
  - The `except ValueError` block catches the custom error we raised earlier and returns the error message.
- **Function Call**: We call the `calculate_bmi` function with example values for `weight` and `height`, and print the result.

This function is particularly useful in Healthcare for assessing the health status of patients based on their BMI.

#### 4. **Application**

In the Healthcare industry, BMI is a critical measure used to assess whether individuals are underweight, normal weight, overweight, or obese. Automating BMI calculations can save time for healthcare providers and reduce errors associated with manual calculations. 

For instance, in a healthcare application, you can use the `calculate_bmi` function to quickly assess patients' health metrics during routine check-ups. This can help in early detection of potential health issues related to weight, such as diabetes, heart disease, and hypertension, allowing for timely intervention and personalized care plans.

### Integration
- Ensure the content is structured with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting.

---

By mastering the concept of defining and calling functions, you'll be able to create reusable and maintainable code, enhancing your problem-solving skills for real-world applications. Keep practicing and exploring how these concepts can be applied to different scenarios in both your personal interests and professional goals.

Happy coding!