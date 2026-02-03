---
layout: layouts/post.njk
title: Chapter 8 - Functions
date: 2026-02-03
---

Chapter 8 - Functions of the book Python Crash Course by Eric Matthes covers how to write functions. Here are my programs from working through this chapter.

01_defining_functions.py

{% raw %}
```python
# 01_defining_functions.py

# In this chapter, you'll learn to write functions, which are named blocks of
# code that are designed to do one specific job. When you want to perform a
# particular task that you've defined in a function, you call the function
# responsible for it. If you need to perform that task multiple times throughout
# your program, you don't need to type all the code for the same task again and
# again; you just call the function dedicated to handling that task, and the
# call tells Python to run the code inside the function. You'll find that using
# functions makes your programs easier to write, read, test, and fix.

# In this chapter you'll also learn ways to pass information to functions.
# You'll learn how to write certain functions whose primary job is to display
# information and other functions designed to process data and return a value
# or a set of values. Finally, you'll learn to store functions in separate files
# called modules to help organize your main program files.

# Defining a Function

# Here's a simple function named greet_user() that prints a greeting:

# 1 def greet_user():
# 2     """Display a simple greeting."""
# 3     print("Hello!")
# 4 greet_user()

# This example shows the simplest structure of a function. The line at 1 uses
# the keyword def to informa Python that you're defining a function. This is the
# function definition, which tells Python the name of the function and, if
# applicable, what kind of information the function needs to do its job. The
# parentheses hold that information. In this case, the name of the function is
# greet_user(), and it needs no information to do its job, so its parentheses
# are empty. (Even so, the parentheses are required.) Finally, the definition
# ends in a colon.

# Any indented lines that follow def greet_user(): make up of the body of the
# function. The text at 2 is a comment called a docstring, which describes what
# the function does. Docstrings are enclosed in triple quotes, which Python
# looks for when it generates documentation for the functions in your programs.

# The line print("Hello!") 3 is the only line of actual code in the body of this
# function, so greet_user() has just one job: print("Hello!").

# When you want to use this function, you call it. A function call tells Python
# to execute the code in the function. To call a function, you write the name of
# the function, followed by any necessary information in parentheses, as shown
# at 4. Because no information is needed here, calling our function is as simple
# as entering greet_user(). As expected, it prints Hello!:

# Hello!
print("This program contains notes in the comments.")
```
{% endraw %}

02_passing_info_to_a_function.py

{% raw %}
```python
# 02_passing_info_to_a_function.py

# Passing Information to a Function

# Modified slightly, the function greet_user() can not only tell the user Hello!
# but also greet them by name. For the function to do this, you enter username
# in the parentheses of the function's definition at def greet_user(). By adding
# username here you allow the function to accept any value of username you
# specify. The function now expects you to provide a value for username each
# time you call it. When you call greet_user(), you can pass a name, such as
# 'jesse', inside the parentheses:

# def greet_user(username):
#     """Display a simple greeting."""
#     print(f"Hello, {username.title()}!")
# greet_user('jesse')

# Entering greet_user('jesse') calls greet_user() and gives the function the
# information it needs to execute the print() call. The function accepts the
# name you passed it and displays the greeting for that name:

# Hello, Jesse!

# Likewise, entering greet_user('sarah') calls greet_user(), passes it 'sarah',
# and prints Hello, Sarah! You can call greet_user() as often as you want and
# pass it any name you want to produce a predictable output every time.
print("This program contains notes in the comments.")
```
{% endraw %}

03_arguments_and_parameters.py

{% raw %}
```python
# 03_arguments_and_parameters.py

# def greet_user(username):
#     """Display a simple greeting."""
#     print(f"Hello, {username.title()}!")
# greet_user('jesse')

# Arguments and Parameters

# In the preceeding greet_user() function, we defined greet_user() to require a
# value for the variable username. Once we called the function and gave it the
# information (a person's name), it printed the right greeting.

# The variable username in the definition of greet_user() is an example of a
# parameter, a piece of information the function needs to do its job. The value
# 'jesse' in greet_user('jesse') is an example of an argument. An argument is a
# piece of information that's passed from a function call to a function. When we
# call the function, we place the value we want the function to work with in
# parentheses. In this case the argument 'jesse' was passed to the function
# greet_user(), and the value was assigned to the paramenter username.

# NOTE

# People sometimes speak of arguments and paramenters interchangeably. Don't be
# surprised if you see the variables in a function refured to as arguments or
# the variables in a function call referred to as parameters.
print("This program contains in the comments.")
```
{% endraw %}

04_message.py

{% raw %}
```python
# 04_message.py

# 8-1. Message: Write a function called display_message() that prints one
# sentence telling everyone what you are learning about in this chapter. Call
# the function, and make sure the message displays correctly.

def display_message():
  """Prints a simple message."""
  print("This is a simple message.")

display_message()
```
{% endraw %}

05_favorite_book.py

{% raw %}
```python
# 05_favorite_book.py

# 8.2. Favorite Book: Write a function called favorite_book() that accepts one
# parameter, title. The function should print a message, such as One of my
# favorite books is Alice in Wonderland. Call the function, making sure to
# include a book title as an argument in the function call.

def favorite_book(title):
  """Prints a message contain a favorite book."""
  print(f"My favorite book is {title.title()}.")

favorite_book('the imitation of christ')
```
{% endraw %}

06_positional_arguments.py

{% raw %}
```python
# 06_positional_arguments.py

# Passing Arguments

# Because a function definition can have multiple paramenters, a function call
# may need multiple arguments. You can pass arguments to your functions in a
# number of ways. You can use positional arguments, which need to be in the same
# order the parameters were written: keyword arguments, where each argument
# consists of a variable name and a value; and lists and dictionaries of values.
# Let's look at each of these in turn.

# Positional Arguments

# When you call a function, Python must match each argument in the function
# call with a parameter in the function definition. The simplest way to do this
# is based on the order of the arguments provided. Values matched up this way
# are called positional arguments.

# To see how this works, consider a function that displays information about
# pets. The function tells us what kind of animal each pet is and the pet's name
# , as shown here:

# def_describe_pet(animal_type, pet_name):
#     """Display information about a pet."""
#     print(f"\nI have a {animal_type}.")
#     print(f"My {animal_type}'s name is {pet_name.title()}.")

# describe_pet('hamster', 'harry')

# The defintion shows that this function eeds a type of animal and the animal's
# name 1. When we call describe_pet(), we need to provide an animal type and a
# name, in that order. For example, in the function call, the argument 'hamster'
# is assigned to the parameter animal_type and the argument 'harry' is assigned
# to the parameter pet_name 2. In the function body, these two parameters are
# used to display information about the pet being described.

# The output describes a hamster named Harry:

# I have a hamster.
# My hamster's name is Harry.

print("This program contains notes in the comments.")
```
{% endraw %}

07_multiple_function_calls.py

{% raw %}
```python
# 07_multiple_function_calls.py

# Multiple Function Calls

# You can call a function as many times as need. Describing a second, different
# pet requires just one more call to describe_pet():

# def_describe_pet(animal_type, pet_name):
#     """Display information about a pet."""
#     print(f"\nI have a {animal_type}.")
#     print(f"My {animal_type}'s name is {pet_name.title()}.")

# describe_pet('hamster', 'harry')
# describe_pet('dog', 'willie')

# In this second function call, we pass describe_pet() the arguments 'dog' and
# 'willie'. As wit hthe previous set of arguments we used, Python matches 'dog'
# wit the parameter animal_type and 'willie' with the parameter pet_name.

# As before, the function does its job, but this time it prints values for a dog
# named Willie. Now we have a hamster named Harry and a dog named Willie.

# I have a hamster.
# My hamster's name is Harry.

# I have a dog.
# My dog's name is Willie.

# Calling a function multiple times is a very efficient way to work. The code
# describing a pet is written once in the function. Then, anytime you want to
# describe a new pet, you call the function wit hthe new pet's information. Even
# if the code for describing a pet were to expand to ten lines, you could still
# describe a new pet in just one line by calling the function again.

# You can use as many positional arguments as you need in your functions. Python
# works through the argumetns you provide when calling the function and matches
# each one with the corresponding parameters in the function's definition.

print("This program contains notes in the comments.")
```
{% endraw %}

08_order_matters_in_positional_arguments.py

{% raw %}
```python
# 08_order_matters_in_postional_arguments.py

# You can get unexpected results if you mix up the order of the arguments in
# a function call when using postional arguments:

# def describe_pet(animal_type, pet_name):
#     """Display information about a pet."""
#     print(f"\nI have a {animal_type}.")
#     print(f"My {animal_type}'s name is {pet_name.title()}.")

# describe_pet('harry', 'hamster')

# In this function call we list the name first and then the type of animal
# second. Because the argument 'harry' is listed first this time, that value is
# assigned to the parameter animal_type. Likewise, 'hamster' is assigned to
# pet_name. Now we have a "harry" named "Hamster":

# I have a harry.
# My harry's name is Hamster.

# If you get funny results like this, check to make sure the order of the
# arguments in your function call matches the order of the parameters in the
# function's defintion.
print("This program contains notes in the comments.")
```
{% endraw %}

09_keyword_arguments.py

{% raw %}
```python
# 09_keyword_arguments.py

# Keyword Arguments

# A keyword argument is a name-value pair that you pass to a function. You
# directly associate the name and the value within the argument, so when you
# pass the argument to the function, there's no confusion (you won't end up
# with a harry named Hamster). Keyword arguments free you from having to
# worry about correctly ordering your aruments in the function call, and they
# clarify the role of each value in the function call.

# Let's rewrite pets.py using keyword arguments to call describe_pets():

# def describe_pet(naimal_type, pet_name):
#     """Display information about a pet."""
#     print(f"\nI have a {animal_type}.")
#     print(f"My {animal_type}'s name is {pet_name.title()}.")

# describe_pet(animal_type='hamster', pet_name='harry')

# The function describe_pet() hasn't changed. But when we call the function,
# we explicitly tell Python which parameter each argument should be matched
# with. When Python reads the function call, it knows to assign the argument
# 'hamster' with the parameter animal_type and the argument 'harry' to pet_name.
# The output correctly shows that we have a hamster named Harry.

# The order of keyword arguments doesn't matter because Python knows where each
# value should go. The following two function calls are equivalent:

# describe_pet(animal_type='hamster', pet_name='harry')
# describe_pet(pet_name='harry', animal_type='hamster')

# NOTE
# When you use keyword arguments, be sure to use the exact name of the
# parameters in the function's definition.
print("This program contains notes in the comments.")
```
{% endraw %}

10_default_values.py

{% raw %}
```python
# 10_default_values.py

# Default Values

# When writing a function, you can define a default value for each parameter.
# If an argument for a parameter is provided in the function call, Python uses
# the argument value. If not, it uses the parameter's default value. So when
# you define a default value for a parameter, you can exclude the corresponding
# argument you'd usually write in the function call. Using default values can
# simplify your function calls and clarify the ways in which your functions are
# typically used.

# For example, if you notice ethat most of the calls to describe_pet() are being
# used to describe dogs, you can set the default value of animal_type to 'dog'.
# Now anyone calling describe_pet() for a dog can omit that information:

# def describe_pet(pet_name, animal_type='dog'):
#     """Display information about a pet."""
#     print(f"\nI have a {animal_type}.")
#     print(f"My {animal_type}'s name is {pet_name.title()}.")

# describe_pet(pet_name='willie')

# We've changed the definiton of describe_pet() to include a default value,
# 'dog', for animal_type. Now when the function is called with no animal_type
# specified, Python knows to use the value 'dog' for this parameter:

# I have a dog.
# My dog's name is Willie.

# Note that the order of parameters in the function definition had to be
# changed. Because the default value makes it unnecessary to specify a type of
# animal as an argument, the only argument left in the function call is the
# pet's name. Python still interprets this as a positional argument, so if the
# function is called with just a pet's name, that argument will match up with
# the first parameter listed in the function's definition. This is the reason
# the first parameter needs to be pet_name.

# The simplest way to use this function is to provide just a dog's name in the
# function call:

# describe_pet('willie')

# This function call would have the same output as the previous example. The
# only argument provided is 'willie', so it is matched up with the first
# parameter in the definition, pet_name. Because no argument is provided for
# animal_type, Python uses the default value 'dog'.

# To describe an animal other than a dog, you could use a function call like
# this:

# describe_pet(pet_name='harry', animal_type='hamster')

# Because an explicit argument for animal_type is provided, Python will ignore
# the parameter's default value.

# NOTE

# When you use default values, any parameter with a default value needs to be
# listed after all the parameters that don't have default values. This allows
# Python to continue interpreting positional arguments correctly.
```
{% endraw %}

11_equivalent_function_calls.py

{% raw %}
```python
# 11_equivalent_function_calls.py

# Becaue positional arguments, keyword arguments, and default values can be used
# together, often you'll have several equivalent ways to call a function.
# Consider the fuollowing definition for describe_pet() with one default value
# provided:

# def describe_pet(pet_name, animal_type='dog'):

# With this definition, an argument always needs to be provided for pet_name,
# and this value can be provided using the positional or keyword format. If the
# animal being described is not a dog, an argument for animal_type must be
# included in the call, and this this argument can also be specified using the
# positional or keyword format.

# All of the following calls would work for this function:

# A dog named Willie.
# describe_pet('willie')
# describe_pet(pet_name='willie')

# A hamster named Harry.
# describe_pet('harry', 'hamster')
# describe_pet(pet_name='harry', animal_type='hamster')
# describe_pet(animal_type='hamster', pet_name='harry')

# Each of these function calls would have the same output as the previous
# examples.

# NOTE

# It doesn't really matter which calling style you use. As long as your function
# calls produce the output you want, just use the style you find easiest to
# understand.
```
{% endraw %}

12_avoiding_argument_errors.py

{% raw %}
```python
# 12_avoiding_argument_errors.py

# Avoiding Argument Errors

# When you start to use functions, don't be surprised if you encounter errors
# about unmatched arguments. Unmatched arguments occur when you provide fewer or
# more arguments than a function needs to do its work. For example, here's what
# happens if we try to call describe_pet() with no arguments:

# def describe_pet(animal_type, pet_name):
#     """Display information about a pet."""
#     print(f"\nI have a {animal_type}.")
#     print(f"My {animal_type}'s name is {pet_name.title()}.")

# describe_pet()

# Python recognizes that some information is missing from the function call, and
# the traceback tells us that:

#   Traceback (most recent call last):
# 1   File "pets.py", line 6, in <module>
# 2     describe_pet()
# 3 TypeError: describe_pet() missing 2 required positional arguments:
# 4 'animal_type' and 'pet_name'

# At 1 the traceback tells us the location of the problem, allowing us to look
# back and see that something went wrong in our function call. At 2 the
# offending function call is written out for us to see. At 3 the traceback
# tells us the call is missign two arguments and reports the names of the
# missing arguments. If this function were in a separate file, we could probably
# rewrite the call correctly without having to open that file and read
# the function code.

# Python is helpful in that it reads the function's code for us and tells us the
# names of the arguments we need to provide. This is another motivation for
# giving your variables and functions descriptive names. If you do, Python's
# error messages will be more useful to you and anyone else who might use your
# code.

# If you provide too many arguments, you should get a similar traceback that can
# help you correctly match your function call to the function definition.
print("This program contains notes in the comments.")
```
{% endraw %}

13_t_shirt.py

{% raw %}
```python
# 13_t_shirt.py

# 8-3. T-Shirt: Write a function called make_shirt() that accepts a size and the
# text of a message that should be printed on the shirt. The function should
# print a sentence summarizing the size of the shirt and the message printed on
# it.

# Call the function once using positional arguments to make a shirt. Call the
# function a second time using keyword arguments.

def make_shirt(size, message):
  print(f"The shirt's size is {size.title()}.")
  print(f'The message on the shirt reads, "{message}"')

make_shirt('s', 'I like Python.')
make_shirt(size='m', message='I like C.')
```
{% endraw %}

14_large_shirts.py

{% raw %}
```python
# 14_large_shirts.py

# 8-4. Large Shirts: Modify the make_shirt() function so that shirts are large
# by default with a message that reads I love Python. Make a large shirt and a
# medium shirt with the default message, and a shirt of any size with a
# different message.

def make_shirt(size='l', message='I love Python.'):
  print(f"The shirt's size is {size.title()}.")
  print(f'The message on the shirt reads, "{message}"')

make_shirt()
make_shirt('m')
make_shirt('s', 'I prefer C.')
```
{% endraw %}

15_cities.py
{% raw %}
```python
# 15_cities.py

# 8-5. Cities: Write a function called describe_city() that accepts the name of
# a city and its country. The function should print a simple sentence, such as
# Reykjavik is in Iceland. Give the parameter for the country a default value.
# Call your function for three different cities, at least one of which is not
# in the default country.

def describe_city(city, country='the United States'):
  print(f"{city.title()} is located in {country}.")

describe_city('chicago')
describe_city('los angeles')
describe_city('paris', 'France')
```
{% endraw %}

16_returning_a_simple_value.py

{% raw %}
```python
# 16_returning_a_simple_value.py

# Return Values

# A function doesn't always have to display its output directly. Instead, it can
# process some data and then return a value or a set of values. The value the
# function returns is called a return value. The return statement takes a value
# from inside a function and sends it back to the line that called the function.
# Return values allow you to move much of your program's grunt work into
# functions, which can simplify the body of your program.

# Returning a Simple Value

# Let's look at a function that takes a first and last name, and returns a
# neatly formatted full name:

# def get_formatted_name(first_name, last_name):
#     """Return a full name, neatly formatted."""
#     full_name = f"{first_name} {last_name}"
#     return full_name.title()

# musician = get_formatted_name('jimi', 'hendrix')
# print(musician)

# The definition of get_formatted_name() takes as parameters a first and a last
# name 1. The function combines these two names, adds a space between them, and
# assigns the result to full_name 2. The value of full_name is converted to
# title case, and then returned to the calling line at 3.

# When you call a function that returns a value, you need to provide a variable
# that the return value can be assigned to. In this case, the returned value is
# assigned to the variable musician at 4. The output shows a neatly formatted
# name made up of the parts of a person's name:

# Jimi Hendrix

# This might seem like a lot of work to get a neatly formatted name when we
# could have just written:

# print("Jimi Hendrix")

# But when you consider working with a large program that needs to store many
# first and last names separately, functions like get_formatted_name() become
# very useful. You store first and last names separately and then call this
# function whenever you want to display a full name.

print("This program contains notes in the comments.")
```
{% endraw %}

17_making_an_argument_optional.py

{% raw %}
```python
# 17_making_an_argument_optional.py

# Making an Argument Optional

# Sometimes it makes sense to make an argument optional so that people using
# the function can choose to provide extra information only if they want to.
# You can use default values to make an argument optional.

# For example, say we want to expand get_formatted_Name() to handle middle names
# as well. A first attempt to include middle names might look like this:

# def get_formatted_name(first_name, middle_name, last_name):
#     """Return a full name, neatly formatted."""
#     full_name = f"{first_name} {middle_name} {last_name}"
#     return full_name.title()

# musician = get_formatted_name('john', 'lee', 'hooker')
# print(musician)

# This function works when given a first, middle, and last name. The function
# takes in all three parts of a name and then builds a string out of them. The
# function adds space where appropriate and converts the full name to title
# case:

# John Lee Hooker

# But middle names aren't always needed, and this function as written would not
# work if you tried to call it with only a first name and a last name. To make
# the middle name optional, we can give the middle_name argument an empty
# default value and ignore the argument unless the user provides a value. To
# make get_formatted_name() work without a middle name, we set the default value
# of middle_name to an empty string and move it to the end of the list of
# parameters:

# 1 def get_formatted_name(first_name, last_name, middle_name=''):
#       """Return a full name, neatly formatted."""
# 2     if middle_name:
#           full_name = f"{first_name} {middle_name} {last_name}"
# 3     else:
#           full_name = f"{first_name} {last_name}"
#       return full_name.title()

# musician = get_formatted_name('jimi', 'hendrix')
# print(musician)

# 4 musician = get_formatted_name('johm', 'hooker', 'lee')
# print(musician)

# In this example, the name is built from three possible parts. Because there's
# always a first and a last name, these parameters are listed first in the
# function's definition. The middle name is optional, so it's listed last in the
# defintion, and its default value is an empty string 1.

# In the body of the function, we check to see if a middle name has been
# provided. Python interprets non-empty strings as True, so middle_name
# evaluates to True if a middle name argument is in the function call 2. If a
# middle name is provided, the first, middle, and last names are combined to
# form a full name. This name is then changed to title case and returned to the
# function call line where it's assigned to the variable musician and printed.
# If no middle name is provided, the empty string fails the if test and the else
# block runs 3. The full name is made with just a first and last name, and the
# formatted name is returned to the calling line where it's assigned to musician
# and printed.

# Calling this function with a first and last name is straightforward. If we're
# using a middle name, however, we have to make sure the middle name is the last
# argument passed so Python will match up the positional arguments correctly 4.

# This modified version of our function works for people with just a first
# and last name, and it works for people who have a middle name as well.

# Jimi Hendrix
# John Lee Hooker

# Optional values allow functions to handle a wide range of use cases while
# letting function calls remain as simple as possible.
print("This program contains notes in the comments.")
```
{% endraw %}

18_returning_a_dictionary.py

{% raw %}
```python
# 18_returning_a_dictionary.py

# A function can return any kind of value you need it to, including more
# complicated data structures like lists and dictionaries. For example, the
# following function takes in parts of a name and returns a dictionary
# representing a person:

#   def build_person(first_name, last_name):
#       """Return a dictionary of information about a person."""
# 1     person = {'first': first_name, 'last': last_name}
# 2     return person

# musician = build_person('jimi', 'hendrix')
# 3 print(musician)

# The function build_person() takes in a first annd last name, and puts these
# values into a dictionary at 1. The value of first_name is stored with the key
# 'first', and the value of last_name is stored with the key 'last'. The entire
# dictionary representing the person is returned at 2. The return value is
# printed at 3 with the original two pieces of textual information now stored
# in a dictionary:

# {'first': 'jimi', 'last': 'hendrix'}

# This function takes in simple textual information and puts it into a more
# meaningful data structure that lets you work with the information beyond just
# printing it. The strings 'jimi' and 'hendrix' are now labeld as a first name
# and last name. You can easily extend this function to accept optional values
# like a middle name, an age, an occupation, or any other information you want
# to store about a person. For example, the following change allows you to store
# a person's age as well:

# def build_person(first_name, last_name, age=None):
#     """Return a dictionary of information about a person."""
#     person = {'first': firstname, 'last': last_name}
#     if age:
#         person['age'] = age
#     return person

# musician = build_person('jimi', 'hendrix', age=27)
# print(musician)

# We add a new optional parameter age to the function definition and assign the
# parameter the special value None, which is used when a variable has no
# specific value assigned to it. You can think of None as a placeholder value.
# In conditional tests, None evaluates to False. If the function call includes
# a value for age, that value is stored in the dictionary. This function always
# stores a person's name, but it can also be modified to store any other
# information you want about a person.
print("This program contains notes in the comments.")
```
{% endraw %}

19_using_a_function_with_a_while_loop.py

{% raw %}
```python
# 19_using_a_function_with_a_while_loop.py

# You can use functions with all the Python structures you've learned about so
# far. For example, leet's use the get_formatted_name() function with a while
# loop to greet users more formally. Here's a first attempt at greeting people
# using their first and last names:

# def get_formatted_name(first_name, last_name):
#     """Return a full name, neatly formatted."""
#     full_name = f"{first_name}, {last_name}"
#     return full_name.title()

#   This is an infinite loop!
#   While True:
# 1     print("\nPlease tell me your name:")
#       f_name = input("First name: ")
#       l_name = input("Last name: ")

#       formatted_name = get_formatted_name(f_name, l_name)
#       print(f"\nHello, {formatted_name}!")

# For this example, we use a simple version of get_formatted_name() that doesn't
# involve middle names. The while loop asks the user to enter their name, and we
# prompt for their first and last name separately 1. But there's one problem
# with this whileLoop: We haven't defined a quit condition. Whre do you put a
# quit condition when you ask for a series of inputs? We want the user to be
# able to quit as easily as possible, so each prompt should offer a way to quit.
# The break statement offers a straightforward way to exit the loop at either
# prompt:

# def get_formatted_name(first_name, last_name):
#     """Return a full name, neatly formatted."""
#     full_name = f"{first_name}, {last_name}"
#     return full_name.title()

# This is an infinite loop!
# while True:
#     print("\nPlease tell me your name:")
#     print("(enter 'q' at any time to quit)")

#     f_name = input("First name: ")
#     if f_name == 'q':
#         break

#     l_name = input("Last name: ")
#     if l_name == 'q':
#         break

#     formatted_name = get_formatted_name(f_name, l_name)
#     print(f"\nHello, {formatted_name}!")

# We add a message ethat informas the user how to quit, and then we break out of
# the loop if the user enters the quit value at either prompt. Now the program
# will continue greeting people until someone enters 'q' for either name:

# Please tell me your name:
# (enter 'q' at any time to quit)
# First name: eric
# Last name: matthes

# Hello, Eric Matthes!

# Please tell me your name:
# (enter 'q' at any time to quit)
# First name: q
print("This program contains notes in the comments.")
```
{% endraw %}

20_city_names.py

{% raw %}
```python
# 20_city_names.py

# 8-6. City Names: Write a function called city_country() that takes in the name
# of a city and its country. The function should return a string formatted like
# this:

# "Santiago, Chile"

# Call your function with at least three city-country pairs, and print the
# values that are returned.

def city_country(city, country):
  """Return a formatted string about a city and country."""
  formatted_string = f"{city.title()}, {country.title()}"
  return formatted_string

city_country_1 = city_country('tokyo', 'japan')
city_country_2 = city_country('seoul', 'south korea')
city_country_3 = city_country('beijing', 'china')
print(city_country_1)
print(city_country_2)
print(city_country_3)

```
{% endraw %}

21_album.py

{% raw %}
```python
# 21_album.py

# 8-7. Album. Write a function called make_album() that builds a dictionary
# describing a music album. The function should take in an artist name and an
# album title, and it should return a dictionary containing these two pieces of
# information. Use the function to make three dictionaries representing
# different albums. Print each return value to show that the dictionaries are
# storing the album information correctly.

# Use None to add an optional parameter to make_album() that allows you to store
# the number of songs on an album. If the calling line includes a value for the
# number of songs, add that value to the album's dictionary. Make at least one
# new function call that includes the number of songs on an album.

def make_album(artist_name, album_title, songs=None):
    """Return an album's information formatted in a dictionary."""
    album_dictionary = {'artist_name': artist_name, 'album_name': album_title}
    if songs:
        album_dictionary['songs'] = songs
    return album_dictionary

album_1 = make_album('TWICE', 'Twicetagram', '13')
album_2 = make_album('Itzy', 'Crazy in Love', '16')
album_3 = make_album('IU', 'Growing Up', '16')

print(album_1)
print(album_2)
print(album_3)
```
{% endraw %}

21_album.py

{% raw %}
```python
# 21_album.py

# 8-7. Album. Write a function called make_album() that builds a dictionary
# describing a music album. The function should take in an artist name and an
# album title, and it should return a dictionary containing these two pieces of
# information. Use the function to make three dictionaries representing
# different albums. Print each return value to show that the dictionaries are
# storing the album information correctly.

# Use None to add an optional parameter to make_album() that allows you to store
# the number of songs on an album. If the calling line includes a value for the
# number of songs, add that value to the album's dictionary. Make at least one
# new function call that includes the number of songs on an album.

def make_album(artist_name, album_title, songs=None):
    """Return an album's information formatted in a dictionary."""
    album_dictionary = {'artist_name': artist_name, 'album_name': album_title}
    if songs:
        album_dictionary['songs'] = songs
    return album_dictionary

album_1 = make_album('TWICE', 'Twicetagram', '13')
album_2 = make_album('Itzy', 'Crazy in Love', '16')
album_3 = make_album('IU', 'Growing Up', '16')

print(album_1)
print(album_2)
print(album_3)
```
{% endraw %}

22_user_albums.py

{% raw %}
```python
# 22_user_albums.py

# 8-8. User Albums. Start with your program from Exercise 8-7. Write a while
# loop that allows users to enter an album's artist and title. Once you have
# the information, call make_album() with the user's input and print the
# dictionary that's created. Be sure to include a quit value in the while loop.

def make_album(artist_name, album_title, songs=None):
    """Return an album's information formatted in a dictionary."""
    album_dictionary = {'artist_name': artist_name, 'album_name': album_title}
    if songs:
        album_dictionary['songs'] = songs
    return album_dictionary

# This is an infinite loop.
while True:
    print("\nPlease enter the name of an artist and album:")
    print("(enter 'q' at any time to quit)")

    artist_name = input("Artist name: ")
    if artist_name == 'q':
        break

    album_title = input("Album title: ")
    if album_title == 'q':
        break

    album_information = make_album(artist_name, album_title)
    print(album_information)
```
{% endraw %}

23_passing_a_list.py

{% raw %}
```python
# 23_passing_a_list.py

# Passing a List

# You'll often find it useful to pass a list to a function, whether it's a list
# of names, numbers or more complex objects, such as dictionaries. When you pass
# a list to a function, the function gets direct access to the contents of the
# list. Let's use functions to make morking ith lists more efficient.

# Say we have a list of users and want to print a greeting to each. The
# following example sends a list of names to a function called greet_users(),
# which greets each person in the list individually:

# def greet_users(names)
#     """Print a simple greeting to each user in the list."""
#     for name in names:
#         msg = f"Hello, {name.title()}!"
#         print(msg)

# usernames = ['hannah', 'ty', 'margot']
# greet_users(usernames)

# We define greet_users() so it expects a list of names, which it assigns to
# the parameter names. The function loops through the list it receives and
# prints a greeting to each user. At 1 we define a list of users and then pass
# the list usernames to greet_users() in our function call:

# Hello, Hannah!
# Hello, Ty!
# Hello, Margot!

# This is the output we wanted. Every user sees a personalized greeting, and you
# can call the function any time you want to greet a specific set of users.
print("This program contains notes in the comments.")
```
{% endraw %}

24_modifying_a_list_in_a_function.py

{% raw %}
```python
# 24_modifying_a_list_in_a_function.py

# Modifying a List in a Function

# When you pass a list to a function, the function can modify the list. Any
# changes made to the list inside the function's body are permanent, allowing
# you to work efficiently even when you're dealing with large amounts of data.

# Consider a company that creates 3D printed models of designs that users
# submit. Designs that need to be printed are stored in a list, and after being
# printed they're moved to a separate list. The following code does this without
# using functions:

# Start with some designs that need to be printed.
# unprinted_designs = ['phone case', 'robot pendant', 'dodecahedron']
# completed_models = []

# Simulate printing each design, until none are left.
# Move each design to completed_models after printing.
# while unprinted_designs:
#     current_design = unprinted_designs.pop()
#     print(f"Printing model: {current_design}")
#     completed_models.append(current_design)

# Display all completed models.
# print("\nThe following models have been printed:")
# for completed_model in completed_models:
#     print(completed_model)

# This program starts with a list of designs that need to be printed and an
# empty list called complete_models that each design will be moved to after it
# has been printed. As long as designs remain in unprinted_designs, the while
# loop simulates printing each design by removing a design from the end of the
# list, storing it in current_design, and displaying a message that the current
# design is being printed. It then adds the design to the list of completed
# models. When the loop is finished running, a list of the designs that have
# been printed is displayed:

# Printing model: dodecahedron
# Printing model: robot pendant
# Printing model: phone case

# The following models have been printed:
# dodecahedron
# robot pendant
# phone case

# We can reorganize this code by writing two functions, each of which does one
# specific job. Most of the code won't change; we're just making it more
# carefully structured. The first function will handle printing the designs, and
# the second will summarize the prints that have been made:

# def print_models(unprinted_designs, completed_models):
#     "
#     Simulate printing each design, until none are left.
#     Move each design to completed_models after printing.
#     "
#     while unprinted_designs:
#         current_design = unprinted_designs.pop()
#         print(f"Printing model: {current_design}")
#         completed_models.append(current_design)

# def show_completed_models(completed_models):
#     """Show all the models that were printed."""
#     print("\nThe following models have been printed:")
#     for completed_model in completed_models:
#         print(completed_model)

# unprinted_designs = ['phone case', 'robot pendant', 'dodecahedron']
# completed_models = []

# print_models(unprinted_designs, completed_models)
# show_completed_models(completed_models)

# At 1 we define the function print_models() with two parameters: a list of
# designs that need to be printed and a list of completed models. Given these
# two lists, the function simulates printing each design by emptying the list of
# unprinted designs and filling up the list of completed models. At 2 we define
# the function show_completed_models() with one parameter: the list of completed
# models. Given this list, show_completed_models() displays the name of each
# model that was printed.

# This program has the same output as the version without functions, but the
# code is much more organized. The code that does most of the work has been
# moved to two separate functions, which makes the main part of the program
# easier to understand. Look at the body of the program to see how much easier
# it is to understand what this program is doing:

# unprinted_designs = ['phone case', 'robot pendant', 'dodecahedron']
# completed_models = []

# print_models(unprinted_designs, completed_models)
# show_completed_models(completed_models)

# We set up a list of unprinted designs and an empty list that will hold the
# completed models. Then, because we've already defined our two functions, all
# we have to do is call them and pass them the right arguments. We call
# print_models() and pass it the two lists it needs; as expected, print_models()
# simulates printing the designs. Then we call show_completed_models() and pass
# it the list of completed models so it can report the models that have been
# printed. The descriptive function names allow others to read this code and
# understand it, even without comments.

# This program is easier to extend and maintain than the version without
# functions. If we need to print more designs later on, we can simply call
# print_models() again. If we realize the printing code needs to be modified,
# we can change the code once, and our changes will take place everwhere the
# function is called. This technique is more efficient than having to update
# code separately in several places in the program.

# This example also demonstrates the idea that every function should have one
# specific job. The first function prints each design, and the second displays
# the completed models. This is more beneficial than using one function to do
# both jobs. If you're writing a function and notice the function is doing too
# many different tasks, try to split the code into two functions. Remember that
# you can always call a function from another function, which can be helpful
# when splitting a complex task into a series of steps.
print("This program contains notes in the comments.")
```
{% endraw %}

25_preventing_a_function_from_modifying_a_list.py

{% raw %}
```python
# 25_preventing_a_function_from_modifying_a_list.py

# Preventing a Function from Modifying a List

# Sometimes you'll want to prevent a function from modifying a list. For
# example, sary that you start with a list of unprinted designs and write a
# function to move them to a list of completed models, as in the previous
# example. You may decide that even though you've printed all the designs, you
# want to keep the original list of unprinted designs for your records.

# But because you moved all the design names out of unprinted_designs, the list
# is now empty, and the empty list is the only version you have; the original is
# gone. In this case, you can address this issue by passing the function a copy
# of the list, not the original. Any changes the function makes to the list will
# only affect the copy, leaving the original list intact.

# You can send a copy of a list to a function like this:

# function_name(list_name[:])

# The slice notation [:] makes a copy of the list to send to the function. If we
# didn't want to empty the list of unprinted designs in printing_models.py,
# we would call print_models() like this:

# print_models(unprinted_designs[:], completed_models)

# The function print_models() can do its work because it still receives the
# names of all unprinted designs. But this time it uses a copy of the original
# unprinted designs list, not the actual unprinted_designs list. The list
# completed_models will fill up with the names of printed models like it did
# before, but the original list of unprinted designs will be unaffected by the
# function.

# Even though you can perserve the contents of a list by passing a copy of it to
# your functions, you should pass the original list to functions unless you have
# a specific reason to pass a copy. It's more efficient for a function to work
# with an existing list to avoid using the time and memory needed to make a
# separate copy, especially when you're working with large files.
print("This program contains notes in the comments.")
```
{% endraw %}

26_messages.py

{% raw %}
```python
# 26_messages.py

# 8-9. Messages: Make a list containing a series of short text messages. Pass
# the list to a funciton called show_messages(), which prints each text message.

messages = [
    'I like TWICE.', 'I also like Itzy.', 'I like NMIXX.',
    'I also like BLACKPINK.', 'I also like fromis_9', 'I like FIFTY FIFTY too.'
]

def show_messages(messages):
    for message in messages:
        print(message)

show_messages(messages)
```
{% endraw %}

27_sending_messages.py

{% raw %}
```python
# 27_sending_messages.py

# 8-10. Sending Messages: Start with a copy of your program from Exercise 8-9.
# Write a function called send_messages() that prints each text message and
# moves each message to a new list called sent_messages as it's printed. After
# calling the function, print both of your lists to make sure the messages were
# moved correctly.

messages = [
    'I like TWICE.', 'I also like Itzy.', 'I like NMIXX.',
    'I also like BLACKPINK.', 'I also like fromis_9', 'I like FIFTY FIFTY too.'
]

sent_messages = []

def show_messages(messages):
    for message in messages:
        print(message)

def send_messages(messages, sent_messages):
    """Move messages to sent mesages."""
    while messages:
        current_message = messages.pop()
        print(f"Sending message: {current_message}")
        sent_messages.append(current_message)

def print_messages(messages):
    print("This is what is in the messages list.")
    print(messages)

def print_sent_messages(sent_messages):
    print("This is what is in the sent_messages list.")
    print(sent_messages)

send_messages(messages, sent_messages)
print_messages(messages)
print_sent_messages(sent_messages)
```
{% endraw %}

28_archived_messages.py

{% raw %}
```python
# 28_archived_messages.py

# 8-11. Archived Messages: Start with your work from Exercise 8-10. Call the
# function send_messages() with a copy of the list of messages. After calling
# the function, print both of your lists to show that the orignal list has
# retained its messages.

messages = [
    'I like TWICE.', 'I also like Itzy.', 'I like NMIXX.',
    'I also like BLACKPINK.', 'I also like fromis_9', 'I like FIFTY FIFTY too.'
]

sent_messages = []

def show_messages(messages):
    for message in messages:
        print(message)

def send_messages(messages, sent_messages):
    """Move messages to sent mesages."""
    while messages:
        current_message = messages.pop()
        print(f"Sending message: {current_message}")
        sent_messages.append(current_message)

def print_messages(messages):
    print("This is what is in the messages list.")
    print(messages)

def print_sent_messages(sent_messages):
    print("This is what is in the sent_messages list.")
    print(sent_messages)

send_messages(messages[:], sent_messages)
print_messages(messages)
print_sent_messages(sent_messages)
```
{% endraw %}

29_passing_an_arbitrary_number_of_arguments.py

{% raw %}
```python
# 29_passing_an_arbitrary_number_of_arguments.py

# Passing an Arbitrary Number of Arguments

# Sometimes you won't know ahead of time how many arguments a function needs to
# accept. Fortunately, Python allows a function to collect an arbitrary number
# of arguments from the calling statement.

# For example, consider a function that builds a pizza. It needs to accept a
# number of toppings, but you can't know ahead of time how many toppings a
# person will want. The function in the following example has one parameter,
# *toppings, but this parameter collects as many arguments as the calling line
# provides:

# def make_pizza(*toppings):
#     """Print the list of toppings that have been requested."""
#     print(toppings)

# make_pizza('pepperoni')
# make_pizza('mushrooms', 'green peppers', 'extra cheese')

# The asterisk in the parameter name *toppings tells Python to make an empty
# tuple called toppings and pack whatever values it receives into this tuple.
# The print() call in the function body produces output showing that Python
# can handle a function call with one value and a call with three values. It
# treats the different calls similarly. Note that Python packs the arguments
# into a tuple, even if the function receives only one value:

# ('pepperoni')
# ('mushrooms', 'green peppers', 'extra cheese')

# Now we can replace the print() call with a loop that runs through all the list
# of toppings and describes the pizza being ordered:

# def make_pizza(*toppings):
#     """Summarize the pizza we are about to make."""
#     print("\nMaking a pizza with the following toppings:")
#     for topping in toppings:
#         print(f"- {topping}")

# make_pizza('pepperoni')
# make_pizza('mushrooms', 'green peppers', 'extra cheese')

# The function responds appropriately, whether it receives one value or three
# values:

# Making a pizza with the following toppings:
# - pepperoni

# Making a pizza with the following toppings:
# - mushrooms
# - green peppers
# - extra cheese

# This syntax works no matter how many arguments the function receives.
print("This program contains notes in the comments.")
```
{% endraw %}

30_mixing_positional_and_arbitrary_arguments.py

{% raw %}
```python
# 30_mixing_positional_and_arbitrary_arguments.py

# Mixing Positional and Arbitrary Arguments

# If you want a function to accept several different kinds of arguments, the
# parameter that accepts an arbitrary number of arguments must be placed last
# in the function definition. Python matches positional and keyword arguments
# first and then collects any remaining arguments in the final parameter.

# For example, if the function needs to take in a size for the pizza, that
# parameter must come before the parameter *toppings:

# def make_pizza(size, *toppings):
#     """Summarize the pizza we are about to make."""
#     print(f"\nMaking a {size}-inch pizza with the following toppings:")
#     for topping in toppings:
#         print(f"- {topping}")

# make_pizza(16, 'pepperoni')
# make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

# In the function definition, Python assigns the first value it receives to the
# parameter size. All other values that come after are stored in the tuple
# toppings. The function calls include an argument for the size first, followed
# by as many toppings as needed.

# Now each pizza has a size and a number of toppings, and each piece of
# information is printed in the proper place, showing size first and toppings
# after:

# Making a 16-inch pizza with the following toppings:
# - pepperoni

# Making a 12-inch pizza with the following toppings:
# - mushrooms
# - green peppers
# - extra cheese

# NOTE

# You'll often see the generic parameter name *args, which collects arbitrary
# positional arguments like this.
print("This program contains notes in the comments.")
```
{% endraw %}

31_using_arbitrary_keyword_arguments.py

{% raw %}
```python
# 31_using_arbitrary_keyword_arguments.py

# Using Arbitrary Keyword Arguments

# Sometimes you'll want to accept an arbitrary number of arguments, but you
# won't know ahead of time what kind of information will be passed to the
# function. In this case, you can write functions that accept as many key-value
# pairs as the calling statement provides. One example involves building user
# profiles: you know you'll get information about a user, but you're not sure
# what kind of information you'll receive. The function build_profiles() in the
# following example always takes in a first and a last name, but it accepts an
# arbitrary number of keyword arguments as well:

# def build_profile(first, last, **user_info):
#     """Build a dictionary containing everything we know about a user."""
#     user_info['first_name'] = first
#     user_info['last_name] = last
#     return user_info

# user_profile = build_profile('albert', 'einstein',
#                              location='princeton',
#                              field='physics')

# print(user_profile)

# The definition of build_profile() expexts a first and a last name, and then
# it allows the user to pass in as many name-value pairs as they want. The
# double asterisks before the parameter **user_info cause Python to create an
# empty dictionary called user_info and pack whatever name-value pairs it
# receives into this dictionary. Within the function, you can access the
# key-value pairs in user_info just as you would for any dictionary.

# In the body of build_profile(), we add the first and last names to the
# user_info dictionary because we'll always receive these two pieces of
# information from the user 1, and they haven't been placed into the dictionary
# yet. Then we return the user_info dictionary to the function call line.

# We call build_profile(), passing it the first name 'albert', the last name
# 'einstein', and the two key-value pairs location='princeton' and
# field='physics'. We assign the returned profile to user_profile and print
# user_profile:

# {'location': 'princeton', 'field': 'physics',
# 'first_name': 'albert', 'last_name': 'einstein'}

# The returned dictionary contains the user's first and last names and, in this
# case, the location and field of study as well. The function would work no
# matter how many additional key-value pairs are provided in the function call.

# You can mix positional, keyword, and arbitrary values in many different
# ways when writing your own functions. It's useful to know that all these
# argument types exist because you'll see them often when you start reading
# other people's code. It takes practice to learn to use the different types
# correctly and to know when to use each type. For now, remember to use the
# simplest approach that gets the job done. As you progress you'll learn to use
# the most efficient approach each time.

# NOTE

# You'll often see the parameter name **kargs used to collect non-specific
# keyword arguments.
print("This program contains notes in the comments.")
```
{% endraw %}

32_sandwiches.py

{% raw %}
```python
# 32_sandwiches.py

# 8-12. Sandwiches: Write a function that accepts a list of items a person wants
# on a sandwich. The function should have one parameter that collects as many
# items as the function call provides, and it should print a summary of the
# sandwich that's being ordered. Call the function three times, using a
# different nubmer of arguments each time.

def make_sandwich(*items):
    """Summarize the sandwich we are about to make."""
    print(f"Making a sandwich with the following items:")
    for item in items:
        print(f"- {item}")

make_sandwich('turkey', 'colby-jack cheese', 'wheat bread')
make_sandwich('ham', 'cheddar cheese', 'white bread')
make_sandwich('bacon', 'lettuce', 'tomatoes', 'toasted white bread')

```
{% endraw %}

33_user_profile.py

{% raw %}
```python
# 33_user_profile.py

# 8-13. User Profile: Start with a copy of user_profile.py from page 149. Build
# a profile of yourself by calling build_profile(), using your first and last
# names and three other key-value pairs that describe you.

def build_profile(first, last, **user_info):
    """Build a dictionary contain everything we know about a user."""
    user_info['first_name'] = first
    user_info['last_name'] = last
    return user_info

user_profile = build_profile('jane', 'doe',
                             favorite_anime='kimi ni todoke',
                             favorite_kpop_group='itzy',
                             favorite_programming_language='python')

print(user_profile)
```
{% endraw %}

34_cars.py

{% raw %}
```python
# 34_cars.py

# 8-14. Cars: Write a function that stores information about a car in a
# dictionary. The function should always receive a manufacturer and a model
# name. It should then accept an arbitrary number of keyword arguments. Call
# the function with the required information and two other name-value pairs,
# such as a color or an optional feature. Your function should work for a call
# like this one:

# car = make_car('subaru', ''outback', color='blue', tow_package=True)

# Print the dictionary that's returned to make sure all the information was
# stored correctly.

def make_car(manufacturer, model_name, **car_info):
    """Build a dictionary containing everything we know about a car."""
    car_info['manufacturer'] = manufacturer
    car_info['model_name'] = model_name
    return car_info

car = make_car('subaru', 'outback', color='blue', tow_package=True)
print(car)
```
{% endraw %}

35_importing_an_entire_module.py

{% raw %}
```python
# 35_importing_an_entire_module.py

# Storing Your Functions in Modules

# One advantage of functions is the way they separate blocks of code from your
# main program. By using descriptive names for your functions, you main
# program will be much easier to follow. You can go a step further by storing
# your functions in a separate file called a module and then importing that
# module into your main program. An import statement tells Python to make the
# code in a module available in the currently running program file.

# Storing your functions in a separate file allows you to hid the details of
# your program's code and focus on it's higher-level logic. It also allows you
# to reuse functions in many different programs. When you store your functions
# in separate files, you can share those files with other programmers without
# also having to share your entire program. Knowing know to import functions
# also allows you to use libraries of functions that other programmers have
# written.

# There are several ways to import a module, and I'll show you each of these
# briefly.

# Importing an Entire Module

# To start importing functions, we first need to create a module. A module is a
# file ending in .py that contains code you want to import into your program.
# Let's make a module that contains the function make_pizza(). To make this
# module, we'll remove everything from the file pizza.py except the function
# make_pizza():

# pizza.py

# def make_pizza(size, *toppings):
#     """Summarize the pizza we are about to make."""
#     print(f"\nMaking a {size}-inch pizza with the following toppings:")
#     for topping in toppings:
#         print(f"- {topping}")

# Now we'll make a separate file called making_pizzas.py in the same directory
# as pizza.py. This file imports the module we just created and then makes
# two calls to make_pizza():

# making_pizzas.py

# import pizza

# pizza.make_pizza(16, 'pepperoni')
# pizza.make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

# When Python reads this file, the line import pizza tells Python to open the
# file pizza.py and copy all the functions from it into this program. You don't
# actually see code being copied between files because Python copies the code
# behind the scenes just before the program runs. All you need to know is that
# any function defined in pizza.py will now be available in making_pizzas.py.

# To call a function from an imported module, enter the name of the module you
# imported, pizza, followed by the name of the function make_pizza(), separated
# by a dot 1. This code produces the same output as the original program that
# didn't import a module:

# Making a 16-inch pizza with the following toppings:
# - pepperoni

# Making a 12-inch pizza with the following toppings:
# - mushrooms
# - green peppers
# - extra cheese

# The first approach to importing, in which you simply write import followed
# by the name of the module, makes every function from the module available in
# your program. If you use this kind of import statement to import an entire
# module named module_name.py, each function in the module is available through
# the following syntax:

# module_name.function_name()
print("This program contains notes in the comments.")
```
{% endraw %}

36_importing_specific_functions.py

{% raw %}
```python
# 36_importing_specific_functions.py

# Importing Specific Functions

# You can also import a specific function from a module. Here's the general
# syntax for this approach:

# from module_name import function_name

# You can import as many functions as you want from a module by separating
# each function's name with a comma:

# from module_name import function_0, function_1, function_2

# The making_pizzas example would look like ethis if we want to import just
# the function we're going to use:

# from pizza import make_pizza

# make_pizza(16, 'pepperoni')
# make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

# With this sytnax, you don't need to use the dot notation when you call a
# function. Because we've explicitly imported the function make_pizza() in the
# import statement, we can call it by name when we use the function.
print("This program contains notes in the comments.")
```
{% endraw %}

37_using_as_to_give_a_function_an_alias.py

{% raw %}
```python
# 37_using_as_to_give_a_function_an_alias.py

# Using as to Give a Function an Alias

# If the name of a function you're importing might conflict with an existing
# name in your program or if the function name is long, you can use a short,
# unique alias--an alternate name similar to a nickname for the function. You'll
# give the function this special nickname when you import the function.

# Here we give the function make_pizza() an alias, mp(), by importing make_pizza
# as mp. The as keyword renames a function using the alias you provide:

# from pizza import make_pizza as mp

# mp(16, 'pepperoni')
# mp(12, 'mushrooms', 'green peppers', 'extra cheese')

# The import statement shown here renames the function make_pizza() to mp() in
# this program. Any time we want to call make_pizza() we can simply write mp()
# instead, and Python will run the code in make_pizza() while avoiding any
# confusion with another make_pizza() function you might have written in this
# program file.

# The general syntax for providing an alias is:

# from module_name import function_name as fn
print("This program contains notes in the comments.")
```
{% endraw %}

38_using_as_to_give_a_module_an_alias.py

{% raw %}
```python
# 38_using_as_to_give_a_module_an_alias.py

# You can also provide an alias for a module name. Giving a module a short
# alias, like p for pizza, allows you t ocall the module's functions more
# quickly. Calling p.make_pizza() is more concise then calling
# pizza.make_pizza():

# import pizza as p

# p.make_pizza(16, 'pepperoni')
# p.make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

# The module pizza is given the alias p in the import statement, but all of the
# module's functions retain their original names. Calling the functions by
# writing p.make_pizza() is not only more concise than writing
# pizza.make_pizza(), but also redirects your attention from the module name and
# allows you to focus on the descriptive names of its functions. These function
# names, which clearly tell you want each function does, are more important to
# the readability of your code than using the full mode name.

# The general syntax for this approach is:

# import module_name as mn
print("This program contains notes in the comments.")
```
{% endraw %}

39_importing_all_functions_in_a_module.py

{% raw %}
```python
# 39_importing_all_functions_in_a_module.py

# You can tell Python to import every function in a module by using the asterisk
# (*) operator:

# from pizza import *

# make_pizza(16, 'pepperoni')
# make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

# The asterisk in the import statement tells Python to copy every function from
# the module pizza into this program file. Because every function is imported,
# you can call each function by name without using the dot notaion. However,
# it's not best to use this approach when you're working with larger modules
# that you didn't write: if the module has a function name that matches an
# existing name in your project, you can get some unexpected results. Python
# may see several functions or variables with the same name, and instead of
# importing all the functions separately, it will overwrite the functions.

# The best approach is to import the function or functions you want, or import
# the entire module and use the dot notation. This leads to clear code that's
# easy to read and understand. I include this section so you'll recognize import
# statements like the following when you see them in other people's code:

# from module_name import *
print("This program contains notes in the comments.")
```
{% endraw %}

40_styling_functions.py

{% raw %}
```python
# 40_styling_functions.py

# Styling Functions

# You need to keep a few details in mind when you're styling functions.
# Functions should have descriptive names, and these names should use lowercase
# letters and underscores. Descriptive names help you and others understand what
# your code is trying to do. Module names should use these conventions as well.

# Every function should have a comment that explains concisely what the function
# does. This comment should appear immediately after the function definition and
# use the docstring format. In a well-documented function, other programmers can
# use the function by reading only the description in the docstring. They should
# be able to trust that the code works as described, and as long as they know
# the name of the function, the arguments it needs, and the kind of value it
# returns, they should be able to use it in their programs.

# If you specify a default value for a parameter, no spaces should be used on
# either side of the equal sign:

# def function_name(parameter_0, parameter_1='default value')

# The same convention should be used for keyword arguments in function calls:

# function_name(value_0, parameter_1='value')

# PEP 8 (https://www.python.org/dev/peps/pep-0008/) recommends that you limit
# lines of code to 79 characters so every line is visible in a reasonably sized
# editor window. If a set of paramters cause a function's definition to be
# longer than 79 characters, press ENTER after the opening parenthesis on the
# definition line. On the next line, press TAB twice to separate the list of
# arguments from the body of the function, which will only be indented one
# level.

# Most editors automatically line up any additional lines of parameters to match
# the indentation you have established on the first line:

# def function_name(
#     parameter_0, parameter_1, parameter_2,
#     parameter_3, parameter_4, parameter_5):
# function body...

# If your program or module has more than one function, you can separate each
# two blank lines to make it easier to see where one function ends and the next
# one begins.

# All import statements should be written at the beginning of a file. The only
# exception is if you use comments at the beginning of your file to describe
# the overall program.
print("This program contains notes in the comments.")
```
{% endraw %}

41_printing_models.py

{% raw %}
```python
# 41_printing_models.py

# 8-15. Printing Models: Put the functions for the example printing_models.py
# in a separate file called printing_functions.py. Write an import statement at
# the top of printing_models.py, and modify the file to use the imported
# functions.

# printing_functions.py

# def print_models(unprinted_designs, completed_models):
#     """
#     Simulate printing each design, until none are left.
#     Move each design to completed_models after printing.
#     """
#     while unprinted_designs:
#         current_design = unprinted_designs.pop()
#         print(f"Printing model: {current_design}")
#         completed_models.append(current_design)

# def show_completed_models(completed_models):
#     """Show all the models that were printed."""
#     print("\nThe following models have been printed:")
#     for completed_model in completed_models:
#         print(completed_model)

# 41_printing_models.py

# from printing_functions import *

# unprinted_designs = ['phone case', 'robot pendant', 'dodecahedron']
# completed_models = []

# print_models(unprinted_designs, completed_models)
# show_completed_models(completed_models)

# If I imported using import printing_functions:

# import printing_functions

# printing_functions.print_models(unprinted_designs, completed_models)
# printing_functions.show_completed_models(completed_models)

print("This program contains notes in the comments.")
```
{% endraw %}

42_imports.py

{% raw %}
```python
# 42_imports.py

# 8-16. Imports: Using a program you wrote that has one function in it, store
# that function in a separate file. Import the function into your main program
# file, and call the function using each of these approaches:

# import module_name
# from module_name import function_name
# from module_name import function_name as fn
# import module_name as mn
# from module_name import *

# module_name.py

# def function_name():
#     print("Hello world.")

# -----------------------------------------------------------------

# example_1.py

# Example 1: using import module_name

# import module_name

# module_name.function_name()

# -----------------------------------------------------------------

# example_2.py

# Example 2: using from module_name import function_name

# from module_name import function_name

# function_name()

# -----------------------------------------------------------------

# example_3.py

# Example 3: from module_name import function_name as fn

# from module_name import function_name as fn

# fn()

# -----------------------------------------------------------------

# example_4.py

# Example 4: import module_name as mn

# import module_name as mn

# mn.function_name()

# -----------------------------------------------------------------

# example_5.py

# Example 5: from module_name import *

# from module_name import *

# function_name()

# -----------------------------------------------------------------
```
{% endraw %}

43_styling_functions.py

{% raw %}
```python
# 43_styling_functions.py

# Chose any three programs you wrote for this chapter, and make sure they
# follow the styling guidelines described in this section.

# Styling Functions

# You need to keep a few details in mind when you're styling functions.
# Functions should have descriptive names, and these names should use lowercase
# letters and underscores. Descriptive names help you and others understand what
# your code is trying to do. Module names should use these conventions as well.

# Every function should have a comment that explains concisely what the function
# does. This comment should appear immediately after the function definition and
# use the docstring format. In a well-documented function, other programmers can
# use the function by reading only the description in the docstring. They should
# be able to trust that the code works as described, and as long as they know
# the name of the function, the arguments it needs, and the kind of value it
# returns, they should be able to use it in their programs.

# If you specify a default value for a parameter, no spaces should be used on
# either side of the equal sign:

# def function_name(parameter_0, parameter_1='default value')

# The same convention should be used for keyword arguments in function calls:

# function_name(value_0, parameter_1='value')

# PEP 8 (https://www.python.org/dev/peps/pep-0008/) recommends that you limit
# lines of code to 79 characters so every line is visible in a reasonably sized
# editor window. If a set of paramters cause a function's definition to be
# longer than 79 characters, press ENTER after the opening parenthesis on the
# definition line. On the next line, press TAB twice to separate the list of
# arguments from the body of the function, which will only be indented one
# level.

# Most editors automatically line up any additional lines of parameters to match
# the indentation you have established on the first line:

# def function_name(
#     parameter_0, parameter_1, parameter_2,
#     parameter_3, parameter_4, parameter_5):
# function body...

# If your program or module has more than one function, you can separate each
# two blank lines to make it easier to see where one function ends and the next
# one begins.

# All import statements should be written at the beginning of a file. The only
# exception is if you use comments at the beginning of your file to describe
# the overall program.

print("This program contains notes in the comments. "
      "My programs follow these guidelines.")

```
{% endraw %}

44_summary.py

{% raw %}
```python
# 44_summary.py

# Summary

# In this chapter you learned how to write functions and to pass arguments so
# that your functions have access to the information they need to do their work.
# You learned how to use positional and keyword arguments, and how to accept an
# arbitrary number of arguments. You saw functions that display output and
# functions that return values. You learned how to use functions with lists,
# dictionaries, if statements, and while loops. You also saw how to store your
# functions in seperate files called modules, so your program files will be
# simpler and easier to understand. Finally, you learned to style your functions
# so your programs will continue to be well-structured and as easy as possible
# for you and others to read.

# One of your goals as a programmer should be to write simple code that does
# what you want it to, and functions help you do this. They allow you to
# write blocks of code and leave them alone once you know they work. When you
# know a function does its job correctly, you can trust that it will continue
# to work and move on to your next coding task.

# Functions allow you to write code once and then reuse that code as many times
# as you want. When you need to run the code in a function, all you need to do
# is write a one-line call and the function does its job. When you need to
# modify a function's behavior, you only have to modify one block of code, and
# your change takes effect everywhere you've made a call to that function.

# Using functions makes your programs easier to read, and good function names
# summarize what each part of a program does. Reading a series of function
# calls gives you a much quicker sense of what a program does than reading a
# long series of code blocks.

# Functions also make your code easier to test and debut. When the bulk of your
# program's work is done by a set of functions, each of which has a specific job
#, it's much easier to test and maintain the code you've written. You can write
# a separate program that calls each function and tests wheter each function
# works in all the situations it may encounter. When you do this, you can be
# confident that your functions will work properly each time you call them.

# In Chapter 9 you'll learn to write classes. Classes combine functions and data
# into one neat package that can be used in flexible and efficient ways.
print("This program contains notes in the comments.")
```
{% endraw %}
