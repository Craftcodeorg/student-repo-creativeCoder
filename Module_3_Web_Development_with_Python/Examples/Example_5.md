### Module Title: Web Development with Python

---

### Learning Objectives
- Understand and apply Example 5: Connecting to a database and performing CRUD operations in practical scenarios.
- Enhance problem-solving skills with real-world applications.

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Preferred Learning Method: Project-based learning, interactive tutorials, and code-along videos

---

### Example 5: Connecting to a Database and Performing CRUD Operations

#### 1. Introduction
Welcome to Example 5: "Connecting to a database and performing CRUD operations" in the "Web Development with Python" module. This example is crucial for anyone looking to become a proficient Python Developer, as it covers the essential skill of interacting with databases to create, read, update, and delete data (CRUD). Mastering CRUD operations will enable you to build robust and dynamic web applications, which is particularly useful in fields such as Healthcare, where data management and accessibility are critical.

#### 2. Code Snippet
Below is a Python code snippet using Flask and SQLite to demonstrate how to connect to a database and perform CRUD operations. The example is suitable for a beginner and includes error handling and best practices.

```python
# app.py
from flask import Flask, request, jsonify, g
import sqlite3

app = Flask(__name__)
DATABASE = 'healthcare.db'

def get_db():
    db = getattr(g, '_database', None)
    if db is None:
        db = g._database = sqlite3.connect(DATABASE)
    return db

@app.teardown_appcontext
def close_connection(exception):
    db = getattr(g, '_database', None)
    if db is not None:
        db.close()

@app.route('/patients', methods=['POST'])
def add_patient():
    try:
        data = request.get_json()
        db = get_db()
        cursor = db.cursor()
        cursor.execute("INSERT INTO patients (name, age, ailment) VALUES (?, ?, ?)",
                       (data['name'], data['age'], data['ailment']))
        db.commit()
        return jsonify({"message": "Patient added successfully!"}), 201
    except Exception as e:
        return jsonify({"error": str(e)}), 400

@app.route('/patients', methods=['GET'])
def get_patients():
    try:
        db = get_db()
        cursor = db.cursor()
        cursor.execute("SELECT * FROM patients")
        patients = cursor.fetchall()
        return jsonify(patients), 200
    except Exception as e:
        return jsonify({"error": str(e)}), 400

@app.route('/patients/<int:id>', methods=['PUT'])
def update_patient(id):
    try:
        data = request.get_json()
        db = get_db()
        cursor = db.cursor()
        cursor.execute("UPDATE patients SET name=?, age=?, ailment=? WHERE id=?",
                       (data['name'], data['age'], data['ailment'], id))
        db.commit()
        return jsonify({"message": "Patient updated successfully!"}), 200
    except Exception as e:
        return jsonify({"error": str(e)}), 400

@app.route('/patients/<int:id>', methods=['DELETE'])
def delete_patient(id):
    try:
        db = get_db()
        cursor = db.cursor()
        cursor.execute("DELETE FROM patients WHERE id=?", (id,))
        db.commit()
        return jsonify({"message": "Patient deleted successfully!"}), 200
    except Exception as e:
        return jsonify({"error": str(e)}), 400

if __name__ == '__main__':
    app.run(debug=True)
```

#### 3. Explanation
Let's break down the code step-by-step:

1. **Setup and Configuration**:
    - `Flask` is imported to create the web application.
    - `sqlite3` is imported for database operations.
    - The database file is named `healthcare.db`.

2. **Database Connection**:
    - `get_db()` function: Manages the connection to the SQLite database, ensuring only one connection per request.
    - `close_connection()`: Closes the database connection after the request ends.

3. **CRUD Operations**:
    - **Create (POST /patients)**:
        - Retrieves JSON data from the request.
        - Inserts the new patient record into the `patients` table.
        - Commits the transaction and returns a success message.
    - **Read (GET /patients)**:
        - Queries all patient records from the `patients` table.
        - Returns the list of patients in JSON format.
    - **Update (PUT /patients/<id>)**:
        - Retrieves JSON data from the request.
        - Updates the patient record with the specified `id` in the `patients` table.
        - Commits the transaction and returns a success message.
    - **Delete (DELETE /patients/<id>)**:
        - Deletes the patient record with the specified `id` from the `patients` table.
        - Commits the transaction and returns a success message.

4. **Error Handling**:
    - Each CRUD operation includes a `try-except` block to catch and return any errors that occur during database interactions.

#### 4. Application
In the Healthcare industry, efficient data management is critical for patient care and operational efficiency. By implementing CRUD operations, healthcare applications can:

- **Improve Patient Management**: Easily add, update, and delete patient records, ensuring that the most current information is available to healthcare providers.
- **Streamline Operations**: Automate routine tasks such as updating patient information or generating reports, freeing up time for healthcare staff to focus on patient care.
- **Enhance Data Accuracy**: Reduce the risk of errors by maintaining a single source of truth for patient data, accessible to all authorized personnel.

For example, a healthcare clinic could use this CRUD functionality to manage patient appointments, track medical histories, and update treatment plans dynamically, thereby improving the overall quality of care provided to patients.

---

### Integration
This example is structured with clear headings and sections for easy parsing and integration into the learning platform. The use of markdown ensures that the content is well-formatted and accessible.

#### Next Steps
In the next part of the module, we will delve into "Integrating Databases" in greater detail, where you'll learn more advanced techniques for database interaction, including more complex queries and optimizations. This will be crucial for further developing your projects, such as financial dashboards and F1 race data applications.

Stay tuned and keep practicing!