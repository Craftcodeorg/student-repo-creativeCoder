# Module Title: Introduction to Python Programming

## Example 2: Using Variables to Store Data

### 1. Introduction
In this section, we will explore the concept of using variables to store data, a fundamental aspect of programming that allows developers to manage and manipulate information effectively. This concept builds upon the foundational skills established in the lecture on setting up the Python environment, where we learned about the installation of Python, the importance of IDEs, and how to create virtual environments for our projects.

In the context of Healthcare, understanding how to use variables is crucial for tasks such as managing patient data, tracking medical records, and analyzing treatment outcomes. By mastering variables, you can create scripts that automate data entry, perform calculations on patient metrics, and generate reports that can help healthcare professionals make informed decisions.

### 2. Code Snippet
Here’s a simple code snippet that illustrates how to use variables to store data in Python:

```python
# Define variables to store patient data
patient_name = "John Doe"  # Storing the name of the patient
patient_age = 30           # Storing the age of the patient
patient_temperature = 98.6  # Storing the patient's temperature in Fahrenheit

# Function to check if the patient's temperature is normal
def check_temperature(temp):
    try:
        if temp < 97.0 or temp > 99.5:
            return "Abnormal temperature"
        else:
            return "Normal temperature"
    except TypeError:
        return "Invalid temperature value"

# Output patient information and temperature status
print(f"Patient Name: {patient_name}")
print(f"Patient Age: {patient_age}")
print(f"Patient Temperature: {patient_temperature}°F")
print(check_temperature(patient_temperature))
```

### 3. Explanation
- **Variable Declaration**: In the snippet, we declare three variables: `patient_name`, `patient_age`, and `patient_temperature`. Each variable is assigned a specific value that represents a piece of patient information.
  
- **Function Definition**: We define a function `check_temperature(temp)` that takes a temperature value as an argument. The function checks whether the temperature is within the normal range (97.0°F to 99.5°F) and returns a corresponding message.
  
- **Error Handling**: The function includes a try-except block to handle potential errors, such as passing an invalid type (e.g., a string instead of a float) to the function.
  
- **Output**: Finally, we print out the patient's information and the result of the temperature check. This demonstrates how variables can be used to store and manipulate data in a healthcare context.

### 4. Application
In a real-world healthcare application, this code could be part of an electronic health record (EHR) system where patient data is collected and analyzed. By using variables to store patient information, healthcare providers can efficiently track vital signs like temperature, which is critical for diagnosing illnesses.

For instance, if a nurse inputs a patient's temperature into the system, the program can automatically check if it falls within a normal range and alert the staff if there are any abnormalities. This not only streamlines the process of monitoring patient health but also enhances overall patient safety by ensuring timely responses to potential health issues.

### Conclusion
In this example, we have seen how using variables to store data is not just a basic programming skill but also a vital tool in healthcare applications. By continuing to build on these concepts, you will be well-equipped to develop scripts that can automate tasks and improve efficiency in various healthcare settings.

---

This structured content aligns with your learning goals as a beginner Python developer interested in applying programming skills in healthcare contexts. It emphasizes practical applications while ensuring clarity and engagement through code examples and real-world relevance.