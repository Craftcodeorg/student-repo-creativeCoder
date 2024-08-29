# Module Title: Introduction to Web Development with Flask

## 1. Introduction
In this section, we will explore "Example 2: Creating routes for different web pages" as discussed in the lecture titled "Creating Routes and Handling Requests." This example is particularly significant in the Healthcare sector, where effective routing can enhance user experience by providing seamless navigation through applications that manage patient data, appointment scheduling, or health records.

### Significance in Healthcare
In a healthcare application, routes can be used to direct users to various functionalities such as viewing patient information, submitting new patient data, or accessing healthcare resources. For instance, a route might allow healthcare professionals to submit patient treatment plans or access medical records through a user-friendly web interface. Understanding how to create and manage these routes is crucial for developing robust applications that improve efficiency and accessibility in healthcare settings.

## 2. Code Snippet
Here’s a simple Flask application that demonstrates how to create routes for different web pages relevant to a healthcare application. This code snippet includes error handling and best practices suitable for a beginner-level programmer.

```python
from flask import Flask, request, render_template_string

app = Flask(__name__)

# Route for the homepage
@app.route('/')
def home():
    return "<h1>Welcome to the Healthcare Portal</h1>"

# Route to display patient submission form
@app.route('/submit_patient', methods=['GET'])
def submit_patient():
    return render_template_string('''
        <form method="POST" action="/submit_patient">
            <input type="text" name="patient_name" placeholder="Patient Name" required>
            <input type="text" name="patient_age" placeholder="Patient Age" required>
            <input type="text" name="patient_condition" placeholder="Condition" required>
            <input type="submit" value="Submit">
        </form>
    ''')

# Route to handle patient submission
@app.route('/submit_patient', methods=['POST'])
def handle_patient_submission():
    try:
        name = request.form['patient_name']
        age = request.form['patient_age']
        condition = request.form['patient_condition']
        # Here you would typically save this data to a database
        return f"<h2>Patient {name} submitted successfully!</h2>"
    except Exception as e:
        return f"<h2>Error: {str(e)}</h2>", 400

if __name__ == '__main__':
    app.run(debug=True)
```

## 3. Explanation
### Step-by-Step Breakdown:
1. **Importing Libraries**: We import the `Flask` class and the `request` object from the `flask` module to handle web requests.
  
2. **Creating the Flask Application**: We instantiate the Flask application with `app = Flask(__name__)`.

3. **Defining Routes**:
   - **Homepage Route**: The `@app.route('/')` decorator defines the homepage of the application, returning a welcome message.
   - **Patient Submission Form Route**: The `@app.route('/submit_patient', methods=['GET'])` decorator defines a route that serves a form for submitting patient data.
   - **Handling Patient Submission**: The `@app.route('/submit_patient', methods=['POST'])` decorator handles form submissions. It retrieves form data using `request.form`, processes it, and returns a success message.

4. **Error Handling**: The `try-except` block in the `handle_patient_submission` function captures any errors that occur during data retrieval and returns an error message with a 400 status code if necessary.

### Real-World Problem Solving
This code snippet illustrates how healthcare professionals can easily submit patient information through a web interface. The application can be expanded to include database interactions for storing patient data, thus streamlining processes such as record-keeping and patient management.

## 4. Application in Healthcare
In a real-world healthcare application, this routing structure can be used to build an entire system where healthcare providers can manage patient records effectively. For example:
- **Patient Registration**: New patients can fill out their details through an online form, which can be routed to a backend service for storage in a database.
- **Appointment Scheduling**: Users could access different routes to schedule or view appointments, enhancing user engagement and operational efficiency.
- **Data Visualization**: By implementing additional routes, healthcare providers can visualize patient data trends over time, aiding in better decision-making.

By mastering the concepts of routing in Flask, you will be well-equipped to develop applications that address common challenges in healthcare, ultimately leading to improved patient care and streamlined operations. 

### Next Steps
In our next lecture, we will delve into rendering templates in Flask, allowing us to create more dynamic and visually appealing web pages. To prepare, consider reviewing HTML basics, which will help you understand how to structure your web pages effectively.