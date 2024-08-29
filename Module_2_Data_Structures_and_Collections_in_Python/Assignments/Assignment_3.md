### Assignment: Develop an Interactive Dashboard Using Dictionaries to Visualize Driver Statistics

#### Problem Statement:
Create a function that analyzes driver statistics for a Formula 1 racing team, utilizing the concepts of iteration and dictionaries discussed in the lecture. The function should calculate the average finishing position of drivers over a series of races and identify any drivers whose finishing positions were consistently worse than the average. This will help in visualizing driver performance and making informed decisions about team strategies.

#### Starter Code:
```python
# Starter code for analyzing driver statistics

def analyze_driver_statistics(driver_results):
    """
    Analyzes driver statistics from a dictionary of race results.
    
    Parameters:
    driver_results (dict): A dictionary where keys are driver names and values are lists of finishing positions.
    
    Returns:
    tuple: Average finishing position and a list of drivers with below-average performance.
    """
    
    # Step 1: Calculate the average finishing position
    total_positions = 0
    total_drivers = len(driver_results)
    
    for positions in driver_results.values():
        total_positions += sum(positions)
    
    avg_position = total_positions / (total_drivers * len(positions))
    
    # Step 2: Identify drivers with below-average performance
    below_average_drivers = []
    
    for driver, positions in driver_results.items():
        if sum(positions) / len(positions) > avg_position:
            below_average_drivers.append(driver)
    
    # Return results
    return avg_position, below_average_drivers

# Test the function with sample data
driver_stats = {
    'Lewis Hamilton': [1, 2, 1, 3],
    'Max Verstappen': [2, 1, 3, 1],
    'Charles Leclerc': [5, 4, 6, 5],
    'Sergio Perez': [3, 5, 4, 6]
}

average_position, underperformers = analyze_driver_statistics(driver_stats)
print(f"Average Finishing Position: {average_position}")
print(f"Drivers Below Average Performance: {underperformers}")
```

#### Detailed Instructions:
1. **Step 1**: Modify the function to return not only the average finishing position but also a list of drivers whose average finishing position is worse than the overall average. Ensure that you calculate the average for each driver correctly.

2. **Step 2**: Enhance the output to provide detailed feedback. For example, instead of just listing the drivers below average, include their average finishing positions as well. This will provide better insights into their performance.

3. **Step 3**: Add error handling to manage potential issues, such as an empty dictionary or drivers with no race results. Ensure your function handles these cases gracefully.

4. **Step 4**: Document your code thoroughly. Make sure to include comments explaining what each part of the code does and why it is necessary.

#### Criteria for Success and Evaluation:
- **Functionality**: The function must correctly calculate the average finishing position and identify drivers who performed below this average.
- **Code Quality**: The code should be clean, well-structured, and follow best practices in Python programming.
- **Documentation**: All parts of the code must be documented with clear comments explaining the logic and purpose of each section.
- **Output Format**: The output should be user-friendly and formatted clearly to present the results effectively.

By completing this assignment, you will reinforce your understanding of iteration in Python and its application in analyzing real-world data relevant to Formula 1 racing. This project will also contribute to your portfolio as you work towards your goal of becoming a Python Developer.