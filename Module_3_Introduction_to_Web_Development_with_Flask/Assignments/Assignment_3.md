# Assignment: Implement User Authentication for Your Investment Portfolio App

## Problem Statement
In this assignment, you will implement user authentication for your investment portfolio app using Flask and Jinja2. This will involve creating a simple login and registration system that allows users to create an account, log in, and view their investment portfolio securely. This task will help you apply the concepts of dynamic HTML rendering with Jinja2, as discussed in the lecture.

## Starter Code
Below is a basic framework for your Flask application. You will need to build upon this code to implement user authentication.

```python
from flask import Flask, render_template, request, redirect, url_for, session
from flask_sqlalchemy import SQLAlchemy
from werkzeug.security import generate_password_hash, check_password_hash

app = Flask(__name__)
app.secret_key = 'your_secret_key'
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///users.db'
db = SQLAlchemy(app)

# User model
class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(150), unique=True, nullable=False)
    password = db.Column(db.String(150), nullable=False)

# Home route
@app.route('/')
def home():
    return render_template('home.html')

# Registration route
@app.route('/register', methods=['GET', 'POST'])
def register():
    if request.method == 'POST':
        username = request.form['username']
        password = generate_password_hash(request.form['password'], method='sha256')
        new_user = User(username=username, password=password)
        db.session.add(new_user)
        db.session.commit()
        return redirect(url_for('login'))
    return render_template('register.html')

# Login route
@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        username = request.form['username']
        password = request.form['password']
        user = User.query.filter_by(username=username).first()
        if user and check_password_hash(user.password, password):
            session['user_id'] = user.id
            return redirect(url_for('portfolio'))
    return render_template('login.html')

# Portfolio route
@app.route('/portfolio')
def portfolio():
    if 'user_id' in session:
        return render_template('portfolio.html')  # Add your portfolio logic here
    return redirect(url_for('login'))

if __name__ == '__main__':
    db.create_all()  # Create database tables
    app.run(debug=True)
```

### HTML Templates
You will also need to create the following HTML templates in a folder named `templates`:

1. **home.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Home</title>
</head>
<body>
    <h1>Welcome to Your Investment Portfolio App</h1>
    <a href="/register">Register</a>
    <a href="/login">Login</a>
</body>
</html>
```

2. **register.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Register</title>
</head>
<body>
    <h1>Register</h1>
    <form method="POST">
        <input type="text" name="username" placeholder="Username" required>
        <input type="password" name="password" placeholder="Password" required>
        <button type="submit">Register</button>
    </form>
</body>
</html>
```

3. **login.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Login</title>
</head>
<body>
    <h1>Login</h1>
    <form method="POST">
        <input type="text" name="username" placeholder="Username" required>
        <input type="password" name="password" placeholder="Password" required>
        <button type="submit">Login</button>
    </form>
</body>
</html>
```

4. **portfolio.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Your Portfolio</title>
</head>
<body>
    <h1>Your Investment Portfolio</h1>
    <!-- Display user's investment data here -->
    <a href="/">Logout</a>
</body>
</html>
```

## Detailed Instructions
1. **Database Setup**: Ensure you have SQLite installed and the `flask_sqlalchemy` package available. The starter code includes a basic SQLite setup for user data.

2. **User Registration**: Implement the registration logic in the `register()` function. Ensure that usernames are unique and passwords are hashed for security.

3. **User Login**: Complete the login logic in the `login()` function. Verify the user’s credentials and manage sessions to keep users logged in.

4. **Portfolio Page**: In the `portfolio()` function, implement logic to display the user's investment data once they are logged in.

5. **Template Rendering**: Use Jinja2 to dynamically render content in your HTML templates based on user sessions and data.

## Criteria for Success and Evaluation
- **Functionality**: The user registration and login processes should work correctly without errors.
- **Security**: Passwords must be stored securely using hashing.
- **Code Quality**: Code should be clean, well-organized, and follow best practices.
- **User Experience**: The application should provide clear feedback to users during registration and login.

### Success Criteria:
- The application allows users to register and log in successfully.
- User credentials are stored securely.
- The portfolio page is accessible only after successful login.

This assignment will not only reinforce your understanding of Jinja2 and Flask but also provide practical experience that can be valuable in your career as a Python Developer in the Healthcare industry.