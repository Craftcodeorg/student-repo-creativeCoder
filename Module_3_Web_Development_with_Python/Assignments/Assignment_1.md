### Personalized Curriculum for "Web Development with Python"

#### Module Title: Web Development with Python

---

### Assignment 1: Create a Flask/Django App for Stock Portfolio Tracking

**Problem Statement:**
Develop a web application using Flask or Django that allows users to manage a stock portfolio. The app should support adding, updating, and removing stocks. Additionally, it should display current stock prices and provide a summary of the portfolio's performance.

**Requirements:**
- Allow users to add, update, and remove stocks.
- Fetch real-time stock prices using an API.
- Display a summary of the portfolio, including total investment and current value.
- Provide data visualization of stock performance over time.

**Requirements.txt:**
```
Flask==2.0.2  # or Django==3.2
requests==2.26.0
pandas==1.3.3
matplotlib==3.4.3
```

**Starter Code:**
```python
# Flask Starter Code for Stock Portfolio App
from flask import Flask, request, render_template
import requests
import pandas as pd

app = Flask(__name__)

portfolio = []

@app.route('/')
def home():
    # Fetch real-time stock prices and calculate portfolio value
    for stock in portfolio:
        response = requests.get(f'https://api.example.com/stock/{stock["symbol"]}')
        stock['price'] = response.json()['price']
    return render_template('portfolio.html', portfolio=portfolio)

@app.route('/add', methods=['POST'])
def add_stock():
    symbol = request.form['symbol']
    quantity = int(request.form['quantity'])
    portfolio.append({'symbol': symbol, 'quantity': quantity})
    return home()

@app.route('/remove', methods=['POST'])
def remove_stock():
    symbol = request.form['symbol']
    portfolio[:] = [stock for stock in portfolio if stock['symbol'] != symbol]
    return home()

if __name__ == '__main__':
    app.run(debug=True)
```

**Detailed Instructions:**
1. **Set Up Your Environment:**
   - Install Flask and other dependencies listed in `requirements.txt`.
   - Create a new Flask project and set up the basic project structure.

2. **Build the Portfolio Page:**
   - Create an HTML template (`portfolio.html`) to display the list of stocks, their quantities, and current prices.
   - Add a form to allow users to add new stocks to their portfolio.

3. **Implement CRUD Operations:**
   - Use Flask routes to handle adding and removing stocks.
   - Fetch real-time stock prices using an API (e.g., Alpha Vantage, Yahoo Finance).

4. **Data Visualization:**
   - Integrate a library like Matplotlib to visualize the portfolio's performance over time.
   - Add a chart to the portfolio page showing stock performance.

5. **Testing and Deployment:**
   - Test the application locally to ensure all features work as expected.
   - Optionally, deploy your Flask app to a platform like Heroku or PythonAnywhere.

**Criteria for Success and Evaluation:**
- The app should allow users to manage their stock portfolio effectively.
- Real-time stock prices should be fetched and displayed accurately.
- The portfolio summary should correctly calculate the total investment and current value.
- Data visualization should provide clear insights into stock performance.

---

### Assignment 2: Interactive Dashboard for F1 Race Data

**Problem Statement:**
Create a web application using Flask or Django that visualizes Formula 1 race data. The application should fetch real-time race statistics from an API, allow users to filter data by race, driver, or team, and display interactive charts.

**Requirements:**
- Fetch real-time F1 race data using an API.
- Visualize race data using interactive charts.
- Allow users to filter data by race, driver, or team.

**Requirements.txt:**
```
Flask==2.0.2  # or Django==3.2
requests==2.26.0
plotly==5.3.1
pandas==1.3.3
```

**Starter Code:**
```python
# Flask Starter Code for F1 Race Data Dashboard
from flask import Flask, render_template, request
import requests
import plotly.express as px
import pandas as pd

app = Flask(__name__)

@app.route('/')
def home():
    response = requests.get('https://api.example.com/f1/race-data')
    race_data = response.json()
    df = pd.DataFrame(race_data)
    fig = px.line(df, x='lap', y='time', color='driver')
    graph_html = fig.to_html()
    return render_template('dashboard.html', graph=graph_html)

@app.route('/filter', methods=['POST'])
def filter_data():
    driver = request.form['driver']
    team = request.form['team']
    response = requests.get(f'https://api.example.com/f1/race-data?driver={driver}&team={team}')
    race_data = response.json()
    df = pd.DataFrame(race_data)
    fig = px.line(df, x='lap', y='time', color='driver')
    graph_html = fig.to_html()
    return render_template('dashboard.html', graph=graph_html)

if __name__ == '__main__':
    app.run(debug=True)
```

**Detailed Instructions:**
1. **Set Up Your Environment:**
   - Install Flask and other dependencies listed in `requirements.txt`.
   - Create a new Flask project and set up the basic project structure.

2. **Build the Dashboard Page:**
   - Create an HTML template (`dashboard.html`) to display the interactive charts.
   - Use Plotly to create dynamic and interactive visualizations of the race data.

3. **Fetch and Display Data:**
   - Use Flask routes to fetch race data from an API.
   - Pass the data to Plotly for visualization and render the charts in the HTML template.

4. **Add Filtering Functionality:**
   - Implement a form in the dashboard template to allow users to filter race data by driver or team.
   - Modify the Flask routes to handle filtering and update the displayed charts accordingly.

5. **Testing and Deployment:**
   - Test the application locally to ensure all features work as expected.
   - Optionally, deploy your Flask app to a platform like Heroku or PythonAnywhere.

**Criteria for Success and Evaluation:**
- The app should fetch and display real-time F1 race data accurately.
- Interactive charts should provide clear and insightful visualizations of race data.
- Filtering functionality should work seamlessly and update the charts dynamically.

---

### Assignment 3: Automating Stock Market Analysis

**Problem Statement:**
Develop a web application using Flask or Django that automates stock market analysis. The app should collect historical stock data, analyze trends using data analysis libraries, and generate downloadable reports.

**Requirements:**
- Collect historical stock data from an API.
- Analyze stock trends using Pandas.
- Generate and provide downloadable reports.

**Requirements.txt:**
```
Flask==2.0.2  # or Django==3.2
requests==2.26.0
pandas==1.3.3
matplotlib==3.4.3
```

**Starter Code:**
```python
# Flask Starter Code for Automating Stock Market Analysis
from flask import Flask, render_template, request, send_file
import requests
import pandas as pd
import matplotlib.pyplot as plt

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

@app.route('/analyze', methods=['POST'])
def analyze_stock():
    symbol = request.form['symbol']
    response = requests.get(f'https://api.example.com/stock/{symbol}/historical')
    stock_data = response.json()
    df = pd.DataFrame(stock_data)
    # Analyze trends
    trend = df['close'].rolling(window=20).mean()  # Simple moving average
    df['trend'] = trend
    # Generate report
    plt.figure(figsize=(10, 5))
    plt.plot(df['date'], df['close'], label='Close Price')
    plt.plot(df['date'], df['trend'], label='Trend (20-day SMA)')
    plt.legend()
    plt.savefig('static/report.png')
    return render_template('report.html', symbol=symbol)

@app.route('/download', methods=['GET'])
def download_report():
    return send_file('static/report.png', as_attachment=True)

if __name__ == '__main__':
    app.run(debug=True)
```

**Detailed Instructions:**
1. **Set Up Your Environment:**
   - Install Flask and other dependencies listed in `requirements.txt`.
   - Create a new Flask project and set up the basic project structure.

2. **Build the Analysis Page:**
   - Create an HTML template (`index.html`) to allow users to input the stock symbol.
   - Create another template (`report.html`) to display the analysis results.

3. **Fetch and Analyze Data:**
   - Use Flask routes to fetch historical stock data from an API.
   - Use Pandas to analyze stock trends (e.g., calculate moving averages).

4. **Generate and Download Reports:**
   - Use Matplotlib to generate visualizations of the stock analysis.
   - Provide an option for users to download the generated reports.

5. **Testing and Deployment:**
   - Test the application locally to ensure all features work as expected.
   - Optionally, deploy your Flask app to a platform like Heroku or PythonAnywhere.

**Criteria for Success and Evaluation:**
- The app should collect and analyze historical stock data accurately.
- Generated reports should provide meaningful insights and visualizations.
- The download functionality should work seamlessly, allowing users to