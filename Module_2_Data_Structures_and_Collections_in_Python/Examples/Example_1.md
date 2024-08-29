# Module Title: Data Structures and Collections in Python

## Example 1: Creating and Manipulating Lists

### 1. Introduction
In this section, we will delve into the concept of "Creating and manipulating lists" as covered in the lecture on Lists, Tuples, and Dictionaries. Lists are a fundamental data structure in Python, allowing for the storage and manipulation of ordered collections of items. This example will not only reinforce your understanding of lists but also illustrate their significance in the healthcare industry, where managing data efficiently is crucial.

### 2. Code Snippet
Here’s a simple code snippet demonstrating how to create and manipulate lists in Python, specifically tailored for a beginner level programmer:

```python
# List of patient temperatures recorded over a week
patient_temperatures = [98.6, 99.1, 98.7, 100.2, 97.9, 98.5, 99.3]

# Function to calculate the average temperature
def calculate_average(temperatures):
    if not temperatures:  # Check if the list is empty
        return 0
    return sum(temperatures) / len(temperatures)

# Function to find the highest temperature
def find_highest_temperature(temperatures):
    if not temperatures:  # Check if the list is empty
        return None
    return max(temperatures)

# Function to find the lowest temperature
def find_lowest_temperature(temperatures):
    if not temperatures:  # Check if the list is empty
        return None
    return min(temperatures)

# Calculate average, highest, and lowest temperatures
average_temp = calculate_average(patient_temperatures)
highest_temp = find_highest_temperature(patient_temperatures)
lowest_temp = find_lowest_temperature(patient_temperatures)

# Display results
print(f"Average Temperature: {average_temp:.2f}°F")
print(f"Highest Temperature: {highest_temp:.2f}°F")
print(f"Lowest Temperature: {lowest_temp:.2f}°F")
```

### 3. Explanation
Let's break down the code step-by-step:

1. **List Creation**: We create a list called `patient_temperatures` that holds temperature readings of a patient over a week.
   
2. **Function Definitions**:
   - **`calculate_average`**: This function takes a list of temperatures as input and returns the average temperature. It includes error handling to return `0` if the list is empty.
   - **`find_highest_temperature`**: This function returns the highest temperature from the list. If the list is empty, it returns `None`.
   - **`find_lowest_temperature`**: Similar to the previous function, it returns the lowest temperature or `None` if the list is empty.

3. **Calculating Results**: We call each function using `patient_temperatures` and store the results in variables.

4. **Output**: Finally, we print out the average, highest, and lowest temperatures with formatted output for better readability.

### 4. Application in Healthcare
In healthcare, monitoring patient vitals such as body temperature is crucial for diagnosing conditions and tracking recovery. This example demonstrates how lists can be utilized to manage patient temperature data effectively. 

- **Efficiency**: By storing multiple readings in a list, healthcare professionals can easily compute averages, identify trends, and make informed decisions based on patient data.
- **Real-World Relevance**: For instance, if a patient exhibits fluctuating temperatures over a week, analyzing this data can help healthcare providers determine if further investigation or intervention is necessary.

### Integration
This content is structured with clear headings and sections for easy parsing and integration into a learning platform. The use of markdown formatting enhances readability and organization, making it accessible for learners at all levels. 

By engaging with this example, you will build a strong foundation in utilizing lists in Python while also appreciating their practical applications in healthcare settings. This aligns perfectly with your goal of becoming a proficient Python Developer while focusing on real-world scenarios that matter to you.