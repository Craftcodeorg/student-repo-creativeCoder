### Module Title: Introduction to Python Programming ###

### Exercise Requirements ###

1. **Problem Statement**: 
   Create a program that converts temperatures between Celsius and Fahrenheit, which can be useful for analyzing performance data in Formula 1 racing. For example, teams often need to adjust tire performance based on track temperature, which can be measured in Celsius. Your task is to create a program that allows users to input a temperature in Celsius and receive the equivalent temperature in Fahrenheit.

2. **Fill-in-the-Blank Starter Code**: 
   Below is a starter code template that you will complete. The comments guide you on what each part of the code should do, particularly focusing on the context of Formula 1 racing.

   ```python
   # Starter code for converting temperatures
   def celsius_to_fahrenheit(celsius):
       # Convert Celsius to Fahrenheit using the formula (C * 9/5) + 32
       fahrenheit = _______ * _______ + _______
       return fahrenheit

   # Function to get user input and display the converted temperature
   def main():
       # Prompt the user for a temperature in Celsius
       celsius_input = float(input("Enter temperature in Celsius: "))
       # Call the conversion function and store the result
       fahrenheit_output = celsius_to_fahrenheit(celsius_input)
       # Print the result in a formatted string
       print(f"{celsius_input}°C is equal to {fahrenheit_output}°F")

   # Run the main function
   if __name__ == "__main__":
       main()
   ```

3. **Hints**: 
   - Recall the formula for converting Celsius to Fahrenheit: \( F = C \times \frac{9}{5} + 32 \).
   - The first blank should be filled with the variable `celsius`, the second with `9/5`, and the third with `32`.
   - Ensure that you test your program with a few different Celsius values to verify its correctness.

4. **Expected Outcome**: 
   Upon completion, the student should have a functional program that converts temperatures from Celsius to Fahrenheit. The final solution should:
   - Correctly fill in the blanks in the starter code.
   - Handle any potential input errors (e.g., non-numeric input).
   - Include comments explaining each step of the code.
   - Demonstrate an understanding of how temperature conversion can be applied in real-world scenarios, such as adjusting strategies based on track conditions in Formula 1 racing.

### Integration ###
- Ensure that this exercise is structured clearly with headings for each section.
- Use markdown formatting for easy readability.
- Include any relevant resources or links to further reading on temperature conversion and its applications in data analysis for racing.

By completing this exercise, learners will not only practice Python programming skills but also apply these skills in a context related to their interests in Formula 1 racing, enhancing their understanding of practical applications in their future careers as Python Developers.