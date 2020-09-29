+++
title = "Python for beginners"
weight = 4
+++


Welcome to our Python Tutorial. We’ll cover the basics here and link to more in depth resources along the way. We hope you enjoy the tutorial and walk away with a better understanding of the Python programming language. Let’s get started with our introduction to Python for beginners!

1.  [Download and Install Python](https://www.pythonforbeginners.com/python-tutorial#1)
2.  [Variables](https://www.pythonforbeginners.com/python-tutorial#2)
3.  [Functions](https://www.pythonforbeginners.com/python-tutorial#3)
4.  [Comments](https://www.pythonforbeginners.com/python-tutorial#4)
5.  [Docstrings](https://www.pythonforbeginners.com/python-tutorial#5)
6.  [Escape Characters](https://www.pythonforbeginners.com/python-tutorial#6)
7.  [Numbers](https://www.pythonforbeginners.com/python-tutorial#7)
8.  [Keywords](https://www.pythonforbeginners.com/python-tutorial#8)
9.  [Strings](https://www.pythonforbeginners.com/python-tutorial#9)
10.  [Style Rules](https://www.pythonforbeginners.com/python-tutorial#10)
11.  [Booleans](https://www.pythonforbeginners.com/python-tutorial#11)
12.  [Loops](https://www.pythonforbeginners.com/python-tutorial#12)
13.  [Lists](https://www.pythonforbeginners.com/python-tutorial#13)
14.  [Operators](https://www.pythonforbeginners.com/python-tutorial#14)
15.  [Conditional Statements](https://www.pythonforbeginners.com/python-tutorial#15)
16.  [Exception Handling](https://www.pythonforbeginners.com/python-tutorial#16)
17.  [Dictionaries](https://www.pythonforbeginners.com/python-tutorial#17)
18.  [Modules](https://www.pythonforbeginners.com/python-tutorial#18)
19.  [Taking Input From The User](https://www.pythonforbeginners.com/python-tutorial#19)

## Download and Install Python

Python is a interpreted language which means that the code is translated (interpreted) to binary code while the program runs. That is different from compiled languages (C++ etc.) where the code is first compiled to binary code.

To run Python code you need to have a Python interpreter. There are different versions of Python, either Python 2 or Python 3. To see that the difference are and to decide which one to use, please see  [this](https://wiki.python.org/moin/Python2orPython3 "moin")  wiki page at python.org.

### Installing Python

Python is available on most operating system, (Linux, Unix, Mac OS X and Windows).

Installing it on your computer is very easy, and on some systems it’s already there.

To see if it’s already installed, open up a terminal and run this command below.

If you see a response from a Python interpreter it will include a version number in its initialdisplay.

```python
>> python
Python 2.7.2 (default, Jun 20 2012, 16:23:33)

```

If you don’t have Python installed, you can take a look at this link on how to install it on the platform that you use.  
[http://www.diveintopython.net/installing_python/index.html](http://www.diveintopython.net/installing_python/index.html "DiveIntoPython")

#### How do I run my code?

There are two ways to run the programs in Python. Either you type in the code directly in  
the Python shell. When doing that you will see the result of every command that you type  
in. This works best for very short programs or for testing purpose. The other way to run  
the code is within a script.

Additional Resources

[Recommended Course: Intro to Python](https://www.datacamp.com/courses/intro-to-python-for-data-science?tap_a=5644-dce66f&tap_s=75426-9cf8ad&tm_source=ic_recommended_course)

#### Python Shell

When you are in the Python Shell, the python interpreter will translate all code for you.

To leave the help mode and return to the interpreter, we use the quit command.

**The help command provides some help about Python.**

```python
>>> help
Type help() for interactive help, or help(object) for help about object.
>>>

```

You can also use the Python Shell for doing math  
(please see my  [earlier post](https://www.pythonforbeginners.com/basics/using-math-in-python "using_math")  about using math in Python)

```python
>>> 2 + 4
6
>>> 5 * 56
280
>>> 5 - 45
-40
>>> 

```

To exit the Python Shell, press Ctrl+d.

#### Python Script

To run the program as script, open an text editor (vi, pico, nano etc.) and put in the  
following code:

```python
#!/usr/bin/python  
print "hello world"

```

Save the file as hello.py and exit the editor.

```python
# To execute the program, type python and the file name in the shell. 
$python hello.py

The output should be:
hello world
 
```

Python scripts can be made directly executable, like shell scripts, by putting the shebang  
at the beginning of the script and give the file an executable mode. The shebang is meant  
for the script to recognize the interpretor type when you want to execute the script from  
the shell.

```python
# The script can be given an executable mode, or permission, using the chmod command:
$ chmod +x hello.py


```

Now you can execute the script directly by its name.

Learn More About Installing Python

## Variables

In Python, variables are a storage placeholder for texts and numbers.

It must have a name so that you are able to find it again.

The variable is always assigned with the equal sign, followed by the value of the  
variable.

Python is dynamically typed, which means that you don’t have to declare what  
type each variable is.

The variables are being referred in the program to get the value of it.

The value of the variable can be changed later on.

Store the value 10 in a variable named foo  
foo = 10

Store the value of foo+10 in a variable named bar  
bar = foo + 10

```python
#List of some different variable types:
x = 123      # integer
x = 123L     # long integer
x = 3.14      # double float
x = "hello"       # string
x = [0,1,2]       # list
x = (0,1,2)       # tuple
x = open(‘hello.py’, ‘r’)  # file

#You can also assign a single value to several variables simultaneously.
# variable a,b and c are assigned to the same memory location,with the value of 1
a = b = c = 1  

```

### Get Area using Python Variables

```python
length = 1.10
width  = 2.20
area   = length * width
print "The area is: " , area
```

This will print out:

```python
The area is:  2.42
```

Learn More About Variables

## Functions

A function is something you can call (possibly with some parameters, the things you put in the parentheses), which performs an action and returns a value.

Functions are useful because:

-   Reuse code
-   Easy to debug
-   Smaller unit of code(relatively speaking)

### Function syntax

A function must be defined before it is called. To define a function, use the following syntax:

```python
def myFunction():
```

The above function has no parameters, meaning no values are being passed into the function. To name parameters, use the following syntax.

```python
def myFunction(name,age):
```

Now we have a function call that passes in a few parameters. We’ll move onto the body of the function and use those parameters.

```python
def myFunction(name,age):
   print 'Name: ' + name
   print 'Age: ' + age
```

With our function body, the code MUST be indented. The method, when called, would print the name and age passed into it.

Instead of printing a value, a function can return that value to the program.

```python
def myFunction(name,age):
   return 'My name is ' + name + ' and I am ' + age + ' years old'
```

```python
>>> myFunction('John','44'):
'My name is John and I am 44 years old'
```

Return is the common conclusion of a function as the calling program will typical store its contents into a variable or act on the return value in a conditional statement.

Learn More About Functions

## Comments

Comments in Python are used to explain what the code does.

They are meant as documentation for anyone reading the code.

Python is automatically ignoring all text that comes after the “#”

Comments can be in the beginning of the line or at the end of one.

Multiline comments are possible and are enclosed by triple quotes.

```python
# First comment
print "Hello, Python!";  # second comment
#this is a comment in Python
 
""" This is an example of a multiline
comment that spans multiple lines
...
"""

```

Learn More About Comments

## Docstrings

Python documentation strings (or docstrings) provide a convenient way of  
associating documentation with Python modules, functions, classes, and methods.

An object’s docsting is defined by including a string constant as the first  
statement in the object’s definition.

It’s specified in source code that is used, like a comment, to document a  
specific segment of code.

Unlike conventional source code comments the docstring should describe what the  
function does, not how.

All functions should have a docstring

This allows the program to inspect these comments at run time, for instance as an interactive help system, or as metadata.

Docstrings can be accessed by the  **doc**  attribute on objects.

### How should a Docstring look like?

The doc string line should begin with a capital letter and end with a period.

The first line should be a short description.

Don’t write the name of the object.

If there are more lines in the documentation string, the second line should be  
blank, visually separating the summary from the rest of the description.

The following lines should be one or more paragraphs describing the object’s  
calling conventions, its side effects, etc.

### Docstring Example

Here is an example of a multi-line docstring:

```python
def my_function():
...     """Do nothing, but document it.
...
...     No, really, it doesn't do anything.
...     """
...     pass
...

```

Now that we have created our Docstring in the my_function() method, let’s see how it can be useful. Let’s say I’m a new developer in a project and I want to know what my_function() does. See below using the print function.

```python
>>> print my_function.__doc__
Do nothing, but document it.

    No, really, it doesn't do anything.

```

### Multiple Docstrings In One Source File

The following Python file shows the declaration of docstrings within a python  
source file. You can clearly see the different levels of docstrings and how they can be used within a single source file.

```python
"""
Assuming this is file mymodule.py, then this string, being the
first statement in the file, will become the "mymodule" module's
docstring when the file is imported.
"""
 
class MyClass(object):
    """The class's docstring"""
 
    def my_method(self):
        """The method's docstring"""
 
def my_function():
    """The function's docstring"""


```

### How to access the Docstring

Below we show you two methods you can use to access the docstring.

```python
>>> import mymodule
>>> help(mymodule)

Assuming this is file mymodule.py then this string, being the
first statement in the file will become the mymodule modules
docstring when the file is imported

```

```python

>>> help(mymodule.MyClass)
The class's docstring

>>> help(mymodule.MyClass.my_method)
The method's docstring

>>> help(mymodule.my_function)
The function's docstring

```

### Docstrings vs Comments

Docstrings and comments are similar in nature, but serve a different purpose. Comments are great for describing lines of code and why they are there. This is very helpful in large code sets.

Docstrings document what a class, module or package does and most importantly, is available to the help function, whereas, comments are not.

Docstrings, therefore, can help to document the code programmatically.

Learn More About Docstring

## Escape Characters

Escape characters allow you to do things you normally wouldn’t be able to do following the normal Python syntax rules.

For example, you want to print this line in your code with double quotes around the title of the movie, “Titanic”.

```python
>>> print "Cory's favorite movie is "Titanic""
SyntaxError: invalid syntax
```

The compiler doesn’t allow you to use double quotes inside double quotes, so you have to “escape” the double quotes from the compiler and allow them to be treated as a string.

To do this, you simply add a backslash(\) before the character you want to escape.

```python
>>> print "Cory's favorite movie is \"Titanic\""
Cory's favorite movie is "Titanic"
```

Below is a table of other common escape characters.

| Escape Character | Result       |
|:------------------:|:--------------|
| \’               | Single Quote |
| \\               | Backslash    |
| \b               | Backspace    |
| \f               | Line Feed    |
| \n               | New Line     |
| \r               | Line Feed    |
| \t               | Tab          |
| \v               | Vertical Tab |

## Numbers

Python supports 4 types of Numbers, the int, the long, the float and the complex.

You don’t have to specify what type of variable you want. Python does that  
automatically.

| Int     | This is the basic integer type in python.              |
|:---------|:--------------------------------------------------------|
| Long    | This is a integer number that’s length is non-limited. |
| Float   | This is a binary floating point number.                |
| Complex | This is a complex number consisting of two floats.     |

### Converting Numbers

You can simply convert them, like this:

```python
>>> float(3)
3.0
>>> int(4.123)
4
```

### Using Python interpreter as a calculator

You can use the interpreter to do math with numbers.

```python

>>> 2 + 2
4

>>> 4 * 2
8

>>> 10 / 2
5

>>> 10 - 2
8

```

## Keywords

Keywords in Python are reserved words that cannot be used as ordinary identifiers. They must be spelled exactly as they are written.

### List of keywords

The following is a list of keywords for the Python programming language.

| and     | del    | from   | not      |
|:---------:|:--------:|:--------:|:----------:|
| while   | as     | elif   | global   |
| or      | with   | assert | else     |
| if      | pass   | yield  | break    |
| except  | import | print  | class    |
| exec    | in     | raise  | continue |
| finally | is     | return | def      |
| for     | lambda | try    | nan      |

## Strings

A string is a list of characters in order. A character is anything you can type on the keyboard in one keystroke, like a letter, a number, or a backslash.

Additional Resources

[Recommended Course: Intro to Python](https://www.datacamp.com/courses/intro-to-python-for-data-science?tap_a=5644-dce66f&tap_s=75426-9cf8ad&tm_source=ic_recommended_course)

Strings can have spaces: “hello world”.
An empty string is a string that has 0 characters.
Python strings are immutable, which means they can’t change.
String syntax is recognized by anything between ” ” or ‘ ‘.
Much like Lists, Strings have functions that can work on their value.

### String Functions

**Changing Case**
```py
string.lower() # lower case the string
string.upper() # upper case the string
string.title() # upper case the first letters
```
**Replace**

string.replace(“This”,”That”) # will replace the text “This” with “That”

**Split**

Split will split a string into an array based on the delimiter passed into the function.

```python
x = '1,2,3'
x.split(",")
['1','2','3']
```

There are many more string functions available. See our Learn More About Strings section.

### String Concatenation

In Python there are a few different ways to concatenating strings. Concatenation combines two (or more) strings into a new string object.

**You can use the + operator, like this:**

```python
print "You can concatenate two " + "strings with the '+' operator."

```

```python 
str1 = "Hello"
str2 = "World"
str1 + str2    	# concatenation: a new string
# String literals may be concatenated by a space
word = 'left' "right" 'left'
# Any string expression may be concatenated by a +
word = wordA + "
" + wordB
```

Learn More About Strings

## Style Rules

A style guide is about consistency. Consistency with this style guide is important. Consistency within a project is more important. Consistency within one module or function is most important.

An example of this would be:

#### Semicolons

Do not terminate your lines with semi-colons and do not use semi-colons to put  
two commands on the same line.

#### Line length

Maximum line length is 80 characters.

#### Parentheses

Use parentheses sparingly.

#### Indentation

Indent your code blocks with 4 spaces.

Learn More About Style Rules

## Booleans

The built-in type Boolean can hold only one of two possible objects: True or False

#### Boolean Values

Boolean values respond to logical operators and / or. The examples below show how multiple boolean values act together with differing operators.

```python
>>> True and False
False

>>> True and True
True

>>> False and True
False

>>> False or True
True

>>> False or False
False
```

Learn More About Booleans

## Loops

Programming languages need a way to repeat the same sequence, this is called Iteration. Loops in programming allow us to iterate over elements in severals ways.

### For Loops

For loops allows us to iterate over elements of a sequence, it is often used when you have a piece of code which you want to repeat “n” number of time.

It works like this:

Let’s say that you have a list of browsers like below. That reads, for every element that we assign the variable browser, in the list browsers, print out the variable browser

```python
>>> browsers = ["Safari","Firefox","Chrome"]
>>> for browser in browsers:
...     print browser
... 
Safari
Firefox
Chrome
```

### While Loops

The while loop tells the computer to do something as long as the condition is met It’s construct consists of a block of code and a condition.

The loop will continue WHILE the condition met is true. Once it is false, the loop will exit.

```python
browsers = ["Safari", "Firefox", "Google Chrome", "Opera", "IE"]
i = 0
while i < len(browsers):
    print browsers[i]
    #add 1 to i each iteration so that we exit once we reach the total number of browsers
    i = i + 1
```

### Eternal Loops

You typically want to avoid Eternal loops as they will never end until all system resources are consumed or the program is killed externally.

An example of an eternal loop.

```python
while True:
    print "Hello World"
```

Typically eternal loops aren't this obvious and usually involves inadvertently updating a variable that is being used as a counter.

### Continue

The continue statement is used to tell Python to skip the rest of the statements in the current loop block and to continue to the next iteration of the loop.

This is typically used when a certain condition is met that makes it unnecessary to execute the remaining block.

```python
for i in range(1,10):
    if i == 3:
        # don't print 3's, I hate 3's, but keeping printing
        continue
    print i
```

### Break

Break statements allow you to exit the loop if a condition is met. This is different from the Continue statement where the loop will continue.

```python
for i in range(1,10):
    if i == 3:
        # 3's are so bad that I can't continue this loop any longer
        break
    print i
```

### Pass

The pass statement does nothing. It can be used when a statement is required syntactically but the program requires no action.

```python
>>> while True:
    ...       pass # Busy-wait for keyboard interrupt
    ... 
```

Learn More About Loops

## Lists

Lists in Python are a collection of items, such as Strings, Integers or other Lists.
Lists are enclosed in [ ] with each item separated by commas.
Lists, unlike Strings are mutable, which means they can be changed.

### List Examples

```python
emptyList = []
bourbonList = ['jeffersons','woodford reserve','maker's mark']
numList = [1,2,3,4]
```

### List Functions

While you can use other function against a list, like len to get the length of a list

```python
len(bourbonList)
>>> 3
```

Lists has its own set of methods.

Append will add an element to the end of a list.

```python
bourbonList.append("Jack Daniels")
```

```python
print bourbonList
>>> ['jeffersons','woodford reserve','maker's mark','Jack Daniels']
```

Here are more List functions and their purpose

| Function |Description |
|:----------:|:----------|
| Insert(x,y) |Inserts an item(x) into an array after (y) |
| Remove(x) |Removes (x) on a match |
| Extend(list) |Adds another list to the calling list |
| Delete(1) |Deletes an item based on the index passed in |

## Operators

### Comparison operators

| Operator |Description |Example |
|:----------:|:----------|:----------:|
| < |less than |x < 10 |
| <= |less than or equal to |x <= 10 |
| > |greater than |x > 10 |
| >= |greater than or equal to |x >= 10 |
| == |equality |x == 10 |
| != |inequality (also <>) |x != 10 |

#### Logical operators

| Operator |Description |Example |
|:----------:|:----------|:----------|
| not |logical notation |not b |
| and |logical and |(x <= 10) and (y == True) |
| or |logical or |(x < 10) or (y > 100.1) |

## Conditional Statements

In programming, very often we want to check the conditions and change the behavior of the program. We can write programs that has more than one choice of actions depending on a  
variable's value.

Perhaps the most well-known statement type is the if statement.

You use the if statement to perform one action if one thing is true, or any number of other actions, if something else is true.

We must use indentation to define that code that is executed, based on whether acondition is met.

To compare data in Python we can use the comparison operators, find in this post

### If Statement

```python

The syntax of the if statement is:

if expression:
   statement(s)

```

#### Elif Statement

Sometimes there are more than two possibilities, in that case we can use the elif statement

It stands for "else if," which means that if the original if statement is false  
and the elif statement is true, execute the block of code following the elif statement.

The syntax of the if…elif statement is:

```python
if expression1:
   statement(s)
elif expression2:
   statement(s)
elif expression3:
   statement(s)
else:
   statement(s)

```

#### Else Statement

An else statement can be combined with an if statement.

An else statement contains the block of code that executes if the conditional  
expression in the if statement resolves to 0 or a false value.

The else statement is an optional statement and there could be at most only one  
else statement following if.

The syntax of if..else is:

```python
if expression:
   statement(s)
else:
   statement(s)

```

#### Examples

This script will compare two strings based on the input from the user.

```python
# This program compares two strings.
# Get a password from the user.
password = raw_input('Enter the password: ')
# Determine whether the correct password
# was entered.
if password == 'hello':
    print'Password Accepted'
else:
    print'Sorry, that is the wrong password.'

```

#### Another Example

Let's show one more example that makes use of the elif statement.

```python
#!/usr/bin/python
number = 20
guess = int(input('Enter an integer : '))
if guess == number:
    print('Congratulations, you guessed it.')
elif guess < number:
    print('No, it is a little higher than that')
else:
    print('No, it is a little lower than that')

```

Learn More About Conditional Statements

## Exception Handling

When an error occurs in a Python program, Python generates an Exception. Why? So that it can be handled gracefully without breaking the program or causing issues with user interaction.

### Exception Examples

**IOError**  
If the file cannot be opened.

**ImportError**  
If python cannot find the module

**ValueError**  
Raised when a built-in operation or function receives an argument that has the  
right type but an inappropriate value

**KeyboardInterrupt**  
Raised when the user hits the interrupt key (normally Control-C or Delete)

**EOFError**  
Raised when one of the built-in functions (input() or raw_input()) hits an  
end-of-file condition (EOF) without reading any data

### Handling Exceptions

To handle exceptions you need to use the catch-all except clause. This involves using the "try" and "except" Python keywords.

Simply put, you wrap the executing code in a "try" block and if any exception occurs, you catch it and handle it accordingly.

An example in pseudo code:
```py
try:
some statements here

except:
exception handling
```
Let's see a short example on how to do this:
```py
try:
print 1/0

except ZeroDivisionError:
print "You can't divide by zero, you're silly."
```


## Dictionaries

Dictionary is another data type in Python.

Dictionaries are collections of items that have a “key” and a “value”.

Python dictionaries are also known as associative arrays or hash tables.

They are just like lists, except instead of having an assigned index number,  
you make up the index.

### Create a Dictionary

```python
# This is a list
myList = ["first","second","third"]

# This is a dictionary
myDictionary = {0:"first",1:"second",2:"third"} 

```

## Accessing / Getting values

To access dictionary elements, you can use the square brackets along with the key  
to obtain its value.

```python
data = {'Name':'Zara','Age':7,'Class':'First'};

# Get all keys
data.keys()

# Get all values
data.values()

# Print key1
print data['Name']

# Prints 7
print data['Age']

# Prints name and age
print 'Name', data['Name'];
print 'Age', data['Age'];

```

### Looping through a Dictionary

You can use a for loop to iterate Dictionary items.

```python
data = {
        'key1': 'value1',
        'key2': 'value2',
        'key3': 'value3'
        }

for key, value in data.items():
    print key,value

Looping their values directory (not in order)
for value in data.values():
    print value

```

There are many more operations you can perform on a Dictionary, like add, clear, delete, list all keys, list all values, test if a key exists, etc. You can learn more about these features by reviewing the articles in Learn More About Dictionaries.

Learn More About Dictionaries

## Modules

Python modules makes the programming a lot easier. It’s basically a file that consist of already written code. When Python imports a module, it first checks the module registry (sys.modules) to see if the module is already imported. If that’s the case, Python uses the existing module object as is. There are different ways to import a module.

### Importing Modules

```py
import sys    		
#access module, after this you can use sys.name to refer to things defined in module sys.

from sys import stdout  
# access module without qualiying name. 
This reads from the module "sys" import "stdout", so that we would be able to 
refer "stdout"in our program.

from sys import *       
# access all functions/classes in the sys module. 

```

### Python Standard Library

URL:  [http://docs.python.org/library/index.html](https://docs.python.org/library/index.html "library")  Collection of of modules that are already on the system, there is no need to install them. Just import the modules you want to use. Search for a module: http://docs.python.org/py-modindex.html

### Python Package Index

URL:  [http://pypi.python.org/pypi](https://pypi.python.org/pypi "pypi")  Created by community members. It's a repository of software containing more than 2400 packages

### Math Module

The math module provides access to mathematical constants and functions.

```python
 
import math
math.pi      #Pi, 3.14...
math.e        #Euler's number, 2.71...
math.degrees(2)    #2 radians = 114.59 degreees
math.radians(60)  #60 degrees = 1.04 radians
math.sin(2)       #Sine of 2 radians
math.cos(0.5)     #Cosine of 0.5 radians
math.tan(0.23)    #Tangent of 0.23 radians
math.factorial(5) #1 * 2 * 3 * 4 * 5 = 120
math.sqrt(49)     #Square root of 49 = 7

```

### Requests Module

The Requests module is a an elegant and simple HTTP library for Python that allows you to send HTTP/1.1 requests.

To install requests, simply:  
$ pip install requests

Or, if you absolutely must:  
$ easy_install requests

To create a Request object, simply call a URL using the following syntax.

```python
>>> r = requests.get('https://github.com/timeline.json')
```

To operate on the object, you have many choices. Here is one example to check the http status code.

```python
>>> r = requests.get('https://github.com/timeline.json')
>>> r.status_code
200
```

Learn More About Modules

Additional Resources

[Recommended Course: Intro to Python](https://www.datacamp.com/courses/intro-to-python-for-data-science?tap_a=5644-dce66f&tap_s=75426-9cf8ad&tm_source=ic_recommended_course)

## Taking User Input

There are two functions in Python that you can use to read data from the user:

raw_input and input

You can store the results from them into a variable.

raw_input is used to read text (strings) from the user:

```python
#Ask the user to input a name, and store it in the variable name
name = raw_input("What is your name? ")
type(name)

#Create a new string with a greeting
greet = 'hello ' + name

```

input is used to read integers

```python
age = input("What is your age? ")
print "Your age is: ", age
type(age)

#Ask the user to input a number, and store it in the variable foo
foo = int(raw input('enter a number: '))

```

Learn More About Taking User Input

##### Sources

[http://www.python.org/](https://www.python.org/)

[http://www.tutorialspoint.com/python/index.htm](https://www.tutorialspoint.com/python/index.htm)

[http://loris.som.jhmi.edu/python_course/basic_syntax.html](http://loris.som.jhmi.edu/python_course/basic_syntax.html)

> Reference : https://www.pythonforbeginners.com/python-tutorial