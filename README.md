
## Object Oriented Programming [Suggested Time: 20 minutes]

In this exercise you will primarily be exploring a Pokemon dataset. Pokemon are fictional creatures from the [Nintendo franchise](https://en.wikipedia.org/wiki/Pok%C3%A9mon) of the same name.

Some Pokemon facts that might be useful:
* The word "pokemon" is both singular and plural. You may refer to "one pokemon" or "many pokemon".
* Pokemon have attributes such as a name, weight, and height.
* Pokemon have one or multiple "types". A type is something like "electric", "water", "ghost", or "normal" that indicates the abilities that pokemon may possess.
* The humans who collect pokemon are called "trainers".

As a pokemon trainer we want to make sure our pokemon are performing at their peak. To measure this, we want to calculate a pokemon's Body Mass Index (or BMI). This is a statistic calculated using the pokemon's height and weight. 

To help with this task we we will create Pokemon objects that methods can be called on. 

You'll be working with following dictionaries to create the `Pokemon` objects


```
# Use the following data
bulbasaur_data = {"name": 'bulbasaur', "weight": 69, "height": 7, "base_experience": 64, "types": ["grass", "poison"]}
charmander_data = {"name": 'charmander', "weight": 85, "height": 6, "base_experience": 62, "types": ["fire"]}
squirtle_data = {"name": 'squirtle', "weight": 90, "height": 5, "base_experience": 63, "types": ["water"]}
```


```
# __SOLUTION__
# Use the following data
bulbasaur_data = {"name": 'bulbasaur', "weight": 69, "height": 7, "base_experience": 64, "types": ["grass", "poison"]}
charmander_data = {"name": 'charmander', "weight": 85, "height": 6, "base_experience": 62, "types": ["fire"]}
squirtle_data = {"name": 'squirtle', "weight": 90, "height": 5, "base_experience": 63, "types": ["water"]}
```

### 1. Creating a Class

Create a class called `Pokemon` with an `__init__` method. Every `Pokemon` instance should have the following attributes:
* `name`
* `weight`
* `height`


```
# Create your class below with the correct syntax, including an __init__ method.
```


```
# __SOLUTION__ 
# Create your class below with the correct syntax, including an __init__ method.
class Pokemon:
    def __init__(self, data):
        self.name = data["name"]
        self.weight = data["weight"]
        self.height = data["height"]
        
    def bmi(self):
        return (self.weight*0.1)/(self.height*0.1)**2
        
```

    
### 2. Instantiating Objects

Using the `bulbasaur_data`, `charmander_data` and `squirtle_data` variables, create the corresponding pokemon objects.


```
# Your code here
bulbasaur = pass
charmander = pass
squirtle = pass
```


```
# __SOLUTION__ 
bulbasaur = Pokemon(bulbasaur_data)
charmander = Pokemon(charmander_data)
squirtle = Pokemon(squirtle_data)
```


```
# run this cell to test and check your code
# you may need to edit the attribute variable names if you named them differently!

def print_pokeinfo(pkmn):
    print('Name: ' + pkmn.name)
    print('Weight: ' + str(pkmn.weight))
    print('Height: ' + str(pkmn.height))
    print('\n')
    
print_pokeinfo(bulbasaur)
print_pokeinfo(ivysaur)
print_pokeinfo(venusaur)
```


```
# __SOLUTION__ 
# run this cell to test and check your code
# you may need to edit the attribute variable names if you named them differently!

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
    
    


### 3. Instance Methods

Write an instance method called `bmi` within the class `Pokemon` defined above to calculate the BMI of a Pokemon. 

BMI is defined by the formula: $\frac{weight}{height^{2}}$ 

The BMI should be calculated with weight in **kilograms** and height in **meters**. 


The height and weight data of Pokemon from the API is in **decimeters** and **hectograms** respectively. Here are the conversions:

```
1 decimeter = 0.1 meters
1 hectogram = 0.1 kilograms
```


```
# run this cell to test and check your code

# After defining a new instance method on the class, 
# you will have to rerun the code instantiating your objects

print(bulbasaur.bmi()) # 14.08
print(charmander.bmi()) # 23.61
print(squirtle.bmi()) # 36.0
```


```
# __SOLUTION__ 
# run this cell to test and check your code

# After defining a new instance method on the class, 
# you will have to rerun the code instantiating your objects

print(bulbasaur.bmi()) # 14.08
print(charmander.bmi()) # 23.61
print(squirtle.bmi()) # 36.0
```

    14.081632653061222
    23.611111111111104
    36.0

