### Module Title: Introduction to Web Development with Flask ###

### Exercise Requirements ###

1. **Problem Statement**: 
   Create a simple web page that displays your favorite F1 car, incorporating the concepts learned in the lecture about setting up a Flask web application. The web page should include an image of the car, its name, and a brief description of why it is your favorite. This exercise will help you apply your understanding of Flask to create a dynamic web application.

2. **Fill-in-the-Blank Starter Code**: 
   Below is starter code that you will complete to create your Flask web application. Fill in the blanks to implement the functionality.

   ```python
   from flask import Flask, render_template
   
   app = Flask(__name__)

   @app.route('/')
   def home():
       # This function will render the main page
       return render_template('index.html')

   @app.route('/favorite_f1_car')
   def favorite_f1_car():
       # Define your favorite F1 car details here
       car_name = "______"  # e.g., "Ferrari SF90"
       car_image = "______"  # e.g., URL to the car image
       car_description = "______"  # e.g., "The Ferrari SF90 is my favorite because of its speed and design."
       
       return render_template('favorite_car.html', name=car_name, image=car_image, description=car_description)

   if __name__ == '__main__':
       app.run(debug=True)
   ```

   **HTML Template (favorite_car.html)**:
   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>My Favorite F1 Car</title>
   </head>
   <body>
       <h1>My Favorite F1 Car: {{ name }}</h1>
       <img src="{{ image }}" alt="{{ name }}">
       <p>{{ description }}</p>
       <a href="/">Back to Home</a>
   </body>
   </html>
   ```

3. **Hints**: 
   - Remember to create an `index.html` file that serves as the homepage for your application.
   - Use the `render_template` function to pass variables to your HTML files.
   - Ensure that you have Flask installed and that your project structure allows for templates to be rendered correctly (typically in a `templates` folder).
   - Think about how you can use CSS to style your page once you have the basic functionality working.

4. **Expected Outcome**: 
   By completing this exercise, you should be able to create a simple web application that displays your favorite F1 car on a dedicated page. The final solution should:
   - Include a clear structure with Flask routes.
   - Use HTML templates effectively to display dynamic content.
   - Be well-commented to explain the reasoning behind each step.
   - Follow best practices for error handling and code organization.

### Integration ###
- Ensure the exercise content is well-structured with clear headings and sections for easy parsing and integration into the learning platform.
- Use markdown for formatting and include any necessary files or resources as links. 

This exercise aligns with your interests in Formula 1 Racing and your goal of becoming a proficient Python developer, while also allowing you to build a portfolio piece that showcases your skills in web development.