---
title: "Python Ultimate Crash Course (Zero-To-Hero)"
date: 2020-07-14T19:33:21+05:30
Description: "A guide on python 3 and python 2"
Tags: []
Categories: []
draft: true
DisableComments: false
---
# Introduction
Python is one of most popular and most powerful and one of the fastest programming languages until now, Millions upon millions developers use python in their projects to script easily. also python is one of the easiest languages to learn and master. But there are some differences between python 2 and 3, and most beginners get confused and leave python because they can't understand how these work. So let's begin with python 2 and 3 at the same time shall we?

# Environment
I'm using [Visual Studio Code](/post/vs-code-for-web-developers.md) as my code editor. Windows, Mac and linux users can download and install python from the main website [Here](https://www.python.org/). And if you're just going to try it, you can use these Online terminals for [Python 2](https://www.tutorialspoint.com/execute_python_online.php) and for [Python 3](https://www.tutorialspoint.com/execute_python3_online.php). Follow the installer guide and don't forget to add python to the path (Setup would do it for you). If everything goes according to the plan, you can see wether it's installed or not by typing
>       python -v

To a terminal window, or windows Powershell or windows CMD and you'll be greeted with bunch of version numbers. If it pops up errors, try adding python path.

# Zero
Here, we're starting and continuing with the terminal, GUI programming is something else in python so, Don't expect anything GUI related in the beginning. But I'll provide you a GUI Tutorial in the future.

## Folder Structure
Now, let's begin with the Python Document. you have to create a file with .py extension, so it'll be Identified as a python script. If you are using VS Code, just save it as a python file.

![Python VSCode](/uploads/20200714_01.png)

And you're ready with the file.

## Basic Syntax
Here begins the differences of python 2 and 3. Let's print a hello world phrase to the terminal. In python 2
>       print "Hello World!"

Python 3
>       print("Hello World!")

write this line in your document and save it. Now you can use a terminal and type
>       python <file-path>

To run the python script.

![Python VSCode](/uploads/20200714_02.png)

or simply if you're using VS Code like me, give the key combination

>       Ctrl + Shift + `

to get the terminal window and enter

>       python <filename>

to Run the file.

![Python VSCode](/uploads/20200714_03.png)

You should see the Hello world printed to the terminal! Now we can explore what we can do with python as a programming language.

## Python Identifiers
Identifiers are names, that used to identify classes variables functions module or other objects. Identifiers must start with a-z or A-Z and can be continued with characters, underscores and numbers. Python does not allow punctuation characters such as @, $, and % within identifiers. And also python is case sensitive, which means it watches for capital and simple letters and 'a' is not the same as 'A'.

Here are naming conventions for Python identifiers −
* Class names start with an uppercase letter. All other identifiers start with a lowercase letter.
* Starting an identifier with a single leading underscore indicates that the identifier is private.
* Starting an identifier with two leading underscores indicates a strongly private identifier.
* If the identifier also ends with two trailing underscores, the identifier is a language-defined special name.

## Reserved Words
These words are literally python keywords so you can't use these as Identifiers, you'll get in trouble if you did so, so keep these noticed

| ======== | ======== | ======== |
| :------- | :------: | -------: |
| and      |   exec   |      not |
| assert   | finally  |       or |
| break    |   for    |     pass |
| class    |   from   |    print |
| continue |  global  |    raise |
| def      |    if    |   return |
| del      |  import  |      try |
| elif     |    in    |    while |
| else     |    is    |     with |
| except   |  lambda  |    yield |

## Lines and Indentation
Now this is something, you have to keep in your mind. python is different from other languages because of several reasons and here, It doesn't has any braces at all, so white spacing is compulsory! Let's check an example, Don't consider the codes, I'll explain them later.

Python 2

>       if True:
>           print "Hello World"
>       else:
>           print "Noo World"

Python 3

>       if True:
>           print ("Hello World")
>       else:
>           print ("Noo World")

But this would show you an error because it doesn't have proper white spaces.

Python 2

>       if True:
>       print "Hello World"
>       else:
>       print "Noo World"

## Multi-Line Statements

Statements in python ends with a new line, how ever there are some multiline statements, a hand full of them to try out. The line continuation character (\) would make a statement multiline as this. ( Examples are only for reference, we'll discuss everything later. )

>       total = item_one + \
>               item_two + \
>               item_three

Statements withing [],{} or () doesn't need the line continuation character.

>       classes = [ "12a", "13b",
>                   "5a", "6a",
>                   "7a", "8a"]

## Quotation in Python

Python can identify single(') double (") or triple (''' or """) quotations to denote string literals, as long as it starts and ends, you're good to go. The triple quotation can be used to denote multiline strings.

>       a = 'string here'
> 
>       b = "Another string here"
> 
>       c = ''' Do you guys
>               have strings? '''
> 
>       d = """ Multiline Without
>               any escape characters """

## Comments in Python
Comments are important to give hints about your program to future you, because no one can keep a thousand line codebase on their heads, and humans are designed to forget everything withing few days. Comments in python starts with a # sign and can be placed in a new line or after a statement

>       # This is a comment
>       variable = "bla bla bla" # This is a comment

and for multiline comments, you can also use the triple quotation technique but only in new lines.

python 2

>       print "hello"
>       '''
>       This is a comment
>       '''
>       print "comment ends"

python 3

>       print ("hello")
>       '''
>       This is a comment
>       '''
>       print ("comment ends")

## Using Blank Lines
You're free to use blank line as much as you want. But you can't use blank lines inside objects classes or functions, It'll make a mess, so  trust me. Use blank lines for good.

Let's begin some actual codings.

## Waiting for the user
In a certain point, we all have to take an input from the user. in python console, it's simple as this. This is not a "String" input, but this is more like a "Press enter to continue" input.

>       raw_input("\n\nPress the enter key to exit.")

## Multiple Statements on a Single Line
We can use a semi-colone (;) to add multiple statements to a single line

python 2

>       x = "hello"; y = "world"; print x + y

python 3

>       x = "hello"; y = "world"; print (x + y)

## Multiple Statement Groups as Suites
Here, it's more like the curly braces of other languages, we call them suites here, the mechanic is the same so you won't be bothered that much.

>       if expression : 
>              suite
>       elif expression : 
>              suite 
>       else : 
>              suite

if you aren't comfortable with these for now, be cool you'll understand later in this series. Let's start with assigning variables.

## Assigning Values to Variables
This is why python is one of my favorite programming languages, it does it's basic work, it self. so considering variables, python is automatically assigning it's variable types (explicit declaration), to reserve memory for that variable, so you can assign variables as this. Continue with the examples from now on.

>       a = "Hello World"   # This is a string
>       b = 15              # This is an integer
>       c = 15.23           # This is a float
>       d = true            # This is a boolean

you can check them using,

Python 2

>       print a
>       print b
>       print c
>       print d

Python 3

>       print (a)
>       print (b)
>       print (c)
>       print (d)

And there's a way to assign multiple variables in python, at once. I can assign value of 1 (integer) to all a, b, and c using

>       a = b = c = 1

and you can use the print statements above to check again.

## Standard Data Types
This is an important topic to understand, here I'm explaining what kind of data types you have to work with, programming languages are all the same so it won't be hard if you're coming from a "Background", I'm explaining for everyone, so don't panic.

Standerd Data Types And What They Are

| Data Type  | Description                                                                                                                                        | Examples                                    |
| :--------- | :------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------ |
| Numbers    | These are Integers. Whole numbers in common.                                                                                                       | 1, 2, 3, 5, 10, 100                         |
| String     | These are paragraphs and they should contain within quotations.                                                                                    | "This is a string"                          |
| List       | Lists are a collection of strings, numbers or any other data types and they contain within square brackets, It's also the most versatile data Type | ["Hello","World","15",35]                   |
| Tuple      | These are exactly like lists but starts and ends with normal brackets. And Tuples can't be updated, which means they are constants.                | ("Hello","World","15",35)                   |
| Dictionary | This is one of my favorites. Dictionaries consists of keys and values, which we can index in a way and return their data in another way.           | {'name': 'john','ID':6734, 'salary': '500'} | . |

Now Let's Explore Data types One by one

## Python Strings
Just paragraphs. and that's all for the definition. There are string operators, which can be used to process strings in python. You can multiply, add another string to a string and slice. Run this example and see for your self

python 2

>       str = "Hello World"
>       print str           # Prints Whole String
>       print str*3         # Prints the string Three Times
>       print str + "WW"    # Print the modified string
>       print str[0]        # Prints the first character
>       print str[2:7]      # Prints characters from 3rd to 7th
>       print str[2:]       # Prints characters from 3 onwards

python 3

>       str = "Hello World"
>       print (str)           # Prints Whole String
>       print (str*3)         # Prints the string Three Times
>       print (str + "WW")    # Print the modified string
>       print (str[0])        # Prints the first character
>       print (str[2:7])      # Prints characters from 3rd to 7th
>       print (str[2:])       # Prints characters from 3 onwards

## Python Numbers

We'll discuss basic operators later, for now, these are the types of numbers you have to work with

|  int   |         long          |   float    |  complex   |
| :----: | :-------------------: | :--------: | :--------: |
|   10   |       51924361L       |    0.0     |   3.14j    |
|  100   |       -0x19323L       |   15.20    |    45.j    |
|  -786  |         0122L         |   -21.9    | 9.322e-36j |
|  080   | 0xDEFABCECBDAECBFBAEl |  32.3+e18  |   .876j    |
| -0490  |     535633629843L     |    -90.    | -.6545+0J  |
| -0x260 |    -052318172735L     | -32.54e100 |   3e+26J   |
|  0x69  |    -4721885298529L    |  70.2-E12  |  4.53e-7j  |

* Python allows you to use a lowercase l with long, but it is recommended that you use only an uppercase L to avoid confusion with the number 1. Python displays long integers with an uppercase L.
* A complex number consists of an ordered pair of real floating-point numbers denoted by x + yj, where x and y are the real numbers and j is the imaginary unit.

## Python Lists

These are versatile and you can use these to store a list of other data types as it is a "list". now let's define a list

>       lista = ["This is a list", 56, "Hello There", 98, 2.56]
>       listb = ["Another String", 56.56]

Now let's do some list operations

Python 2

>       print lista*2           # Prints out the list 2 times
>       print lista + listb     # Prints out lista and listb as a single list
>       print lista[0]          # Prints the first item in the list
>       print lista[0:3]        # Prints from first item to the third item
>       print lista[1:]         # Prints from 2nd item onwards

Python 3

>       print (lista*2)           # Prints out the list 2 times
>       print (lista + listb)     # Prints out lista and listb as a single list
>       print (lista[0])          # Prints the first item in the list
>       print (lista[0:3])        # Prints from first item to the third item
>       print (lista[1:])         # Prints from 2nd item onwards

Also you can change certain items in lists as this

>       lista[0] = "Something Else"
>       print lista                # For Python 2
>       print (lista)              # For Python 3

## Python Tuples

These are also lists but they can't be changed in the future

>       tuplea = ["This is a tuple", 56, "Hello There", 98, 2.56]
>       tupleb = ["Another String", 56.56]

Now let's do some Tuple operations

Python 2

>       print tuplea*2           # Prints out the tuple 2 times
>       print tuplea + tupleb     # Prints out tuplea and tupleb as a single tuple
>       print tuplea[0]          # Prints the first item in the tuple
>       print tuplea[0:3]        # Prints from first item to the third item
>       print tuplea[1:]         # Prints from 2nd item onwards

Python 3

>       print (tuplea*2)           # Prints out the tuple 2 times
>       print (tuplea + tupleb)     # Prints out tuplea and tupleb as a single tuple
>       print (tuplea[0])          # Prints the first item in the tuple
>       print (tuplea[0:3])        # Prints from first item to the third item
>       print (tuplea[1:])         # Prints from 2nd item onwards

And That's all for Tuples. Now To the final data type, Dictionaries

## Python Dictionary

Dictionaries are defined using curly braces {} and you can add items in the beginning or later. Remember dictionaries are using key, value pairs to define entries in it. for an example, a Phone book. Let's make a simple phonebook here.

>       phonebook = {}
>       phonebook["Jhon"] = "0712345678"
>       phonebook["Doce"] = "0712345679"
>       phonebook["Anna"] = "0712345680"
>       
>       anotherPhonebook = {"Bella":"0721234567","Becky":"0721234568","Bola":"0721234569"}

Now, Defining out to the way, you can use some simple operators to process these phone books. (Dictionaries)
Let's Combine, get values by name, get names, and get numbers from this phonebook.

>       bigPhonebook = phonebook + anotherPhonebook     # Combines Phonebooks to a big one
>       print phonebook["Jhon"]                         # Prints the number of Jhon
>       print phonebook                                 # Prints the whole phonebook
>       print phonebook.keys()                          # Prints all of the names
>       print phonebook.values()                        # Prints all of the numbers

## Data Type Conversion

There are certain times when you have to convert data to another type, for an example let's consider the string "180", And we want to convert this to integers. so we can use a simple function and convert it to 180. Now look carefully, "180" is a string and not a number, because it has quotations around it. Let's explore a bit.

| Sr.No. | Function              | Description                                                             |
| :----- | :-------------------- | :---------------------------------------------------------------------- |
| 1      | int(x [,base])        | Converts x to an integer. base specifies the base if x is a string.     |
| 2      | long(x [,base] )      | Converts x to a long integer. base specifies the base if x is a string. |
| 3      | float(x)              | Converts x to a floating-point number.                                  |
| 4      | complex(real [,imag]) | Creates a complex number.                                               |
| 5      | str(x)                | Converts object x to a string representation.                           |
| 6      | repr(x)               | Converts object x to an expression string.                              |
| 7      | eval(str)             | Evaluates a string and returns an object.                               |
| 8      | tuple(s)              | Converts s to a tuple.                                                  |
| 9      | list(s)               | Converts s to a list.                                                   |
| 10     | set(s)                | Converts s to a set.                                                    |
| 11     | dict(d)               | Creates a dictionary. d must be a sequence of (key,value) tuples.       |
| 12     | frozenset(s)          | Converts s to a frozen set.                                             |
| 13     | chr(x)                | Converts an integer to a character.                                     |
| 14     | unichr(x)             | Converts an integer to a Unicode character.                             |
| 15     | ord(x)                | Converts a single character to its integer value.                       |
| 16     | hex(x)                | Converts an integer to a hexadecimal string.                            |
| 17     | oct(x)                | Converts an integer to an octal string.                                 |

plug the value to x and you can use the function anywhere you want. I'll give you a single example on how to do this,

>       a = "150"
>       b = int(a)

Python 2

>       print a*2
>       print b*2

Python 3

>       print (a*2)
>       print (b*2)

Figure out what happened here.

## Basic Operators

Now, We're in to the arithmetic part of our journey. But not only the arithmetics, Types of Operators in
Python are categorized as below.

* Arithmetic Operators
* Comparison (Relational) Operators
* Assignment Operators
* Logical Operators
* Bitwise Operators
* Membership Operators
* Identity Operators

Let's Explore one by one, I'll provide you everything with brief explanations, We'll dig deeper into these late. Also these are self explanatory.

#### Python Arithmetic Operators

These are the operators we use to preform arithmetic calculations.

Assume variable a holds 10 and variable b holds 20, then

| Operator         | Description                                                                                                                                                                                                                                                 | Example                                             |
| :--------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------- |
| + Addition       | Adds values on either side of the operator.                                                                                                                                                                                                                 | a + b = 30                                          |
| - Subtraction    | Subtracts right hand operand from left hand operand.                                                                                                                                                                                                        | a – b = -10                                         |
| * Multiplication | Multiplies values on either side of the operator                                                                                                                                                                                                            | a * b = 200                                         |
| / Division       | Divides left hand operand by right hand operand                                                                                                                                                                                                             | b / a = 2                                           |
| % Modulus        | Divides left hand operand by right hand operand and returns remainder                                                                                                                                                                                       | b % a = 0                                           |
| **               | Exponent	Performs exponential (power) calculation on operators                                                                                                                                                                                              | a**b =10 to the power 20                            |
| //               | Floor Division - The division of operands where the result is the quotient in which the digits after the decimal point are removed. But if one of the operands is negative, the result is floored, i.e., rounded away from zero (towards negative infinity) | 9//2 = 4 and 9.0//2.0=4.0, -11//3=-4, -11.0//3=-4.0 |

#### Python Comparison Operators

we use comparison for our logical expressions.

Assume variable a holds 10 and variable b holds 20, then

| Operator | Description                                                                                                       | Example                                           |
| :------- | :---------------------------------------------------------------------------------------------------------------- | :------------------------------------------------ |
| ==       | If the values of two operands are equal, then the condition becomes true.                                         | (a == b) is not true.                             |
| !=       | If values of two operands are not equal, then condition becomes true.                                             | (a != b) is true.                                 |
| <>       | If values of two operands are not equal, then condition becomes true.                                             | (a <> b) is true. This is similar to != operator. |
| >        | If the value of left operand is greater than the value of right operand, then condition becomes true.             | (a > b) is not true.                              |
| <        | If the value of left operand is less than the value of right operand, then condition becomes true.                | (a < b) is true.                                  |
| >=       | If the value of left operand is greater than or equal to the value of right operand, then condition becomes true. | (a >= b) is not true.                             |
| <=       | If the value of left operand is less than or equal to the value of right operand, then condition becomes true.    | (a <= b) is true.                                 |

For an example, we can use on of these in a IF statement ( Just for examples )

>       a = "cat"
>       b = "cat"
>       if (a == b):
>           print(a)
>       else:
>           print(b)

#### Python Assignment Operators

These are for assigning variables

Assume variable a holds 10 and variable b holds 20, then

| Operator | Description                                                                                             | Example                                 |
| :------- | :------------------------------------------------------------------------------------------------------ | :-------------------------------------- |
| =        | Assigns values from right side operands to left side operand                                            | c = a + b assigns value of a + b into c |
| +=       | Add AND	It adds right operand to the left operand and assign the result to left operand                 | c += a is equivalent to c = c + a       |
| -=       | Subtract AND	It subtracts right operand from the left operand and assign the result to left operand     | c -= a is equivalent to c = c - a       |
| *=       | Multiply AND	It multiplies right operand with the left operand and assign the result to left operand    | c *= a is equivalent to c = c * a       |
| /=       | Divide AND	It divides left operand with the right operand and assign the result to left operand         | c /= a is equivalent to c = c / a       |
| %=       | Modulus AND	It takes modulus using two operands and assign the result to left operand                   | c %= a is equivalent to c = c % a       |
| **=      | Exponent AND	Performs exponential (power) calculation on operators and assign value to the left operand | c **= a is equivalent to c = c ** a     |
| //=      | Floor Division	It performs floor division on operators and assign value to the left operand             | c //= a is equivalent to c = c // a     |

#### Python Bitwise Operators

Bitwise operator works on bits and performs bit by bit operation. Assume if a = 60 and b = 13 Now in the binary format their values will be 0011 1100 and 0000 1101 respectively.

a = 0011 1100

b = 0000 1101

--------------------

a&b = 0000 1100

a|b = 0011 1101

a^b = 0011 0001

~a  = 1100 0011

What the f happened here? It's BITWISE. let's explore

| Operator | Description                                                                                                     | Example                                                                            |
| :------- | :-------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------- |
| &        | Binary AND	Operator copies a bit to the result if it exists in both operands                                    | (a & b) (means 0000 1100)                                                          |
| \|       | Binary OR	It copies a bit if it exists in either operand.                                                       | (a \| b) = 61 (means 0011 1101)                                                    |
| ^        | Binary XOR	It copies the bit if it is set in one operand but not both.                                          | (a ^ b) = 49 (means 0011 0001)                                                     |
| ~        | Binary Ones Complement	It is unary and has the effect of 'flipping' bits.                                       | (~a ) = -61 (means 1100 0011 in 2's complement form due to a signed binary number. |
| <<       | Binary Left Shift	The left operands value is moved left by the number of bits specified by the right operand.   | a << 2 = 240 (means 1111 0000)                                                     |
| >>       | Binary Right Shift	The left operands value is moved right by the number of bits specified by the right operand. | a >> 2 = 15 (means 0000 1111)                                                      |

#### Python Logical Operators
We use these very often and notice these are more like creating sentences.

Assume variable a holds 10 and variable b holds 20 then.

| Operator | Description                                                                     | Example                |
| :------- | :------------------------------------------------------------------------------ | :--------------------- |
| and      | Logical AND	If both the operands are true then condition becomes true.          | (a and b) is true.     |
| or       | Logical OR	If any of the two operands are non-zero then condition becomes true. | (a or b) is true.      |
| not      | Logical NOT	Used to reverse the logical state of its operand.                   | Not(a and b) is false. |

#### Python Membership Operators
These Operators used to check wether some value is in something, this would get handy when creating search engines or so.

| Operator | Description                                                                                         | Example                                                                    |
| :------- | :-------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------- |
| in       | Evaluates to true if it finds a variable in the specified sequence and false otherwise.             | x in y, here in results in a 1 if x is a member of sequence y.             |
| not      | in	Evaluates to true if it does not finds a variable in the specified sequence and false otherwise. | x not in y, here not in results in a 1 if x is not a member of sequence y. |

#### Python Identity Operators

Identity operators compare the memory locations of two objects. It would be more clear if you know how [variables work](https://en.wikipedia.org/wiki/Variable_(computer_science))

| Operator | Description                                                                                                     | Example                                                              |
| :------- | :-------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------- |
| is       | Evaluates to true if the variables on either side of the operator point to the same object and false otherwise. | x is y, here is results in 1 if id(x) equals id(y).                  |
| is not   | Evaluates to false if the variables on either side of the operator point to the same object and true otherwise. | x is not y, here is not results in 1 if id(x) is not equal to id(y). |

#### Python Operators Precedence
We used to know how the BODMAS works, and this is the BODMAS for programming. Highest to lowest.

| Sr.No. | Operator                                      | Description                                                                    |
| :----- | :-------------------------------------------- | :----------------------------------------------------------------------------- |
| 1      | **                                            | Exponentiation (raise to the power)                                            |
| 2      | ~ + -                                         | Complement, unary plus and minus (method names for the last two are +@ and -@) |
| 3      | * / % //                                      | Multiply, divide, modulo and floor division                                    |
| 4      | + -                                           | Addition and subtraction                                                       |
| 5      | >> <<                                         | Right and left bitwise shift                                                   |
| 6      | &                                             | Bitwise 'AND'                                                                  |
| 7      | ^ \|                                          | Bitwise exclusive `OR' and regular `OR'                                        |
| 8      | <= < > >=                                     | Comparison operators                                                           |
| 9      | <> == !=                                      | Equality operators                                                             |
| 10     | = %= /= //= -= += *= **= Assignment operators |
| 11     | is ,is not                                    | Identity operators                                                             |
| 12     | in, not, in                                   | Membership operators                                                           |
| 13     | not, or, and                                  | Logical operators                                                              |

## Decision Making

Here we're in a critical part, no logical program can made without these. go through one by one carefully. Depiction making logs down to checking TRUE or FALSE on a condition so if it's true it can do something and if it's false it can do something else.

![Desicion Making](https://www.tutorialspoint.com/python/images/decision_making.jpg)

Python programming language provides following types of decision making statements

| Sr.No. | Statement            | Description                                                                                                         |
| :----- | :------------------- | :------------------------------------------------------------------------------------------------------------------ |
| 1      | if statements        | An if statement consists of a boolean expression followed by one or more statements.                                |
| 2      | if...else statements | An if statement can be followed by an optional else statement, which executes when the boolean expression is FALSE. |
| 3      | nested if statements | You can use one if or else if statement inside another if or else if statement(s).                                  |

#### Single Statement Suites
you can create a if statement single lined. and here's how you can do it

>       if(condition): <code to run if true>

For a practical statement

>       a = 10
>       if( a != 9): print("a Is not 9!")

#### If statements
remember python is a case sensitive programming language which means you have to be careful with capitals and simples, all of the python keywords are simple. keep it in mind.

>       if (expression):
>           <statement>

This is the basic code for a if statement, did you notice that there is a whitespace (few spaces) after the if statement, that indicates that statement belongs to that if statement.

for a practical use

>       a = 10
>       if (a == 10):
>           print("A is 10")

#### if...else statement
Now what can we do if the if statement is false? Here's the solution for you. just use a else statement and It'll run if the condition is false.

>       if (expression):
>           <statement>
>       else:
>           <statement>

This is the boilerplate for if...else statement, let's consider a practical usage.

>       a = 9
>       if (a == 10):
>           print("A is 10")
>       else:
>           print("A is not 9")

Try for yourself and try to play with it.

#### Nested If statements
Here you can set several if statements to run if the previous one is false. let me demonstrate.

>       if (expression):
>           <statement>
>       elif (expression):
>           <statement>
>       else:
>           <statement>

Now the elif checks the condition if the if statement gets false and if both are false, it would run else statement. You can add any number of elif statements in to your code. Let's consider a practical usage. 

>       a = 5
>       if (a == 10):
>           print("A is 10")
>       elif (a == 9):
>           print("A is 9")
>       elif (a == 8):
>           print("A is 8")
>       elif (a == 7):
>           print("A is 7")
>       else:
>           print("A is something else!")

## Loops
Well, here comes the fun part. we can run a code for a number of times without writing the same code over and over again, and That's fun! There are several loop statements and loop control statements in python

![loops](https://www.tutorialspoint.com/python/images/loop_architecture.jpg)

| Sr.No. | Loop Type    | Description                                                                                                                        |
| :----- | :----------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| 1      | while loop   | Repeats a statement or group of statements while a given condition is TRUE. It tests the condition before executing the loop body. |
| 2      | for loop     | Executes a sequence of statements multiple times and abbreviates the code that manages the loop variable.                          |
| 3      | nested loops | You can use one or more loop inside any another while, for or do..while loop.                                                      |



#### Loop control

These are used in loops to alter their functionality, keep these in mind and next we'll consider on how we can use these to our will.

| Sr.No. | Control Statement  | Description                                                                                                                         |
| :----- | :----------------- | :---------------------------------------------------------------------------------------------------------------------------------- |
| 1      | break statement    | Terminates the loop statement and transfers execution to the statement immediately following the loop.                              |
| 2      | continue statement | Causes the loop to skip the remainder of its body and immediately retest its condition prior to reiterating.                        |
| 3      | pass statement     | The pass statement in Python is used when a statement is required syntactically but you do not want any command or code to execute. |

#### While loop
As it claims, these loops are running until the provided expression stays true

![loop](https://www.tutorialspoint.com/python/images/python_while_loop.jpg)

>       while(expression):
>           <statement>

Let's consider a practical usage

>       a = 0
>       while( a<10 ):
>           print(a)
>           a += 1

This would print out the value of a until it passes 10. and then, the expression turns false and the loops breaks.

#### For loop
for loop is executing through a sequence like a list or so. 

![loop](https://www.tutorialspoint.com/python/images/python_for_loop.jpg)

the basic use case is like this,

>       for <variable> in <sequence>:
>           <statement>

let's consider a practical usage. Here, you can see a word is a sequence of letters, so we can use it.

>       for letter in 'HelloWorld':
>           print(letter)

Here you can see 'letter' is the variable and 'HelloWorld' is the sequence. this would print out all of the letters in the provided sequence.

>       a = ["hello world","nice world","rice bowl","remote control?"]
>       for i in a:
>           print(i)

Here, I used a variable called i and as the sequence I provided a list. and this code should loop through the list and print out everything in it one by one.

#### Nested loops
Loops can be written inside other loops and that's what nested loops are. This isn't hard or something, just use a bit of logic and you're good to go, let me show you some examples and you just have to know that you can do that.

>       a = ["First Time : ","Second Time : ","Third Time : "]
>       b = ["a","e","i","o","u"]
>       
>       for season in a:
>           for letter in b:
>               print(season + letter)

And the output should be

>       First Time : a
>       First Time : e
>       First Time : i
>       First Time : o
>       First Time : u
>       Second Time : a
>       Second Time : e
>       Second Time : i
>       Second Time : o
>       Second Time : u
>       Third Time : a
>       Third Time : e
>       Third Time : i
>       Third Time : o
>       Third Time : u

#### Using loop controls
Using loop controls isn't that hard, let me demonstrate you how they work.

>       b = ["a","e","i","o","u"]
>
>       for letter in b:
>           if( b == "i"):
>               break
>           print(season + letter)

Here, only a and e would be printed, whenever it comes to i, the loop breaks with the break command

>       b = ["a","e","i","o","u"]
>
>       for letter in b:
>           if( b == "i"):
>               continue
>           print(season + letter)

Here, everything except for i would be printed, whenever it comes to i, the loop skips the rest of the code and starts again with the continue command

pass statement is somewhat different

>       b = ["a","e","i","o","u"]
>
>       for letter in b:
>           if( b == "i"):
>               pass
>           print(season + letter)

After running this, you won't be able to see any difference as the pass command wasn't there. and that's exactly it. pass command does nothing. it just holds a place and maybe it'll help to debug the code.

## Number Functions
What are these for? well, these are for atypical calculations, I won't explain these in details because if you don't know the functions in real-life-maths, you don't want to use them here either. If you know these from real-life-maths, you know what to do.

#### Mathematical Functions

plug in a value or a variable in the place of x and you're pretty much done with it.

| Sr.No. | Function & Returns | description                                                                                                                             |
| :----- | :----------------- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| 1      | abs(x)             | The absolute value of x: the (positive) distance between x and zero.                                                                    |
| 2      | ceil(x)            | The ceiling of x: the smallest integer not less than x                                                                                  |
| 3      | cmp(x, y)          | -1 if x < y, 0 if x == y, or 1 if x > y                                                                                                 |
| 4      | exp(x)             | The exponential of x: ex                                                                                                                |
| 5      | fabs(x)            | The absolute value of x.                                                                                                                |
| 6      | floor(x)           | The floor of x: the largest integer not greater than x                                                                                  |
| 7      | log(x)             | The natural logarithm of x, for x> 0                                                                                                    |
| 8      | log10(x)           | The base-10 logarithm of x for x> 0.                                                                                                    |
| 9      | max(x1, x2,...)    | The largest of its arguments: the value closest to positive infinity                                                                    |
| 10     | min(x1, x2,...)    | The smallest of its arguments: the value closest to negative infinity                                                                   |
| 11     | modf(x)            | The fractional and integer parts of x in a two-item tuple. Both parts have the same sign as x. The integer part is returned as a float. |
| 12     | pow(x, y)          | The value of x**y.                                                                                                                      |
| 13     | round(x [,n])      | x rounded to n digits from the decimal point. Python rounds away from zero as a tie-breaker: round(0.5) is 1.0 and round(-0.5) is -1.0. |
| 14     | sqrt(x)            | The square root of x for x > 0                                                                                                          |

#### Random Number Functions

Random numbers are used for games, simulations, testing, security, and privacy applications. Python includes following functions that are commonly used.

| Sr.No. | Function                          | Description                                                                                                                                          |
| :----- | :-------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1      | choice(seq)                       | A random item from a list, tuple, or string.                                                                                                         |
| 2      | randrange ([start,] stop [,step]) | A randomly selected element from range(start, stop, step)                                                                                            |
| 3      | random()                          | A random float r, such that 0 is less than or equal to r and r is less than 1                                                                        |
| 4      | seed([x])                         | Sets the integer starting value used in generating random numbers. Call this function before calling any other random module function. Returns None. |
| 5      | shuffle(lst)                      | Randomizes the items of a list in place. Returns None.                                                                                               |
| 6      | uniform(x, y)                     | A random float r, such that x is less than or equal to r and r is less than y                                                                        |

#### Trigonometric Functions
Python includes following functions that perform trigonometric calculations.


| Sr.No. | Function    | Description                                 |
| :----- | :---------- | :------------------------------------------ |
| 1      | acos(x)     | Return the arc cosine of x, in radians.     |
| 2      | asin(x)     | Return the arc sine of x, in radians.       |
| 3      | atan(x)     | Return the arc tangent of x, in radians.    |
| 4      | atan2(y, x) | Return atan(y / x), in radians.             |
| 5      | cos(x)      | Return the cosine of x radians.             |
| 6      | hypot(x, y) | Return the Euclidean norm, sqrt(x*x + y*y). |
| 7      | sin(x)      | Return the sine of x radians.               |
| 8      | tan(x)      | Return the tangent of x radians.            |
| 9      | degrees(x)  | Converts angle x from radians to degrees.   |
| 10     | radians(x)  | Converts angle x from degrees to radians.   |

#### Mathematical Constants
Just our atypical mathematical constants, these can be used as numbers.

| Sr.No. | Constants | Description                   |
| :----- | :-------- | :---------------------------- |
| 1      | pi        | The mathematical constant pi. |
| 2      | e         | The mathematical constant e.  |