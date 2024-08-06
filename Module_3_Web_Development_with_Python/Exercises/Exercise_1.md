### Module Title: Web Development with Python

---

### Learning Objectives
- Apply the concept of "Exercise 1: Create a basic route in Flask/Django" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Formula 1 Racing and Healthcare.
  
---

### User Profile
- **Interest**: Formula 1 Racing
- **Career Goal**: Python Developer
- **Technical Experience**: Beginner
- **Learning Method Preferences**: Project-based learning, interactive tutorials, code-along videos

---

### Exercise Requirements

1. **Problem Statement**: 

   **Develop a Healthcare Dashboard with Flask/Django**

   Your task is to create a basic web application using Flask (or Django) that serves a simple dashboard displaying patient data. This exercise will help you understand how to set up routes and render templates in a web framework, which is an essential skill for building more complex web applications. In the future, this knowledge can be applied to create dynamic applications like a Formula 1 race data dashboard or a stock market analysis tool.

   **Scenario**: 

   You are working as a Python Developer at a healthcare startup. Your team needs a web application that displays patient data for doctors to quickly access and review. The primary goal of this exercise is to set up a basic route and render a template with dummy patient data.

2. **Starter Code**:

   Here is the starter code to help you set up the basic environment for your Flask application. This code includes the basic structure of a Flask application with placeholders for your implementation.

   ```python
   # app.py
   from flask import Flask, render_template

   app = Flask(__name__)

   # Basic route to serve the home page
   @app.route('/')
   def home():
       # Dummy patient data
       patient_data = [
           {'name': 'John Doe', 'age': 30, 'condition': 'Flu'},
           {'name': 'Jane Smith', 'age': 45, 'condition': 'Diabetes'},
           {'name': 'Sam Brown', 'age': 50, 'condition': 'Hypertension'}
       ]
       return render_template('dashboard.html', patients=patient_data)

   if __name__ == '__main__':
       app.run(debug=True)
   ```

   ```html
   <!-- templates/dashboard.html -->
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Healthcare Dashboard</title>
   </head>
   <body>
       <h1>Patient Data</h1>
       <ul>
           {% for patient in patients %}
               <li>{{ patient.name }} - {{ patient.age }} - {{ patient.condition }}</li>
           {% endfor %}
       </ul>
   </body>
   </html>
   ```

3. **Hints**:

   - **Understanding Routes**: A route in Flask is a URL pattern that is associated with a view function. The `@app.route('/')` decorator binds the route to the `home` function.
   - **Templates**: Flask uses the Jinja2 template engine to render HTML templates. The `render_template` function takes the name of the template and any variables you want to pass to it.
   - **Passing Data**: In the `home` function, dummy patient data is passed to the `dashboard.html` template. This data is then looped through using Jinja2 syntax to display each patient's information.
   - **Running the Application**: Use the command `python app.py` to run the Flask application. Open your web browser and go to `http://127.0.0.1:5000/` to see your dashboard in action.

---

### Exercise Outcome

- **Understanding**: By completing this exercise, you should understand how to create a basic route and render a template in Flask, which are fundamental skills for any web developer.
- **Application**: You will see how these concepts apply to creating a simple healthcare dashboard, which can be adapted to more complex applications like a Formula 1 race data dashboard or stock market analysis tool.
- **Best Practices**: The solution should include well-commented code and proper error handling to ensure it is maintainable and scalable.

---

### Integration

Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform. Use the provided markdown for formatting and include any necessary files or resources as links.

---

**This concludes the exercise on creating a basic route in Flask/Django within the context of a healthcare application. Practice this exercise to gain a solid understanding of web development fundamentals, which will be beneficial for your career as a Python Developer.**