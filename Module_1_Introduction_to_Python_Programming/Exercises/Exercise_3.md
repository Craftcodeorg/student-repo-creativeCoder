# Module Title: Introduction to Python Programming

## Exercise Requirements

### 1. Problem Statement
You are tasked with creating a function that calculates the factorial of a number. In the context of your interest in Formula 1 racing, consider this scenario: You are analyzing the performance of different drivers over multiple laps. The factorial can be used to calculate the total number of possible combinations of laps completed by a driver in a given race. This exercise will help you practice using functions and understand how to apply mathematical concepts in programming.

### 2. Fill-in-the-Blank Starter Code
Below is the starter code with strategically placed blanks that you need to fill in to complete the functionality of the factorial function.

```python
# Starter code for calculating factorial
def calculate_factorial(n):
    # Ensure n is a non-negative integer
    if n < 0:
        return "Factorial is not defined for negative numbers"
    elif n == 0:
        return 1  # Base case: factorial of 0 is 1
    else:
        factorial = 1
        # Calculate factorial using a loop
        for i in range(1, n + 1):
            factorial *= i  # Multiply factorial by each number up to n
        return factorial

# Test the function with an example value
print(f"The factorial of 5 is: {calculate_factorial(5)}")  # Expected output: 120
```

### 3. Hints
- Remember that the factorial of a number `n` (denoted as `n!`) is the product of all positive integers up to `n`.
- Use a loop to multiply the numbers from `1` to `n` together.
- Consider what should happen if a negative number is inputted into your function.
- Don’t forget to include comments in your code to explain each step, which will help you and others understand your logic later.

### 4. Expected Outcome
By completing this exercise, you should be able to:
- Fill in the blanks correctly, demonstrating your understanding of how to define and use functions in Python.
- Handle edge cases such as negative inputs appropriately.
- Comment your code effectively to explain your reasoning and ensure clarity.
- The final solution should be well-structured and adhere to best practices in Python programming.

### Integration
This exercise is designed to reinforce the concepts discussed in the lecture on basic syntax and data types. It provides a practical application relevant to your interests in Formula 1 racing, ensuring that you can relate programming concepts to real-world scenarios. Use markdown formatting for clarity, and remember that practice is key to mastering these skills!