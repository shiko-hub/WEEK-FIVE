ACTIVITY 1:

# Base class for a Superhero
class Superhero:
    def __init__(self, name, power, strength):
        self.name = name                # Public attribute
        self._power = power             # Protected attribute
        self.__strength = strength      # Private attribute

    def display_info(self):
        return f"Superhero: {self.name}, Power: {self._power}"

    def use_power(self):
        return f"{self.name} uses their {self._power}!"

# Derived class for a specific superhero with unique features
class Speedster(Superhero):
    def __init__(self, name, power, strength, speed):
        super().__init__(name, power, strength)
        self.speed = speed

    def use_power(self):
        return f"{self.name} runs at {self.speed} mph using their {self._power}!"

# Create objects
hero1 = Superhero("Captain Light", "Light Manipulation", 95)
hero2 = Speedster("Flash Bolt", "Super Speed", 80, 300)

# Test
print(hero1.display_info())          # Outputs: Superhero: Captain Light, Power: Light Manipulation
print(hero1.use_power())             # Outputs: Captain Light uses their Light Manipulation!
print(hero2.display_info())          # Outputs: Superhero: Flash Bolt, Power: Super Speed
print(hero2.use_power())             # Outputs: Flash Bolt runs at 300 mph using their Super Speed!


ACTIVITY 2:

# Base class: Animal
class Animal:
    def move(self):
        raise NotImplementedError("This method should be overridden in subclasses")

# Derived classes with their own version of move()
class Dog(Animal):
    def move(self):
        return "The dog is running 🐕"

class Bird(Animal):
    def move(self):
        return "The bird is flying 🐦"

class Fish(Animal):
    def move(self):
        return "The fish is swimming 🐟"

# Create objects
dog = Dog()
bird = Bird()
fish = Fish()

# Test polymorphism
print(dog.move())  # Outputs: The dog is running 🐕
print(bird.move()) # Outputs: The bird is flying 🐦
print(fish.move()) # Outputs: The fish is swimming 🐟
