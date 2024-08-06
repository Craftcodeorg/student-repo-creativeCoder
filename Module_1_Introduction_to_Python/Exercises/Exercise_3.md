### Module Title: Introduction to Python ###

---

### Learning Objectives ###
1. Apply the concept of "Exercise 3: Write an if-else statement to check conditions" in a practical coding exercise.
2. Develop problem-solving skills through real-world scenarios relevant to Healthcare.

---

### User Profile ###
- **Interest**: Formula 1 Racing
- **Career Goal**: Python Developer
- **Technical Experience**: Beginner
- **Learning Method Preferences**: Project-based learning, interactive tutorials, and code-along videos.

---

### Exercise Requirements ###

#### Problem Statement
You are a Python developer working in the healthcare industry. Your task is to create a simple script to determine if a patient's vital signs indicate the need for immediate medical attention. Specifically, you need to check the patient's heart rate and temperature. If the heart rate is above 100 beats per minute or the temperature is above 37.5 degrees Celsius, the patient needs immediate attention.

#### Starter Code
```python
# Starter code to check patient's vital signs

def check_vital_signs(heart_rate, temperature):
    """
    Function to check if the patient needs immediate attention based on their vital signs.
    :param heart_rate: Patient's heart rate in beats per minute
    :param temperature: Patient's temperature in degrees Celsius
    :return: A message indicating if the patient needs immediate attention
    """
    # TODO: Write an if-else statement to check the conditions
    if _______ > 100 or ________ > 37.5:
        return "Immediate attention needed!"
    else:
        return "Vital signs are normal."

# Test the function with example values
patient_heart_rate = 105
patient_temperature = 36.7

print(check_vital_signs(patient_heart_rate, patient_temperature))
```

#### Hints
1. **Hint 1**: Recall that the `if` statement can check multiple conditions using logical operators such as `or`. You can check if either the heart rate is above 100 or the temperature is above 37.5.
2. **Hint 2**: Ensure you are comparing the correct variables inside the `if` statement. For example, `heart_rate > 100`.
3. **Hint 3**: Use the provided example values to test your function and verify that it works correctly for different scenarios.

---

### Exercise Outcome ###
- Users will be able to solve the problem using the concepts learned, demonstrating an understanding of how if-else statements apply to real-world scenarios in healthcare.
- The solution should include best practices, error handling, and be well-commented to explain the reasoning behind each step.

---

### Integration ###
Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

---

### Completed Code Example (For Reference)
```python
# Complete code to check patient's vital signs

def check_vital_signs(heart_rate, temperature):
    """
    Function to check if the patient needs immediate attention based on their vital signs.
    :param heart_rate: Patient's heart rate in beats per minute
    :param temperature: Patient's temperature in degrees Celsius
    :return: A message indicating if the patient needs immediate attention
    """
    # Check conditions using an if-else statement
    if heart_rate > 100 or temperature > 37.5:
        return "Immediate attention needed!"
    else:
        return "Vital signs are normal."

# Test the function with example values
patient_heart_rate_1 = 105
patient_temperature_1 = 36.7

patient_heart_rate_2 = 85
patient_temperature_2 = 38.0

# Output should indicate if immediate attention is needed
print(check_vital_signs(patient_heart_rate_1, patient_temperature_1))  # Expected: Immediate attention needed!
print(check_vital_signs(patient_heart_rate_2, patient_temperature_2))  # Expected: Immediate attention needed!
```

---

*Feel free to use multimedia elements like diagrams or videos to further illustrate these concepts. Quizzes at the end of each section can also help reinforce learning.*