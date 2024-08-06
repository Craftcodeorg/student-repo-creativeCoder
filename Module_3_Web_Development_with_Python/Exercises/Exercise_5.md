# Module Title: Web Development with Python

## Learning Objectives
- Apply the concept of "Exercise 5: Build a simple RESTful API" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

## User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

## Exercise: Build a Simple RESTful API for Healthcare Data

### Problem Statement
You are a Python developer working for a healthcare startup. Your task is to build a simple RESTful API that allows the retrieval and management of patient records. The API should support operations such as creating a new patient record, retrieving a list of all patients, updating a patient's information, and deleting a patient record. This exercise will help you understand the basics of RESTful API development and how it can be applied to real-world scenarios in the healthcare industry.

### Starter Code
Below is the starter code to set up the basic environment for your RESTful API. We will be using Flask, a lightweight web framework for Python. Make sure you have Flask installed (`pip install Flask`).

```python
from flask import Flask, jsonify, request

app = Flask(__name__)

# A simple in-memory storage for patient records
patients = []

# Helper function to find a patient by ID
def find_patient(patient_id):
    for patient in patients:
        if patient["id"] == patient_id:
            return patient
    return None

# Route to get all patients
@app.route('/patients', methods=['GET'])
def get_patients():
    return jsonify(patients)

# Route to create a new patient
@app.route('/patients', methods=['POST'])
def add_patient():
    new_patient = request.get_json()
    patients.append(new_patient)
    return jsonify(new_patient), 201

# Route to get a single patient by ID
@app.route('/patients/<int:patient_id>', methods=['GET'])
def get_patient(patient_id):
    patient = find_patient(patient_id)
    if patient is None:
        return jsonify({'error': 'Patient not found'}), 404
    return jsonify(patient)

# Route to update an existing patient
@app.route('/patients/<int:patient_id>', methods=['PUT'])
def update_patient(patient_id):
    patient = find_patient(patient_id)
    if patient is None:
        return jsonify({'error': 'Patient not found'}), 404
    updated_data = request.get_json()
    patient.update(updated_data)
    return jsonify(patient)

# Route to delete a patient
@app.route('/patients/<int:patient_id>', methods=['DELETE'])
def delete_patient(patient_id):
    patient = find_patient(patient_id)
    if patient is None:
        return jsonify({'error': 'Patient not found'}), 404
    patients.remove(patient)
    return '', 204

if __name__ == '__main__':
    app.run(debug=True)
```

### Hints
1. **Understanding Routes and Methods**: Each route in the Flask application corresponds to a specific URL and HTTP method (GET, POST, PUT, DELETE). Understanding these will help you map out the required API endpoints.
   
2. **Working with JSON**: The Flask `request` object allows you to access incoming JSON data via `request.get_json()`. Ensure that your API endpoints correctly handle JSON input and output.

3. **Error Handling**: Implement error handling to manage cases where patient records are not found. Use appropriate HTTP status codes (e.g., 404 for not found, 201 for created).

4. **Updating Data**: When updating a patient record, make sure to only update the fields provided in the request. Use the `update()` method on dictionaries to achieve this.

5. **Testing the API**: Use tools like Postman or curl to test your API endpoints. This will help you understand how each endpoint works and ensure that your API is functioning correctly.

### Exercise Outcome
By completing this exercise, you will:
- Gain hands-on experience in building a RESTful API using Flask.
- Understand how to handle CRUD operations (Create, Read, Update, Delete) in a web application.
- Learn the importance of data validation and error handling in API development.
- Apply best practices in API development, including clear commenting and code organization.

### Integration
Ensure the exercise content is neatly structured with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

---

Happy coding, and remember to test your endpoints thoroughly to ensure they work as expected!