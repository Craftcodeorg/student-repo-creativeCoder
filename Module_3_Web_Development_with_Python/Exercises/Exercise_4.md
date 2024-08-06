## Module Title: Web Development with Python

### Learning Objectives
- Apply the concept of "Exercise 4: Perform CRUD operations on a database" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Formula 1 Racing.

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements

#### Problem Statement:
You are tasked with developing a simple web application to manage patient records in a healthcare clinic. This application should allow users to perform CRUD (Create, Read, Update, Delete) operations on the patient data. The web application will be built using Flask and an SQLite database.

The key features should include:
1. **Create**: Add new patient records.
2. **Read**: View a list of all patients.
3. **Update**: Edit existing patient records.
4. **Delete**: Remove patient records.

##### Requirements:
- Each patient record should include the following fields: `Patient ID`, `Name`, `Age`, `Gender`, and `Medical History`.
- Implement basic form validation to ensure that the data entered is correct.

#### Starter Code:
Below is the starter code that sets up the basic environment for the exercise. This code includes the setup for a Flask application and a basic SQLite database schema for storing patient records.

```python
from flask import Flask, request, render_template, redirect, url_for
from flask_sqlalchemy import SQLAlchemy

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///patients.db'
db = SQLAlchemy(app)

# Model for Patient
class Patient(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(100), nullable=False)
    age = db.Column(db.Integer, nullable=False)
    gender = db.Column(db.String(10), nullable=False)
    medical_history = db.Column(db.String(500), nullable=False)

# Home Route to display all patients
@app.route('/')
def index():
    patients = Patient.query.all()
    return render_template('index.html', patients=patients)

# Route to add a new patient
@app.route('/add', methods=['GET', 'POST'])
def add_patient():
    if request.method == 'POST':
        name = request.form['name']
        age = request.form['age']
        gender = request.form['gender']
        medical_history = request.form['medical_history']

        # Add new patient to database
        new_patient = Patient(name=name, age=age, gender=gender, medical_history=medical_history)
        db.session.add(new_patient)
        db.session.commit()
        return redirect(url_for('index'))
    return render_template('add.html')

# Route to update a patient
@app.route('/update/<int:id>', methods=['GET', 'POST'])
def update_patient(id):
    patient = Patient.query.get_or_404(id)
    if request.method == 'POST':
        patient.name = request.form['name']
        patient.age = request.form['age']
        patient.gender = request.form['gender']
        patient.medical_history = request.form['medical_history']
        
        db.session.commit()
        return redirect(url_for('index'))
    return render_template('update.html', patient=patient)

# Route to delete a patient
@app.route('/delete/<int:id>')
def delete_patient(id):
    patient = Patient.query.get_or_404(id)
    db.session.delete(patient)
    db.session.commit()
    return redirect(url_for('index'))

if __name__ == '__main__':
    db.create_all()
    app.run(debug=True)
```

#### Hints:
1. **Form Validation**: Ensure that the form fields are not empty when the form is submitted. You can use HTML5 attributes like `required` or add validation logic in the Flask route.
2. **Database Initialization**: Make sure to run `db.create_all()` to initialize the database tables before running the application.
3. **Error Handling**: Implement error handling to manage scenarios where the patient ID does not exist during update or delete operations.
4. **Modular Code**: Break down the logic into separate functions to keep the code clean and manageable.

### Exercise Outcome
- The user should be able to create, read, update, and delete patient records using the Flask web application.
- The solution should incorporate best practices such as proper error handling, form validation, and modular code structure.

### Integration
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting and include any necessary files or resources as links.

### Additional Resources
- [Flask Documentation](https://flask.palletsprojects.com/en/2.0.x/)
- [SQLAlchemy Documentation](https://docs.sqlalchemy.org/en/14/)
- [HTML Forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)

By completing this exercise, you will gain hands-on experience with CRUD operations in a real-world scenario, enhancing your skills in web development with Python and preparing you for more complex projects in the future. Happy coding!