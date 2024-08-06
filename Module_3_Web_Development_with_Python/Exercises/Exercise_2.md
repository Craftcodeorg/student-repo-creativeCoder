### Module Title: Web Development with Python ###

### Learning Objectives ###
- Apply the concept of "Exercise 2: Render a template with dynamic data" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Formula 1 Racing.
- Understand how to integrate and render dynamic data in web applications using Python frameworks (Flask/Django).

### User Profile ###
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements ###

#### 1. Problem Statement
Develop a problem statement that challenges the user to apply "Exercise 2: Render a template with dynamic data" to a scenario relevant to Healthcare. The problem should encourage critical thinking and be solvable with the concepts covered in "Web Development with Python".

**Problem Statement:**
You are tasked with developing a web application for a healthcare startup that wants to visualize patient data efficiently. The application should allow healthcare professionals to input patient details and dynamically render this data on a dashboard. You will use Flask to build this application and render templates with dynamic data.

**Requirements:**
- Set up a new Flask project.
- Create a form to input patient details (Name, Age, Diagnosis).
- Store the patient details in a list.
- Render a template to display the patient data dynamically.

#### 2. Starter Code
Provide starter code that sets up the basic environment or framework for the exercise. The code should be annotated to guide the user, especially focusing on areas relevant to Formula 1 Racing and suitable for someone with Beginner experience.

```python
# Import the necessary Flask modules
from flask import Flask, render_template, request

# Initialize the Flask application
app = Flask(__name__)

# Create a list to store patient details
patients = []

# Define the route for the home page
@app.route('/')
def index():
    return render_template('index.html', patients=patients)

# Define the route to handle form submissions
@app.route('/add_patient', methods=['POST'])
def add_patient():
    # Get the form data
    name = request.form['name']
    age = request.form['age']
    diagnosis = request.form['diagnosis']
    
    # Add the patient to the list
    patients.append({'name': name, 'age': age, 'diagnosis': diagnosis})
    
    # Redirect back to the home page to display the updated list of patients
    return render_template('index.html', patients=patients)

# Run the application
if __name__ == '__main__':
    app.run(debug=True)
```

Create a basic HTML form (`templates/index.html`):
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Patient Dashboard</title>
</head>
<body>
    <h1>Patient Dashboard</h1>
    <form action="/add_patient" method="POST">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required><br><br>
        <label for="age">Age:</label>
        <input type="number" id="age" name="age" required><br><br>
        <label for="diagnosis">Diagnosis:</label>
        <input type="text" id="diagnosis" name="diagnosis" required><br><br>
        <button type="submit">Add Patient</button>
    </form>
    <h2>Patient List</h2>
    <ul>
        {% for patient in patients %}
            <li>{{ patient.name }}, {{ patient.age }}, {{ patient.diagnosis }}</li>
        {% endfor %}
    </ul>
</body>
</html>
```

#### 3. Hints
Offer hints that can help the user approach the solution without giving it away. The hints should be tailored to support learning, encourage exploration, and offer insights into solving similar problems in the Healthcare industry.

**Hints:**
- **Hint 1:** Ensure you understand how to handle form submissions in Flask. Look up how to use `request.form` to access form data.
- **Hint 2:** Remember to update the patient list each time a new form is submitted. Think about how you can store and retrieve this data effectively within the application.
- **Hint 3:** Make sure your `index.html` template correctly loops through the list of patients to display their details dynamically.
- **Hint 4:** Consider error handling for edge cases, such as empty form submissions or invalid data types.

### Exercise Outcome ###
- The user should be able to solve the problem using the concepts learned, demonstrating an understanding of how these concepts apply to real-world scenarios in Healthcare.
- The solution should include best practices, error handling, and be well-commented to explain the reasoning behind each step.

### Integration ###
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

---

By completing this exercise, you will gain hands-on experience in setting up a Flask project, handling user input, and rendering dynamic content on a web page. This foundation will be crucial as you continue to build more complex web applications, whether for Healthcare, Formula 1 Racing, or any other domain of interest. Happy coding!