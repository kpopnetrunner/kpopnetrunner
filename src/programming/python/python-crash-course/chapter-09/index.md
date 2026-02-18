---
layout: layouts/post.njk
title: Chapter 9 - Classes
date: 2026-02-03
---

Chapter 9 - Classes of the book Python Crash Course by Eric Matthes covers how to write functions. Here are my programs from working through this chapter.

01_creating_and_using_a_class.py

{% raw %}
```python
# 01_creating_and_using_a_class.py

# Object-oriented programming is one of the most effective approaches to writing
# software. In object-oriented programming you write classes tht represent
# real-world things and situations, and you create objects based on these
# classes. When you write a class, you define the general behavior that a whole
# category of objects can have.

# When you create individual objects from the class, each object is
# automatically equipped with the general behavior; you can then give each
# object whatever unique traits you desire. You'll be amazed how real-world
# situations can be modeled with object-oriented programming.

# Making an object from a class is called instatiation, and you work with
# instances of a class. In this chapter you'll write classes and create instances
# of those classes. You'll specify the kind of information that can be stored in
# instances, and you'll define actions that can be taken with these instances.
# You'll also write classes that extend the functionality of existing classes,
# so similar classes can share code efficiently. You'll store your classses in
# modules and import classes written by other programmers into your own program
# files.

# Understanding object-oriented programming will help you see the world as a
# programmer does. It'll help you really know your code, not just what's
# happening line by line, but also the bigger concepts behind it. Knowing the
# logic behind classes will train you to think logically so you can write
# programs that effectively address almost any problem you encounter.

# Classes also make life easier for you and other programmers you'll work with
# as you take on increasingly complex challenges. When you and other programmers
# write code based on the same kind of logic, you'll be able to understand each
# other's work. Your programs will make sense to many collaborators, allowing
# everyone to accomplish more.

# Creating and Using a Class

# You can model almost anything using classes. Let's start by writing a simple
# class, Dog, that represents a dog--not one dog in particular, but any dog.
# What do we know about most pet dogs? Well, they have a name and age. We also
# know that most dogs sit and roll over. Those two pieces of information
# (name and age) and those two behaviors (sit and roll over) will go in our Dog
# class because they're common to most dogs. This class will tell Python how to
# make an object representing a dog. After our class is written, we'll use it to
# make individual instances, each of which represents one specific dog.

# Creating the Dog Class

# Each instance created from the dog class will store a name and an age, and
# we'll give each dog the ability to sit() and roll_over():

# 1 class Dog:
# 2     """A simple attempt to model a dog."""
#
# 3     def __init__(self, name, age):
#           """Initialize name and age attributes."""
# 4         self.name = name
#           self.age = age
#
# 5     def sit(self):
#           """Simulate a dog sitting in response to a command."""
#           print(f"{self.name} is now sitting.")
#
#       def roll_over(self):
#           """Simulate rolling over in response to a command."""
#           print(f"{self.name} rolled over!")

# There's a lot to notice here, but don't worry. You'll see this structure
# throughout this chapter and have lots of time to get used to it. At 1 we
# define a class called Dog. By convention, capitalized names refer to classes
# in Python. There are no parentheses in the class definition because we're
# creating this class from scratch. At 2 we write a docstring describing what
# this class does.

# The __init__() Method

# A function that's part of a class is a method. Everything you learned about
# functions applies to methods as well: the only practical difference for now is
# the way we'll call methods. The __init__() method at 3 is a special method
# that Python runs automatically whenever we create a new instance based on the
# Dog class. This method has two leading underscores and two trailing
# underscores, a convention that helps prevent Python's default method names
# from conflicting with your method names. Make sure to use two underscores on
# each side of __init__(). If you use just one on each side, the method won't be
# called automatically when you use your class, which can result in errors that
# are difficult to identify.

# We define the __init__() method to have three parameters: self, name, and age.
# The self parameter is required in the method defintion, and it must come first
# before the other parameters. It just be included in the definition because
# when Python calls this method later (to create an instance of Dog), the method
# call will automatically pass the self argument. Every method call associated
# with an instance automatically passes self, which is a reference to the
# instance itself; it gives the individual instance access to the attributes and
# methods in the class. When we make an instance of Dog, Python will call the
# __init__() method from the Dog class. We'll pass Dog() a name and an age as
# arguments; self is passed automatically, so we don't need to pass it. Whenever
# we want to make an instance from the Dog class, we'll provide values for only
# the last two parameters, name and age.

# The two variables defined at 4 each have the prefix self. Any variable
# prefixed with self is available to every method in the class, and we'll also
# be able to access these variables through any instancecreated from the class.
# The line self.name = name takes the value associated with the parameter name
# and assigns it to the variable name, which is then attached to the instance
# being created. The same process happens with self.age = age. Variables that
# are accessible through instances like this are called attributes.

# The Dog class has two other methods defined: sit() and roll_over() 5. Because
# these methods don't need additional information to run, we just define them
# to have one parameter, self. The instances we create later will have access
# to these methods. In other words, they'll be able to sit and roll over.
# For now, sit() and roll_over() don't do much. They simply print a message
# saying the dog is sitting or rolling over. But the concet can be extended to
# realistic situations: if this class were part of an actual computer game,
# these methods would contain code to make an animated dog sit and roll over. If
# this class was written to control a robot, these methods would direct
# movements that cause a robotic dog to sit and roll over.

print("This program contains notes in the comments.")
```
{% endraw %}

02_making_an_instance_from_a_class.py

{% raw %}
```python
# 02_making_an_instance_from_a_class.py

# Think of a class as a set of instructions for how to make an instance. The
# class Dog is a set of instructions that tells Python how to make individual
# instances representing specific dogs.

# Let's name an instance representing a specific dog:

class Dog:
    """A simple attempt to model a dog."""

    def __init__(self, name, age):
        """Initialize name and age attributes."""
        self.name = name
        self.age = age

    def sit(self):
        """Simulate a dog sitting in response to a command."""
        print(f"{self.name} is now sitting.")

    def roll_over(self):
        """Simulate rolling over in response to a command."""
        print(f"{self.name} rolled over!")

my_dog = Dog('Willie', 6)

print(f"My dog's name is {my_dog.name}.")
print(f"My dog is {my_dog.age} years old.")

# The Dog class we're using here is the one we just wrote in the previous
# example. At 1 we well Python to create a dog whose name is 'Willie' and whose
# age is 6. When Python reads this line, it calls the __init__() method in Dog
# with the arguments 'Willie' and 6. The __init__() method creates an instance
# representing this particular dog and sets the name and age attributes using
# the values we provided. Python then returns an instance representing this dog.
# We assign that instance to the variable my_dog. The naming convention is
# helpful here: we can usually assume that a capitalized name like Dog refers
# to a class, and a lowercase name like my_dog refers to a single instance
# created from a class.
```
{% endraw %}

03_accessing_attributes.py

{% raw %}
```python
# 03_accessing_attributes.py

# 1 class Dog:
# 2     """A simple attempt to model a dog."""
#
# 3     def __init__(self, name, age):
#           """Initialize name and age attributes."""
# 4         self.name = name
#           self.age = age
#
# 5     def sit(self):
#           """Simulate a dog sitting in response to a command."""
#           print(f"{self.name} is now sitting.")
#
#       def roll_over(self):
#           """Simulate rolling over in response to a command."""
#           print(f"{self.name} rolled over!")

# 1 my_dog = Dog('Willie', 6)

# 2 print(f"My dog's name is {my_dog.name}.")
# 3 print(f"My dog is {my_dog.age} years old.")

# To access the attributes of an instance, you use dot notation. At 2 we access
# the value of my_dog's attrubute name by writing:

# my_dog.name

# Dot notation is used often in Python. This syntax demonstrates how Python
# find an attribute's value. Here Python looks at the instance my_dog and then
# finds the attribute name associated with my_dog. This is the same attribute
# referrred to as self.name in the class Dog. At 3 we use the same approach to
# work with the attribute age.

# The output is a summary of what we know about my_dog:

# My dog's name is Willie.
# My dog is 6 years old.
print("This program contains notes in the comments.")
```
{% endraw %}

04_calling_methods.py

{% raw %}
```python
# 04_calling_methods.py

# Calling Methods

# After we create an instance from the class Dog, we can use dot notation to
# call any method defined in Dog. Let's make our dog sit and roll over:

class Dog:
    """A simple attempt to model a dog."""

    def __init__(self, name, age):
        """Initialize name and age attributes."""
        self.name = name
        self.age = age

    def sit(self):
        """Simulate a dog sitting in response to a command."""
        print(f"{self.name} is now sitting.")

    def roll_over(self):
        """Simulate rolling over in response to a command."""
        print(f"{self.name} rolled over!")

my_dog = Dog('Willie', 6)
my_dog.sit()
my_dog.roll_over()

# To call a method, give the name of the instance (in this case, my_dog) and the
# method you want to call, seperated by a dot. When Python reads my_dog.sit(),
# it looks for the method sit() in the class Dog and runs that code. Python
# interprets the line my_dog.roll_over() in the same way.

# Now Willie does what we tell him to:

# Willie is now sitting.
# Willie rolled over!

# This syntax is quite useful. When attributes and methods have been given
# appropriately descriptive names like name, age, sit(), and roll_over(), we can
# easily infer what a block of code, even once we've never seen before, is
# supposed to do.
```
{% endraw %}

05_creating_multiple_instances.py

{% raw %}
```python
# 05_creating_multiple_instances.py

# Creating Multiple Instances

# You can create as many instances from a class as you need. Let's create a
# second dog called your_dog:

class Dog:
    """A simple attempt to model a dog."""

    def __init__(self, name, age):
        """Initialize name and age attributes."""
        self.name = name
        self.age = age

    def sit(self):
        """Simulate a dog sitting in response to a command."""
        print(f"{self.name} is now sitting.")

    def roll_over(self):
        """Simulate rolling over in response to a command."""
        print(f"{self.name} rolled over!")

my_dog = Dog('Willie', 6)
your_dog = Dog('Lucy', 3)

print(f"My dog's name is {my_dog.name}.")
print(f"My dog is {my_dog.age} years old.")
my_dog.sit()

print(f"\nYour dog's name is {your_dog.name}.")
print(f"Your dog is {your_dog.age} years old.")
your_dog.sit()

# In this example we create a dog named Willie and a dog named Lucy. Each dog is
# a seperate instance with its own set of attributes, capable of the same set
# of actions:

# My dog's name is Willie.
# My dog is 6 years old.
# Willie is now sitting.

# Your dog's name is Lucy.
# Your dog is 3 years old.
# Lucy is now sitting.

# Even if we used the same name and age for the second dog, Python would still
# create a separate instance from the Dog class. You can make many instances
# from one class as you need, as long as you give each instance a unique
# variable name or it occupies a unique spot in a list or dictionary.
```
{% endraw %}

06_restaurant.py

{% raw %}
```python
# 06_restaurant.py

# 9-1. Restaurant: Make a class called Restaurant. The __init__() method for
# Restaurant should store two attributes: a restaurant_name and a cuisine_type.
# Make a method called describe_restaurant() that prints these two pieces of
# information, and a method called open_restaurant() that prints a message
# indicating that the restaurant is open.

# Make an instance called restaurant from your class. Print the two attributes
# individually, and then call both methods.

class Restaurant:
    """A simple attempt to model a restaurant."""

    def __init__(self, restaurant_name, cuisine_type):
        """Initialize restaurant_name and cuisine_type attributes."""
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type

    def describe_restaurant(self):
        """Prints restaurant information."""
        print(f"This restaurant is called {self.restaurant_name.title()}, "
              f"and it serves {self.cuisine_type.title()} cuisine.")
    def open_restaurant(self):
        """Prints a message that the restaurant is open."""
        print(f"{self.restaurant_name.title()} is open.")

restaurant = Restaurant('Chipotle', 'Mexican')
print(restaurant.restaurant_name)
print(restaurant.cuisine_type)
restaurant.describe_restaurant()
restaurant.open_restaurant()
```
{% endraw %}

07_three_restaurants.py

{% raw %}
```python
# 07_three_restaurants.py

# 9-2. Three Restaurants: Start with your class from Exercise 9-1. Create three
# different instances from the class, and call describe_restaurant() for each
# instance.

class Restaurant:
    """A simple attempt to model a restaurant."""

    def __init__(self, restaurant_name, cuisine_type):
        """Initialize restaurant_name and cuisine_type attributes."""
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type

    def describe_restaurant(self):
        """Prints restaurant information."""
        print(f"This restaurant is called {self.restaurant_name.title()}, "
              f"and it serves {self.cuisine_type.title()} cuisine.")
    def open_restaurant(self):
        """Prints a message that the restaurant is open."""
        print(f"{self.restaurant_name.title()} is open.")

restaurant_1 = Restaurant('Chipotle', 'Mexican')
restaurant_2 = Restaurant('McDonalds', 'American')
restaurant_3 = Restaurant('Panda Express', 'Chinese')

restaurant_1.describe_restaurant()
restaurant_2.describe_restaurant()
restaurant_3.describe_restaurant()
```
{% endraw %}

08_users.py

{% raw %}
```python
# 08_users.py

# 9-3. Users: Make a class called User. Create two attributes called first_name
# and last_name, and then creat eseveral other attributes that are typically
# stored in a user profile. Make a method called describe_user() that prints
# a summary of the user's information. Make another method called greet_user()
# that prints a personalized greeting to the user.

# Create several instances representing different users, and call both methods
# for each user.

class User:
    """A simple attempt to model a user."""

    def __init__(self, first_name, last_name, age, height):
        """Initialize first_name, last_name, age, and height attributes."""
        self.first_name = first_name
        self.last_name = last_name
        self.age = age
        self.height = height

    def describe_user(self):
        """Prints user information."""
        print(f"{self.first_name.title()} {self.last_name.title()} "
        f"is {self.age} years old and has a height of {self.height} "
        f"centimeters.")

    def greet_user(self):
        """Prints a personalized greeting to the user."""
        print(f"Hello {self.first_name.title()} {self.last_name.title()}!")

yeji = User('Yeji', 'Hwang', '25', '167')
lia = User('Jisu', 'Choi', '25', '163')
ryujin = User('Ryujin', 'Shin', '24', '164')
chaeryeong = User('Chaeryeong', 'Lee', '24', '166')
yuna = User('Yuna', 'Shin', '22', '170')

yeji.describe_user()
yeji.greet_user()
lia.describe_user()
lia.greet_user()
ryujin.describe_user()
ryujin.greet_user()
chaeryeong.describe_user()
chaeryeong.greet_user()
yuna.describe_user()
yuna.greet_user()
```
{% endraw %}

09_working_with_classes_and_instances.py

{% raw %}
```python
# 09_working_with_classes_and_instances.py

# Working with Classes and Instances

# You can use classes to represent many real-world situations. Once you write
# a class, you'll spend most of your time working with instances created from
# that class. One of the first tasks you'll want to do is modify the attributes
# associated with a particular instance. You can modify the attributes of an
# instance directly or write methods that update attributes in specific ways.

# The Car Class

# Let's write a new class representing a car. Our class will store information
# about the kind of car we're working with, and it will have a method that
# summarizes this information:

class Car:
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):                # 1
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year

    def get_descriptive_name(self):                       # 2
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

my_new_car = Car('audi', 'a4', 2019)                      # 3
print(my_new_car.get_descriptive_name())

# At 1 in the Car class, we define the __init__() method with the self parameter
# first, just like we did before with our Dog class. We also give it three other
# parameters: make, model, and year. The __init__() method takes in these
# parameters and assigns them to the attributes that will be associated with
# instances made from this class. When we make a new Car instance, we'll need to
# specify a make, model, and year for our instance.

# At 2, we define a method called get_descriptive_name() that puts a car's year,
# make, and model into one string neatly describing the car. This will spare
# us from having to print each attribute's value individually. To work with the
# attribute values in this method, we use self.make, self.model, and self.year.

# At 3 we make an instance from the Car class and assign it to the variable
# my_new_car. Then we call get_descriptive_name() to show what kind of car we
# have:

# 2019 Audi A4
```
{% endraw %}

10_setting_a_default_value_for_an_attribute.py

{% raw %}
```python
# 10_setting_a_default_value_for_an_attribute.py

# To make the class more interesting, let's add an attribute that changes over
# time. We'll add an attribute that stores the car's overall mileage.

# Setting a Default Value for an Attribute

# When an instance is created, attributes can be defined without being passed
# in as parameters. These attributes can be defined in the __init__() method,
# where they are assigned a default value.

# Let's add an attribute called odometer_reading that always starts with a value
# of 0. We'll also add a method read_odometer() that helps us read each car's
# odometer:

class Car:
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print(f"This car has {self.odometer_reading} miles on it.")

my_new_car = Car('audi', 'a4', '2019')
print(my_new_car.get_descriptive_name())
my_new_car.read_odometer()

# This time when Python calls the __init__() method to create a new instance, it
# stores the make, model, and year values as attributes like it did in the
# previous example. Then Python creates a new attribute called odometer_reading
# and seets its initial value to 0 1. We also have a new method called
# read_odometer() at 2 that makes it easier to read a car's mileage.

# Our car starts with a mileage of 0:

# 2019 Audi A4
# This car has 0 miles on it.

# Not many cars are sold with exactly 0 miles on the odometer, so we need a way
# to change the value of this attribute.
```
{% endraw %}

11_modifying_an_attributes_value_directly.py

{% raw %}
```python
# 11_modifying_an_attributes_value_directly.py

# Modifying Attribute Values

# You can change an attribute's value in three ways: you can change the value
# directly through an instance, set the value through a method, or increment the
# value (add a certain amount to it) through a method. Let's look at each of
# these approaches.

# Modifying an Attribute's Value Directly

# The simplest way to modify the value of an attribute is to access the
# attribute directly through an instance. Here we set the odometer reading to 23
# directly:

class Car:
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print(f"This car has {self.odometer_reading} miles on it.")

my_new_car = Car('audi', 'a4', '2019')
print(my_new_car.get_descriptive_name())
my_new_car.odometer_reading = 23                        # 1
my_new_car.read_odometer()

# At 1 we use dot notation to access the car's odometer_reading attribute and
# set it's value directly. This line tells Python to take the instance
# my_new_car, find the attribute odometer_reading associated with it, and set
# the value of that attribute to 23:

# 2019 Audi A4
# This car has 23 miles on it.

```
{% endraw %}

12_modifying_an_attributes_value_through_a_method.py

{% raw %}
```python
# 12_modifying_an_attributes_value_through_a_method.py

# Sometimes you'll want to access attributes directly like this, but other times
# you'll want to write a method that updates the value for you.

# Modifying an Attribute's Value Through a Method

# It can be helpful to have methods that update certain attributes for you.
# Instead of accessing the attribute directly, you pass the new value to a
# method that handles the updating internally.

# Here's an example showing a method called update_odometer():

class Car:
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):                            # 1
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

my_new_car = Car('audi', 'a4', '2019')
print(my_new_car.get_descriptive_name())

my_new_car.update_odometer(23)                                     # 2
my_new_car.read_odometer()

# The only modification to Car is the addition of update_odometer() at 1. This
# method takes in a mileage value and assigns it to self.odometer_reading. At 2
# we call update_odomter() and give it 23 as an argument (corresponding to the
# mileage parameter in the method defintion). It sets the odometer reading to 23
# , and read_odometer() prints the reading:

# 2019 Audi A4
# This car has 23 miles on it.

# We can extend the method update_odometer() to do additional work every time
# the odometer reading is modified. Let's add a little logic to make sure no
# one tried to roll back the odometer reading:


#    def update_odometer(self, mileage):
#        """
#        Set the odometer reading to the given value.
#        Reject the change if it attempts to roll the odometer back.
#        """
#        if mileage >= self.odometer_reading:
#            self.odometer_reading = mileage
#        else:
#            print("You can't roll back an odometer!")

# Now update_odometer() checks that the new reading makes sense before modifying
# the attribute. If the new mileage, mileage, is greater than or equal to the
# existing mileage, self.odometer_reading, you can update the odometer reading
# to the new mileage 1. If the new mileage is less than the existing mileage,
# you'll get a warning that you can't roll back an odometer 2.

```
{% endraw %}

13_incrementing_an_attributes_value_through_a_method.py

{% raw %}
```python
# 13_incrementing_an_attributes_value_through_a_method.py

# Incrementing an Attribute's Value Through a Method

# Sometimes you'll want to increment an attribute's value by a certain amount
# rather than set an entirely new value. Say we buy a used car and put 100 miles
# on it between the time we buy it and the time we register it. Here's a method
# that allows us to pass this incremental amount and add that value to the
# odometer reading:

class Car:
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):                           # 1
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

my_used_car = Car('subaru', 'outback', 2015)                       # 2
print(my_used_car.get_descriptive_name())

my_used_car.update_odometer(23_500)                                # 3
my_used_car.read_odometer()

my_used_car.increment_odometer(100)                                # 4
my_used_car.read_odometer()

# The new method increment_odometer() at 1 takes in a number of miles, and adds
# this value to self.odometer_reading. At 2 we create a used car, my_used_car.
# We set its odometer to 23,500 by calling update_odometer() and passing it
# 23_500 at 3. At 4 we call increment_odometer() and pass it 100 to add the 100
# miles that we drove between buying the car and registering it:

# 2015 Subaru Outback
# This car has 23500 miles on it.
# This car has 23600 miles on it.

# You can easily modify this method to reject negative increments so no one uses
# this function to roll back an odometer.

# NOTE

# You can use methods like this to control how users of your program update
# values such as an odomter reading, but anyone with access to the program can
# set the odometer reading to any value by accessing the attribute directly.
# Effective security takes extreme attention to detail in addition to basic
# checks like thoe shown here.
```
{% endraw %}

14_number_served.py

{% raw %}
```python
# 14_number_served.py

# Page 167

# 9-4. Number Served: Start with your program from Exercise 9-1 (page 162).
# Add as an attribute called number_served with a default value of 0. Create
# an instance called restaurant from this class. Print the number of customers
# the restaurant has served, and then change the value and print it again.

# Add a method called set_number_served() that lets you set the number of
# customers that have been served. Call this method with a new number and print
# the value again.

# Add a method called increment_number_served() that lets you increment the
# number of customers who've been served. Call this method with any number you
# like that could represent how many customers were served in, say, a day of
# business.

class Restaurant:
    """A simple attempt to model a restaurant."""

    def __init__(self, restaurant_name, cuisine_type):
        """Initialize restaurant_name and cuisine_type attributes."""
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type
        self.number_served = 0

    def describe_restaurant(self):
        """Prints restaurant information."""
        print(f"This restaurant is called {self.restaurant_name.title()}, "
              f"and it serves {self.cuisine_type.title()} cuisine.")
    def open_restaurant(self):
        """Prints a message that the restaurant is open."""
        print(f"{self.restaurant_name.title()} is open.")
    def set_number_served(self, customers):
        """Sets the number of customers served."""
        self.number_served = customers
    def increment_number_served(self, customers):
        """Increments the number of customers served."""
        self.number_served += customers

restaurant = Restaurant('Chipotle', 'Mexican')
print(restaurant.number_served)
restaurant.number_served = 9
print(restaurant.number_served)

restaurant.set_number_served(10)
print(restaurant.number_served)

restaurant.increment_number_served(10)
print(restaurant.number_served)
```
{% endraw %}

15_login_attempts.py

{% raw %}
```python
# 15_login_attempts.py

# 9-5. Login Attempts: Add an attribute called login_attempts to your User class
# from Exercise 9-3 (page 162). Write a method called increment_login_attempts()
# that increments the value of login_attempts by 1. Write another method called
# reset_login_attempts() that resets the value of login_attempts to 0.

# Make an instance of the User class and call increment_login_attempts() several
# times. Print the vaue of login_attempts to make sure it was incremented
# properly, and then call reset_login_attempts(). Print login_attempts again to
# make sure it was reset to 0.

class User:
    """A simple attempt to model a user."""

    def __init__(self, first_name, last_name, age, height):
        """Initialize first_name, last_name, age, and height attributes."""
        self.first_name = first_name
        self.last_name = last_name
        self.age = age
        self.height = height
        self.login_attempts = 0

    def describe_user(self):
        """Prints user information."""
        print(f"{self.first_name.title()} {self.last_name.title()} "
        f"is {self.age} years old and has a height of {self.height} "
        f"centimeters.")

    def greet_user(self):
        """Prints a personalized greeting to the user."""
        print(f"Hello {self.first_name.title()} {self.last_name.title()}!")

    def increment_login_attempts(self):
        """Increments the value of login_attempts by 1."""
        self.login_attempts += 1

    def reset_login_attempts(self):
        """Resets the value of login_attempts to 0."""
        self.login_attempts = 0

yeji = User('Yeji', 'Hwang', '25', '167')
yeji.increment_login_attempts()
print(yeji.login_attempts)
yeji.increment_login_attempts()
print(yeji.login_attempts)
yeji.increment_login_attempts()
print(yeji.login_attempts)
yeji.reset_login_attempts()
print(yeji.login_attempts)
```
{% endraw %}

16_inheritance.py

{% raw %}
```python
# 16_inheritance.py

# Inheritance

# You don't always have to start from scratch when writing a class. If the class
# you're writing is a specialized version of another class you wrote, you can
# use inheritance. When one class inherits from another, it takes on the
# attributes and methods of the first class. The original class is called the
# parent class, and the new class is the child class. The child class can
# inherit any or all of the attributes and methods of its paraent class, but
# it's also free to define new attributes and methods of its own.

# The __init__() Method for a Child Class

# When you're writing a new class based on an existing class, you'll often want
# to call the __init__() method from the parent class. This will initialize any
# attributes that were defined in the parent __init__() method and make them
# available in the child class.

# As an example, let's model an electric car. An electric car is just a specific
# kind of car, so we can base our new ElectricCar class on the Car class we
# wrote earlier. Then we'll only have to wrie code for the attributes and
# behavior specific to electric cars.

# Let's start by making a simple version of the ElectricCar class, which does
# everything the Car class does:

class Car:                                                                    #1
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

class ElectricCar(Car):                                                       #2
    """Represents aspects of a car, specific to electric vehicles."""

    def __init__(self, make, model, year):                                    #3
        """Initialize attributes of the parent class."""
        super().__init__(make, model, year)                                   #4

my_tesla = ElectricCar('tesla', 'model s', 2019)                              #5
print(my_tesla.get_descriptive_name())

# At 1 we start with Car. When you create a child class, the parent class must
# be part of the current file and must appear before the child class in the
# file. At 2 we define the child class, ElectricCar. The name of the parent
# class must be included in parentheses in the definition of a child class. The
# __init__() method at 3 takes in the information required to make a Car
# instance.

# The super() function at 4 is a special function that allows you to call a
# method from the parent class. This line tells Python to call the __init__()
# method from Car, which gives an ElectricCar instance all the attributes
# defined in that method. The name super comes from a convention of calling the
# parent class a superclass and the child class a subclass.

# We test wheter inheritance is working properly by trying to create an electric
# car with the same kind of information we'd provide when making a regular car.
# At 5 we make an instance of the ElectricCar class and assign it to my_tesla.
# This line class the __init__() method defined in ElectricCar, which in turn
# tells Python to call the __init__() method defined in the parent class Car. We
# provide the arguments 'tesla', 'model s', and 2019.

# Aside from __init__(), there are no attributes or methods yet that are
# particular to an electric car. At this point we're just making sure the
# electric car has the appropriate Car behavior:

# 2019 Tesla Model S

# The ElectricCar instance works just like an instance of Car, so now we can
# begin defining attributes and methods specific to electric cars.
```
{% endraw %}

17_defining_attributes_and_methods_for_the_child_class.py

{% raw %}
```python
# 17_defining_attributes_and_methods_for_the_child_class.py

# Once you have a child class that inherits from a parent class, you can add any
# new attributes and methods necessary to differentiate the child class from the
# parent class.

# Let's add an attribute that's specific to electric cars (a battery,
# for example) and a method to report on this attribute. We'll store the battery
# size and write a method that prints a description of the battery:


# You don't always have to start from scratch when writing a class. If the class
# you're writing is a specialized version of another class you wrote, you can
# use inheritance. When one class inherits from another, it takes on the
# attributes and methods of the first class. The original class is called the
# parent class, and the new class is the child class. The child class can
# inherit any or all of the attributes and methods of its paraent class, but
# it's also free to define new attributes and methods of its own.

# The __init__() Method for a Child Class

# When you're writing a new class based on an existing class, you'll often want
# to call the __init__() method from the parent class. This will initialize any
# attributes that were defined in the parent __init__() method and make them
# available in the child class.

# As an example, let's model an electric car. An electric car is just a specific
# kind of car, so we can base our new ElectricCar class on the Car class we
# wrote earlier. Then we'll only have to wrie code for the attributes and
# behavior specific to electric cars.

# Let's start by making a simple version of the ElectricCar class, which does
# everything the Car class does:

class Car:
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

class ElectricCar(Car):
    """Represents aspects of a car, specific to electric vehicles."""

    def __init__(self, make, model, year):
        """
        Initialize attributes of the parent class.
        Then initialize attributes specific to an electric car.
        """
        super().__init__(make, model, year)
        self.battery_size = 75                                                #1

    def describe_battery(self):                                               #2
        """Print a statement describing the battery size."""
        print(f"This car has a {self.battery_size}-kWh battery.")

my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name())
my_tesla.describe_battery()

# At 1 we add a new attribute self.battery_size and set its inital value to, say
# , 75. This attribute will be associated with all instances created from the
# ElectricCar class but won't be associated with any instances of Car. We also
# add a method called describe_battery() that prints information about the
# battery at 2. When we call this method, we get a description that is clearly
# specific to an electric car:

# 2019 Tesla Model S
# This car has a 75-kWh battery.

# There's no limit to how much you can specialize the ElectricCar class. You can
# add as many attributes and methods as you need to model an electric car to
# whatever degree of accuracy you need. An attribute or method that could belong
# to any car, rather than one that's specific to an electric car, should be
# added to the Car class instead of the ElectricCar class. Then anyone who uses
# the Car class will have that functionality available as well, behavior
# specific to electric vehicles.
```
{% endraw %}

18_overriding_methods_from_the_parent_class.py

{% raw %}
```python
# 18_overriding_methods_from_the_parent_class.py

# You can override any method from the parent class that doesn't fit what you're
# trying to model with the child class. To do this, you define a method in the
# child class with the same name as the method you want to override in the
# parent class. Python will disregard the parent class method and only pay
# attention to the method you define in the child class.

# Say the class Car had a method called fill_gas_tank(). This method is
# meaningless for an all-electric vehicle, so you might want to override this
# method. Here's one way to do that:

class Car:
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

class ElectricCar(Car):
    """Represents aspects of a car, specific to electric vehicles."""

    def __init__(self, make, model, year):
        """
        Initialize attributes of the parent class.
        Then initialize attributes specific to an electric car.
        """
        super().__init__(make, model, year)
        self.battery_size = 75

    def describe_battery(self):
        """Print a statement describing the battery size."""
        print(f"This car has a {self.battery_size}-kWh battery.")

    def fill_gas_tank(self):
        """Electric cars don't have gas tanks."""
        print("This car doesn't need a gas tank!")

# Now if someone tries to call fill_gas_tank() with an electric car, Python will
# ignore the method fill_gas_tank() in Car and run this code instead. When you
# use inheritance, you can make your child classes retain what you need and
# override anything you don't need from the parent class.

```
{% endraw %}

19_instances_as_attributes.py

{% raw %}
```python
# 19_instances_as_attributes.py

# When modeling something from the real world in code, you may find that you're
# adding more and more detail to a class. You'll find that you have a growing
# list of attributes and methods and that your files are becoming lengthy. In
# these situations, you might recognize that part of one class can be written as
# a separate class. You can break your large class into smaller classes that
# work together.

# For example, if we continue adding detail to the ElectricCar class, we might
# notice that we're adding many attributes and methods specific to the car's
# battery. When we see this happening, we can stop and move those attributes and
# methods to a separate class called Battery. Then we can use a Battery instance
# as an attribute in the ElectricCar class:

# 18_overriding_methods_from_the_parent_class.py

# You can override any method from the parent class that doesn't fit what you're
# trying to model with the child class. To do this, you define a method in the
# child class with the same name as the method you want to override in the
# parent class. Python will disregard the parent class method and only pay
# attention to the method you define in the child class.

# Say the class Car had a method called fill_gas_tank(). This method is
# meaningless for an all-electric vehicle, so you might want to override this
# method. Here's one way to do that:

class Car:
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

class Battery:                                                                #1
    """A simple attempt to model a battery for an electric car."""

    def __init__(self, battery_size=75):                                      #2
        """Initialize the battery's attributes."""
        self.battery_size = battery_size

    def describe_battery(self):                                               #3
        """Print a statement describing the battery size."""
        print(f"This car has a {self.battery_size}-kWh battery.")

    def get_range(self):
        """Print a statement about the range this battery provides."""
        if self.battery_size == 75:
            range = 260
        elif self.battery_size == 100:
            range = 315

        print(f"This car can go about {range} miles on a full charge.")

class ElectricCar(Car):
    """Represents aspects of a car, specific to electric vehicles."""

    def __init__(self, make, model, year):
        """
        Initialize attributes of the parent class.
        Then initialize attributes specific to an electric car.
        """
        super().__init__(make, model, year)
        self.battery = Battery()                                              #4

    def fill_gas_tank(self):
        """Electric cars don't have gas tanks."""
        print("This car doesn't need a gas tank!")

my_tesla = ElectricCar('tesla', 'model s', 2019)

print(my_tesla.get_descriptive_name())
my_tesla.battery.describe_battery()
my_tesla.battery.get_range()

# At 1 we define a new class called Battery that doesn't inherit from any other
# class. The __init__() method at 2 has one parameter, battery_size, in additon
# to self. This is an optional parameter that sets the battery's size to 75 if
# no value is provided. The method describe_battery() has been moved to this
# class as well 3.

# In the ElectricCar class, we now add an attribute called self.batter 4. This
# line tells Python to create a new instance of Battery (with a default size of
# 75, because we're not specifying a value) and assign that instance to the
# attribute self.battery. This will happen every time the __init__() method is
# called; any ElectricCar instance will now have a Battery instance created
# automatically.

# We create an electric car and assign it to the variable my_tesla. When we want
# to describe the battery, we need to work through the car's battery attribute:

# my_tesla.battery.describe_battery()

# This line tells Python to ook at the instance my_tesla, find its battery
# attribute, and call the method describe_battery() that's associated with the
# Battery instance stored in the attribute.

# The output is identical to what we saw previously:

# 2019 Tesla Model S
# This car has a 75-kWh battery.

# This looks like a lot of extra work, but now we can describe the battery in
# as much detail as we want without cluttering the ElectricCar class. Let's add
# another method to Battery that reports the range of the car based on the
# battery size:

#     def get_range(self):
#         """Print a statement about the range this battery provides."""
#         if self.battery_size == 75:
#             range = 260
#         elif self.battery_size == 100:
#             range = 315

#         print(f"This car can go about {range} miles on a full charge.")
```
{% endraw %}

20_modeling_real_world_objects.py

{% raw %}
```python
# 20_modeling_real_world_objects.py

# As you begin to model more complicated things like electric cars, you'll
# wrestle with interesting questions. Is the range of an electric care a
# property of the battery or of the car? If we're only describing one car, it's
# probably fine to maintain the association of the method get_range() with the
# Battery class. But if we're describing a manufacturer's entire line of cars,
# we probably want to move get_range() to the ElectricCar class. The get_range()
# method would still check the battery size before determining the range, but it
# world report a range specific to the kind of car it's associated with.
# Alternatively, we could maintain the association of the get_range() method with
# the battery but pass it a parameter such as car_model. The get_range() method
# would then report a range based on the battery size and car model.

# This brings you to an interesting point in your growth as a programmer. When
# you wrestle with questions like these, you're thinking at a higher logical
# level rather than a syntax-focused level. You're thinking not about Python,
# but about how to represent the real world in code. When you reach this point,
# you'll realize there are often no write or wrong approaches to modeling
# real-world situations. Some approaches are more efficient than others, but it
# takes practice to find the most efficient representations. If your code is
# working as you want it to, you're doing well! Don't be discouraged if you find
# you're ripping apart your classes and rewriting them several times using
# different approaches. In the quest to write accurate, efficient code, everyone
# goes through this process.
print("This program contains notes in the comments.")
```
{% endraw %}

21_ice_cream_stand.py

{% raw %}
```python
# 21_ice_cream_stand.py

# 9-6. Ice Cream Stand: An ice cream stand is a specific kind of restaurant.
# Write a class called IceCreamStand that inherits from the Restaurant class you
# wrote in Exercise 9-1 (page 162) or Exercise 9-4 (page 167). Either version
# of the class will work; just pick the one you like better. Add an attribute
# called flavors that stores a list of ice cream flavors. Write a method that
# displays these flavors. Create an instance of IceCreamStand, and call this
# method.

class Restaurant:
    """A simple attempt to model a restaurant."""

    def __init__(self, restaurant_name, cuisine_type):
        """Initialize restaurant_name and cuisine_type attributes."""
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type
        self.number_served = 0

    def describe_restaurant(self):
        """Prints restaurant information."""
        print(f"This restaurant is called {self.restaurant_name.title()}, "
              f"and it serves {self.cuisine_type.title()} cuisine.")
    def open_restaurant(self):
        """Prints a message that the restaurant is open."""
        print(f"{self.restaurant_name.title()} is open.")
    def set_number_served(self, customers):
        """Sets the number of customers served."""
        self.number_served = customers
    def increment_number_served(self, customers):
        """Increments the number of customers served."""
        self.number_served += customers

class IceCreamStand(Restaurant):
    """Represents an ice cream stand."""

    def __init__(self, restaurant_name, cuisine_type):
        """
        Initialize attributes of the parent class.
        The initialize attributes specific to an ice cream stand.
        """
        super().__init__(restaurant_name, cuisine_type)
        self.flavors = ['vanilla', 'chocolate', 'strawberry']

    def display_flavors(self):
        """Displays the available flavors."""
        print("Available flavors:")
        for flavor in self.flavors:
            print(f"- {flavor.title()}")

my_ice_cream_stand = IceCreamStand('My Ice Cream Stand', 'Ice Cream')
my_ice_cream_stand.display_flavors()
```
{% endraw %}

22_admin.py

{% raw %}
```python
# 22_admin.py

# 9-7. Admin: An administrator is a special kind of user. Write a class called
# Admin that inherits from the User class you wrote in Exercise 9-3 (page 162)
# or Exercise 9-5 (page 167). Add an attribute, privileges, that stores a list
# of strings like "can add post", "can delete post", "can ban user", and so on.

# Write a method called show_privileges() that lists the administrator's set of
# privileges. Create an instance of Admin, and call your method.

class User:
    """A simple attempt to model a user."""

    def __init__(self, first_name, last_name, age, height):
        """Initialize first_name, last_name, age, and height attributes."""
        self.first_name = first_name
        self.last_name = last_name
        self.age = age
        self.height = height
        self.login_attempts = 0

    def describe_user(self):
        """Prints user information."""
        print(f"{self.first_name.title()} {self.last_name.title()} "
        f"is {self.age} years old and has a height of {self.height} "
        f"centimeters.")

    def greet_user(self):
        """Prints a personalized greeting to the user."""
        print(f"Hello {self.first_name.title()} {self.last_name.title()}!")

    def increment_login_attempts(self):
        """Increments the value of login_attempts by 1."""
        self.login_attempts += 1

    def reset_login_attempts(self):
        """Resets the value of login_attempts to 0."""
        self.login_attempts = 0

class Admin(User):
    """Represents an administrator."""

    def __init__(self, first_name, last_name, age, height):
        """
        Initialize attributes of the parent class.
        Then initialize attributes specific to an administrator.
        """
        super().__init__(first_name, last_name, age, height)
        self.privileges = ['can add post', 'can delete post', 'can ban user']

    def show_privileges(self):
        """Displays the administrator's privileges."""
        print("Privileges:")
        for privilege in self.privileges:
            print(f"- {privilege}")

new_admin = Admin('Yeji', 'Hwang', 25, 167)
new_admin.show_privileges()
```
{% endraw %}

23_privileges.py

{% raw %}
```python
# 23_privileges.py

# 9-8. Privileges: Write a seperate Privileges class. The class should have one
# attribute, privileges, that stores a list of strings as described in Exercise
# 9-7. Move the show_privileges() method to this class. Make a Privileges
# instance as an attribute in the Admin class. Create a new instance of Admin
# an use your method to show its privileges.


class User:
    """A simple attempt to model a user."""

    def __init__(self, first_name, last_name, age, height):
        """Initialize first_name, last_name, age, and height attributes."""
        self.first_name = first_name
        self.last_name = last_name
        self.age = age
        self.height = height
        self.login_attempts = 0

    def describe_user(self):
        """Prints user information."""
        print(f"{self.first_name.title()} {self.last_name.title()} "
        f"is {self.age} years old and has a height of {self.height} "
        f"centimeters.")

    def greet_user(self):
        """Prints a personalized greeting to the user."""
        print(f"Hello {self.first_name.title()} {self.last_name.title()}!")

    def increment_login_attempts(self):
        """Increments the value of login_attempts by 1."""
        self.login_attempts += 1

    def reset_login_attempts(self):
        """Resets the value of login_attempts to 0."""
        self.login_attempts = 0

class Admin(User):
    """Represents an administrator."""

    def __init__(self, first_name, last_name, age, height):
        """
        Initialize attributes of the parent class.
        Then initialize attributes specific to an administrator.
        """
        super().__init__(first_name, last_name, age, height)
        self.privileges = Privileges()

class Privileges:
    """Represents the privileges of an administrator."""

    def __init__(self):
        """Initialize the privileges attribute."""
        self.privileges = ['can add post', 'can delete post', 'can ban user']

    def show_privileges(self):
        """Displays the administrator's privleges."""
        print("Privileges:")
        for privilege in self.privileges:
            print(f"- {privilege}")

new_admin = Admin('Yeji', 'Hwang', 25, 167)
new_admin.privileges.show_privileges()
```
{% endraw %}

24_battery_upgrade.py

{% raw %}
```python
# 24_battery_upgrade.py

# 9-9. Battery Upgrade: Use the final version of electric_car.py from this
# section. Add a method to the Battery class called upgrade_battery(). This
# method should check the battery size and set the capacity to 100 if it isn't
# already. Make an electric car with a default battery size, call get_range()
# once, and then call get_range() a second time after upgrading the battery. You
# should see an increase in the car's range.

class Car:
    """A simple attempt to represent a car."""

    def __init__(self, make, model, year):
        """Initinalize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

class Battery:                                                                #1
    """A simple attempt to model a battery for an electric car."""

    def __init__(self, battery_size=75):                                      #2
        """Initialize the battery's attributes."""
        self.battery_size = battery_size

    def describe_battery(self):                                               #3
        """Print a statement describing the battery size."""
        print(f"This car has a {self.battery_size}-kWh battery.")

    def get_range(self):
        """Print a statement about the range this battery provides."""
        if self.battery_size == 75:
            range = 260
        elif self.battery_size == 100:
            range = 315

        print(f"This car can go about {range} miles on a full charge.")

    def upgrade_battery(self):
        """Check the battery size and set the capacity to 100 if it isn't."""
        if self.battery_size != 100:
            self.battery_size = 100
            print("The battery has been upgraded to 100 kWh.")
        else:
            print("The battery is already upgraded.")

class ElectricCar(Car):
    """Represents aspects of a car, specific to electric vehicles."""

    def __init__(self, make, model, year):
        """
        Initialize attributes of the parent class.
        Then initialize attributes specific to an electric car.
        """
        super().__init__(make, model, year)
        self.battery = Battery()                                              #4

    def fill_gas_tank(self):
        """Electric cars don't have gas tanks."""
        print("This car doesn't need a gas tank!")

my_tesla = ElectricCar('tesla', 'model s', 2019)
my_tesla.battery.get_range()
my_tesla.battery.upgrade_battery()
my_tesla.battery.get_range()
```
{% endraw %}

25_importing_a_single_class.py

{% raw %}
```python
# 25_importing_a_single_class.py

# Importing Classes

# As you add more functionality to your classes, your files can get long, even
# when you use inheritance properly. In keeping with the overall philosophy of
# Python, you'll want to keep your files as uncluttered as possible. To help,
# Python let's you store classes in modules and then import the classes you need
# into your main program.

# Importing a Single Class

# Let's create a module containing just the Car class. This brings up a subtle
# naming issue: we already have a file named car.py in this chapter, but this
# module should be named car.py because it contains code representing a car.
# We'll resolve this naming issue by storing the Car class in a module named
# car.py, replacing the car.py file we were previously using. From now on, any
# program that uses this module will need a more specific filename, such as
# my_car.py. Here's car.py with just the code from the class Car:

# car.py

# """A class that can be used to represent a car."""                            #1

# class Car:
#     """A simple attempt to represent a car."""
#
#     def __init__(self, make, model, year):
#         """Initinalize attributes to describe a car."""
#         self.make = make
#         self.model = model
#         self.year = year
#         self.odometer_reading = 0
#
#     def get_descriptive_name(self):
#         """Return a neatly formatted descriptive name."""
#         long_name = f"{self.year} {self.make} {self.model}"
#         return long_name.title()
#
#     def read_odometer(self):
#         """Print a statement showing the car's mileage."""
#         print(f"This car has {self.odometer_reading} miles on it.")
#
#     def update_odometer(self, mileage):
#         """
#         Set the odometer reading to the given value.
#         Reject the change if it attempts to roll the odometer back.
#         """
#         if mileage >= self.odometer_reading:
#             self.odometer_reading = mileage
#         else:
#             print("You can't roll back an odometer!")
#
#     def increment_odometer(self, miles):
#         """Add the given amount to the odometer reading."""
#         self.odometer_reading += miles

# At 1 we include a module-level docstring that briefly describes the contents
# of this module. You should write a docstring for each module you create.

# Now we make a separate file called my_car.py. This file will import the Car
# class and then create an instance from that class:

# my_car.py

# from car import Car

# my_new_car = Car('audi', 'a4', 2019)
# print(my_new_car.get_descriptive_name())
#
# my_new_car.odometer_reading = 23
# my_new_car.read_odometer()

# The import statement at 1 tells Python to open the car module and import the
# class Car. Now we can use the Car class as if it were defined in this file.
# The output is the name as we saw erlier:

# 2019 Audi A4
# This car has 23 miles on it.

# Importing classes is an effective way to program. Picture how long this
# program file would be if the entire Car class were included. When you instead
# move the class to a module and import the module, you still get all the same
# functionality, but you keep your main program file clean and easy to read. You
# also store most of the logic in separate files; once your classes work as you
# want them to, you can leave those files alone and focus on the higher-level
# logic of your main program.
print("This program contains notes in the comments.")
```
{% endraw %}

26_storing_multiple_classes_in_a_module.py

{% raw %}
```python
# 26_storing_multiple_classes_in_a_module.py

# You can store as many classes as you need in a single module, although each
# class in a module should be related somehow. The classes Battery and
# ElectricCar both help represent cars, so let's add them to the module car.py.

# car.py
# """A set of classes used to represent gas""" and electric cars.

# class Car:
#     """A simple attempt to represent a car."""
#
#     def __init__(self, make, model, year):
#         """Initinalize attributes to describe a car."""
#         self.make = make
#         self.model = model
#         self.year = year
#         self.odometer_reading = 0
#
#     def get_descriptive_name(self):
#         """Return a neatly formatted descriptive name."""
#         long_name = f"{self.year} {self.make} {self.model}"
#         return long_name.title()
#
#     def read_odometer(self):
#         """Print a statement showing the car's mileage."""
#         print(f"This car has {self.odometer_reading} miles on it.")
#
#     def update_odometer(self, mileage):
#         """
#         Set the odometer reading to the given value.
#         Reject the change if it attempts to roll the odometer back.
#         """
#         if mileage >= self.odometer_reading:
#             self.odometer_reading = mileage
#         else:
#             print("You can't roll back an odometer!")
#
#     def increment_odometer(self, miles):
#         """Add the given amount to the odometer reading."""
#         self.odometer_reading += miles


# class Battery:
#     """A simple attempt to model a battery for an electric car."""
#
#     def __init__(self, battery_size=75):
#         """Initialize the battery's attributes."""
#         self.battery_size = battery_size
#
#     def describe_battery(self):
#         """Print a statement describing the battery size."""
#         print(f"This car has a {self.battery_size}-kWh battery.")
#
#     def get_range(self):
#         """Print a statement about the range this battery provides."""
#         if self.battery_size == 75:
#             range = 260
#         elif self.battery_size == 100:
#             range = 315
#
#         print(f"This car can go about {range} miles on a full charge.")
#
#     def upgrade_battery(self):
#         """Check the battery size and set the capacity to 100 if it isn't."""
#         if self.battery_size != 100:
#             self.battery_size = 100
#             print("The battery has been upgraded to 100 kWh.")
#         else:
#             print("The battery is already upgraded.")
#
# class ElectricCar(Car):
#     """Represents aspects of a car, specific to electric vehicles."""
#
#     def __init__(self, make, model, year):
#         """
#         Initialize attributes of the parent class.
#         Then initialize attributes specific to an electric car.
#         """
#         super().__init__(make, model, year)
#         self.battery = Battery()
#
#     def fill_gas_tank(self):
#         """Electric cars don't have gas tanks."""
#         print("This car doesn't need a gas tank!")

# Now we can make a new file called my_electric_car.py, import the ElectricCar
# class, and make an electric car:

# from car import ElectricCar

# my_tesla = ElectricCar('tesla', 'model s', 2019)

# print(my_tesla.get_descriptive_name())
# my_tesla.battery.describe_battery()
# my_tesla.battery.get_range()

# This has the same output we saw earlier, even though most of the logic is
# hidden away in a module.

# 2019 Tesla Model S
# This has the same output we saw earlier, even though most of the logic is
# hidden away in a module:

# 2019 Tesla Model S
# This car has a 75-kWh battery.
# This car can go about 260 miles on a full charge.
print("This program contains notes in the comments.")
```
{% endraw %}

27_importing_multiple_classes_from_a_module.py

{% raw %}
```python
# 27_importing_multiple_classes_from_a_module.py

# You can import as many classes as you need into a program file. If we want to
# make a regular car and an electric car in the same file, we need to import
# both classes, Car and ElectricCar:

# my_cars.py

# from car import Car, ElectricCar

# my_beetle = Car('volkswagen', 'beetle', 2019)
# print(my_beetle.get_descriptive_name())

# my_tesla = ElectricCar('tesla', 'roadster', 2019)
# print(my_tesla.get_descriptive_name())

# You import multiple classes from a module by seperating each class with a
# comma 1. Once you've imported the necessary classes, you're free to make as
# many instances of each class as you need.

# In this example, we make a regular Volkswage Beetle at 2 and an electric Tesla
# Roadster at 3:

# 2019 Volkswagen Beetle
# 2019 Tesla Roadster
print("This program contains notes in the comments.")
```
{% endraw %}

28_importing_an_entire_module.py

{% raw %}
```python
# 28_importing_an_entire_module.py

# Importing an Entire Module

# You can also import an entire module and the access the classes you need using
# dot notation. This approach is simple and results in code that is easy to
# read. Because every call that creates an instance of a class includes the
# module name, you won't have naming conflicts with any names used in the
# current file.

# Here's what it looks like to import the entire car module and then create a
# regular car and an electric car:

# import car                                                                  #1

# my_beetle = car.Car('volkswagen', 'beetle', 2019)                           #2
# print(my_beetle.get_descriptive_name())

# my_tesla = car.ElectricCar('tesla', 'roadster', 2019)                       #3
# print(my_tesla.get_descriptive_name())

# At 1 we import the entire car module. We then access the classes we need
# through the module_name.ClassName syntax. At 2 we again create a Volkswagen
# Beetle, and at 3 we create a Tesla Roadster.
print("This program contains notes in the comments.")
```
{% endraw %}

29_importing_all_classes_from_a_module.py

{% raw %}
```python
# 29_importing_all_classes_from_a_module.py

# You can import every class from a module using the following syntax:

# from module_name import *

# This module name is not recommended for two reasons. First, it's helpful to be
# able to read the import statements at the top of a file and get a clear sense
# of which clases a program uses. With this approach it's unclear which classes
# you're using from the module. This approach can also lead to confusion with
# names in the file. If you accidently import a class with the same name as
# something else in your program file, you can create errors that are bard to
# diagnose. I show this here because even though it's not a recommended approach
# , you'll likely see it in other people's code at some point.

# If you need to import many classes from a module, you're better off importing
# the entire module and using the module_name.ClassName syntax. You won't see
# all the classes used at the top of the file, but you'll see clearly where the
# module is used in the program. You'll also avoid the potential naming
# conflicts that can arise when you import every class in a module.
print("This program contains notes in the comments.")
```
{% endraw %}

30_importing_a_module_into_a_module.py

{% raw %}
```python
# 30_importing_a_module_into_a_module.py

# Sometimes you'll want to spread out your classes over several modules to keep
# any one file from growing too large and avoid storing unrelated classes in the
# same module. When you store your classes in several modules, you may find that
# a class in one module depends on a class in another module. When this happens,
# you can import the required class into the first module.

# For example, let's store the Car class in one module and the ElectricCar and
# Battery classes in a separate module. We'll make a new module called
# electric_car.py--replacing the electric_car.py file we created earlier--and
# copy just the Battery and ElectricCar classes into this file:

# electric_car.py
# """A set of classes that can be used to represent electric cars."""

# from car import Car                                                         #1

# class Battery:
#     --snip--

# class ElectricCar(Car):
#     --snip--

# The class ElectricCar needs access to its parent class Car, so we import Car
# directly into the module at 1. If we forget this line, Python will raise an
# error when we try to import the electric_car module. We also need to update
# the Car module so it contains only the Car class:

# car.py
# """A clas that can be used to represent a car."""

# class Car:
#     --snip--

# Now we can import each module seperately and create whatever kind of car we
# need:

# my_cars.py

# from car import Car                                                         #1
# from electric_car import ElectricCar

# my_beetle = Car('volkswagen', 'beetle', 2019)
# print(my_beetle.get_descriptive_name())

# my_tesla = ElectricCar('tesla', 'roadster', 2019)
# print(my_tesla.get_descriptive_name())

# At 1 we import Car from its module, and ElectricCar from its module. We then
# create one regular car and one electric car. Both kinds of cars are created
# correctly:

# 2019 Volkswagen Beetle
# 2019 Tesla Roadster
print("This program contains notes in the comments.")
```
{% endraw %}

31_using_aliases.py

{% raw %}
```python
# 31_using_aliases.py

# As you saw in Chapter 8, aliases can be quite helpful when using modules to
# organize your projects' code. You can use aliases when importing classes as
# well.

# As an example, consider a program where you want to make a bunch of electric
# cars. It might get tedious to type (and read) ElectricCar over and over again.
# You can give ElectricCar an alias in the import statement:

# from electric_car import ElectricCar as EC

# Now you can use this alias whenever you want to make an electric car:

# my_tesla = EC('tesla', 'roadster', 2019)
print("This program contains notes in the comments.")
```
{% endraw %}

32_finding_your_own_workflow.py

{% raw %}
```python
# 32_finding_your_own_workflow.py

# Finding Your Own Workflow

# As you can see, Python gives you many options for how to structure code in a
# large project. It's important to know all these possibilities so you can
# determine the best ways to organize your projects as well as understand other
# people's projects.

# When you're starting out, keep your code structure simple. Try doing
# everything in one file and moving your classes to separate modules once
# everything is working. If you like how modules and files interact, try storing
# your clases in modules when you start a project. Find an approach that let's
# you write code that works, and go from there.
print("This program contains notes in the comments.")
```
{% endraw %}

33_imported_restaurant.py

{% raw %}
```python
# 33_imported_restaurant.py

# 9-10. Imported Restaurant: Using your latest Restaurant class, store it in a
# module. Make a separate file that imports Restaurant. Make a Restaurant
# instance, and call one of the Restaurant's methods to show that the import
# statement is working properly.

# restaurant_module.py

class Restaurant:
    """A simple attempt to model a restaurant."""

    def __init__(self, restaurant_name, cuisine_type):
        """Initialize restaurant_name and cuisine_type attributes."""
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type
        self.number_served = 0

    def describe_restaurant(self):
        """Prints restaurant information."""
        print(f"This restaurant is called {self.restaurant_name.title()}, "
              f"and it serves {self.cuisine_type.title()} cuisine.")
    def open_restaurant(self):
        """Prints a message that the restaurant is open."""
        print(f"{self.restaurant_name.title()} is open.")
    def set_number_served(self, customers):
        """Sets the number of customers served."""
        self.number_served = customers
    def increment_number_served(self, customers):
        """Increments the number of customers served."""
        self.number_served += customers

# my_restaurant.py

from restaurant_module import Restaurant

my_restaurant = Restaurant('the best restaurant', 'italian')
my_restaurant.describe_restaurant()
my_restaurant.open_restaurant()
```
{% endraw %}

34_imported_admin.py

{% raw %}
```python
# 34_imported_admin.py

# 9-11. Imported Admin: Start with your work from Exercise 9-8 (page 173). Store
# the classes User, Privileges, and Admin in one module. Create a separate file,
# make an Admin instance, and call show_privileges() to show that everything is
# working correctly.

# admin_modules.py

class User:
    """A simple attempt to model a user."""

    def __init__(self, first_name, last_name, age, height):
        """Initialize first_name, last_name, age, and height attributes."""
        self.first_name = first_name
        self.last_name = last_name
        self.age = age
        self.height = height
        self.login_attempts = 0

    def describe_user(self):
        """Prints user information."""
        print(f"{self.first_name.title()} {self.last_name.title()} "
        f"is {self.age} years old and has a height of {self.height} "
        f"centimeters.")

    def greet_user(self):
        """Prints a personalized greeting to the user."""
        print(f"Hello {self.first_name.title()} {self.last_name.title()}!")

    def increment_login_attempts(self):
        """Increments the value of login_attempts by 1."""
        self.login_attempts += 1

    def reset_login_attempts(self):
        """Resets the value of login_attempts to 0."""
        self.login_attempts = 0

class Admin(User):
    """Represents an administrator."""

    def __init__(self, first_name, last_name, age, height):
        """
        Initialize attributes of the parent class.
        Then initialize attributes specific to an administrator.
        """
        super().__init__(first_name, last_name, age, height)
        self.privileges = Privileges()

class Privileges:
    """Represents the privileges of an administrator."""

    def __init__(self):
        """Initialize the privileges attribute."""
        self.privileges = ['can add post', 'can delete post', 'can ban user']

    def show_privileges(self):
        """Displays the administrator's privleges."""
        print("Privileges:")
        for privilege in self.privileges:
            print(f"- {privilege}")

# my_admin.py

from admin_modules import User, Admin, Privileges

new_admin = Admin('Yeji', 'Hwang', 25, 167)
```
{% endraw %}

35_multiple_modules.py

{% raw %}
```python
# 35_multiple_modules.py

# 9-12. Multiple Modules: Store the User class in one module, and store the
# Privileges and Admin classes in a separate module. In a separate file, create
# one Admin instance and call show_privileges() to show that everything is still
# working correctly.

# user_module.py

class User:
    """A simple attempt to model a user."""

    def __init__(self, first_name, last_name, age, height):
        """Initialize first_name, last_name, age, and height attributes."""
        self.first_name = first_name
        self.last_name = last_name
        self.age = age
        self.height = height
        self.login_attempts = 0

    def describe_user(self):
        """Prints user information."""
        print(f"{self.first_name.title()} {self.last_name.title()} "
        f"is {self.age} years old and has a height of {self.height} "
        f"centimeters.")

    def greet_user(self):
        """Prints a personalized greeting to the user."""
        print(f"Hello {self.first_name.title()} {self.last_name.title()}!")

    def increment_login_attempts(self):
        """Increments the value of login_attempts by 1."""
        self.login_attempts += 1

    def reset_login_attempts(self):
        """Resets the value of login_attempts to 0."""
        self.login_attempts = 0

# admin_module.py

from user_module import User

class Admin(User):
    """Represents an administrator."""

    def __init__(self, first_name, last_name, age, height):
        """
        Initialize attributes of the parent class.
        Then initialize attributes specific to an administrator.
        """
        super().__init__(first_name, last_name, age, height)
        self.privileges = Privileges()

class Privileges:
    """Represents the privileges of an administrator."""

    def __init__(self):
        """Initialize the privileges attribute."""
        self.privileges = ['can add post', 'can delete post', 'can ban user']

    def show_privileges(self):
        """Displays the administrator's privleges."""
        print("Privileges:")
        for privilege in self.privileges:
            print(f"- {privilege}")

# my_admin.py

from user_module import User
from admin_module import Admin, Privileges

my_admin = Admin('Yeji', 'Hwang', 25, 167)
my_admin.privileges.show_privileges()
```
{% endraw %}

36_the_python_standard_library.py

{% raw %}
```python
# 36_the_python_standard_library.py

# The Python Standard Library

# The Python standard library is a set of modules included with every Python
# installation. Now that you have a basic understanding of how functions and
# classes work, you can start to use modules like these that other programmers
# have written. You can use any function or class in the standard library by
# including a simple import statement at the top of your file. Let's look at one
# module, random, which can be useful in modeling many real-world situations.

# One interesting function from the random module is randint(). This function
# takes two integer arguments and returns a randomly selected integer between
# (and including) those numbers.

# Here's how to generate a random number between 1 and 6:

# from random import randint
# randint(1, 6)
# 3

# Another useful function is choice(). This function takes in a list or tuple
# and returns a randomly chosen element:

# from random import choice
# players = ['charles', 'martina', 'michael', 'florence', 'eli']
# first_up = choice(players)
# first_up
# 'florence'

# The random module shouldn't be used when building security-related
# applications, but it's good enough for many fun and interesting projects.

# NOTE

# You can also download modules from external sources. You'll see a number of
# these examples in Part II, where we'll need external modules to complete each
# project.
print("This program contains notes in the comments.")
```
{% endraw %}

37_dice.py

{% raw %}
```python
# 37_dice.py

# 9-13. Dice: Make a class Die with one attribute called sides, which has a
# default value of 6. Write a method called roll_die() that prints a random
# number between 1 and the number of sides the die has. Make a 6-sided die and
# roll it 10 times.

# Make a 10-sided die and a 20-sided die. Roll each die 10 times.

from random import randint

class Die:
    """Represents a die."""

    def __init__(self, sides=6):
        """Initialize the sides attribute."""
        self.sides = sides

    def roll_die(self):
        """
        Prints a random number between 1 and the number of sides the die has.
        """
        print(randint(1, self.sides))

six_sided_die = Die()

print("6-sided die rolls:")
for n in range(10):
    six_sided_die.roll_die()

ten_sided_die = Die(10)
print("\n10-sided die rolls:")
for n in range(10):
    ten_sided_die.roll_die()

twenty_sided_die = Die(20)
print("\n20-sided die rolls:")
for n in range(10):
    twenty_sided_die.roll_die()
```
{% endraw %}

38_lottery.py

{% raw %}
```python
# 38_lottery.py

# 9-14. Lottery: Make a list or tuple containing a series of 10 numbers and five
# letters. Randomly select four numbers or letters from the list and print a
# message saying that any ticket matching these four numbers or letters wins a
# prize.

from random import choice

lucky_list = [
    0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 'A', 'B', 'C', 'D', 'E'
]

winning_ticket = []

for n in range(4):
    winning_ticket.append((choice(lucky_list)))

# Join the elements of winning_ticket into a single string for cleaner output
formatted_ticket = "".join(str(item) for item in winning_ticket)

print(f"The winning ticket is {formatted_ticket}.")
```
{% endraw %}

39_lottery_analysis.py

{% raw %}
```python
# 39_lottery_analysis.py

# 9-15. Lottery Analysis: You can use a loop to see how hard it might be to win
# the kind of lottery you just modeled. Make a list or tuple called my_ticket.
# Write a loop that keeps pulling numbers until your ticket wins. Print a
# message reporting how many times the loop had to run to give you a winning
# ticket.

from random import choice

lucky_list = [
    0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 'A', 'B', 'C', 'D', 'E'
]

winning_ticket = ['C', 1, 8, 8]

my_ticket = []

count = 0

while my_ticket != winning_ticket:
    my_ticket = [] # Reset my_ticket for each attempt
    for n in range(4):
        my_ticket.append(choice(lucky_list))
    count += 1
    print(my_ticket)
    print(count)

print(f"It took {count} times to get a winning ticket.")
```
{% endraw %}

40_python_module_of_the_week.py

{% raw %}
```python
# 40_python_module_of_the_week.py

# 9-16. Python Module of the Week: Once excellent resource for exploring the
# Python standard library is a site called Python Module of the Week. Go to
# https://pymotw.com/ and look at the table of contents. Find a module that
# looks interesting to you and read about it, perhaps starting with the random
# module.

# datetime -- Date/time value manipulation

# Purpose: The datetime module includes functions and classes for doing date
# and time parsing, formatting, and arithmetic.

# Avaliable In: 2.3 and later

# datetime contains functions and classes for working with dates and times,
# separately and together.

# Times

# Time values are represented with the time class. Times have attributes for
# hour, minute, second, and microsecond. They can also include time zone
# information. The arguments to initialize a time instance are optional, but the
# default of 0 is unlikely to be what you want.

import datetime

t = datetime.time(1, 2, 3)
print(t)
print(f"hour : {t.hour}")
print(f"minute : {t.minute}")
print(f"second : {t.second}")
print(f"microsecond : {t.microsecond}")
```
{% endraw %}

41_styling_classes.py

{% raw %}
```python
# 41_styling_classes.py

# Styling Classes

# A few styling issues related to classes are worth clarifying, especially as
# your programs become more complicated.

# Class names should be written in CamelCase. To do this, Capitalize the first
# letter or each word in the name, and don't use underscores. Instance and
# module names should be written in lowercase with underscores between words.

# Every class should have a docstring immediately following the class definition
# . The docstring should be a brief description of what the class does, and you
# should follow the same formatting conventions you used for writing docstrings
# in functions. Each module should also have a docstring describing what the
# classes in a module can be used for.

# You can use blank lines to organize code, but don't use them excessively.
# Within a class you can use one blank line between methods, and within a module
# you can use two blank lines to separate classes.

# If you need to import a module from the standard library and a module that you
# wrote, place the import statement for the standard library module first. Then
# add a blank line and the import statement for the module you wrote. In
# programs with multiple import statements, this convention makes it easier to
# see where the different modules used in the program come from.

# Summary

# In this chapter you learned how to write your own classes. You learned how to
# store information in a class using attributese and how to write methods that
# give your classes the behavior they need. You learned to write __ini__()
# methods that create instances from your classes with exactly the attributes
# you want. You saw how to modify the attributes of an instance directly and
# through methods. You learned that inheritance can simplify the creation of
# classes that are related to each other, and you learned to use instances of
# one class as attributes in another class to keep each class simple.

# You saw how storing classes in modules and importing classes you need into the
# files where they'll be used can keep your projects organized. YOu started
# learning about the Python standard library, and you saw an example based on
# the random module. Finally, you learned to style your classes using Python
# conventions.

# In Chapter 10 you'll learn to work with files so you can save the work you've
# done in a program and the work you've allowed users to do. You'll also learn
# about exceptions, a special Python class designed to help you respond to
# errors when they arise.
print("This program contains notes in the comments.")
```
{% endraw %}

42_compound_interest.py

{% raw %}
```python
# 42_compound_interest.py

"""
This program calculates compound interest using the formula A = P(1 + r/n)^nt,
using the CompoundIntereset and GetInput classes.
"""

class CompoundInterest:
    """An attempt to calculate compound interest."""

    def __init__(self, principal, rate, periods, time):
        """Initialize principal, rate, periods, and time attributes."""
        self.principal = principal
        self.rate = rate
        self.periods = periods
        self.time = time

    def calculate_interest(self):
        base = 1 + (self.rate / self.periods)
        exponent = self.periods * self.time
        amount = self.principal * (base ** exponent)
        return amount

class GetInput:
    """An attempt to get user input."""

    def __init__(self):
        """Initialize principal, rate, periods, and time attributes."""
        self.principal = 0.0
        self.rate = 0.0
        self.periods = 0.0
        self.time = 0.0

    def get_input(self):
        """Get user input for principal, rate, periods, and time."""
        self.principal = float(input("Enter the principal amount: "))
        self.rate = float(input("Enter the annual interest rate (ex: 0.08): "))
        self.periods = float(input("Enter the number of periods per year (ex: 1): "))
        self.time = float(input("Enter the number of years: "))

# Create an instance of GetInput and get user input.
user_input = GetInput()
user_input.get_input()

# Create an instance of CompoundInterest using the values from user_input.
compound_calculator = CompoundInterest(
    user_input.principal,
    user_input.rate,
    user_input.periods,
    user_input.time
)

# Calculate and print the interest.
final_amount = compound_calculator.calculate_interest()
print(f"The final amount after compounding interest is: {final_amount:.2f}")
```
{% endraw %}

43_mortgage_payment.py

{% raw %}
```python
# 43_mortage_payment.py

"""An attempt to calculate a monthly mortgage payment."""

class MortgagePayment():
    """An attempt to calculate a monthly mortgage payment."""

    def __init__(self, principal, rate, years, property_taxes, insurance):
        """
        Initialize principle, rate, years, property_taxes, and insurance
        attributes.
        """
        self.principal = principal
        self.rate = rate
        self.years = years
        self.property_taxes = property_taxes
        self.insurance = insurance

    def calculate_payment(self):
        """Calculate and return the monthly payment."""
        r = self.rate / 12
        n = self.years * 12
        numerator = r * (1 + r) ** n
        denominator = (1 + r) ** n - 1
        payment = self.principal * (numerator / denominator)
        monthly_property_taxes = self.property_taxes / 12
        monthly_insurance = self.insurance / 12
        total_payment = payment + monthly_property_taxes + monthly_insurance
        return total_payment

class GetInput:
    """An attempt to get user input."""

    def __init__(self):
        """
        Initialize principal, rate, years, property_taxes, and insurance
        attributes.
        """
        self.principal = 0.0
        self.rate = 0.0
        self.years = 0.0
        self.property_taxes = 0.0
        self.insurance = 0.0

    def get_input(self):
        """Get user input for principal, rate, and years."""
        self.principal = float(input("Enter the principal amount: "))
        self.rate = float(input("Enter the annual interest rate (ex: 0.08):"))
        self.years = float(input("Enter the number of years: "))
        self.property_taxes = float(input("Enter the annual property taxes: "))
        self.insurance = float(input("Enter the annual insurance amount: "))

# Create an instance of GetInput and get user input.
user_input = GetInput()
user_input.get_input()

# Create an instance of MortgagePayment using the values from user_input.
mortgage_calculator = MortgagePayment(
    user_input.principal,
    user_input.rate,
    user_input.years,
    user_input.property_taxes,
    user_input.insurance
)

# Calculate and print the monthly mortage payment.
monthly_payment = mortgage_calculator.calculate_payment()
print(f"The monthly mortgage payment is {monthly_payment:.2f}.")
```
{% endraw %}
