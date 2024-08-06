### Module Title: Advanced Python Concepts ###

### Learning Objectives ###
- Apply the concept of "Exercise 5: Define a class with attributes and methods" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Formula 1 Racing and Healthcare.

### User Profile ###
- **Interest:** Formula 1 Racing
- **Career Goal:** Python Developer
- **Technical Experience:** Beginner
- **Learning Method Preferences:** Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements ###

#### 1. Problem Statement:
**Scenario:** You are tasked with developing a healthcare application to manage patient information and track their vital signs. Specifically, you need to create a class to represent a patient and include attributes such as name, age, and medical history, along with methods to display the patient's information and update their medical history.

**Problem Statement:** 
Define a class `Patient` that includes attributes for the patient's name, age, and medical history. Implement methods to:
1. Display the patient's information.
2. Update the patient's medical history with new entries.

#### 2. Starter Code:
```python
# Define the Patient class
class Patient:
    def __init__(self, name, age):
        """
        Initialize the patient with a name and age.
        Medical history is initialized as an empty list.
        """
        self.name = name
        self.age = age
        self.medical_history = []

    def display_info(self):
        """
        Display the patient's information.
        """
        # Provide a string representation of the patient's info
        info = f"Patient Name: {self.name}\nAge: {self.age}\nMedical History: {self.medical_history}"
        return info

    def update_medical_history(self, new_entry):
        """
        Add a new entry to the patient's medical history.
        """
        # Append the new entry to the medical history list
        self.medical_history.append(new_entry)

# Example usage
if __name__ == "__main__":
    # Create a new patient
    patient = Patient("John Doe", 30)
    
    # Update the patient's medical history
    patient.update_medical_history("2023-01-01: Annual check-up")
    patient.update_medical_history("2023-06-15: Blood test")

    # Display the patient's information
    print(patient.display_info())
```

#### 3. Hints:
1. **Hint 1:** Remember that the `__init__` method is used to initialize the attributes of the class. This is where you will set the name, age, and initialize the medical history list.
2. **Hint 2:** To update the medical history, you can use the `append` method to add new entries to the list.
3. **Hint 3:** When displaying the patient's information, consider using formatted strings (f-strings) to make the output more readable.
4. **Hint 4:** Think about edge cases, such as what happens if the medical history is empty when displaying the patient's information.

### Exercise Outcome ###
- The user should be able to define a class with attributes and methods, demonstrating an understanding of basic OOP principles in Python.
- The solution should include best practices, such as clear and concise code, appropriate use of comments, and error handling where necessary.

### Integration ###
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

---

### Summary and Next Steps ###
In this exercise, you've applied the concepts of defining classes with attributes and methods to create a healthcare application. This practical application helps solidify your understanding of Object-Oriented Programming in Python and prepares you for more complex scenarios.

Next, we'll explore **Advanced Data Structures**, where you'll learn about sophisticated ways to manage and manipulate data, further enhancing your Python programming skills. Stay tuned for more engaging and informative sessions!

---

### Multimedia Elements ###
- **Diagrams:** UML class diagrams to visualize the structure of the `Patient` class and its methods.
- **Videos:** Short video tutorials on defining classes and methods in Python.
- **Quizzes:** Interactive quizzes to reinforce understanding of key concepts.

By combining theoretical knowledge with practical, real-world examples, this exercise aims to provide a comprehensive understanding of Classes and Object-Oriented Programming, preparing you for advanced Python development tasks. Happy learning!