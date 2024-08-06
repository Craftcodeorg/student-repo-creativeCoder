# Personalized Curriculum: Web Development with Python

## Module Title: Web Development with Python

### Assignment 2: Build a Form to Submit Favorite F1 Race Tracks

#### Problem Statement
Develop a web application using Flask or Django that allows users to submit their favorite F1 race tracks. The application should display the submitted race tracks in a list. This assignment integrates real-world applications, particularly focusing on Formula 1 Racing and relevant industry practices. The goal is to apply multiple concepts covered in the module to create a functional and interactive web application.

#### Requirements.txt
Here is a list of necessary dependencies for the assignment. This will facilitate a seamless setup in GitHub Codespaces.
```
Flask==2.0.1
Django==3.2.6
pandas==1.3.3
numpy==1.21.2
matplotlib==3.4.3
```

#### Starter Code
The starter code provides a basic setup for both Flask and Django projects. Choose one framework to complete the assignment.

**Flask Starter Code:**
```python
# app.py
from flask import Flask, request, render_template

app = Flask(__name__)

race_tracks = []

@app.route('/', methods=['GET', 'POST'])
def index():
    if request.method == 'POST':
        track_name = request.form['track_name']
        race_tracks.append(track_name)
    return render_template('index.html', race_tracks=race_tracks)

if __name__ == '__main__':
    app.run(debug=True)
```

**Django Starter Code:**
```python
# urls.py
from django.contrib import admin
from django.urls import path
from . import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.index, name='index'),
]

# views.py
from django.shortcuts import render
from django.http import HttpResponse

race_tracks = []

def index(request):
    if request.method == 'POST':
        track_name = request.POST.get('track_name')
        race_tracks.append(track_name)
    return render(request, 'index.html', {'race_tracks': race_tracks})
```

#### Detailed Instructions
**Flask Instructions:**
1. Set up a new Flask project and include the provided `app.py` as your main application file.
2. Create a template directory and an `index.html` file inside it.
3. In `index.html`, create a form that allows users to input their favorite F1 race track name.
4. Display the list of submitted race tracks below the form.
5. Run the Flask application and test the form submission.

**Django Instructions:**
1. Set up a new Django project and create a new app within it.
2. Replace the existing `urls.py` and `views.py` with the provided starter code.
3. Create a `templates` directory in your app and an `index.html` file inside it.
4. In `index.html`, create a form that allows users to input their favorite F1 race track name.
5. Display the list of submitted race tracks below the form.
6. Run the Django server and test the form submission.

**index.html (for both Flask and Django):**
```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Favorite F1 Race Tracks</title>
  </head>
  <body>
    <h1>Submit Your Favorite F1 Race Track</h1>
    <form method="post">
      <input type="text" name="track_name" placeholder="Enter race track name">
      <button type="submit">Submit</button>
    </form>
    <h2>Submitted Race Tracks</h2>
    <ul>
      {% for track in race_tracks %}
        <li>{{ track }}</li>
      {% endfor %}
    </ul>
  </body>
</html>
```

#### Criteria for Success and Evaluation
**Success Criteria:**
- The application should correctly display a form to submit the race track name.
- Submitted race tracks should appear in a list below the form.
- The application should handle multiple submissions and display all submitted race tracks.

**Evaluation Rubric:**
- **Functionality (40%)**: The form works correctly, and submitted race tracks are displayed.
- **User Interface (20%)**: The form and list are visually accessible and user-friendly.
- **Code Quality (20%)**: The code is clean, well-documented, and follows best practices.
- **Innovation (20%)**: Additional features or enhancements beyond the basic requirements.

This assignment encourages critical thinking and practical application of web development skills using Flask or Django. It supports your journey toward becoming proficient in web development, with a focus on Formula 1 Racing and relevant industry practices.