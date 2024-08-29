### Assignment: Develop an Interactive Dashboard to Visualize F1 Race Data Using Flask

#### Problem Statement
Create a Flask web application that allows users to visualize Formula 1 race data. The application should provide routes for displaying race statistics and submitting user predictions for upcoming races. This project will help you apply the concepts of routing and handling requests learned in the lecture, while also integrating your interest in Formula 1 Racing.

#### Starter Code
Below is a basic framework for your Flask application. You will expand upon this code by adding the necessary functionality to create routes for displaying race data and handling user predictions.

```python
from flask import Flask, request, render_template

app = Flask(__name__)

# Route to display the race statistics
@app.route('/race')
def show_race():
    # Placeholder for race data (you can replace this with actual data)
    race_data = {
        'race_name': 'Grand Prix of Monaco',
        'lap_times': [90.2, 91.5, 89.8, 95.0, 92.3],
        'average_lap_time': sum([90.2, 91.5, 89.8, 95.0, 92.3]) / 5
    }
    return render_template('race.html', data=race_data)

# Route to handle user predictions
@app.route('/predict', methods=['GET', 'POST'])
def predict():
    if request.method == 'POST':
        prediction = request.form['prediction']
        return f"Your prediction: {prediction} has been submitted!"
    return '''
        <form method="POST">
            <input type="text" name="prediction" placeholder="Your prediction">
            <input type="submit" value="Submit">
        </form>
    '''

if __name__ == '__main__':
    app.run(debug=True)
```

#### Detailed Instructions
1. **Set Up Your Environment**: Ensure you have Flask installed in your Python environment. You can do this by running:
   ```bash
   pip install Flask
   ```

2. **Create HTML Template**: Create a new folder named `templates` in the same directory as your Python script. Inside this folder, create a file named `race.html` and add the following code:
   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>F1 Race Statistics</title>
   </head>
   <body>
       <h1>{{ data.race_name }}</h1>
       <h2>Average Lap Time: {{ data.average_lap_time }}</h2>
       <h3>Lap Times:</h3>
       <ul>
           {% for time in data.lap_times %}
               <li>{{ time }}</li>
           {% endfor %}
       </ul>
       <a href="/predict">Make a Prediction</a>
   </body>
   </html>
   ```

3. **Modify the Race Route**: In the `show_race` function, replace the placeholder `race_data` with actual race data if available. Ensure that the average lap time is calculated dynamically.

4. **Enhance User Predictions**: Modify the prediction form to include additional fields (e.g., predicted winner, lap time) as you see fit. Update the logic in the `/predict` route to handle these new fields.

5. **Test Your Application**: Run your Flask application by executing your Python script. Navigate to `http://127.0.0.1:5000/race` in your web browser to view the race statistics and test the prediction form.

#### Criteria for Success and Evaluation
- **Functionality**: The application should correctly display race statistics and handle user predictions.
- **Code Quality**: The code should be clean, well-documented, and follow best practices.
- **User Experience**: The output should be formatted in a clear and user-friendly manner, ensuring that users can easily navigate through the application.
- **Dynamic Data Handling**: Ensure that any changes made to the data (like lap times) are reflected in the output without requiring hard-coded values.

By completing this assignment, you will gain practical experience in web development using Flask while focusing on your passion for Formula 1 Racing. This will contribute to your portfolio and help you on your journey to becoming a proficient Python Developer.