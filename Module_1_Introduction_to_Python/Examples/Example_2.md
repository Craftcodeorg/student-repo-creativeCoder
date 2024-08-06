### Module Title: Introduction to Python ###

### Learning Objectives ###
- Understand and apply Example 2: Performing arithmetic operations in practical scenarios.
- Enhance problem-solving skills with real-world applications.

### User Profile ###
- **Interest**: Formula 1 Racing
- **Career Goal**: Python Developer
- **Technical Experience**: Beginner
- **Preferred Learning Method**: Project-based learning, interactive tutorials, and code-along videos

---

## Example 2: Performing Arithmetic Operations

### 1. Introduction
Arithmetic operations are fundamental in any programming language, and Python provides a simple yet powerful way to perform these operations. In the context of healthcare, arithmetic operations can be used in various applications such as calculating medication dosages, analyzing patient data, or managing hospital resources. This example will introduce you to basic arithmetic operations in Python and demonstrate how these can be applied to solve real-world healthcare problems.

### 2. Code Snippet
Below is a Python code snippet that demonstrates performing basic arithmetic operations:

```python
# Example: Performing arithmetic operations in Python

# Basic arithmetic operations
a = 10
b = 5

# Addition
addition = a + b
print("Addition:", addition)  # Output: 15

# Subtraction
subtraction = a - b
print("Subtraction:", subtraction)  # Output: 5

# Multiplication
multiplication = a * b
print("Multiplication:", multiplication)  # Output: 50

# Division
try:
    division = a / b
    print("Division:", division)  # Output: 2.0
except ZeroDivisionError:
    print("Error: Division by zero is not allowed.")

# Modulus
modulus = a % b
print("Modulus:", modulus)  # Output: 0

# Exponentiation
exponentiation = a ** b
print("Exponentiation:", exponentiation)  # Output: 100000
```

### 3. Explanation
Let's break down the code step-by-step to understand each part:

1. **Variable Initialization**:
   - We start by initializing two variables `a` and `b` with values 10 and 5, respectively.

2. **Addition**:
   - We perform addition using the `+` operator and store the result in the `addition` variable.
   - `print("Addition:", addition)` outputs the result of the addition.

3. **Subtraction**:
   - We perform subtraction using the `-` operator and store the result in the `subtraction` variable.
   - `print("Subtraction:", subtraction)` outputs the result of the subtraction.

4. **Multiplication**:
   - We perform multiplication using the `*` operator and store the result in the `multiplication` variable.
   - `print("Multiplication:", multiplication)` outputs the result of the multiplication.

5. **Division**:
   - We perform division using the `/` operator and store the result in the `division` variable.
   - To handle potential division by zero errors, we use a `try-except` block.
   - `print("Division:", division)` outputs the result of the division.

6. **Modulus**:
   - We perform the modulus operation using the `%` operator to find the remainder of the division.
   - `print("Modulus:", modulus)` outputs the result of the modulus operation.

7. **Exponentiation**:
   - We perform exponentiation using the `**` operator and store the result in the `exponentiation` variable.
   - `print("Exponentiation:", exponentiation)` outputs the result of the exponentiation.

### 4. Application
#### Real-world Application: Medication Dosage Calculation in Healthcare
In healthcare, calculating the correct dosage of medication based on patient weight and other factors is crucial. Arithmetic operations can help automate these calculations, reducing the risk of human error and improving patient safety.

**Scenario**:
A doctor needs to prescribe a medication dosage based on a patient's weight. The dosage is calculated as 2 mg per kg of body weight. 

**Steps**:
1. **Input Patient Weight**:
   ```python
   patient_weight = 70  # in kg
   ```
2. **Calculate Dosage**:
   ```python
   dosage_per_kg = 2  # 2 mg per kg
   total_dosage = patient_weight * dosage_per_kg
   print("Total Dosage:", total_dosage, "mg")  # Output: 140 mg
   ```
3. **Output**:
   - The total dosage for a 70 kg patient is calculated to be 140 mg.

By automating such calculations, healthcare professionals can ensure accurate and efficient medication administration.

---

### Integration ###
Ensure the content is structured with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting.