### Module Title: Advanced Python Concepts ###

### Learning Objectives ###
- Apply the concept of "Exercise 6: Implement a custom decorator" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

### User Profile ###
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements ###

1. **Problem Statement**: 
   Develop a problem statement that challenges the user to apply "Exercise 6: Implement a custom decorator" to a scenario relevant to Healthcare. The problem should encourage critical thinking and be solvable with the concepts covered in "Advanced Python Concepts".

   **Problem Statement:**
   As a Python Developer in the healthcare industry, you are tasked with creating a logging system for a medical application that tracks patient data. The application needs a function to calculate the Body Mass Index (BMI) of patients. To ensure that all BMI calculations are logged for auditing purposes, you will create a custom decorator to log the input parameters and the result of the BMI calculation.

   **Task:**
   - Create a function `calculate_bmi(weight, height)` that computes the BMI.
   - Implement a custom decorator `log_bmi_calculation` that logs the input parameters (weight and height) and the result of the BMI calculation.
   - Apply the decorator to the `calculate_bmi` function.

2. **Starter Code**: 
   Provide starter code that sets up the basic environment or framework for the exercise. The code should be annotated to guide the user, especially focusing on areas relevant to Healthcare and suitable for someone with Beginner experience.

   ```python
   # Define the custom decorator to log BMI calculations
   def log_bmi_calculation(func):
       def wrapper(*args, **kwargs):
           # Log the input parameters
           weight, height = args
           print(f"Calculating BMI for weight: {weight} kg, height: {height} meters")
           
           # Call the original function and get the result
           result = func(*args, **kwargs)
           
           # Log the result
           print(f"Calculated BMI: {result}")
           
           return result
       return wrapper

   # Function to calculate BMI
   @log_bmi_calculation
   def calculate_bmi(weight, height):
       # Calculate BMI (weight in kg / height in meters squared)
       bmi = weight / (height ** 2)
       return bmi

   # Test the function with example values
   print(calculate_bmi(70, 1.75))
   ```

3. **Hints**:
   Offer hints that can help the user approach the solution without giving it away. The hints should be tailored to support learning, encourage exploration, and offer insights into solving similar problems in the Healthcare industry.

   **Hints:**
   - Remember that the decorator function should accept a function as its argument and return a new function (the wrapper).
   - In the wrapper function, you can access the arguments passed to the original function using `*args` and `**kwargs`.
   - To calculate BMI, use the formula `BMI = weight / (height ** 2)`.
   - Ensure that the decorator logs both the input parameters and the output result to the console.

### Exercise Outcome ###
- The user should be able to solve the problem using the concepts learned, demonstrating an understanding of how these concepts apply to real-world scenarios in Healthcare.
- The solution should include best practices, error handling, and be well-commented to explain the reasoning behind each step.

### Integration ###
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

---

### Exercise: Implement a Custom Decorator for BMI Calculation Logging ###

#### Problem Statement ####
As a Python Developer in the healthcare industry, you are tasked with creating a logging system for a medical application that tracks patient data. The application needs a function to calculate the Body Mass Index (BMI) of patients. To ensure that all BMI calculations are logged for auditing purposes, you will create a custom decorator to log the input parameters and the result of the BMI calculation.

#### Task ####
- Create a function `calculate_bmi(weight, height)` that computes the BMI.
- Implement a custom decorator `log_bmi_calculation` that logs the input parameters (weight and height) and the result of the BMI calculation.
- Apply the decorator to the `calculate_bmi` function.

#### Starter Code ####
```python
# Define the custom decorator to log BMI calculations
def log_bmi_calculation(func):
    def wrapper(*args, **kwargs):
        # Log the input parameters
        weight, height = args
        print(f"Calculating BMI for weight: {weight} kg, height: {height} meters")
        
        # Call the original function and get the result
        result = func(*args, **kwargs)
        
        # Log the result
        print(f"Calculated BMI: {result}")
        
        return result
    return wrapper

# Function to calculate BMI
@log_bmi_calculation
def calculate_bmi(weight, height):
    # Calculate BMI (weight in kg / height in meters squared)
    bmi = weight / (height ** 2)
    return bmi

# Test the function with example values
print(calculate_bmi(70, 1.75))
```

#### Hints ####
- Remember that the decorator function should accept a function as its argument and return a new function (the wrapper).
- In the wrapper function, you can access the arguments passed to the original function using `*args` and `**kwargs`.
- To calculate BMI, use the formula `BMI = weight / (height ** 2)`.
- Ensure that the decorator logs both the input parameters and the output result to the console.

### Summary and Next Steps ###
In this exercise, you learned how to implement a custom decorator to log the input parameters and the result of a function in a healthcare context. This skill is crucial for creating maintainable and auditable code in real-world applications. 

**Next Steps**:
In the next lecture, we will dive into **Advanced Iterators and Generators**, where you'll learn how to handle large datasets efficiently and create custom iterators. This knowledge will be particularly useful for your interests in data analysis and building interactive dashboards.

Stay tuned and keep coding!