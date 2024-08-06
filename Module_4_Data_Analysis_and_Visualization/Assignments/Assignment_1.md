## Curriculum: Data Analysis and Visualization

### Module Title: Data Analysis and Visualization

---

### Assignment 1: Analyze a Dataset Containing F1 Race Results and Visualize the Performance of Different Drivers

---

#### Problem Statement

Develop a Python application that reads Formula 1 race data from a file, processes the data to identify key insights, and generates a summary report. The application should also visualize the performance of different drivers using various plots and charts. This task will integrate multiple concepts covered in the module and encourage practical application of data analysis and visualization techniques.

---

#### Requirements.txt

Create a `requirements.txt` file listing all necessary dependencies. This will facilitate a seamless setup in GitHub Codespaces.

```plaintext
pandas
numpy
matplotlib
seaborn
```

---

#### Starter Code

```python
# Starter code for F1 race data analysis
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

def read_data(file_path):
    return pd.read_csv(file_path)

def process_data(data):
    # Calculate average lap time
    data['Average_Lap_Time'] = data.groupby('Driver')['Lap_Time'].transform('mean')
    # Identify fastest driver
    fastest_driver = data.loc[data['Lap_Time'].idxmin()]['Driver']
    return data, fastest_driver

def generate_report(data, fastest_driver):
    report = f"Fastest Driver: {fastest_driver}\n"
    report += f"Average Lap Times:\n{data.groupby('Driver')['Average_Lap_Time'].mean()}"
    print(report)

def visualize_performance(data):
    plt.figure(figsize=(12, 6))
    sns.barplot(x='Driver', y='Lap_Time', data=data)
    plt.title('Lap Times of Different Drivers')
    plt.xlabel('Driver')
    plt.ylabel('Lap Time')
    plt.show()

# Provide the file path and call the functions
file_path = 'f1_race_data.csv'
data = read_data(file_path)
processed_data, fastest_driver = process_data(data)
generate_report(processed_data, fastest_driver)
visualize_performance(processed_data)
```

---

#### Detailed Instructions

1. **Step 1: Read the Data**
   - Load the F1 race data from the provided CSV file using pandas.
   - `file_path = 'f1_race_data.csv'`
   - `data = pd.read_csv(file_path)`

2. **Step 2: Process the Data**
   - Calculate the average lap time for each driver.
   - Identify the fastest driver based on the minimum lap time.
   - `data['Average_Lap_Time'] = data.groupby('Driver')['Lap_Time'].transform('mean')`
   - `fastest_driver = data.loc[data['Lap_Time'].idxmin()]['Driver']`

3. **Step 3: Generate a Summary Report**
   - Create a text-based summary report that includes the fastest driver and average lap times of all drivers.
   - Print the report to the console.
   - `print(f"Fastest Driver: {fastest_driver}")`
   - `print(f"Average Lap Times:\n{data.groupby('Driver')['Average_Lap_Time'].mean()}")`

4. **Step 4: Visualize the Performance**
   - Use Matplotlib and Seaborn to create visualizations of the lap times for different drivers.
   - Generate a bar plot showing the lap times of different drivers.
   - `sns.barplot(x='Driver', y='Lap_Time', data=data)`
   - `plt.title('Lap Times of Different Drivers')`

---

#### Criteria for Success and Evaluation

- **Data Reading**: The application should correctly read the data from the provided CSV file.
- **Data Processing**: The application should accurately calculate average lap times and identify the fastest driver.
- **Report Generation**: The summary report should include the fastest driver and average lap times, presented in a clear and concise format.
- **Visualization**: The bar plot should effectively visualize the lap times of different drivers, with appropriate titles and labels.

**Evaluation Rubric**:
- **Data Reading (20%)**: Correctly loads data from CSV file.
- **Data Processing (30%)**: Accurately calculates average lap times and identifies the fastest driver.
- **Report Generation (20%)**: Generates a clear and accurate summary report.
- **Visualization (30%)**: Creates an informative and well-labeled bar plot.

---

### Assignment 2: Develop an Interactive Dashboard for Healthcare Data Analysis

---

#### Problem Statement

Create a Python application that reads healthcare data from a file, processes the data to identify key insights, and visualizes the data using an interactive dashboard. The application should enable users to explore different aspects of the data through interactive charts and graphs, facilitating better decision-making in the healthcare industry.

---

#### Requirements.txt

```plaintext
pandas
numpy
matplotlib
seaborn
plotly
dash
```

---

#### Starter Code

```python
# Starter code for healthcare data analysis dashboard
import pandas as pd
import plotly.express as px
import dash
from dash import dcc, html
from dash.dependencies import Input, Output

def read_data(file_path):
    return pd.read_csv(file_path)

def process_data(data):
    # Example processing steps
    data['Average_Visit_Duration'] = data.groupby('Department')['Visit_Duration'].transform('mean')
    return data

def create_dashboard(data):
    app = dash.Dash(__name__)

    app.layout = html.Div([
        html.H1("Healthcare Data Analysis Dashboard"),
        dcc.Dropdown(
            id='department-dropdown',
            options=[{'label': dep, 'value': dep} for dep in data['Department'].unique()],
            value=data['Department'].unique()[0]
        ),
        dcc.Graph(id='visit-duration-graph')
    ])

    @app.callback(
        Output('visit-duration-graph', 'figure'),
        [Input('department-dropdown', 'value')]
    )
    def update_graph(selected_department):
        filtered_data = data[data['Department'] == selected_department]
        fig = px.bar(filtered_data, x='Date', y='Visit_Duration', title=f'Visit Duration in {selected_department}')
        return fig

    app.run_server(debug=True)

# Provide the file path and call the functions
file_path = 'healthcare_data.csv'
data = read_data(file_path)
processed_data = process_data(data)
create_dashboard(processed_data)
```

---

#### Detailed Instructions

1. **Step 1: Read the Data**
   - Load the healthcare data from the provided CSV file using pandas.
   - `file_path = 'healthcare_data.csv'`
   - `data = pd.read_csv(file_path)`

2. **Step 2: Process the Data**
   - Perform data processing to calculate the average visit duration for each department.
   - `data['Average_Visit_Duration'] = data.groupby('Department')['Visit_Duration'].transform('mean')`

3. **Step 3: Create the Dashboard**
   - Use Dash to create an interactive dashboard.
   - Add a dropdown menu for selecting different departments.
   - Display a bar graph showing the visit duration for the selected department.

4. **Step 4: Implement Interactivity**
   - Implement callback functions to update the graph based on the selected department.
   - Use Plotly Express to create the bar graph.
   - Ensure the dashboard updates dynamically when the user selects a different department.

---

#### Criteria for Success and Evaluation

- **Data Reading (20%)**: Application correctly reads data from the provided CSV file.
- **Data Processing (30%)**: Application accurately processes the data to calculate average visit durations.
- **Dashboard Creation (30%)**: Application creates an interactive dashboard with a dropdown menu and dynamic graphs.
- **Interactivity (20%)**: Dashboard updates dynamically based on user input, providing an intuitive and informative user experience.

**Evaluation Rubric**:
- **Data Reading (20%)**: Correctly loads data from CSV file.
- **Data Processing (30%)**: Accurately calculates average visit durations.
- **Dashboard Creation (30%)**: Creates an interactive and user-friendly dashboard.
- **Interactivity (20%)**: Implements dynamic updates based on user input.

---

### Summary and Next Steps

In these assignments, you will apply data analysis and visualization techniques to real-world scenarios in Formula 1 racing and healthcare. By completing these assignments, you will enhance your Python skills, gain practical experience with data analysis libraries, and create interactive visualizations that can be showcased in your portfolio.

**Next Steps**:
In the next lecture, we will explore advanced data manipulation and cleaning techniques using Pandas. You will learn how to handle missing values, perform various data transformations, and prepare data for analysis. Stay tuned and get ready to elevate your data analysis skills to the next level!

---

### Multimedia Elements

- **Videos**: Include links to introductory videos on Pandas, NumPy, Matplotlib, and Plotly to provide visual and auditory learning.
- **Diagrams**: Use flowcharts to explain the data analysis process.
- **Quizzes**: Embed short quizzes at the end of each section to reinforce learning and check comprehension.

This structured and engaging approach will ensure you grasp the fundamentals of data analysis and visualization with Python, setting you up for success in your journey to becoming a Python Developer.