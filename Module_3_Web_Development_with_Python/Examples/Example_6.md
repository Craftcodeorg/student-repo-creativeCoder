### Module Title: Web Development with Python

---

### Learning Objectives
- Understand and apply Example 6: Creating an API endpoint with Flask/Django in practical scenarios.
- Enhance problem-solving skills with real-world applications.

---

### User Profile
- **Interest**: Formula 1 Racing
- **Career Goal**: Python Developer
- **Technical Experience**: Beginner
- **Preferred Learning Method**: Project-based learning, interactive tutorials, and code-along videos

---

### Example 6: Creating an API Endpoint with Flask/Django

---

## Introduction
Welcome to Example 6 of our "Web Development with Python" module! Today, we will explore how to create an API endpoint using Flask and Django. As a beginner Python Developer interested in building dynamic web applications, mastering API creation is crucial. APIs (Application Programming Interfaces) enable different software systems to communicate with each other, which is fundamental in modern web development.

In the context of Healthcare, APIs can be used to retrieve patient data, manage appointments, and integrate with various health information systems. This example will provide you with the basic knowledge to create your own API endpoints, making your applications more functional and interactive.

---

## Code Snippet

### Flask Implementation

```python
from flask import Flask, jsonify, request

app = Flask(__name__)

# Sample data
patients = [
    {'id': 1, 'name': 'John Doe', 'age': 30, 'condition': 'Flu'},
    {'id': 2, 'name': 'Jane Smith', 'age': 25, 'condition': 'Cold'}
]

# API endpoint to get all patients
@app.route('/api/patients', methods=['GET'])
def get_patients():
    return jsonify(patients)

# API endpoint to add a new patient
@app.route('/api/patients', methods=['POST'])
def add_patient():
    if request.is_json:
        new_patient = request.get_json()
        patients.append(new_patient)
        return jsonify(new_patient), 201
    return jsonify({"error": "Request must be JSON"}), 400

# Error handling
@app.errorhandler(404)
def not_found(e):
    return jsonify({"error": "Not found"}), 404

if __name__ == '__main__':
    app.run(debug=True)
```

### Django Implementation

1. **Install Django and Create Project/App:**

```bash
pip install django
django-admin startproject healthcare
cd healthcare
python manage.py startapp api
```

2. **Define Models in `api/models.py`:**

```python
from django.db import models

class Patient(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
    condition = models.CharField(max_length=100)
```

3. **Create Serializers in `api/serializers.py`:**

```python
from rest_framework import serializers
from .models import Patient

class PatientSerializer(serializers.ModelSerializer):
    class Meta:
        model = Patient
        fields = '__all__'
```

4. **Define Views in `api/views.py`:**

```python
from rest_framework import viewsets
from .models import Patient
from .serializers import PatientSerializer

class PatientViewSet(viewsets.ModelViewSet):
    queryset = Patient.objects.all()
    serializer_class = PatientSerializer
```

5. **Configure URLs in `api/urls.py`:**

```python
from django.urls import path, include
from rest_framework.routers import DefaultRouter
from .views import PatientViewSet

router = DefaultRouter()
router.register(r'patients', PatientViewSet)

urlpatterns = [
    path('', include(router.urls)),
]
```

6. **Include API URLs in `healthcare/urls.py`:**

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/', include('api.urls')),
]
```

7. **Migrate and Run Server:**

```bash
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

---

## Explanation

### Flask Implementation
1. **Flask Setup**: Import Flask, jsonify, and request modules.
2. **Sample Data**: Create a list of dictionaries to simulate patient data.
3. **API Endpoints**:
   - `GET /api/patients`: Returns a JSON list of all patients.
   - `POST /api/patients`: Accepts a JSON object to add a new patient to the list.
4. **Error Handling**: Define a custom error handler for 404 errors.
5. **Run Server**: Start the Flask development server.

### Django Implementation
1. **Project and App Creation**: Create a new Django project and app.
2. **Model Definition**: Define a `Patient` model with `name`, `age`, and `condition` fields.
3. **Serializer Creation**: Create a serializer to convert model instances to JSON.
4. **View Definition**: Define a viewset to handle CRUD operations for the `Patient` model.
5. **URL Configuration**: Set up routing for the API endpoints.
6. **Database Migration**: Apply the database migrations to create tables.
7. **Run Server**: Start the Django development server.

---

## Application

### Real-world Application in Healthcare
Creating API endpoints is essential in Healthcare for the following reasons:
- **Data Retrieval**: APIs allow healthcare applications to retrieve patient data efficiently, enabling better patient management.
- **Integration**: APIs facilitate integration with other health information systems, improving interoperability.
- **Automation**: APIs can automate tasks such as appointment scheduling and prescription management, enhancing workflow efficiency.

For example, an API endpoint can be created to manage patient records in a healthcare system. This allows different departments (e.g., billing, radiology) to access and update patient data in real-time, ensuring that all stakeholders have the most current information, thereby improving patient care and operational efficiency.

---

### Summary and Next Steps
In this example, we've explored how to create API endpoints using Flask and Django. You learned the basics of setting up API routes, handling JSON data, and error handling. These skills are essential for building robust web applications in Healthcare and other industries.

### Next Steps:
In the next lecture, we will cover "User Authentication and Authorization". This will involve creating secure login systems, managing user permissions, and ensuring data privacy, which are critical components of any professional web application.

Stay tuned, and keep practicing with the interactive exercises to solidify your understanding of creating API endpoints!