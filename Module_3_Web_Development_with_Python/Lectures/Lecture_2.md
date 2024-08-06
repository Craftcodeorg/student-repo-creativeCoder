## Lecture 2: Setting up a Flask/Django Project

### 1. Introduction
Welcome to Lecture 2 of our "Web Development with Python" module. Today's focus is on setting up Flask and Django projects, which are essential frameworks for any Python Developer. Mastering these frameworks will empower you to create robust web applications, whether you're building investment portfolio apps, visualizing stock market trends, or analyzing F1 race data. By the end of this lecture, you'll have a solid foundation in both Flask and Django, ready to tackle your own projects.

### 2. Key Concepts
#### Flask
- **What is Flask?**
  Flask is a micro web framework written in Python. It's known for its simplicity and flexibility, making it ideal for small to medium-sized web applications.

- **Why Flask?**
  Flask allows you to build web applications quickly and with minimal overhead. It's particularly suited for projects where you want more control over your application's components.

- **Setting Up Flask**
  - **Installation**: Use `pip install flask` to install Flask.
  - **Basic Structure**: Create a new directory for your project and a file named `app.py`.
  - **Hello World Example**:
    ```python
    from flask import Flask
    app = Flask(__name__)

    @app.route('/')
    def hello_world():
        return 'Hello, World!'

    if __name__ == '__main__':
        app.run(debug=True)
    ```

#### Django
- **What is Django?**
  Django is a high-level Python web framework that encourages rapid development and clean, pragmatic design. It's designed to handle large-scale applications.

- **Why Django?**
  Django comes with a robust set of features out of the box, including an ORM, authentication, and an admin interface. This makes it ideal for larger projects where you need built-in functionality.

- **Setting Up Django**
  - **Installation**: Use `pip install django` to install Django.
  - **Creating a Project**: Run `django-admin startproject myproject` to create a new Django project.
  - **Running the Server**: Navigate to your project directory and run `python manage.py runserver`.
  - **Hello World Example**:
    - Create a new app within your project: `python manage.py startapp hello`.
    - In `hello/views.py`:
      ```python
      from django.http import HttpResponse

      def hello_world(request):
          return HttpResponse('Hello, World!')
      ```
    - In `myproject/urls.py`:
      ```python
      from django.contrib import admin
      from django.urls import path
      from hello.views import hello_world

      urlpatterns = [
          path('admin/', admin.site.urls),
          path('hello/', hello_world),
      ]
      ```

### 3. Real-world Examples
#### Flask Example: Analyzing F1 Race Data
- **Scenario**: Create a Flask web application to visualize F1 race statistics.
- **Code Snippet**:
  ```python
  from flask import Flask, render_template
  import pandas as pd

  app = Flask(__name__)

  @app.route('/')
  def index():
      # Load F1 race data
      data = pd.read_csv('f1_race_data.csv')
      races = data.to_dict(orient='records')
      return render_template('index.html', races=races)

  if __name__ == '__main__':
      app.run(debug=True)
  ```

#### Django Example: Investment Portfolio App
- **Scenario**: Develop a Django application to manage and visualize an investment portfolio.
- **Code Snippet**:
  ```python
  from django.shortcuts import render
  from .models import Investment

  def portfolio(request):
      investments = Investment.objects.all()
      return render(request, 'portfolio.html', {'investments': investments})
  ```

### 4. Interactive Exercises
#### Flask Exercise: Build a Simple F1 Race Track Visualizer
- **Objective**: Create a Flask application that allows users to input race track details and visualize them.
- **Steps**:
  1. Set up a new Flask project.
  2. Create a form for inputting race track details.
  3. Display the race track layout using a simple visualization library like Plotly.

#### Django Exercise: Develop a Stock Market Dashboard
- **Objective**: Create a Django application that fetches and displays stock market data.
- **Steps**:
  1. Set up a new Django project and app.
  2. Create models for storing stock data.
  3. Develop views and templates to display the data in a dashboard format.

### 5. Summary and Next Steps
In this lecture, we explored the basics of setting up Flask and Django projects. You learned how to install the frameworks, create basic project structures, and develop simple applications. These skills are foundational for any Python Developer aiming to build web applications.

#### Teaser for Next Lecture
In the next lecture, we will delve deeper into Flask and Django by exploring how to connect these frameworks to databases. This will enable you to build dynamic, data-driven web applications, further enhancing your ability to create interactive dashboards and automate stock market analysis.

Stay tuned and keep coding!