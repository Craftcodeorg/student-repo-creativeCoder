# Assignment: Implement a Basic Function to Analyze Race Data for Top Speeds

## Problem Statement
Create a function that analyzes lap times for a Formula 1 car, using the techniques discussed in the lecture on basic syntax and data types. The function should calculate the average lap time and identify any laps where the time exceeded the average by more than 10%. This assignment is particularly relevant for those interested in data analysis within the context of Formula 1 racing.

## Starter Code
Below is a basic code framework that you will expand upon. The comments will guide you on where to implement your solutions.

```python
# Starter code for analyzing race lap times

def analyze_lap_times(lap_times):
    # Step 1: Calculate the average lap time
    avg_time = sum(lap_times) / len(lap_times)
    
    # Step 2: Identify laps that exceed the average by more than 10%
    slow_laps = []
    for time in lap_times:
        if time > avg_time * 1.1:
            slow_laps.append(time)
    
    # Return results (students will need to format the output)
    return avg_time, slow_laps

# Test the function with sample data
lap_times = [90.2, 91.5, 89.8, 95.0, 92.3]
average, slow_laps = analyze_lap_times(lap_times)
print(f"Average Lap Time: {average}")
print(f"Laps Exceeding 10% Over Average: {slow_laps}")
```

## Detailed Instructions
1. **Modify the Function**:
   - Change the function to return not only the average time and slow laps but also a list of lap numbers (indices) where the time exceeded the average by more than 10%. You can use the `enumerate` function to help with this.
   
   Example:
   ```python
   for index, time in enumerate(lap_times):
       if time > avg_time * 1.1:
           slow_laps.append((index, time))  # Store both index and time
   ```

2. **Enhance the Output**:
   - Format the output to provide more detailed feedback to the user, such as including the percentage by which each slow lap exceeded the average. You can calculate this percentage using:
   ```python
   percentage_exceed = ((time - avg_time) / avg_time) * 100
   ```

3. **Documentation**:
   - Ensure that your code is clean and well-documented. Add comments explaining each part of your code to clarify your logic.

4. **Testing**:
   - Create additional test cases with different sets of lap times to validate your function. Ensure that it handles edge cases, such as all laps being below or above average.

## Criteria for Success and Evaluation
Your submission will be evaluated based on the following criteria:

- **Functionality**: The function correctly calculates the average lap time and identifies slow laps.
- **Code Quality**: The code is clean, well-documented, and follows best practices (e.g., proper naming conventions, use of comments).
- **Output Formatting**: The output is clear and user-friendly, providing detailed information about slow laps and their respective percentages.
- **Testing**: Additional test cases demonstrate that your function works under various conditions.

By completing this assignment, you will gain practical experience in using basic syntax and data types in Python, while also enhancing your understanding of data analysis in the context of Formula 1 racing. This aligns with your career goals and interests in programming and data analysis.