# Discussion Questions: Object-Orientation in Python

## Instructions

Take 30 minutes and answer the following questions together with your group.
Take turns playing around with the code provided in a Python shell or `ipdb`.

## Questions

1 . If the `Animal` class is defined like this:

```python
class Animal:

  def species(self):
    return "cat"
  
```

How would you:

<ol type="a">
  <li>Make a new instance of `Animal`?</li>
  
  rio = Animal()

  <li>`print` out to the terminal, the species of that new `Animal` instance?</li>
  
  print(rio.species())

</ol>

2 . Although we all know that cats are the best species, not all animals are
cats (unfortunately). How could you change the `Animal` class so that an
instance of `animal` can have its species set to any species at all?

we would have to initialize the class with self and species. Then when we create the instance of Rio as above we would specify the species (ex. Rio = Animal("Dog"))

def __init__(self, species):
    self.species = species

3 . We have the following class, and the following two instances of that class:

```python
class Animal:

  def species(self):
    return "cat"
  
maru = Animal()
hanna = Animal()
```

Given the above, what will the following return? Why?

```python
maru == hanna
```

it will throw an error as the two objects do not equal each other. they are two separate instances of Animal

4 . Given the following class:

```python
class Animal:
  
  def species(self):
    my_species = "cat"
  

  def say_species(self):
    print(f"Hi! I'm a {my_species}") 
  
```

What will happen when we invoke the following code?

```python
maru = Animal()
maru.say_species()
```

the first line will create the instance maru. The second is suppose to  print to the console "Hi! I'm a cat"

Is it broken? Why? How can you fix it?

yes, because it say_species can't acccess my_species, also all the methods need self. to work. Can fix it via initializing the class with self and species like so:

def __init__(self, species):
    self.my_species = species

5 . Reverse engineer this code (i.e., write the class that will make the code
work as invoked below):

```python
frederick = Animal("bull")
frederick.species
# => "bull"
```

class Animal:
    def __init__(self, species = "cat"):
        self.species = species

**Hint:** How can you instantiate, or *initialize*, an instance of a class with
a given value? What kind of variable would you use so that that value can be
shared across instance methods within a class?

6 . Given the following code:

```python
class Animal:
  
  def __init__(self, species):
    self.species = species


lil_bub = Animal("cat")
```

What is the relationship between `lil_bub` and the `Animal` class?

lil_bub is the instance of Animal class with a species of cat