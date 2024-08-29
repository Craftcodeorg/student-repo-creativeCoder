### Assignment: Create a Web Application that Displays Real-Time Stock Market Trends Using an API

---

#### Problem Statement:
You are tasked with developing a Flask web application that displays real-time stock market trends. This application will pull data from a stock market API and present it in a user-friendly format. The goal is to provide insights into stock performance, allowing users to track market trends effectively. This assignment is designed to enhance your understanding of Flask and its application in real-world scenarios, particularly in the finance sector.

---

#### Starter Code:
Below is a basic framework for your Flask application. You will need to build upon this code to complete the assignment.

```python
from flask import Flask, render_template
import requests

app = Flask(__name__)

# Step 1: Create a route for the home page
@app.route('/')
def home():
    return render_template('index.html')

# Step 2: Create a route to fetch stock market data
@app.route('/stock_data')
def stock_data():
    # Replace 'YOUR_API_KEY' and 'YOUR_API_URL' with actual API details
    api_url = 'YOUR_API_URL'
    response = requests.get(api_url)
    data = response.json()  # Assuming the API returns JSON data

    # Step 3: Process the data (this part will be expanded in your implementation)
    stock_info = process_stock_data(data)

    return stock_info  # This should be formatted for display

def process_stock_data(data):
    # Implement logic to extract relevant stock information from the data
    # Return a formatted string or data structure to be displayed on the webpage
    pass

if __name__ == '__main__':
    app.run(debug=True)
```

**Instructions:**
1. **Set Up Your Environment**: Ensure you have Flask installed. Use the command `pip install Flask` if you haven't done so already.
2. **Create HTML Template**: Create a folder named `templates` in your project directory and add an `index.html` file. This file will serve as the front end for your application.
3. **Fetch Data from API**: Replace `'YOUR_API_URL'` with the actual URL of a stock market API that provides real-time data. Make sure to handle any required authentication.
4. **Process and Display Data**: Implement the `process_stock_data` function to extract and format the necessary information from the API response. Consider what stock information is most relevant (e.g., current price, percentage change, etc.).
5. **Render Data on Frontend**: Modify the `home` function to pass the processed stock information to your HTML template for display.
6. **Test Your Application**: Run your Flask application and navigate to `http://127.0.0.1:5000/` to view your web application in action.

---

#### Detailed Instructions:
- **Step 1**: In `index.html`, create a simple layout that includes headings and placeholders for displaying stock information.
- **Step 2**: Use Bootstrap or another CSS framework to style your web page for better user experience.
- **Step 3**: Implement error handling for the API requests to ensure your application can gracefully handle any issues (e.g., network errors, invalid responses).
- **Step 4**: Add additional routes if needed, such as a route for historical data or specific stock details.

---

#### Criteria for Success and Evaluation:
- **Functionality**: The application should successfully fetch and display real-time stock market data.
- **Code Quality**: The code should be clean, well-organized, and follow best practices, including comments and documentation.
- **User Interface**: The web page should be visually appealing and easy to navigate, with clear presentation of data.
- **Error Handling**: Proper error handling should be implemented for API requests.

---

This assignment encourages you to apply the skills learned in the lecture on setting up Flask applications while providing a practical project that aligns with your interests in finance and data analysis. Good luck, and happy coding!