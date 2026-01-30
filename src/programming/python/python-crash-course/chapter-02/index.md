---
layout: layouts/post.njk
title: Chapter 2 - Variables and Simple Data Types 
date: 2026-01-30
---

Chapter 2 - Variables and Simple Data Types of the book Python Crash Course by Eric Matthes covers how the different kinds of variables such as strings and numbers. Here are the programs I wrote as I worked through this chapter.

01_variables.py
{% raw %}
```python
# We've added a variable named message. Every variable is connected to a value, which is the information 
# associated with that variable. In this case the value is the "Hello Python world!" text.

# Adding a variable makes a litte more work for the Python interpreter. When it processes the first line, it
# associates the variable message with the "Hello Python world!" text. When it reaches the second line, it prints
# the value assocated with message to the screen.

message = "Hello Python world!"
print(message)
```
{% endraw %}

02_variable_change.py
{% raw %}
```python
# Let's expand on this program by modifying the hello_world.py to print a second message. Add a blank line to
# hello_world.py, and then add two new lines of code.

# You can change the value of a variable in your program at any time, and Python will always keep track of
# its current value.

message = "Hello Python world!"
print(message)

message = "Hello Python Crash Course world!"
print(message)
```
{% endraw %}

03_variable_name_error.py
{% raw %}
```python
# Every programmer makes mistakes, and most make mistakes every day. Although good programmers might create
# errors, they also know how to respond to those errors efficiently. Let's look at an error you're likely to make early on and learn how to fix it.

# We'll write some code that generates an error on purpose. Enter the following code, including the misspelled
# word mesage shown in bold.

#  When an error occurs in your program, the Python interpreter does its best to help you figure out where the
# problem is. The interpreter provides a traceback when a program cannot run successfully. A traceback is a record
# of where the interpreter ran into trouble when trying to execute your code. Here's an example of a traceback
# that Python provides after you've accidentally misspelled a variable name:

# 0 Traceback (most recent call last):
# 1 File "hello_world.py", line 2, in <module>
# 2     print(mesage)
# 3 NameError: name 'mesage' is not defined

# The output at 1 reports that an error occurs in line 2 of the file hello_world.py. The interpreter shows this
# line 2 to help us spot the error name error and reports that the variable being printed, mesage, has not been
# defined. Python can't identify the variable name provided. A name error usually means we either forgot to set
# a variable's value before using it, or we made a spelling mistake when entering the variable's name.

# Of course, in this example we omitted the letter s in the variable name mesage in the second line. The Python
# interpreter doesn't spellcheck your code, but it does ensure that variable names are spelled consistently.

# Programming languages are strict, but they disregard good and bad spelling. As a result, you don't need to
# consider English spelling and grammar rules when you're trying to create variable names and writing code.

# Many programming errors are simple, single-character typos in one line of a program. If you're spending a long
# time searching for one of these errors, know that you're in good company. Many experienced and talented
# programmers spend hours hunting down these kinds of tiny errors. Try to laugh about it and move on, knowing
# it will happen frequently throughout your programming life.

message = "Hello Python Crash Course reader!"
print(mesage)
```
{% endraw %}

04_simple_message.py
{% raw %}
```python
# Write a separate program to accomplish each of these exercises. Save each program with a filename that follows
# standard Python conventions, using lowercase letters and underscores, such as simple_message.py and simple_messages.py.

# 2.1. Simple Message: Assign a message to a variable, and then print that message.

message = "I am kpopnetrunner. It is a pleasure to meet you!"
print(message)
```
{% endraw %}

05_simple_messages.py
{% raw %}
```python
# Write a separate program to accomplish each of these exercises. Save each program with a filename that follows
# standard Python conventions, using lowercase letters and underscores, such as simple_message.py and simple_messages.py.

# 2-2. Simple Message: Assign a message to a variable, and print that message. Then change the value of the
# variable to a new message, and print the new message.

message = "I am kpopnetrunner."
print(message)

message = "My favorite K-Pop idol is ITZY's Yeji."
print(message)
```
{% endraw %}

06_strings.py
{% raw %}
```python
# Strings

# Because most programs define and gather some sort of data, and then do something useful with it, it helps to
# classify different types of data. The first data type we'll look at is the string. Strings are quite simple at
# first glance, but you can use them in many different ways.

# A string is a series of characters. Anything inside quotes is considered a string in Python, and you can use
# single or double quotes around your strings like this:

# "This is a string."
# 'This is also a string.'

# This flexibility allows you to use quotes and apostrophes within your strings:

# 'I told my friend, "Python is my favorite language!"'
# "The language 'Python' is named after Monty Python, not the snake."
# "One of Python's strengths is its diverse and supportive community."

message_1 = 'I told my friend, "Python is my favorite language!"'
message_2 = "The language 'Python' is named after Monty Python, not the snake."
message_3 = "One of Python's strengths is its diverse and supportive community."
print(message_1)
print(message_2)
print(message_3)
```
{% endraw %}

07_changing_case_in_a_string_with_methods.py
{% raw %}
```python
# One of the simplest taks you can do wit hstrings is change the nase of the words in a string. Look at the
# following code, and try to determine what's happening:

# In this example, the variable name refers to the lowercase string "ada lovelace". The method title() appears
# after the variable in the print() call. A method is an action that Python can perform on a piece of data.
# The dot (.) after name in name.title() tells Python to make the title() method act on the variable name.
# Every method is followed by a set of parentheses, because methods often need additional information to do their
# work. That information is provided inside the parenteses. The title() function doesn't need any additional
# information, so its parentheses are empty.

# The title() method changes each word to title case, where each word begins with a capital letter. This is useful
# because you'll often want to think of a name as a piece of information. For example, you might want your program
# to recognize the input values Ada, ADA, and ada as the same name, and display all of them as Ada.

# Several other useful methods are available for dealing with case as well. For example, you can change a string 
# to all uppercase or all lowercase letters like this:

# name = "Ada Lovelace"
# print(name.upper())
# print(name.lower())

# This will display the following:

# ADA LOVELACE
# ada lovelace

# The lower() method is particularly useful for storing data. Many times you won't want to trust the
# capitalization that your users provide, so you'll convert strings to lowercase before storing them. Then when
# you want to display the information, you'll use the case that makes the most sense for each string.

name = "ada lovelace"
print(name.title())
print(name.upper())
print(name.lower())
```
{% endraw %}

08_using_variables_in_strings.py
{% raw %}
```python
# Using Variables in Strings

# In some situations, you'll want to use a variable's value inside a string. For example, you might
# want two variables to represent a first name and a last name respectively, and then want to combine
# those values to display someone's full name:

# To insert a variable's value into a string, place the letter f immediately before the opening
# quotation mark. Put braces around the name or names of any variable you want to use inside the string.
# Python will replace each variable with its value when the string is displayed.

# These values are called f-strings. The f is for format, because Python formats the string by replacing
# the name of any variable in braces with its value. The output from the previous code was "ada lovelace."

# You can do a lot with f-strings. For example, you can use f-strings to compose complete messages using
# the information associated with a variable, as shown here:

# The full name is used in a stenence that greets the user, and the title() method changes the name to
# titlecase. This code returns a simple, but nicely formatted greeting:

# Hello, Ada Lovelace!

# You can also use f-strings to compose a message, and then assign the entire message to a variable.

# This code displays the message Hello, Ada Lovelace! as well, but by assigning the message to a variable
# we make the final print() call much simpler.

# NOTE

# F-strings were first introduced in Python 3.6. If you're using Python 3.5 or earlier, you'll need to use
# the format() method rather than this f syntax. To use format(), list the variables you want to use in the
# string inside the parentheses following format. Each variable is referred to by a set of braces; the braces
# will be filled by the values listed in parentheses in the order provided:

# full_name = "{} {}".format(first_name, last_name)

first_name = "ada"
last_name = "lovelace"
full_name = f"{first_name} {last_name}"
print(full_name)
print(f"Hello, {full_name.title()}!")
message = f"Hello, {full_name.title()}!"
print(message)
```
{% endraw %}

09_adding_whitespace_to_strings.py
{% raw %}
```python
# In programming, whitespace refers to any nonprinting character, such as spaces, tabs, and end-of-line
# symbols. You can use whitespace to organize your output so it's easier for users to read.

# To add a tab to your text, use the character combination \t as show at:

# >>> print("Python")
# Python
# >>> print("\tPython")
#     Python

# To add a newline in a string, use the character combination \n:

# >>> print("Languages:\nPython\nC\nJavaScript")
# Languages:
# Python
# C
# JavaScript

# You can also combine tabs and newlines in a single string. The string "\n\t" tells Python to move to a
# new line, and start the next line with a tab. The following example shows how you can use a one-line
# string to generate fourlines of output:

# >>> print("Languages:\n\tPython\n\tC\n\tJavaScript")
# Languages:
#     Python
#     C
#     JavaScript

# Newlines and tabs will be very useful in the next two chapters when you want to produce many lines of
# output from just a few lines of code.

print("Itzy members:\nYeji\nYuna\nRyujin\nChaeryeong\nLia")
```
{% endraw %}

10_stripping_whitespace.py
{% raw %}
```python
# Stripping Whitespace

# Extra whitespace can be confusing in your programs. To programmers 'python' and 'python ' look pretty
# much the same. But to a program, they are two different strings. Python detects the extra space in
# 'python ' and considers it significant unless you tell it otherwise.

# It's important to think about whitespace, because often you'll want to compare two strings to determine
# whether they are the name. For example, one important instance might involve checking people's usernames
# when they log in to a website. Extra whitespace can be confusing in much simpler situations as well.
# Fortunately, Python makes it easy to eliminate extraneous whitespace from data that people enter.

# Python can look for extra whitespace on the right and left sides of a string. To ensure that no whitespace
# exists at the right end of a string, use the rstrip() method.

# >>> favorite_language = 'python '
# >>> favorite_language
# 'python '
# >>> favorite_language.rstrip()
# 'python'
# >>> favorite_language
# 'python '

# The value associated with favorite_language at 1 contains extra whitespace at the end of the string. When
# you ask Python for this value in a terminal session, you can see the space at the end of the value 2. When
# the rstrip() method acts on the variable favorite_language at 3, this extra space is removed. However, it is
# only removed temporarily. If you ask for the value of favorite_language again, you can see that the string looks
# the same as when it was entered, including the extra whitespace 4.

# To remove the whitespace from the string permanently, you have to associate the stripped value with the variable
# name:

# >>> favorite_language = 'python '
# >>> favorite_language = favorite_language.rstrip()
# favorite_language
# 'python'

# To remove the whitespace from the string, you strip the whitespace from the right side of the string and then
# associate this new value with the original variable, as shown at 1. Changing a variable's value is done often
# in programming. This is how a variable's value can be updated as a program is executed or in response to user input.

# You can also strip whitespace from the left side of a string using the lstrip() method, or from both sides at once
# using strip():

# >>> favorite_language = ' python '
# >>> favorite_language.rstrip()
# ' python'
# >>> favorite_language.lstrip()
# 'python '
# >>> favorite_language.strip()
# 'strip'

# In this example, we start with a value that has whitespace at the beginning and the end 1. We then remove the extra
# space from the right side at 2, from the left side at 3, and from both sides at 4. Experimenting with these 
# stripping functions can help you become familiar with manipulating strings. In the real world, these striping functions
# are used most often to clean up user input before it's stored in a program.

print("This program mostly contains notes in the comments.")
```
{% endraw %}

11_avoiding_syntax_errors_with_strings.py
{% raw %}
```python
# One kind of error that you might see with some regularity is a syntax error. A syntax error occurs when Python
# doesn't recognize a section of your program as valid Python code. For example, if you use an apostrophe within
# single quotes, you'll produce an error. This happens because Python interprets everything between the first
# single quote and the apostrophe as a string. It then tries to interpret the rest of the text as Python code,
# which causes errors.

# Here's how to use single and double quotes correctly. Save this program as apostrophe.py and then run it:
# message = "One of Python's strengths is its diverse community."
# print(message)

# The apostrophe appears inside a set of double quotes, so the Python interpreter has no trouble reading the
# string correctly:

# One of Python's strengths is its diverse community.

# However, if you use single quotes, Python can't identify where the string should end:

# message = 'One of Python's strengths is its diverse community.'
# print(message)

# You'll see the following output:

# File "apostrophe.py", line 1
#   message = 'One of Python's strenths is its diverse community.'
# SyntaxError: invalid syntax

# In the output you can see that the error occurs at 1 right after the second single quote. This syntax error indicates
# that the interpreter doesn't recognize something in the code as valid Python code. Errors can come from a variety of
# sources, and I'll point out some common ones as they arise. You might see syntax errors often as you learn to write
# proper Python code. Syntax errors are also the least specific kind of error, so they can be difficult and frustrating
# to identify and correct. If you get stuck on a particularly stubborn error, see the suggestions in Appendix C.

# NOTE

# Your editor's syntax highlighting feature should help you spot some syntax errors quickly as you write your programs.
# If you see Python code highlighted as if it's English or English highlighted as if it's Python code, you probably have
# a mismatched quotation mark somewhere in your file.

print("This program contains notes in the comments.")
```
{% endraw %}

12_personal_message.py
{% raw %}
```python
# Save each of the following exercises as a separate file with a name like name_cases.py. If you get stuck,
# take a break or see the suggestions in Appendix C.

# 2-3. Personal Message: Use a variable to represent a person's name, and print a message to that person.
# Your message should be simple, such, as "Hello Eric", would you like to learn some Python today?"

name = "yeji"
message = f"Hello {name.title()}, how are you doing?"
print(message)
```
{% endraw %}

13_name_cases.py
{% raw %}
```python
# Save each of the following exercises as a separate file with a name like name_cases.py. If you get stuck,
# take a break or see the suggestions in Appendix C.

# 2-4. Name Cases: Use a variable to represent a person's name, and then print that person's name in lowercase,
# uppercase, and title case.

first_name = "yeji"
last_name = "hwang"
full_name = f"{first_name} {last_name}"
print(full_name.lower())
print(full_name.upper())
print(full_name.title())
```
{% endraw %}

14_famous_quote.py
{% raw %}
```python
# Save each of the following exercises as a separate file with a name like name_cases.py. If you get stuck,
# take a break or see the suggestions in Appendix C.

# 2-5. Famous Quote. Find a quote from a famous person you admire. Print the quote and the name of the author.
# Your output should look something like the following, including the quotation marks:

# Albert Einstein once said, "A person who never made a mistake never tried anything new."

author = "yeji hwang"
quote = "Addictive + Attractive = Addractive."

message = f'{author.title()} once said, "{quote}"'
print(message)
```
{% endraw %}

15_famous_quote_2.py
{% raw %}
```python
# Save each of the following exercises as a separate file with a name like name_cases.py. If you get stuck,
# take a break or see the suggestions in Appendix C.

author = "so mi song"
quote = (
    "For Myers, the NUSA... I'm just another weapon in their arsenal. A tool for reachin' beyond the "
    "Blackwall. And weapons and tools? They don't get to make decisions or choose to retire."
)

message = f'{author.title()} once said, "{quote}"'
print(message)
```
{% endraw %}

16_stripping_names.py
{% raw %}
```python
# Save each of the following exercises as a separate file with a name like name_cases.py. If you get stuck,
# take a break or see the suggestions in Appendix C.

# 2-7. Stripping Names. Use a variable to represent a person's name, and include some whitespace characters
# at the beginning and end of the name. Make sure you use each character combination, "\t" and "\n", at least
# once.

# Print the name once, so the whitespace around the name is displayed. Then print the name using each of the
# three stripping functions, lstrip(), rstrip(), and strip().

name = "\tyeji hwang\n"
print('The variable "name" is assigned as, "\\tyeji hwang\\n."')
print("Using the print() method:")
print(name)
print("Using the lstrip() method:")
print(name.lstrip())
print("Using the rstrip() method:")
print(name.rstrip())
print("Using the strip() method:")
print(name.strip())
```
{% endraw %}

17_integers.py
{% raw %}
```python
# Numbers

# Numbers are used quite often in programming to keep score in games, represents data in visualizations,
# store information in web applications, and so on. Python treats numbers in several different ways,
# depending on how they're being used. Let's first look at how Python manages integers, because they're
# the simplest to work with.

# Integers

# You can add (+), subtract (-), multiply (*), and divide (/) integers in Python.
# >>> 2 + 3
# 5
# >>> 3 -1
# 1
# >>> 2 * 3
# 6
# >>> 3 / 2
# 1.5

# In a terminal session, Python simply returns the result of the operation. Python uses two multiplication
# symbols to represent exponents:

# >>> 3 ** 2
# 9
# >>> 3 ** 3
# 27
# >>> 10 ** 6
# 1000000

# Python supports the order of operations too, so you can use multiple operations in one expression. You can
# also use parentheses to modify the order of operations so Python can evaluate your expression in the order
# you specify. For example:

# >>> 2 + 3*4
# 14
# >>> (2 + 3) * 4
# 20

# The spacing in these examples has no effect on how Python evaluates the expressions; it simply helps you
# more quickly spot the operations that have priority when you're reading through the code.

print("The program contains notes in the comments.")
```
{% endraw %}

18_floats.py
{% raw %}
```python
# Floats

# Python calls any number with a decimal point a float. This term is used in most programming
# languages, and it refers to the fact that a decimal point can appear at any position in a
# number. Every programming language must be carefully designed to properly manage decimal
# numbers so numbers behave appropriately no matter where the decimal point appears.

# For the most part, you can use decimals without worrying about how they behave. Simply enter
# the numbers you want to use, and Python will most likely do what you expect:
# >>> 0.1 + 0.1
# 0.2
# >>> 0.2 + 0.2
# 0.4
# >>> 2 * 0.1
# 0.2
# >>> 2 * 0.2
# 0.4

# But be aware that you can sometimes get an artitrary number of decimal places in your answer:
# >>> 0.2 + 0.1
# 0.30000000000000000004
# >>> 3 * 0.1
# 0.30000000000000000004

# This happens in all languages and is of little concern. Python tries to find a way to represent
# the result as precisely as possible, which is sometimes difficult given how computers have to
# represent numbers internally. Just ignore the extra decimal places for now; you'll learn ways to
# deal with the extra places when you need to in the projects in Part II.
print("This program contains notes in the comments.")
```
{% endraw %}

19_integers_and_floats.py
{% raw %}
```python
# Intergers and Floats

# When you divide any two numbers, even if they are integers that result in a whole number, you'll
# always get a float:

# >>> 4/2
# 2.0

# If you mix an integer and a float in any other operation, you'll get a float as well:

# >> 1 + 2.0
# 3.0
# >>> 2 * 3.0
# 6.0
# >>> 3.0 ** 2
# 9.0

# Python defaults to a float in any operation that uses a float, even if the output is a whole number.
print("This program has notes in the comments.")
```
{% endraw %}

20_underscores_in_numbers.py
{% raw %}
```python
# Underscores in Numbers

# When you're writing long numbers, you can group digits using underscores to make large numbers more
# readable:

# >>> universe_age = 14_000_000_000

# When you print a number that was defined using underscores, Python prints only the digits:
# >>> print(universe_age)
# 14000000000

# Python ignores the underscores when storing these kinds of values. Even if you don't group the digits
# in threes, the value will still be unaffected. To Python, 1000 is the same as 1_000, which is the same
# as 10_00. This feature works for integers and floats, but it's only available in Python 3.6 and later.
print("This program contains notes in the comments.")
```
{% endraw %}

21_multiple_assignments.py
{% raw %}
```python
# Multiple Assignment

# You can assign values to more than one variable using just a single line. This can help shorten your
# programs and make them easier to read; you'll use this technique most often when initializing a set
# of numbers.

# For example, here's how you can initialize the variables x, y, and z to zero:

# >>> x, y, z = 0, 0, 0

# You need to separate the variable names with commas, and do the same with the values, and Python will
# assign each value to its respectively positioned variable. As long as the number of values matches the
# number of variables, Python will match them up correctly.
print("This program contains notes in the comments.")
```
{% endraw %}

22_constants.py
{% raw %}
```python
# Constants

# A constant is like a variable whose value stays the same throughout the life of a program. Python
# doesn't have built-in constant types, but Python programmers use all capital letters to indicate a
# variable should be treated as a constant and never be changed:

# MAX_CONNECTIONS = 5000

# When you treat a variable as a constant in your code, make the name of the variable all capital
# letters.
print("This program contains notes in the comments.")
```
{% endraw %}

23_number_eight.py
{% raw %}
```python
# 2-8. Number Eight: Write addition, subtraction, multiplication, and division operations that each
# result in the number 8. Be sure to enclose your operations in print() calls to see the results. You
# should create four lines that look like this:

# print(5+3)

# Your output should simply be four lines with the number 8 appearing once on each line.
print(1+7)
print(9-1)
print(4*2)
print(int(16/2))
```
{% endraw %}

24_favorite_number.py
{% raw %}
```python
# 2-9. Favorite Number: Use a variable to represent your favorite number. Then, using that variable,
# create a message that reveals your favorite number. Print that message.

favorite_number = 7
message = f"My favorite number is {favorite_number}."
print(message)
```
{% endraw %}

25_comments.py
{% raw %}
```python
# Comments

# Comments are an extremely useful feature in most programming languages. Everything you've written
# in your programs so far is Python code. As your programs become longer and more complicated, you
# should add notes within your programs that describe your overall approach to the problem you're
# solving. A comment allows you to write notes in English within your programs.

# How Do You Write Comments?

# In Python, the hash mark (#) indicates a comment. Anything following a hash mark in your code is
# ignored by the Python interpreter. For example:

# Say hello to everyone.
# print("Hello Python people!")

# Python ignores the first line and executes the second line.
# Hello Python people!

# What Kind of Comments Should You Write?

# The main reason to write comments is to explain what your code is supposed to do and how you are making
# it work. When you're in the middle of working on a project, you understand how all of the pieces fit
# togeter. But when you return to a project after some time away, you'll likely have forgotten some of the
# details. You can always study your code for a while and figure out how segments were supposed to work, but
# writing good comments can save you time by summarizing your overall approach in clear English.

# If you want to become a professional programmer or collaborate with other programmers, you should write
# meaningful comments. Today, most software is written collaboratively, wheter by a group of employees at one
# company or a group of people working together on an open source project. Skilled programmers expect to see
# comments in code, so it's best to start adding descriptive comments to your programms now. Writing clear,
# concise comments in your code is one of the most beneficial habits you can form as a new programmer.

# When you're determining wheter to write a comment, ask yourself if you had to consider several approaches
# before coming up with a reasonable way to make something work; if so, write a comment about your solution
# and write comments for a sparsely commented program. From now on, I'll use comments in examples throughout
# this book to explain sections of code.

print("This program contains notes in the comments.")
```
{% endraw %}

26_adding_comments.py
{% raw %}
```python
# 2-10. Adding Comments: Choose two of the programs you've written, and add at least one comment to each.
# If you don't have anything specific to write because your programs are too simple at this point, just add
# your name and the current date at the top of each program file. Then write one sentence describing wht the
# program does.

# kpopnetrunner - 01/26/2026

# This program is meant for me to practice with writing comments.
print("There are notes in the comments.")
```
{% endraw %}

27_the_zen_of_python.py
{% raw %}
```python
# The Zen of Python

# Experienced Python programmers will encourage you to avoid complexity and aim for simplicity whenever
# possible. The Python community's philosophy is contained in "The Zen of Python" by Tim Peters. You can
# access this brief set of principles for writing good Python code by entering import this into your
# interpreter. I won't reproduce the entire "Zen of Python" here, but I'll share a few lines to help you
# understand why they should be important to you as a beginning Python programmer.

# >>> import this
# The Zen of Python, by Tim Peters
# Beautiful is better than ugly.

# Pythojn programmers embrace the ntion that code can be beautiful and elegant. In programming, people
# solve problems. Programmers have always respected well-designed, efficient, and event beautiful solutions
# to problems. As you learn more about Python and use it to write more code, someone might look over your
# shoulder one day and say, "Wo, that's some beautiful code!"

# Simple is better than complex.

# If you have a choice between a simple and a complex solution, and both work, use the simple solution.
# Your code will be easier to maintain, and it will be easier for you and others to build on that code later
# on.

# Complex is better than complicated.

# Real life is messy, and sometimes a simple solution to a problem is unattainable. In that case, use the simplest
# solution that works.

# Readablility counts.

# Even when your code is complex, aim to make it readable. When you're working on a project that involves complex
# coding, focus on writing informative comments for that code.

# There should be one-- and perferably only one --obvious way to do it.

# If two Python programmers were asked to solve the same problem, they should come up with fairly compatible solutions.
# This is not to say there's no room for creativity in programming. On the contrary! But much of programming consists
# of using small, common approaches to simple situtations within a larger, more creative project. The nuts and bolts
# of your programs should make sense to other Python programmers.

# Now is better than never.

# You could spend the rest of your life learning all the intricacies of Python and of programming in general, but then
# you''d never complete any projects. Don't try to write perfect code; write code that works, and then decide wheter to
# improve your code for that project or move on to something new.

# As you continue to the next chapter and start digging into more topics, try to keep this philosophy of simplicity and
# clarity in mind. Experienced programmers will respect your code more and will be happy to give you feedback and
# collaborate with you on interesting projects.

print("This program contains notes in the comments.")
```
{% endraw %}
