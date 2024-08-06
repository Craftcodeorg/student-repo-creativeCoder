# Lecture 6: Database Integration with SQLAlchemy/Django ORM

## Introduction
Welcome to Lecture 6 of our "Web Development with Python" module! Today, we will delve into Database Integration with SQLAlchemy and Django ORM. As an aspiring Python Developer, mastering database integration is crucial because it allows you to store, retrieve, and manipulate data efficiently, which is the backbone of any dynamic web application. This lecture will build on what you've learned in previous lectures and equip you with the skills to create robust, data-driven applications.

## Key Concepts

### 1. Introduction to ORMs
- **Object-Relational Mapping (ORM)**: A technique that connects the rich object-oriented world of Python to the relational world of databases.
- **Benefits of Using ORMs**: Simplifies database interactions, improves productivity, and reduces the amount of boilerplate code.

### 2. SQLAlchemy Basics
- **Installation and Setup**: How to install SQLAlchemy using pip and configure it within a Flask project.
  ```python
  from flask import Flask
  from flask_sqlalchemy import SQLAlchemy
  
  app = Flask(__name__)
  app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///example.db'
  db = SQLAlchemy(app)
  ```
- **Defining Models**: Creating classes to represent database tables.
  ```python
  class User(db.Model):
      id = db.Column(db.Integer, primary_key=True)
      username = db.Column(db.String(80), unique=True, nullable=False)
      email = db.Column(db.String(120), unique=True, nullable=False)
  ```
- **CRUD Operations**: Performing Create, Read, Update, Delete operations.
  ```python
  # Create
  new_user = User(username='john_doe', email='john@example.com')
  db.session.add(new_user)
  db.session.commit()
  
  # Read
  user = User.query.first()
  
  # Update
  user.username = 'jane_doe'
  db.session.commit()
  
  # Delete
  db.session.delete(user)
  db.session.commit()
  ```

### 3. Django ORM Basics
- **Installation and Setup**: How to set up Django ORM within a Django project.
  ```bash
  django-admin startproject myproject
  cd myproject
  python manage.py startapp myapp
  ```
- **Defining Models**: Creating classes to represent database tables.
  ```python
  from django.db import models
  
  class User(models.Model):
      username = models.CharField(max_length=80, unique=True)
      email = models.EmailField(unique=True)
  ```
- **CRUD Operations**: Performing Create, Read, Update, Delete operations using Django ORM.
  ```python
  # Create
  user = User(username='john_doe', email='john@example.com')
  user.save()
  
  # Read
  user = User.objects.first()
  
  # Update
  user.username = 'jane_doe'
  user.save()
  
  # Delete
  user.delete()
  ```

## Real-world Examples

### Example 1: Building an F1 Race Data Tracker
- **Scenario**: Create a web application to track F1 race data.
- **SQLAlchemy Implementation**:
  ```python
  class Race(db.Model):
      id = db.Column(db.Integer, primary_key=True)
      race_name = db.Column(db.String(100), nullable=False)
      location = db.Column(db.String(100), nullable=False)
      date = db.Column(db.DateTime, nullable=False)
  ```
- **Django ORM Implementation**:
  ```python
  class Race(models.Model):
      race_name = models.CharField(max_length=100)
      location = models.CharField(max_length=100)
      date = models.DateTimeField()
  ```

### Example 2: Automating Stock Market Analysis
- **Scenario**: Develop a web application to automate stock market analysis.
- **SQLAlchemy Implementation**:
  ```python
  class Stock(db.Model):
      id = db.Column(db.Integer, primary_key=True)
      ticker = db.Column(db.String(10), unique=True, nullable=False)
      price = db.Column(db.Float, nullable=False)
      timestamp = db.Column(db.DateTime, nullable=False)
  ```
- **Django ORM Implementation**:
  ```python
  class Stock(models.Model):
      ticker = models.CharField(max_length=10, unique=True)
      price = models.FloatField()
      timestamp = models.DateTimeField()
  ```

## Interactive Exercises

### Exercise 1: Create a Portfolio Management System
- **Objective**: Build a system to manage an investment portfolio.
- **Task**: Define models for `Portfolio`, `Stock`, and `Transaction`, and implement CRUD operations using SQLAlchemy/Django ORM.
- **Steps**:
  1. Define the models with relevant fields.
  2. Create CRUD operations for each model.
  3. Implement a simple web interface to interact with the database.

### Exercise 2: Develop an F1 Race Tracker
- **Objective**: Create a web application to track F1 race results.
- **Task**: Define models for `Race`, `Driver`, and `Result`, and implement CRUD operations using SQLAlchemy/Django ORM.
- **Steps**:
  1. Define the models with relevant fields.
  2. Create CRUD operations for each model.
  3. Implement a simple web interface to interact with the database.

## Summary and Next Steps
In this lecture, we've explored database integration using SQLAlchemy and Django ORM. You learned how to set up both ORMs, define models, and perform CRUD operations. These skills are essential for developing dynamic, data-driven web applications as a Python Developer.

### Next Steps:
In the next lecture, we will cover "7. User Authentication and Authorization". This will involve creating secure login systems, managing user permissions, and ensuring data privacy, which are critical components of any professional web application.

Stay tuned, and keep practicing with the interactive exercises to solidify your understanding of database integration!