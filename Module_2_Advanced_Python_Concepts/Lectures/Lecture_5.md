## Lecture: 5. Classes and Object-Oriented Programming

### Introduction
Welcome to the fifth lecture in the "Advanced Python Concepts" module. Today, we will delve into **Classes and Object-Oriented Programming (OOP)**, a foundational pillar in modern software development. As an aspiring Python Developer, mastering OOP is crucial for designing robust, scalable, and maintainable software. This lecture will not only help you understand the theoretical aspects but also demonstrate practical applications in areas like Formula 1 Racing and Stock Market Investing, aligning with your interests and career goals.

### Key Concepts

#### 1. What is Object-Oriented Programming?
- **Definition**: OOP is a programming paradigm that uses "objects" to model real-world entities.
- **Importance**: Encourages code reuse, modularity, and organization.

#### 2. Classes and Objects
- **Class**: A blueprint for creating objects. Defines a set of attributes and methods.
- **Object**: An instance of a class. Holds data and behavior as defined by its class.

```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year

# Creating an object of Car class
my_car = Car("Ferrari", "SF21", 2021)
```

#### 3. Attributes and Methods
- **Attributes**: Variables that hold data about the object.
- **Methods**: Functions that define behaviors of the object.

```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year

    def display_info(self):
        return f"{self.year} {self.make} {self.model}"

# Using the display_info method
print(my_car.display_info())  # Output: 2021 Ferrari SF21
```

#### 4. Inheritance
- **Definition**: A mechanism where a new class inherits attributes and methods from an existing class.
- **Use Case**: Promotes code reuse and logical hierarchy.

```python
class RaceCar(Car):
    def __init__(self, make, model, year, team):
        super().__init__(make, model, year)
        self.team = team

    def display_team(self):
        return f"Team: {self.team}"

# Creating an object of RaceCar class
race_car = RaceCar("Ferrari", "SF21", 2021, "Scuderia Ferrari")
print(race_car.display_team())  # Output: Team: Scuderia Ferrari
```

#### 5. Polymorphism
- **Definition**: The ability to present the same interface for different data types.
- **Use Case**: Allows functions to use objects of different classes interchangeably.

```python
class SportsCar(Car):
    def display_info(self):
        return f"{self.year} {self.make} {self.model} - Sports Edition"

cars = [my_car, race_car, SportsCar("Ferrari", "488 GTB", 2021)]
for car in cars:
    print(car.display_info())
```

### Real-world Examples

#### 1. Formula 1 Racing
- **Scenario**: Building an F1 Race Track Simulator
- **Example**: Create classes for different components of a race track, such as `Track`, `PitStop`, and `Lap`.

```python
class Track:
    def __init__(self, name, length):
        self.name = name
        self.length = length

class PitStop:
    def __init__(self, location):
        self.location = location

class Lap:
    def __init__(self, lap_number, lap_time):
        self.lap_number = lap_number
        self.lap_time = lap_time

# Creating objects
track = Track("Monza", 5.793)
pit_stop = PitStop("Start/Finish Line")
lap = Lap(1, "1:20.345")
```

#### 2. Stock Market Investing
- **Scenario**: Developing Investment Portfolio Apps
- **Example**: Create classes for `Stock`, `Portfolio`, and `Transaction`.

```python
class Stock:
    def __init__(self, symbol, price):
        self.symbol = symbol
        self.price = price

class Portfolio:
    def __init__(self):
        self.holdings = []

    def add_stock(self, stock):
        self.holdings.append(stock)

# Creating objects
stock1 = Stock("AAPL", 150.00)
portfolio = Portfolio()
portfolio.add_stock(stock1)
```

### Interactive Exercises

#### Exercise 1: Create a Formula 1 Car Class
- **Task**: Design a class `F1Car` that includes attributes like `driver_name`, `team`, and `engine_type`. Implement a method `race()` that prints a message indicating the car is racing.

#### Exercise 2: Build a Simple Investment Portfolio
- **Task**: Create classes `Stock`, `Transaction`, and `Portfolio`. Implement methods to add stocks to the portfolio and calculate the total value of the portfolio.

#### Exercise 3: Visualize Race Data
- **Task**: Develop a class `RaceData` that stores lap times and provides methods to calculate the fastest lap. Use a library like `matplotlib` to visualize the lap times.

### Summary and Next Steps
In this lecture, you've learned about the fundamentals of Classes and Object-Oriented Programming in Python. We've covered key concepts such as classes, objects, inheritance, and polymorphism, and explored their practical applications in Formula 1 Racing and Stock Market Investing.

Next, we'll dive into **6. Advanced Data Structures**, where we'll explore more sophisticated ways to manage and manipulate data, further enhancing your Python programming skills. Stay tuned for an engaging and informative session!

---

### Multimedia Elements
- **Diagrams**: UML class diagrams to visualize the structure of classes and their relationships.
- **Videos**: Short video tutorials on OOP principles.
- **Quizzes**: Interactive quizzes to reinforce understanding of key concepts.

---

By combining theoretical knowledge with practical, real-world examples, this lecture aims to provide a comprehensive understanding of Classes and Object-Oriented Programming, preparing you for advanced Python development tasks. Happy learning!