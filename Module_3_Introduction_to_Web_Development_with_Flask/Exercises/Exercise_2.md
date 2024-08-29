### Module Title: Introduction to Web Development with Flask

### Exercise Requirements

#### 1. Problem Statement:
As a budding Python Developer interested in the stock market, your task is to create a web application using Flask that allows users to submit their stock market predictions. This application will collect user data through a form and analyze the submitted predictions. By applying the routing and request handling concepts learned in the lecture, you will develop a simple but effective tool for gathering insights into stock market trends.

#### 2. Fill-in-the-Blank Starter Code:
Below is the starter code that you will need to complete. Fill in the blanks to ensure the functionality of the form and its handling.

```python
from flask import Flask, request

app = Flask(__name__)

# Route to display the prediction form
@app.route('/predict', methods=['GET'])
def predict():
    return '''
        <form method="POST" action="/submit">
            <input type="text" name="prediction" placeholder="Your stock market prediction">
            <input type="submit" value="Submit">
        </form>
    '''

# Route to handle form submission
@app.route('/submit', methods=['POST'])
def submit_data():
    # Retrieve the prediction data from the form
    prediction = request.form['prediction']
    # Process the prediction (you can add your analysis logic here)
    return f"Data received: {prediction}"

# Main function to run the app
if __name__ == '__main__':
    app.run(debug=True)
```

#### 3. Hints:
- **Hint 1**: Recall how to use the `@app.route()` decorator to define your routes. Make sure you specify the correct HTTP methods for each route.
- **Hint 2**: When handling form data, remember to use `request.form` to access the submitted values.
- **Hint 3**: Think about what kind of data you want to collect from users. You may want to add additional fields to your form, such as user name or email for better data management.
- **Hint 4**: Consider how you might validate the input data before processing it. This can help ensure that your application handles user submissions gracefully.

#### 4. Expected Outcome:
Upon completing this exercise, you should be able to:
- Create a Flask application with routes for displaying a form and handling user submissions.
- Collect and display user data through a simple HTML form.
- Demonstrate an understanding of Flask's routing and request handling capabilities.
- Ensure that your code is well-commented, explaining each step of the process, as emphasized in the lecture.

### Integration
This exercise is designed to reinforce your understanding of Flask while connecting to your interest in stock market analysis. Make sure to format your code and comments clearly, as this will help you when you showcase your work in your portfolio. Good luck, and enjoy coding!