### Module Title: Advanced Python Concepts

### Learning Objectives
- Apply the concept of "Exercise 1: Create and manipulate a dictionary" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, code-along videos

### Exercise Requirements

#### Problem Statement
You are tasked with creating a Python program to manage patient data in a healthcare setting. Specifically, you will create and manipulate a dictionary that stores patient information. This exercise will help you apply dictionary concepts in a real-world healthcare scenario, enhancing your problem-solving skills.

**Scenario**:
Imagine you are working as a Python developer in a hospital. Your task is to create a system to store and manipulate patient data. Each patient has a unique ID, and you need to store their name, age, and medical conditions. You will write functions to add, update, and retrieve patient information.

**Requirements**:
1. Create a dictionary to store patient information.
2. Write functions to:
    - Add new patients.
    - Update existing patient information.
    - Retrieve patient information by ID.
3. Ensure the program includes error handling for cases such as trying to update or retrieve non-existent patient records.

#### Starter Code
```python
# Starter code for managing patient information

# Initialize an empty dictionary to store patient data
patients = {}

# Function to add a new patient
def add_patient(patient_id, name, age, conditions):
    # Check if the patient_id already exists
    if patient_id in patients:
        print("Patient ID already exists.")
        return
    # Add new patient to the dictionary
    patients[patient_id] = {
        'name': name,
        'age': age,
        'conditions': conditions
    }
    print(f"Patient {name} added successfully.")

# Function to update an existing patient's information
def update_patient(patient_id, name=None, age=None, conditions=None):
    # Check if the patient_id exists
    if patient_id not in patients:
        print("Patient ID does not exist.")
        return
    # Update patient information
    if name:
        patients[patient_id]['name'] = name
    if age:
        patients[patient_id]['age'] = age
    if conditions:
        patients[patient_id]['conditions'] = conditions
    print(f"Patient {patient_id} updated successfully.")

# Function to retrieve patient information
def get_patient(patient_id):
    # Check if the patient_id exists
    if patient_id not in patients:
        print("Patient ID does not exist.")
        return None
    # Retrieve and return patient information
    return patients[patient_id]

# Example usage
add_patient(1, "John Doe", 30, ["Diabetes"])
update_patient(1, age=31)
patient_info = get_patient(1)
print(patient_info)
```

#### Hints
1. **Adding a Patient**: Ensure that the patient ID is unique. Use the `in` keyword to check if an ID already exists in the dictionary.
2. **Updating Patient Data**: Use the `get` method to safely access dictionary values and update only the provided fields.
3. **Retrieving Information**: Handle cases where the patient ID does not exist by returning a meaningful message or `None`.

**Hint Example**:
- When adding a new patient, check if the ID is unique:
  ```python
  if patient_id in patients:
      print("Patient ID already exists.")
  else:
      # Add patient
  ```

- For updating patient information, use conditionals to update only provided fields:
  ```python
  if name:
      patients[patient_id]['name'] = name
  ```

#### Exercise Outcome
By completing this exercise, you will:
- Demonstrate an understanding of dictionary operations (add, update, retrieve) in Python.
- Apply best practices, such as error handling and code documentation.
- Gain practical experience relevant to healthcare, aligning with your career goals as a Python Developer.

### Integration
The exercise content is structured for easy integration into the learning platform. Use markdown for formatting and include the starter code and hints directly in the exercise content. Any additional files or resources necessary for the exercise should be provided as links.

---

Thank you for participating in this exercise. Happy Coding!