### Module Title: Introduction to Python

### Learning Objectives
- Apply the concept of "Exercise 4: Use a for loop to iterate over a list" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Formula 1 Racing and Healthcare.

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements

#### 1. Problem Statement
Develop a problem statement that challenges the user to apply "Exercise 4: Use a for loop to iterate over a list" to a scenario relevant to Healthcare. The problem should encourage critical thinking and be solvable with the concepts covered in "Introduction to Python".

**Problem Statement:**
You are working as a Python Developer in a healthcare organization. Your task is to analyze the patient data to calculate the average heart rate of patients during a health checkup session. You have a list of heart rates recorded at different times for various patients. Your goal is to use a for loop to iterate over the list of heart rates and compute the average heart rate.

#### 2. Starter Code
Provide starter code that sets up the basic environment or framework for the exercise. The code should be annotated to guide the user, especially focusing on areas relevant to Formula 1 Racing and suitable for someone with Beginner experience.

```python
# Starter code to calculate the average heart rate

# List of heart rates recorded during a health checkup session
heart_rates = [72, 75, 78, 80, 74, 77, 79, 76]

def calculate_average_heart_rate(heart_rates):
    # Initialize a variable to store the sum of heart rates
    total_heart_rate = 0
    
    # Use a for loop to iterate over the list of heart rates
    for rate in heart_rates:
        # Add the current heart rate to the total
        total_heart_rate += rate
    
    # Calculate the average heart rate
    average_heart_rate = total_heart_rate / len(heart_rates)
    
    return average_heart_rate

# Test the function and print the result
print("Average Heart Rate:", calculate_average_heart_rate(heart_rates))
```

#### 3. Hints
Offer hints that can help the user approach the solution without giving it away. The hints should be tailored to support learning, encourage exploration, and offer insights into solving similar problems in the Healthcare industry.

**Hints:**
1. Remember to initialize a variable to store the sum of the heart rates before starting the loop.
2. Use the `+=` operator to add each heart rate to the total during each iteration of the loop.
3. To calculate the average, divide the total sum of heart rates by the number of heart rates in the list. You can use the `len()` function to get the length of the list.
4. Ensure you handle the division correctly to avoid any potential errors, such as division by zero if the list is empty.

### Exercise Outcome
- The user should be able to solve the problem using the concepts learned, demonstrating an understanding of how these concepts apply to real-world scenarios in Healthcare.
- The solution should include best practices, error handling, and be well-commented to explain the reasoning behind each step.

**Expected Outcome:**
The user will write a function that correctly calculates the average heart rate from a list of heart rates, effectively using a for loop to iterate over the list.

```python
# List of heart rates recorded during a health checkup session
heart_rates = [72, 75, 78, 80, 74, 77, 79, 76]

def calculate_average_heart_rate(heart_rates):
    # Initialize a variable to store the sum of heart rates
    total_heart_rate = 0
    
    # Use a for loop to iterate over the list of heart rates
    for rate in heart_rates:
        # Add the current heart rate to the total
        total_heart_rate += rate
    
    # Calculate the average heart rate
    average_heart_rate = total_heart_rate / len(heart_rates)
    
    return average_heart_rate

# Test the function and print the result
print("Average Heart Rate:", calculate_average_heart_rate(heart_rates))
```

### Integration
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

**Markdown Formatting:**

```markdown
### Exercise: Calculate Average Heart Rate

#### Problem Statement
You are working as a Python Developer in a healthcare organization. Your task is to analyze the patient data to calculate the average heart rate of patients during a health checkup session. You have a list of heart rates recorded at different times for various patients. Your goal is to use a for loop to iterate over the list of heart rates and compute the average heart rate.

#### Starter Code
```python
# Starter code to calculate the average heart rate

# List of heart rates recorded during a health checkup session
heart_rates = [72, 75, 78, 80, 74, 77, 79, 76]

def calculate_average_heart_rate(heart_rates):
    # Initialize a variable to store the sum of heart rates
    total_heart_rate = 0
    
    # Use a for loop to iterate over the list of heart rates
    for rate in heart_rates:
        # Add the current heart rate to the total
        total_heart_rate += rate
    
    # Calculate the average heart rate
    average_heart_rate = total_heart_rate / len(heart_rates)
    
    return average_heart_rate

# Test the function and print the result
print("Average Heart Rate:", calculate_average_heart_rate(heart_rates))
```

#### Hints
1. Remember to initialize a variable to store the sum of the heart rates before starting the loop.
2. Use the `+=` operator to add each heart rate to the total during each iteration of the loop.
3. To calculate the average, divide the total sum of heart rates by the number of heart rates in the list. You can use the `len()` function to get the length of the list.
4. Ensure you handle the division correctly to avoid any potential errors, such as division by zero if the list is empty.

#### Expected Outcome
The user will write a function that correctly calculates the average heart rate from a list of heart rates, effectively using a for loop to iterate over the list.

```python
# List of heart rates recorded during a health checkup session
heart_rates = [72, 75, 78, 80, 74, 77, 79, 76]

def calculate_average_heart_rate(heart_rates):
    # Initialize a variable to store the sum of heart rates
    total_heart_rate = 0
    
    # Use a for loop to iterate over the list of heart rates
    for rate in heart_rates:
        # Add the current heart rate to the total
        total_heart_rate += rate
    
    # Calculate the average heart rate
    average_heart_rate = total_heart_rate / len(heart_rates)
    
    return average_heart_rate

# Test the function and print the result
print("Average Heart Rate:", calculate_average_heart_rate(heart_rates))
```
```