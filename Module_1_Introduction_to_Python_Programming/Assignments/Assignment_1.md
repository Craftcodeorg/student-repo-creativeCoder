# Assignment: Develop a Simple Text-Based Race Car Game

## Problem Statement
Create a text-based race car game that allows players to simulate a race between multiple cars. The game should use loops and conditionals to manage the racing logic, including the ability to accelerate, brake, and track lap times. Players will input commands to control their car, and the game will determine the winner based on the fastest lap times.

## Starter Code
Below is a basic framework for your race car game. You will need to expand upon this code by adding the necessary logic for the game mechanics.

```python
import random
import time

# Starter code for the text-based race car game

class RaceCar:
    def __init__(self, name):
        self.name = name
        self.lap_time = 0
        self.current_speed = 0

    def accelerate(self):
        self.current_speed += random.randint(5, 15)  # Increase speed randomly
        print(f"{self.name} accelerates to {self.current_speed} km/h.")

    def brake(self):
        self.current_speed -= random.randint(5, 10)  # Decrease speed randomly
        if self.current_speed < 0:
            self.current_speed = 0
        print(f"{self.name} slows down to {self.current_speed} km/h.")

    def complete_lap(self):
        # Simulate lap time based on current speed
        self.lap_time = 100 / self.current_speed if self.current_speed > 0 else float('inf')
        print(f"{self.name} completes the lap in {self.lap_time:.2f} seconds.")

def main():
    # Create race cars
    car1 = RaceCar("Car A")
    car2 = RaceCar("Car B")

    # Start the race
    for lap in range(3):  # Number of laps
        print(f"\n--- Lap {lap + 1} ---")
        for car in [car1, car2]:
            action = input(f"What should {car.name} do? (accelerate/brake): ").strip().lower()
            if action == "accelerate":
                car.accelerate()
            elif action == "brake":
                car.brake()
            else:
                print("Invalid action. Please choose 'accelerate' or 'brake'.")

            time.sleep(1)  # Simulate time delay for realism

            # Complete lap after actions
            car.complete_lap()

    # Determine the winner based on lap times
    winner = car1 if car1.lap_time < car2.lap_time else car2
    print(f"\nThe winner is {winner.name} with a lap time of {winner.lap_time:.2f} seconds!")

if __name__ == "__main__":
    main()
```

## Detailed Instructions
1. **Modify the `RaceCar` Class**: 
   - Add a method that allows players to check their current speed.
   - Implement a method that resets the lap time after each lap.

2. **Enhance Game Mechanics**:
   - Allow players to decide how many laps they want to race.
   - Introduce a feature that gives players a chance to "boost" their speed for one turn, increasing their speed significantly but requiring a cooldown period before it can be used again.

3. **Improve User Interaction**:
   - Enhance the input prompts to make them more user-friendly.
   - Provide feedback after each action, such as showing the current speed and lap time.

4. **Add Error Handling**:
   - Implement error handling for user inputs to ensure that only valid commands are accepted.

5. **Track Overall Performance**:
   - At the end of the race, display the total time taken for each car across all laps and the average lap time.

## Criteria for Success and Evaluation
- **Functionality**: The game should run without errors and allow players to control their cars effectively.
- **Code Quality**: The code should be clean, well-organized, and include comments explaining key sections.
- **User Experience**: The game should provide clear instructions and feedback to players throughout the race.
- **Creativity**: Additional features or enhancements beyond the basic requirements will be positively evaluated.

### Success Criteria:
- The game correctly implements racing mechanics using loops and conditionals.
- The code is well-documented and follows Python best practices.
- The user experience is engaging and informative, with clear prompts and feedback.

By completing this assignment, you will gain hands-on experience with Python programming concepts while creating a fun and interactive project that showcases your skills in coding and game development.