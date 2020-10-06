## Object Oriented Programming

In this exercise you will primarily be exploring a Pokemon dataset. Pokemon are fictional creatures from the [Nintendo franchise](https://en.wikipedia.org/wiki/Pok%C3%A9mon) of the same name.

Some Pokemon facts that might be useful:
* The word "pokemon" is both singular and plural. You may refer to "one pokemon" or "many pokemon".
* Pokemon have attributes such as a name, weight, and height.
* Pokemon have one or multiple "types". A type is something like "electric", "water", "ghost", or "normal" that indicates the abilities that pokemon may possess.
* The humans who collect pokemon are called "trainers".

As a pokemon trainer we want to make sure our pokemon are performing at their peak. To measure this, we want to calculate a pokemon's Body Mass Index (or BMI). This is a statistic calculated using the pokemon's height and weight. 

To help with this task we we will create Pokemon objects that methods can be called on. 

You'll be working with following dictionaries to create the `Pokemon` objects


```python
# Run this cell without changes
bulbasaur_data = {
    "name": 'bulbasaur',
    "weight": 69,
    "height": 7,
    "base_experience": 64,
    "types": ["grass", "poison"]
}
charmander_data = {
    "name": 'charmander',
    "weight": 85,
    "height": 6,
    "base_experience": 62,
    "types": ["fire"]
}
squirtle_data = {
    "name": 'squirtle',
    "weight": 90,
    "height": 5,
    "base_experience": 63,
    "types": ["water"]
}
```

### 1. Creating a Class

Create a class called `Pokemon` with an `__init__` method. 

Along with the necessary `self` parameter, the `__init__` method should 
take in `data` as a parameter.

With the idea that one of the dictionaries above will be passed in as `data`, 
assign these specific attributes within the `__init__` method:
 
* `name` : value from the 'name' key of the dictionary passed in `data`
* `weight`: value from the 'weight' key of the dictionary passed in `data`
* `height`: value from the 'height' key of the dictionary passed in `data`


```python
# Create your class below with the correct syntax, including an __init__ method.

### BEGIN SOLUTION

class Pokemon:
    def __init__(self, data):
        self.name = data["name"]
        self.weight = data["weight"]
        self.height = data["height"]

### END SOLUTION
```


```python
# PUT ALL WORK FOR THE ABOVE QUESTION ABOVE THIS CELL
# THIS UNALTERABLE CELL CONTAINS HIDDEN TESTS

# Pokemon should be a class that exists in this namespace
assert type(Pokemon) == type

### BEGIN HIDDEN TESTS

pikachu = Pokemon({"name":"pikachu", "weight":60, "height":4, "base_experience":112, "types":["electric"]})

assert pikachu.name == "pikachu"
assert pikachu.weight == 60
assert pikachu.height == 4

### END HIDDEN TESTS
```

    
### 2. Instantiating Objects

Using the `bulbasaur_data`, `charmander_data` and `squirtle_data` variables, create the corresponding pokemon objects.


```python
# Replace None with appropriate code

bulbasaur = None
charmander = None
squirtle = None

### BEGIN SOLUTION

bulbasaur = Pokemon(bulbasaur_data)
charmander = Pokemon(charmander_data)
squirtle = Pokemon(squirtle_data)

### END SOLUTION

# This code will test your implementation. Make sure the values printed
# match the dictionaries above!
def print_pokeinfo(pkmn):
    print('Name: ' + pkmn.name)
    print('Weight: ' + str(pkmn.weight))
    print('Height: ' + str(pkmn.height))
    print('\n')
    
print_pokeinfo(bulbasaur)
print_pokeinfo(charmander)
print_pokeinfo(squirtle)
```

    Name: bulbasaur
    Weight: 69
    Height: 7
    
    
    Name: charmander
    Weight: 85
    Height: 6
    
    
    Name: squirtle
    Weight: 90
    Height: 5
    
    



```python
# PUT ALL WORK FOR THE ABOVE QUESTION ABOVE THIS CELL
# THIS UNALTERABLE CELL CONTAINS HIDDEN TESTS

assert type(bulbasaur) == Pokemon
assert type(charmander) == Pokemon
assert type(squirtle) == Pokemon

### BEGIN HIDDEN TESTS

assert bulbasaur.name == "bulbasaur"
assert charmander.weight == 85
assert squirtle.height == 5

### END HIDDEN TESTS
```

### 3. Instance Methods

Re-write the class `Pokemon` below, so that it has an instance method called `bmi` that calculates the BMI of a Pokemon.

BMI is defined by the formula: $\frac{weight}{height^{2}}$ 

The BMI should be calculated with weight in **kilograms** and height in **meters**. 

The height and weight data of Pokemon from the dictionaries above is in **decimeters** and **hectograms**, respectively. 

You will have to convert the given values of height and weight to kilograms and meters to make the BMI calculations correct.

For your convenience, here are the conversions:

```
1 decimeter = 0.1 meters
1 hectogram = 0.1 kilograms
```

**Don't forget**: since you are changing the `Pokemon` class, you will have to create **new objects** of this **new class**. 

If you use the objects created by the first class you wrote, they will not have the `bmi` instance!

You can assign these new objects the same names as you assigned the old ones:
`bulbasaur`, `charmander` and `squirtle`


```python
# Define the new Pokemon class here

# Replace None with appropriate code
bulbasaur = None
charmander = None
squirtle = None

### BEGIN SOLUTION

class Pokemon:
    def __init__(self, data):
        self.name = data["name"]
        self.weight = data["weight"]
        self.height = data["height"]
        
    def bmi(self):
        return (self.weight*0.1)/(self.height*0.1)**2

bulbasaur = Pokemon(bulbasaur_data)
charmander = Pokemon(charmander_data)
squirtle = Pokemon(squirtle_data)

### END SOLUTION

# This code will test your implementation
print(bulbasaur.bmi()) 
print(charmander.bmi()) 
print(squirtle.bmi()) 
```

    14.081632653061222
    23.611111111111104
    36.0



```python
# PUT ALL WORK FOR THE ABOVE QUESTION ABOVE THIS CELL
# THIS UNALTERABLE CELL CONTAINS HIDDEN TESTS

# bulbasaur.bmi should be a method on an instance of type Pokemon
import types
assert type(bulbasaur.bmi) == types.MethodType
# bulbasaur.bmi() should return a floating point number
assert type(bulbasaur.bmi()) == float
### BEGIN HIDDEN TESTS

assert bulbasaur.bmi() == (bulbasaur.weight*0.1)/(bulbasaur.height*0.1)**2

### END HIDDEN TESTS
```

### 4. OOP Concepts

What is the difference between a class and an instance?

=== BEGIN MARK SCHEME ===

A class represents a template or blueprint.  It specifies the variables and that should be associated with a given instance, but it doesn't contain the actual values of those variables.

An instance represents an actual object, an instantiation of a class.  It contains the actual values of the variables specified by the class.

=== END MARK SCHEME ===
