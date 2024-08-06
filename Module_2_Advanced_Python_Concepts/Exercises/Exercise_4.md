### Module Title: Advanced Python Concepts ###

### Learning Objectives ###
- Apply the concept of "Exercise 4: Write data to a file and read it back" in a practical coding exercise.
- Develop problem-solving skills through real-world scenarios relevant to Healthcare.

### User Profile ###
- Interest: Formula 1 Racing
- Career Goal: Python Developer
- Technical Experience: Beginner
- Learning Method Preferences: Project-based learning, interactive tutorials, and code-along videos

### Exercise Requirements ###

1. **Problem Statement**:
   Imagine you are developing a Python script to manage patient data for a healthcare application. Your task is to create a program that reads patient information from a file, processes it, and writes the results to a new file. This exercise will help you understand how to handle real-world data efficiently using Python.

2. **Starter Code**:
   Below is the starter code to help you get started. The code initializes basic file operations and includes comments to guide you through the process.

   ```python
   # Starter code for reading and writing patient data

   def read_patient_data(file_path):
       """
       Function to read patient data from a file.
       :param file_path: Path to the file containing patient data
       :return: List of patient records
       """
       try:
           with open(file_path, 'r') as file:
               patient_data = file.readlines()
           return patient_data
       except FileNotFoundError:
           print("The file was not found.")
           return []

   def write_processed_data(file_path, data):
       """
       Function to write processed data to a new file.
       :param file_path: Path to the file where processed data will be written
       :param data: List of processed data to be written
       """
       with open(file_path, 'w') as file:
           for record in data:
               file.write(record + '\n')

   def process_patient_data(patient_data):
       """
       Function to process patient data.
       :param patient_data: List of patient records
       :return: List of processed patient records
       """
       processed_data = []
       for record in patient_data:
           # Example processing: convert to uppercase
           processed_data.append(record.strip().upper())
       return processed_data

   # Example usage
   input_file = 'patient_data.txt'
   output_file = 'processed_patient_data.txt'
   
   # Read patient data from file
   data = read_patient_data(input_file)
   
   if data:
       # Process the data
       processed_data = process_patient_data(data)
       
       # Write the processed data to a new file
       write_processed_data(output_file, processed_data)
       print(f"Processed data has been written to {output_file}")
   else:
       print("No data to process.")
   ```

3. **Hints**:
   - **Hint 1**: Ensure you handle file operations using the `with` statement to manage resources efficiently.
   - **Hint 2**: Remember to strip any leading or trailing whitespace from each line of data before processing it.
   - **Hint 3**: Think about how you might handle different types of patient data, such as names, ages, or medical records, and how you can format the output file to make it readable.
   - **Hint 4**: Use try-except blocks to handle potential errors, such as file not found or read/write permissions.

### Exercise Outcome ###
- The user should be able to read patient data from a file, process it, and write the results to a new file using the concepts learned in the lecture.
- The solution should include best practices for file handling, error handling, and be well-commented to explain the reasoning behind each step.

### Integration ###
- Ensure the exercise content is well-structured, with clear headings and sections for easy parsing and integration into the learning platform.
- Use markdown for formatting and include any necessary files or resources as links.

---

**Example Problem Statement for Healthcare Context:**

**Task**:
1. Read patient information from `patient_data.txt`. Each line contains patient data in the format: `Name, Age, Condition`.
2. Convert all patient names to uppercase.
3. Write the processed patient data to `processed_patient_data.txt`.

**Starter Code**:
```python
# Starter code for reading and writing patient data

def read_patient_data(file_path):
    """
    Function to read patient data from a file.
    :param file_path: Path to the file containing patient data
    :return: List of patient records
    """
    try:
        with open(file_path, 'r') as file:
            patient_data = file.readlines()
        return patient_data
    except FileNotFoundError:
        print("The file was not found.")
        return []

def write_processed_data(file_path, data):
    """
    Function to write processed data to a new file.
    :param file_path: Path to the file where processed data will be written
    :param data: List of processed data to be written
    """
    with open(file_path, 'w') as file:
        for record in data:
            file.write(record + '\n')

def process_patient_data(patient_data):
    """
    Function to process patient data.
    :param patient_data: List of patient records
    :return: List of processed patient records
    """
    processed_data = []
    for record in patient_data:
        # Example processing: convert to uppercase
        processed_data.append(record.strip().upper())
    return processed_data

# Example usage
input_file = 'patient_data.txt'
output_file = 'processed_patient_data.txt'

# Read patient data from file
data = read_patient_data(input_file)

if data:
    # Process the data
    processed_data = process_patient_data(data)
    
    # Write the processed data to a new file
    write_processed_data(output_file, processed_data)
    print(f"Processed data has been written to {output_file}")
else:
    print("No data to process.")
```

---

**Hints**:
- **Hint 1**: Ensure you handle file operations using the `with` statement to manage resources efficiently.
- **Hint 2**: Remember to strip any leading or trailing whitespace from each line of data before processing it.
- **Hint 3**: Think about how you might handle different types of patient data, such as names, ages, or medical records, and how you can format the output file to make it readable.
- **Hint 4**: Use try-except blocks to handle potential errors, such as file not found or read/write permissions.

By completing this exercise, you will gain practical experience in file handling, which is a crucial skill for any Python developer, especially in real-world applications like healthcare data management.