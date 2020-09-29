+++
title = "Exception Handling"
weight = 5
+++

In this tutorial you will learn to create, format, modify and delete strings in Python. Also, you will be introduced to various string operations and functions.

**Python Exception Handling Using try, except and finally statement**

In this tutorial, you'll learn how to handle exceptions in your Python program using try, except and finally statements with the help of examples.

## Exceptions in Python

Python has many  [built-in exceptions](https://www.programiz.com/python-programming/exceptions)  that are raised when your program encounters an error (something in the program goes wrong).

When these exceptions occur, the Python interpreter stops the current process and passes it to the calling process until it is handled. If not handled, the program will crash.

For example, let us consider a program where we have a  [function](https://www.programiz.com/python-programming/function)  `A`  that calls function  `B`, which in turn calls function  `C`. If an exception occurs in function  `C`  but is not handled in  `C`, the exception passes to  `B`  and then to  `A`.

If never handled, an error message is displayed and our program comes to a sudden unexpected halt.

----------

## Catching Exceptions in Python

In Python, exceptions can be handled using a  `try`  statement.

The critical operation which can raise an exception is placed inside the  `try`  clause. The code that handles the exceptions is written in the  `except`  clause.

We can thus choose what operations to perform once we have caught the exception. Here is a simple example.

```py
# import module sys to get the type of exception
import sys

randomList = ['a', 0, 2]

for entry in randomList:
    try:
        print("The entry is", entry)
        r = 1/int(entry)
        break
    except:
        print("Oops!", sys.exc_info()[0], "occurred.")
        print("Next entry.")
        print()
print("The reciprocal of", entry, "is", r)
```

**Output**

```text
The entry is a
Oops! <class 'ValueError'> occurred.
Next entry.

The entry is 0
Oops! <class 'ZeroDivisionError'> occured.
Next entry.

The entry is 2
The reciprocal of 2 is 0.5

In this program, we loop through the values of the  randomList  list. As previously mentioned, the portion that can cause an exception is placed inside the  `try`  block.

If no exception occurs, the  `except`  block is skipped and normal flow continues(for last value). But if any exception occurs, it is caught by the  `except`  block (first and second values).

Here, we print the name of the exception using the  `exc_info()`  function inside  `sys`  module. We can see that  `a`  causes  `ValueError`  and  `0`  causes  `ZeroDivisionError`.

Since every exception in Python inherits from the base  `Exception`  class, we can also perform the above task 
```

```py
# import module sys to get the type of exception
import sys

randomList = ['a', 0, 2]

for entry in randomList:
    try:
        print("The entry is", entry)
        r = 1/int(entry)
        break
    except Exception as e:
        print("Oops!", e.__class__, "occurred.")
        print("Next entry.")
        print()
print("The reciprocal of", entry, "is", r)
```

This program has the same output as the above program.

----------

## Catching Specific Exceptions in Python

In the above example, we did not mention any specific exception in the  `except`  clause.

This is not a good programming practice as it will catch all exceptions and handle every case in the same way. We can specify which exceptions an  `except`  clause should catch.

A  `try`  clause can have any number of  `except`  clauses to handle different exceptions, however, only one will be executed in case an exception occurs.

We can use a tuple of values to specify multiple exceptions in an except clause. Here is an example pseudo code.

```py
try:
   # do something
   pass

except ValueError:
   # handle ValueError exception
   pass

except (TypeError, ZeroDivisionError):
   # handle multiple exceptions
   # TypeError and ZeroDivisionError
   pass

except:
   # handle all other exceptions
   pass
```

----------

## Raising Exceptions in Python

In Python programming, exceptions are raised when errors occur at runtime. We can also manually raise exceptions using the  `raise`  keyword.

We can optionally pass values to the exception to clarify why that exception was raised.

```py
 raise KeyboardInterrupt
Traceback (most recent call last):
...
KeyboardInterrupt

 raise MemoryError("This is an argument")
Traceback (most recent call last):
...
MemoryError: This is an argument

 try:
...     a = int(input("Enter a positive integer: "))
...     if a <= 0:
...         raise ValueError("That is not a positive number!")
... except ValueError as ve:
...     print(ve)
...    
Enter a positive integer: -2
That is not a positive number!
```

----------

## Python try with else clause

In some situations, you might want to run a certain block of code if the code block inside  `try`  ran without any errors. For these cases, you can use the optional  `else`  keyword with the  `try`  statement.

**Note**: Exceptions in the else clause are not handled by the preceding except clauses.

Let's look at an example:

```py
# program to print the reciprocal of even numbers

try:
    num = int(input("Enter a number: "))
    assert num % 2 == 0
except:
    print("Not an even number!")
else:
    reciprocal = 1/num
    print(reciprocal)
```

**Output**

If we pass an odd number:
```py
Enter a number: 1
Not an even number!
```
If we pass an even number, the reciprocal is computed and displayed.
```py
Enter a number: 4
0.25
```
However, if we pass 0, we get  `ZeroDivisionError`  as the code block inside  `else`  is not handled by preceding  `except`.
```py
Enter a number: 0
Traceback (most recent call last):
  File "<string>", line 7, in <module>
    reciprocal = 1/num
ZeroDivisionError: division by zero
```
----------

## Python try...finally

The  `try`  statement in Python can have an optional  `finally`  clause. This clause is executed no matter what, and is generally used to release external resources.

For example, we may be connected to a remote data center through the network or working with a file or a Graphical User Interface (GUI).

In all these circumstances, we must clean up the resource before the program comes to a halt whether it successfully ran or not. These actions (closing a file, GUI or disconnecting from network) are performed in the  `finally`  clause to guarantee the execution.

Here is an example of  [file operations](https://www.programiz.com/python-programming/file-operation)  to illustrate this.

```py
try:
   f = open("test.txt",encoding = 'utf-8')
   # perform file operations
finally:
   f.close()
```

This type of construct makes sure that the file is closed even if an exception occurs during the program execution.


> Source :  https://www.programiz.com/python-programming/exception-handling


<!--          save                -->

## What is String in Python?

A string is a sequence of characters.

A character is simply a symbol. For example, the English language has 26 characters.

Computers do not deal with characters, they deal with numbers (binary). Even though you may see characters on your screen, internally it is stored and manipulated as a combination of 0s and 1s.

This conversion of character to a number is called encoding, and the reverse process is decoding. ASCII and Unicode are some of the popular encodings used.

In Python, a string is a sequence of Unicode characters. Unicode was introduced to include every character in all languages and bring uniformity in encoding. You can learn about Unicode from  [Python Unicode](http://docs.python.org/3.3/howto/unicode.html).

----------

## How to create a string in Python?

Strings can be created by enclosing characters inside a single quote or double-quotes. Even triple quotes can be used in Python but generally used to represent multiline strings and docstrings.

```py
# defining strings in Python
# all of the following are equivalent
my_string = 'Hello'
print(my_string)

my_string = "Hello"
print(my_string)

my_string = '''Hello'''
print(my_string)

# triple quotes string can extend multiple lines
my_string = """Hello, welcome to
           the world of Python"""
print(my_string)
```

When you run the program, the output will be:

```py
Hello
Hello
Hello
Hello, welcome to
           the world of Python
```

----------

## How to access characters in a string?

We can access individual characters using indexing and a range of characters using slicing. Index starts from 0. Trying to access a character out of index range will raise an  `IndexError`. The index must be an integer. We can't use floats or other types, this will result into  `TypeError`.

Python allows negative indexing for its sequences.

The index of  `-1`  refers to the last item,  `-2`  to the second last item and so on. We can access a range of items in a string by using the slicing operator  `:`(colon).

```py
#Accessing string characters in Python
str = 'programiz'
print('str = ', str)

#first character
print('str[0] = ', str[0])

#last character
print('str[-1] = ', str[-1])

#slicing 2nd to 5th character
print('str[1:5] = ', str[1:5])

#slicing 6th to 2nd last character
print('str[5:-2] = ', str[5:-2])
```

When we run the above program, we get the following output:
```py
str =  programiz
str[0] =  p
str[-1] =  z
str[1:5] =  rogr
str[5:-2] =  am
```
If we try to access an index out of the range or use numbers other than an integer, we will get errors.

```py
# index must be in range
my_string[15]  
...
IndexError: string index out of range

# index must be an integer
my_string[1.5] 
...
TypeError: string indices must be integers
```

Slicing can be best visualized by considering the index to be between the elements as shown below.

If we want to access a range, we need the index that will slice the portion from the string.

![Element Slicing in Python](https://cdn.programiz.com/sites/tutorial2program/files/element-slicling.jpg "Element Slicing")

String Slicing in Python

----------

## How to change or delete a string?

Strings are immutable. This means that elements of a string cannot be changed once they have been assigned. We can simply reassign different strings to the same name.
```py
my_string = 'programiz'
my_string[5] = 'a'
...
TypeError: 'str' object does not support item assignment
my_string = 'Python'
my_string
'Python'
```

We cannot delete or remove characters from a string. But deleting the string entirely is possible using the  `del`  keyword.

```py
del my_string[1]
...
TypeError: 'str' object doesn't support item deletion
del my_string
my_string
...
NameError: name 'my_string' is not defined
```

----------

## Python String Operations

There are many operations that can be performed with strings which makes it one of the most used data types in Python.

To learn more about the data types available in Python visit:  [Python Data Types](https://www.programiz.com/python-programming/variables-datatypes)

### Concatenation of Two or More Strings

Joining of two or more strings into a single one is called concatenation.

The  **+**  operator does this in Python. Simply writing two string literals together also concatenates them.

The  *****  operator can be used to repeat the string for a given number of times.

```py
# Python String Operations
str1 = 'Hello'
str2 ='World!'

# using +
print('str1 + str2 = ', str1 + str2)

# using *
print('str1 * 3 =', str1 * 3)
```

When we run the above program, we get the following output:

```py
str1 + str2 =  HelloWorld!
str1 * 3 = HelloHelloHello
```

Writing two string literals together also concatenates them like  **+**  operator.

If we want to concatenate strings in different lines, we can use parentheses.

```py
# two string literals together
'Hello ''World!'
'Hello World!'

# using parentheses
s = ('Hello '
...      'World')
s
'Hello World'
```

----------

### Iterating Through a string

We can iterate through a string using a  [for loop](https://www.programiz.com/python-programming/for-loop). Here is an example to count the number of 'l's in a string.

```py
# Iterating through a string
count = 0
for letter in 'Hello World':
    if(letter == 'l'):
        count += 1
print(count,'letters found')
```

When we run the above program, we get the following output:

```py
3 letters found
```
----------

### String Membership Test

We can test if a substring exists within a string or not, using the keyword  `in`.

```py
'a' in 'program'
True
'at' not in 'battle'
False
```

----------

### Built-in functions to Work with Python

Various built-in functions that work with sequence work with strings as well.

Some of the commonly used ones are  `enumerate()`  and  `len()`. The  `enumerate()`  function returns an enumerate object. It contains the index and value of all the items in the string as pairs. This can be useful for iteration.

Similarly,  `len()`  returns the length (number of characters) of the string.

```py
str = 'cold'

# enumerate()
list_enumerate = list(enumerate(str))
print('list(enumerate(str) = ', list_enumerate)

#character count
print('len(str) = ', len(str))
```

When we run the above program, we get the following output:

```
list(enumerate(str) =  [(0, 'c'), (1, 'o'), (2, 'l'), (3, 'd')]
len(str) =  4
```
----------

## Python String Formatting

### Escape Sequence

If we want to print a text like  He said, "What's there?", we can neither use single quotes nor double quotes. This will result in a  `SyntaxError`  as the text itself contains both single and double quotes.

```py
print("He said, "What's there?"")
...
SyntaxError: invalid syntax
print('He said, "What's there?"')
...
SyntaxError: invalid syntax
```

One way to get around this problem is to use triple quotes. Alternatively, we can use escape sequences.

An escape sequence starts with a backslash and is interpreted differently. If we use a single quote to represent a string, all the single quotes inside the string must be escaped. Similar is the case with double quotes. Here is how it can be done to represent the above text.

```py
# using triple quotes
print('''He said, "What's there?"''')

# escaping single quotes
print('He said, "What\'s there?"')

# escaping double quotes
print("He said, \"What's there?\"")
```

When we run the above program, we get the following output:
```py
He said, "What's there?"
He said, "What's there?"
He said, "What's there?"
```
Here is a list of all the escape sequences supported by Python.

| Escape Sequence |Description |
|:----------:|----------|
| \newline |Backslash and newline ignored |
| \\ |Backslash |
| \' |Single quote |
| \" |Double quote |
| \a |ASCII Bell |
| \b |ASCII Backspace |
| \f |ASCII Formfeed |
| \n |ASCII Linefeed |
| \r |ASCII Carriage Return |
| \t |ASCII Horizontal Tab |
| \v |ASCII Vertical Tab |
| \ooo |Character with octal value ooo |
| \xHH |Character with hexadecimal value HH |

Here are some examples

```py
print("C:\\Python32\\Lib")
# C:\Python32\Lib

print("This is printed\nin two lines")
#This is printed
# in two lines

print("This is \x48\x45\x58 representation")
# This is HEX representation
```

----------

### Raw String to ignore escape sequence

Sometimes we may wish to ignore the escape sequences inside a string. To do this we can place  `r`  or  `R`  in front of the string. This will imply that it is a raw string and any escape sequence inside it will be ignored.

```py
print("This is \x61 \ngood example")
This is a
good example
print(r"This is \x61 \ngood example")
This is \x61 \ngood example
```

----------

### The format() Method for Formatting Strings

The  `format()`  method that is available with the string object is very versatile and powerful in formatting strings. Format strings contain curly braces  `{}`  as placeholders or replacement fields which get replaced.

We can use positional arguments or keyword arguments to specify the order.

```py
# Python string format() method

# default(implicit) order
default_order = "{}, {} and {}".format('John','Bill','Sean')
print('\n--- Default Order ---')
print(default_order)

# order using positional argument
positional_order = "{1}, {0} and {2}".format('John','Bill','Sean')
print('\n--- Positional Order ---')
print(positional_order)

# order using keyword argument
keyword_order = "{s}, {b} and {j}".format(j='John',b='Bill',s='Sean')
print('\n--- Keyword Order ---')
print(keyword_order)
```

When we run the above program, we get the following output:
```py
--- Default Order ---
John, Bill and Sean

--- Positional Order ---
Bill, John and Sean

--- Keyword Order ---
Sean, Bill and John
```

The  `format()`  method can have optional format specifications. They are separated from the field name using colon. For example, we can left-justify  `<`, right-justify  `>`  or center  `^`  a string in the given space.

We can also format integers as binary, hexadecimal, etc. and floats can be rounded or displayed in the exponent format. There are tons of formatting you can use. Visit here for all the  [string formatting available with the](https://www.programiz.com/python-programming/methods/string/format)  `[format()](https://www.programiz.com/python-programming/methods/string/format)`  method.

```py
# formatting integers
"Binary representation of {0} is {0:b}".format(12)
'Binary representation of 12 is 1100'

# formatting floats
"Exponent representation: {0:e}".format(1566.345)
'Exponent representation: 1.566345e+03'

# round off
"One third is: {0:.3f}".format(1/3)
'One third is: 0.333'

# string alignment
"|{:<10}|{:^10}|{:>10}|".format('butter','bread','ham')
'|butter    |  bread   |       ham|'
```

----------

### Old style formatting

We can even format strings like the old  `sprintf()`  style used in C programming language. We use the  `%`  operator to accomplish this.

```py
x = 12.3456789
print('The value of x is %3.2f' %x)
The value of x is 12.35
print('The value of x is %3.4f' %x)
The value of x is 12.3457
```

----------

## Common Python String Methods

There are numerous methods available with the string object. The  `format()`  method that we mentioned above is one of them. Some of the commonly used methods are  `lower()`,  `upper()`,  `join()`,  `split()`,  `find()`,  `replace()`  etc. Here is a complete list of all the  [built-in methods to work with strings in Python](https://www.programiz.com/python-programming/methods/string).

```py
"PrOgRaMiZ".lower()
'programiz'
"PrOgRaMiZ".upper()
'PROGRAMIZ'
"This will split all words into a list".split()
['This', 'will', 'split', 'all', 'words', 'into', 'a', 'list']
' '.join(['This', 'will', 'join', 'all', 'words', 'into', 'a', 'string'])
'This will join all words into a string'
'Happy New Year'.find('ew')
7
'Happy New Year'.replace('Happy','Brilliant')
'Brilliant New Year'
```

> Source : https://www.programiz.com/python-programming/string