# Module Title: Introduction to Web Development with Flask

## Example 3: Displaying Dynamic Content Using Jinja2 Templates

### 1. Introduction
In this example, we will explore the significance of using Jinja2 for rendering dynamic content in Flask applications, particularly within the Healthcare industry. Jinja2 allows developers to create dynamic web pages by embedding Python-like expressions within HTML, enabling the delivery of personalized and interactive experiences for users. For instance, in a healthcare application, it can be used to display patient data, appointment schedules, or real-time health monitoring information.

### 2. Code Snippet
Below is a well-commented code snippet that demonstrates how to use Jinja2 to display dynamic content related to patient appointments in a healthcare application.

```python
from flask import Flask, render_template

app = Flask(__name__)

# Sample data representing patient appointments
appointments = [
    {'patient_name': 'John Doe', 'date': '2023-10-01', 'time': '10:00 AM'},
    {'patient_name': 'Jane Smith', 'date': '2023-10-01', 'time': '11:00 AM'},
    {'patient_name': 'Alice Johnson', 'date': '2023-10-02', 'time': '09:30 AM'}
]

@app.route('/appointments')
def show_appointments():
    try:
        # Render the appointments template with the appointment data
        return render_template('appointments.html', appointments=appointments)
    except Exception as e:
        # Handle any exceptions that may occur
        return f"An error occurred while rendering appointments: {e}"

if __name__ == '__main__':
    app.run(debug=True)
```

**HTML Template (appointments.html):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Patient Appointments</title>
</head>
<body>
    <h1>Upcoming Patient Appointments</h1>
    <ul>
        {% for appointment in appointments %}
            <li>{{ appointment.patient_name }} - {{ appointment.date }} at {{ appointment.time }}</li>
        {% endfor %}
    </ul>
</body>
</html>
```

### 3. Explanation
1. **Importing Libraries**: The code begins by importing the necessary libraries from Flask.
2. **Sample Data**: A list of dictionaries named `appointments` is created to simulate patient appointment data. Each dictionary contains the patient's name, appointment date, and time.
3. **Route Definition**: The route `/appointments` is defined to handle requests for displaying appointments.
4. **Error Handling**: A try-except block is used to catch any exceptions that may occur while rendering the template.
5. **Rendering Template**: The `render_template` function is called with the template name `appointments.html` and the `appointments` data passed as context.
6. **HTML Template**: The HTML file uses Jinja2 syntax to loop through each appointment and display the patient's name, date, and time in a list format.

This code effectively implements key concepts from the lecture by utilizing variables and control structures to create a dynamic web page that displays real-time data relevant to healthcare providers.

### 4. Application
In a real-world healthcare application, this concept can be applied to create a patient management system where healthcare providers can view their upcoming appointments. By dynamically rendering this information, doctors and nurses can efficiently manage their schedules and ensure timely patient care. This approach not only improves operational efficiency but also enhances patient satisfaction by providing clear and accessible information regarding their appointments.

### Summary
This example illustrates how Jinja2 can be used to render dynamic content in Flask applications, specifically within the context of healthcare. By understanding and applying these concepts, learners can build interactive applications that improve workflows and user experiences in various domains, including healthcare.

### Next Steps
In the next lecture, we will delve into forms and user input handling in Flask applications, enabling users to submit data and receive feedback effectively. To prepare for this topic, consider reviewing basic HTML form elements and their purposes. This foundational knowledge will enhance your understanding of how to process user inputs effectively in Flask applications.