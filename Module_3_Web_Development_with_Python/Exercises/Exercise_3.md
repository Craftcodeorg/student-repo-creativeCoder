### Module Title: Web Development with Python

---

### Learning Objectives
- Apply the concept of "Exercise 3: Handle a form and display submitted data" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to the Healthcare industry.

---

### User Profile
- **Interest:** Formula 1 Racing
- **Career Goal:** Python Developer
- **Technical Experience:** Beginner
- **Learning Method Preferences:** Project-based learning, interactive tutorials, and code-along videos

---

### Exercise Requirements

#### 1. **Problem Statement**
Develop a web application that collects and displays patient feedback for a healthcare service. The application should have a form where users can submit their feedback, and a page that displays all the submitted feedback.

#### 2. **Starter Code**

Below is the starter code to set up a basic Flask application. The code includes a form for submitting feedback and a route to display submitted feedback.

```python
from flask import Flask, render_template, request

app = Flask(__name__)

# Feedback storage (in-memory for this exercise)
feedback_list = []

@app.route('/')
def home():
    return render_template('index.html')

@app.route('/submit_feedback', methods=['GET', 'POST'])
def submit_feedback():
    if request.method == 'POST':
        # Get the submitted feedback from the form
        name = request.form['name']
        feedback = request.form['feedback']
        
        # Add the feedback to the feedback list
        feedback_list.append({'name': name, 'feedback': feedback})
        
        # Redirect to the feedback page
        return render_template('feedback.html', feedback_list=feedback_list)
    return render_template('submit_feedback.html')

@app.route('/feedback')
def feedback():
    return render_template('feedback.html', feedback_list=feedback_list)

if __name__ == '__main__':
    app.run(debug=True)
```

**Templates**

Create three HTML files in a `templates` directory: `index.html`, `submit_feedback.html`, and `feedback.html`.

**index.html**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Home</title>
</head>
<body>
    <h1>Welcome to the Healthcare Feedback System</h1>
    <a href="/submit_feedback">Submit Feedback</a>
    <a href="/feedback">View Feedback</a>
</body>
</html>
```

**submit_feedback.html**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Submit Feedback</title>
</head>
<body>
    <h1>Submit Your Feedback</h1>
    <form method="POST" action="/submit_feedback">
        <label for="name">Name:</label><br>
        <input type="text" id="name" name="name" required><br><br>
        <label for="feedback">Feedback:</label><br>
        <textarea id="feedback" name="feedback" required></textarea><br><br>
        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

**feedback.html**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Feedback</title>
</head>
<body>
    <h1>Submitted Feedback</h1>
    <ul>
        {% for feedback in feedback_list %}
            <li><strong>{{ feedback.name }}</strong>: {{ feedback.feedback }}</li>
        {% endfor %}
    </ul>
</body>
</html>
```

#### 3. **Hints**
- Start by understanding how HTML forms work and how data is submitted using POST requests.
- Use Flask's `request.form` to access the data submitted through the form.
- Make sure you handle both GET and POST methods in your route to display the form and process submissions.
- Consider how you might persist the feedback data in a real-world scenario (e.g., using a database).

---

### Exercise Outcome
- The user should be able to create a simple web application that handles form submission and displays submitted data.
- The user will understand how to implement routes that handle different HTTP methods and how to work with form data in Flask.
- The solution will incorporate best practices, including error handling and code comments to explain the reasoning behind each step.

---

### Integration
This exercise content is well-structured with clear headings and sections for easy parsing and integration into the learning platform. The provided code snippets are annotated, and necessary templates are included to guide the user through the exercise.

---

By completing this exercise, the user will gain practical experience in handling form submissions and displaying data using Flask, a skill that is transferable to other web development projects, including those related to their interests in Formula 1 Racing and Healthcare.