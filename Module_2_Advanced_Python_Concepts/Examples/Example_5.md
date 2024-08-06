### Module Title: Advanced Python Concepts

---

### Learning Objectives
- Understand and apply Example 5: Defining a class and creating objects in practical scenarios.
- Enhance problem-solving skills with real-world applications.

---

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Preferred Learning Method: Project-based learning, interactive tutorials, and code-along videos

---

### Example 5: Defining a class and creating objects

---

## Lecture: Defining a Class and Creating Objects

### Introduction
Welcome to the fifth lecture in the "Advanced Python Concepts" module! Today, we are going to explore **Defining a class and creating objects**, a crucial aspect of Object-Oriented Programming (OOP). As a Python Developer, understanding how to define classes and create objects is essential for building complex, scalable, and maintainable software. This concept is particularly useful in various domains, including Healthcare, where it can help in managing patient records, scheduling, and more.

---

### Key Concepts

#### 1. What is Object-Oriented Programming?
- **Definition**: OOP is a programming paradigm that uses "objects" to model real-world entities.
- **Importance**: Promotes code reuse, modularity, and organization.

#### 2. Classes and Objects
- **Class**: A blueprint for creating objects. Defines a set of attributes and methods.
- **Object**: An instance of a class. Holds data and behavior as defined by its class.

```python
class Patient:
    def __init__(self, name, age, patient_id):
        self.name = name
        self.age = age
        self.patient_id = patient_id

# Creating an object of Patient class
patient1 = Patient("John Doe", 45, "P001")
```

#### 3. Attributes and Methods
- **Attributes**: Variables that hold data about the object.
- **Methods**: Functions that define behaviors of the object.

```python
class Patient:
    def __init__(self, name, age, patient_id):
        self.name = name
        self.age = age
        self.patient_id = patient_id

    def display_info(self):
        return f"Patient ID: {self.patient_id}, Name: {self.name}, Age: {self.age}"

# Using the display_info method
print(patient1.display_info())  # Output: Patient ID: P001, Name: John Doe, Age: 45
```

#### 4. Inheritance
- **Definition**: A mechanism where a new class inherits attributes and methods from an existing class.
- **Use Case**: Promotes code reuse and logical hierarchy.

```python
class InPatient(Patient):
    def __init__(self, name, age, patient_id, room_number):
        super().__init__(name, age, patient_id)
        self.room_number = room_number

    def display_room(self):
        return f"Room Number: {self.room_number}"

# Creating an object of InPatient class
in_patient = InPatient("Jane Doe", 30, "P002", "101B")
print(in_patient.display_room())  # Output: Room Number: 101B
```

#### 5. Polymorphism
- **Definition**: The ability to present the same interface for different data types.
- **Use Case**: Allows functions to use objects of different classes interchangeably.

```python
class OutPatient(Patient):
    def display_info(self):
        return f"OutPatient ID: {self.patient_id}, Name: {self.name}, Age: {self.age}"

patients = [patient1, in_patient, OutPatient("Alice", 29, "P003")]
for patient in patients:
    print(patient.display_info())
```

---

### Real-world Application in Healthcare

#### Scenario: Managing Patient Records
- **Example**: Create classes for different types of patients, such as `Patient`, `InPatient`, and `OutPatient`. Implement methods to display patient details and manage hospital resources efficiently.

```python
class Patient:
    def __init__(self, name, age, patient_id):
        self.name = name
        self.age = age
        self.patient_id = patient_id

class InPatient(Patient):
    def __init__(self, name, age, patient_id, room_number):
        super().__init__(name, age, patient_id)
        self.room_number = room_number

    def display_info(self):
        return f"InPatient ID: {self.patient_id}, Name: {self.name}, Age: {self.age}, Room: {self.room_number}"

class OutPatient(Patient):
    def display_info(self):
        return f"OutPatient ID: {self.patient_id}, Name: {self.name}, Age: {self.age}"

# Creating objects
patient1 = Patient("John Doe", 45, "P001")
in_patient = InPatient("Jane Doe", 30, "P002", "101B")
out_patient = OutPatient("Alice", 29, "P003")

# Managing patients
patients = [patient1, in_patient, out_patient]
for patient in patients:
    print(patient.display_info())
```

### Step-by-Step Explanation
1. **Class Definition**: We define a `Patient` class with attributes `name`, `age`, and `patient_id`.
2. **Inheritance**: We create `InPatient` and `OutPatient` classes that inherit from `Patient`. `InPatient` includes an additional attribute `room_number`.
3. **Method Implementation**: Each class has a `display_info` method to show patient details.
4. **Object Creation**: We create objects for `Patient`, `InPatient`, and `OutPatient`.
5. **Managing Patients**: We store patient objects in a list and iterate through it to call `display_info` on each patient, demonstrating polymorphism.

### Application in Healthcare
In a hospital management system, this approach allows for efficient handling of different patient types, ensuring that relevant information is easily accessible and manageable. This can improve patient care and streamline hospital operations.

---

### Interactive Exercises

#### Exercise 1: Create a Healthcare Staff Class
- **Task**: Design a class `Staff` that includes attributes like `staff_name`, `role`, and `department`. Implement a method `work()` that prints a message indicating the staff is working.

#### Exercise 2: Build a Simple Patient Management System
- **Task**: Create classes `Patient`, `InPatient`, and `OutPatient`. Implement methods to add patients to a list and display patient details. 

#### Exercise 3: Visualize Patient Data
- **Task**: Develop a class `PatientData` that stores patient visit records and provides methods to calculate the average age of patients. Use a library like `matplotlib` to visualize patient demographics.

---

### Summary and Next Steps
In this lecture, you've learned about the fundamentals of defining classes and creating objects in Python. We've covered key concepts such as classes, objects, inheritance, and polymorphism, and explored their practical applications in Healthcare.

Next, we'll dive into **Advanced Data Structures**, where we'll explore more sophisticated ways to manage and manipulate data, further enhancing your Python programming skills. Stay tuned for an engaging and informative session!

---

### Multimedia Elements
- **Diagrams**: UML class diagrams to visualize the structure of classes and their relationships.
- **Videos**: Short video tutorials on OOP principles.
- **Quizzes**: Interactive quizzes to reinforce understanding of key concepts.

---

By combining theoretical knowledge with practical, real-world examples, this lecture aims to provide a comprehensive understanding of defining classes and creating objects, preparing you for advanced Python development tasks. Happy learning!