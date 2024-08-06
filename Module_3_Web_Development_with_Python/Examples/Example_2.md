### Module Title: Web Development with Python

### Learning Objectives
- Understand and apply Example 2: Creating routes and handling HTTP requests in practical scenarios.
- Enhance problem-solving skills with real-world applications.

### User Profile
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Preferred Learning Method: Project-based learning, interactive tutorials, code-along videos

### Required Example Details

#### 1. Introduction
Welcome to Example 2: "Creating routes and handling HTTP requests" in our "Web Development with Python" module.

Creating routes and handling HTTP requests are fundamental skills for any web developer. Routes define how applications respond to client requests at specific endpoints, such as URLs, while HTTP requests enable data transfer between the client and server. Mastering these concepts is essential for building responsive and dynamic web applications.

In the healthcare industry, these skills can be used to create web applications that manage patient records, visualize health data, or automate appointment scheduling. In this lecture, we will explore how to create routes and handle HTTP requests using Flask, a lightweight Python web framework ideal for beginners.

#### 2. Code Snippet

Below is a simple Flask application that demonstrates how to create routes and handle HTTP requests. This example includes error handling and follows best practices to ensure a beginner-level programmer can easily understand and implement it.

```python
from flask import Flask, request, jsonify

app = Flask(__name__)

# Route to handle GET request
@app.route('/greet', methods=['GET'])
def greet_user():
    name = request.args.get('name', 'Guest')  # Get 'name' parameter from query string, default to 'Guest'
    if not name.isalpha():  # Error handling: Check if name contains only alphabets
        return jsonify({"error": "Invalid name. Only alphabetic characters are allowed."}), 400
    return jsonify({"message": f"Hello, {name}!"}), 200

# Route to handle POST request
@app.route('/submit', methods=['POST'])
def submit_data():
    data = request.get_json()  # Parse JSON data from request body
    if not data or 'patient_id' not in data or 'diagnosis' not in data:
        return jsonify({"error": "Invalid data. Please provide 'patient_id' and 'diagnosis'."}), 400
    patient_id = data['patient_id']
    diagnosis = data['diagnosis']
    # Here you would typically store the data in a database
    return jsonify({"message": f"Data received for patient {patient_id} with diagnosis '{diagnosis}'."}), 200

if __name__ == '__main__':
    app.run(debug=True)
```

#### 3. Explanation

Let's break down the code step-by-step:

1. **Importing Flask and necessary modules**:
    - `Flask`: The core class to create a Flask application.
    - `request`: To access incoming request data.
    - `jsonify`: To convert Python dictionaries to JSON responses.

2. **Initializing the Flask application**:
    ```python
    app = Flask(__name__)
    ```

3. **Creating a route to handle GET requests**:
    ```python
    @app.route('/greet', methods=['GET'])
    def greet_user():
        name = request.args.get('name', 'Guest')
        if not name.isalpha():
            return jsonify({"error": "Invalid name. Only alphabetic characters are allowed."}), 400
        return jsonify({"message": f"Hello, {name}!"}), 200
    ```
    - This route handles GET requests to the `/greet` endpoint.
    - It retrieves a `name` parameter from the query string, defaulting to 'Guest' if not provided.
    - It includes error handling to ensure the name contains only alphabetic characters.
    - Returns a JSON response with a greeting message.

4. **Creating a route to handle POST requests**:
    ```python
    @app.route('/submit', methods=['POST'])
    def submit_data():
        data = request.get_json()
        if not data or 'patient_id' not in data or 'diagnosis' not in data:
            return jsonify({"error": "Invalid data. Please provide 'patient_id' and 'diagnosis'."}), 400
        patient_id = data['patient_id']
        diagnosis = data['diagnosis']
        return jsonify({"message": f"Data received for patient {patient_id} with diagnosis '{diagnosis}'."}), 200
    ```
    - This route handles POST requests to the `/submit` endpoint.
    - Parses JSON data from the request body.
    - Validates the presence of `patient_id` and `diagnosis` in the received data.
    - Returns a JSON response confirming the received data.

5. **Running the application**:
    ```python
    if __name__ == '__main__':
        app.run(debug=True)
    ```
    - Starts the Flask application in debug mode, which provides useful error messages during development.

#### 4. Application

**Real-world Application in Healthcare: Managing Patient Records**

Imagine a healthcare web application where doctors need to manage patient records and diagnoses. The above example can be extended to handle such requirements:

- **GET Request**: A doctor can retrieve a greeting message by providing their name as a query parameter. This can be useful for creating a personalized user experience.
- **POST Request**: A doctor can submit patient records using a POST request. The JSON data can include patient information such as `patient_id` and `diagnosis`. This data can then be stored in a database for future reference.

**Example Scenario**: A doctor logs into a web application and submits a new diagnosis for a patient. The application processes the request, validates the data, and stores it securely. This improves efficiency by automating the record-keeping process and reduces the chances of human error.

By understanding and implementing routes and handling HTTP requests, you can create robust web applications that cater to real-world needs, such as healthcare management systems.

---

### Integration
Ensure the content is structured with clear headings and sections for easy parsing and integration into the learning platform. Use markdown for formatting. The content provided above is already formatted in markdown with clear section headings and detailed explanations to facilitate easy learning and integration.