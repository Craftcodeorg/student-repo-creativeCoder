## Module Title: Web Development with Python

### Learning Objectives
- Apply the concept of "Exercise 6: Test your API with Postman" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

### User Profile
- Interest: Formula 1 Racing, Healthcare
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise 6: Test your API with Postman

#### Problem Statement
Imagine you are working for a healthcare startup that aims to digitize patient records and provide an API for healthcare providers to access patient data securely. Your task is to develop a simple API endpoint that allows healthcare providers to retrieve patient information. You will use Postman to test this API endpoint.

#### Starter Code
Below is the starter code to set up a basic Flask application with a single API endpoint to retrieve patient information. This example will guide you through integrating SQLAlchemy for database interactions and testing the API with Postman.

```python
# Import necessary libraries
from flask import Flask, jsonify, request
from flask_sqlalchemy import SQLAlchemy

# Initialize Flask app
app = Flask(__name__)

# Configure the SQLite database
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///patients.db'
db = SQLAlchemy(app)

# Define the Patient model
class Patient(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(100), nullable=False)
    age = db.Column(db.Integer, nullable=False)
    condition = db.Column(db.String(100), nullable=False)

# Create the database and tables
with app.app_context():
    db.create_all()

# Define an endpoint to retrieve patient information
@app.route('/api/patients/<int:patient_id>', methods=['GET'])
def get_patient(patient_id):
    patient = Patient.query.get_or_404(patient_id)
    return jsonify({
        'id': patient.id,
        'name': patient.name,
        'age': patient.age,
        'condition': patient.condition
    })

# Run the Flask app
if __name__ == '__main__':
    app.run(debug=True)
```

Instructions:
1. Save the above code in a file named `app.py`.
2. Run the application by executing `python app.py` in your terminal.
3. Use Postman to test the API endpoint by making a GET request to `http://127.0.0.1:5000/api/patients/1`.

#### Hints
- **Database Setup**: Ensure you have the SQLite database set up correctly. You can add sample patient records manually using the SQLite command line or a database management tool like DB Browser for SQLite.
- **Postman**: When testing with Postman, ensure your Flask app is running. Use the GET method to request patient information by patient ID.
- **Error Handling**: Consider what should happen if a patient with the provided ID does not exist. Use appropriate error handling to return a meaningful message.

#### Exercise Outcome
By the end of this exercise, you should be able to:
- Set up a basic Flask application with SQLAlchemy for database interactions.
- Create a simple API endpoint to retrieve patient information.
- Test your API using Postman.
- Implement best practices for error handling and code commenting.

### Integration
The exercise content is structured with clear headings and sections for easy integration into the learning platform. Use the provided markdown for formatting and include any necessary files or resources as links.

#### Next Steps
- Continue practicing by adding more endpoints to your API, such as creating, updating, and deleting patient records.
- Explore more advanced topics like user authentication and authorization to secure your API.
