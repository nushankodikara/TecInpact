---
title: "Python Ultimate Crash Course (Zero-To-Hero)"
date: 2020-07-16T14:30:00+05:30
Description: "A guide on python 3 and python 2"
Tags: ["Programming","Software Development","Zero To Hero","Crash Course"]
Categories: []
DisableComments: false
---
# Introduction
Python is one of most popular and most powerful and one of the fastest programming languages until now, Millions upon millions developers use python in their projects to script easily. also python is one of the easiest languages to learn and master. But there are some differences between python 2 and 3, and most beginners get confused and leave python because they can't understand how these work. So let's begin with python 2 and 3 at the same time shall we?

# Environment
I'm using [Visual Studio Code](/post/vs-code-for-web-developers/) as my code editor. Windows, Mac and linux users can download and install python from the main website [Here](https://www.python.org/). And if you're just going to try it, you can use these Online terminals for [Python 2](https://www.tutorialspoint.com/execute_python_online.php) and for [Python 3](https://www.tutorialspoint.com/execute_python3_online.php). Follow the installer guide and don't forget to add python to the path (Setup would do it for you). If everything goes according to the plan, you can see wether it's installed or not by typing
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

Standard Data Types And What They Are

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

## String Functions
Here, we considering what kinds of things we can do with python strings. In other words, String processing In Python.

Here you have to keep in mind that strings are a sequence of letters. so we can process them as like lists and tuples.

#### Accessing Values in Strings
Python does not support a character type; these are treated as strings of length one, thus also considered a substring. To access substrings, use the square brackets for slicing along with the index or indices to obtain your substring. For example

>       var1 = 'Hello World!'
>       var2 = "Python Programming"
>       
>       print ("var1[0]: ", var1[0])
>       print ("var2[1:5]: ", var2[1:5])

#### Escape Characters
These are some special characters which you can use in strings. they are called escape characters. for an example you can add a escape character to print a single line paragraph as a multiline paragraph.

| Backslash notation | Hexadecimal character | Description                                                    |
| :----------------- | :-------------------- | :------------------------------------------------------------- |
| \a                 | 0x07                  | Bell or alert                                                  |
| \b                 | 0x08                  | Backspace                                                      |
| \cx                |                       | Control-x                                                      |
| \C-x               |                       | Control-x                                                      |
| \e                 | 0x1b                  | Escape                                                         |
| \f                 | 0x0c                  | Formfeed                                                       |
| \M-\C-x            |                       | Meta-Control-x                                                 |
| \n                 | 0x0a                  | Newline                                                        |
| \nnn               |                       | Octal notation, where n is in the range 0.7                    |
| \r                 | 0x0d                  | Carriage return                                                |
| \s                 | 0x20                  | Space                                                          |
| \t                 | 0x09                  | Tab                                                            |
| \v                 | 0x0b                  | Vertical tab                                                   |
| \x                 |                       | Character x                                                    |
| \xnn               |                       | Hexadecimal notation, where n is in the range 0.9, a.f, or A.F |

#### String Special Operators
These operators can be used to process certain paragraphs.

| Operator | Description                                                                                                                                                                                                                                                                                                                                       | Example                                        |
| :------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------------------------------------------- |
| +        | Concatenation - Adds values on either side of the operator                                                                                                                                                                                                                                                                                        | a + b will give HelloPython                    |
| *        | Repetition - Creates new strings, concatenating multiple copies of the same string                                                                                                                                                                                                                                                                | a*2 will give -HelloHello                      |
| []       | Slice - Gives the character from the given index                                                                                                                                                                                                                                                                                                  | a[1] will give e                               |
| [ : ]    | Range Slice - Gives the characters from the given range                                                                                                                                                                                                                                                                                           | a[1:4] will give ell                           |
| in       | Membership - Returns true if a character exists in the given string                                                                                                                                                                                                                                                                               | H in a will give 1                             |
| not in   | Membership - Returns true if a character does not exist in the given string                                                                                                                                                                                                                                                                       | M not in a will give 1                         |
| r/R      | Raw String - Suppresses actual meaning of Escape characters. The syntax for raw strings is exactly the same as for normal strings with the exception of the raw string operator, the letter "r," which precedes the quotation marks. The "r" can be lowercase (r) or uppercase (R) and must be placed immediately preceding the first quote mark. | print r'\n' prints \n and print R'\n'prints \n |
| %        | Format - Performs String formatting                                                                                                                                                                                                                                                                                                               | See at next section                            |

#### String Formatting Operator
These can be used to add certain values to a pre formatted string. It'll make sense in the future when you work with these, until then Let's explore.

| Format Symbol | Conversion                                      |
| :------------ | :---------------------------------------------- |
| %c            | character                                       |
| %s            | string conversion via str() prior to formatting |
| %i            | signed decimal integer                          |
| %d            | signed decimal integer                          |
| %u            | unsigned decimal integer                        |
| %o            | octal integer                                   |
| %x            | hexadecimal integer (lowercase letters)         |
| %X            | hexadecimal integer (UPPERcase letters)         |
| %e            | exponential notation (with lowercase 'e')       |
| %E            | exponential notation (with UPPERcase 'E')       |
| %f            | floating point real number                      |
| %g            | the shorter of %f and %e                        |
| %G            | the shorter of %f and %E                        |

Now for an example, let's try an example

>       a = "Jhon Doe"
>       b = "The World War 3"
>       c = 56.5
>       print("Hello Mr.%s, This is your book %s which cost you $%g and I Hope you have a nice weekend." % (a, b, c))

Other supported symbols and functionality are listed in the following table

| Symbol | Functionality                                                                                            |
| :----- | :------------------------------------------------------------------------------------------------------- |
| *      | argument specifies width or precision                                                                    |
| -      | left justification                                                                                       |
| +      | display the sign                                                                                         |
| <sp>   | leave a blank space before a positive number                                                             |
| #      | add the octal leading zero ( '0' ) or hexadecimal leading '0x' or '0X', depending on whether 'x' or 'X'  | were used. |
| 0      | pad from left with zeros (instead of spaces)                                                             |
| %      | '%%' leaves you with a single literal '%'                                                                |
| (var)  | mapping variable (dictionary arguments)                                                                  |
| m.n.   | m is the minimum total width and n is the number of digits to display after the decimal point (if appl.) |

#### Built-in String Methods

These functions can be used in order to preform string functions, and process strings in our needs. We'll get hang of these later.

| Sr.No. | Methods                                  | Description                                                                                                                                                             |
| :----- | :--------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1      | capitalize()                             | Capitalizes first letter of string                                                                                                                                      |
| 2      | center(width, fillchar)                  | Returns a space-padded string with the original string centered to a total of width columns.                                                                            |
| 3      | count(str, beg= 0,end=len(string))       | Counts how many times str occurs in string or in a substring of string if starting index beg and ending index end are given.                                            |
| 4      | decode(encoding='UTF-8',errors='strict') | Decodes the string using the codec registered for encoding. encoding defaults to the default string encoding.                                                           |
| 5      | encode(encoding='UTF-8',errors='strict') | Returns encoded string version of string; on error, default is to raise a ValueError unless errors is given with 'ignore' or 'replace'.                                 |
| 6      | endswith(suffix, beg=0, end=len(string)) | Determines if string or a substring of string (if starting index beg and ending index end are given) ends with suffix; returns true if so and false otherwise.          |
| 7      | expandtabs(tabsize=8)                    | Expands tabs in string to multiple spaces; defaults to 8 spaces per tab if tabsize not provided.                                                                        |
| 8      | find(str, beg=0 end=len(string))         | Determine if str occurs in string or in a substring of string if starting index beg and ending index end are given returns index if found and -1 otherwise.             |
| 9      | index(str, beg=0, end=len(string))       | Same as find(), but raises an exception if str not found.                                                                                                               |
| 10     | isalnum()                                | Returns true if string has at least 1 character and all characters are alphanumeric and false otherwise.                                                                |
| 11     | isalpha()                                | Returns true if string has at least 1 character and all characters are alphabetic and false otherwise.                                                                  |
| 12     | isdigit()                                | Returns true if string contains only digits and false otherwise.                                                                                                        |
| 13     | islower()                                | Returns true if string has at least 1 cased character and all cased characters are in lowercase and false otherwise.                                                    |
| 14     | isnumeric()                              | Returns true if a unicode string contains only numeric characters and false otherwise.                                                                                  |
| 15     | isspace()                                | Returns true if string contains only whitespace characters and false otherwise.                                                                                         |
| 16     | istitle()                                | Returns true if string is properly "titlecased" and false otherwise.                                                                                                    |
| 17     | isupper()                                | Returns true if string has at least one cased character and all cased characters are in uppercase and false otherwise.                                                  |
| 18     | join(seq)                                | Merges (concatenates) the string representations of elements in sequence seq into a string, with separator string.                                                      |
| 19     | len(string)                              | Returns the length of the string                                                                                                                                        |
| 20     | ljust(width[, fillchar])                 | Returns a space-padded string with the original string left-justified to a total of width columns.                                                                      |
| 21     | lower()                                  | Converts all uppercase letters in string to lowercase.                                                                                                                  |
| 22     | lstrip()                                 | Removes all leading whitespace in string.                                                                                                                               |
| 23     | maketrans()                              | Returns a translation table to be used in translate function.                                                                                                           |
| 24     | max(str)                                 | Returns the max alphabetical character from the string str.                                                                                                             |
| 25     | min(str)                                 | Returns the min alphabetical character from the string str.                                                                                                             |
| 26     | replace(old, new [, max])                | Replaces all occurrences of old in string with new or at most max occurrences if max given.                                                                             |
| 27     | rfind(str, beg=0,end=len(string))        | Same as find(), but search backwards in string.                                                                                                                         |
| 28     | rindex( str, beg=0, end=len(string))     | Same as index(), but search backwards in string.                                                                                                                        |
| 29     | rjust(width,[, fillchar])                | Returns a space-padded string with the original string right-justified to a total of width columns.                                                                     |
| 30     | rstrip()                                 | Removes all trailing whitespace of string.                                                                                                                              |
| 31     | split(str="", num=string.count(str))     | Splits string according to delimiter str (space if not provided) and returns list of substrings; split into at most num substrings if given.                            |
| 32     | splitlines( num=string.count('\n'))      | Splits string at all (or num) NEWLINEs and returns a list of each line with NEWLINEs removed.                                                                           |
| 33     | startswith(str, beg=0,end=len(string))   | Determines if string or a substring of string (if starting index beg and ending index end are given) starts with substring str; returns true if so and false otherwise. |
| 34     | strip([chars])                           | Performs both lstrip() and rstrip() on string.                                                                                                                          |
| 35     | swapcase()                               | Inverts case for all letters in string.                                                                                                                                 |
| 36     | title()                                  | Returns "titlecased" version of string, that is, all words begin with uppercase and the rest are lowercase.                                                             |
| 37     | translate(table, deletechars="")         | Translates string according to translation table str(256 chars), removing those in the del string.                                                                      |
| 38     | upper()                                  | Converts lowercase letters in string to uppercase.                                                                                                                      |
| 39     | zfill (width)                            | Returns original string leftpadded with zeros to a total of width characters; intended for numbers, zfill() retains any sign given (less one zero).                     |
| 40     | isdecimal()                              | Returns true if a unicode string contains only decimal characters and false otherwise.                                                                                  |

## List Functions

#### Assigning and accessing lists
As we did before, assigning lists isn't that hard. just add a list of data separated by commas and enclosed with square brackets. for an example

>       a = [10,20,50,60,"Fun","Bun,"Run"]

And That's it. the indexing of programming is starting with 0. so you can access it's value using
>       <variable>[<index>]
For an example

>       a = [10,20,50,60,"Fun","Bun,"Run"]
>       print(a[0])

and you'll get the first item. to get items from 3 to 5

>       a = [10,20,50,60,"Fun","Bun,"Run"]
>       print(a[2:5])

#### Updating and Deleting Lists
You can change or delete values of a list using Index of that item

>       a = [10,20,50,60,"Fun","Bun,"Run"]
>       a[0] = 65
>       del a[2]
>       print(a)

#### Basic List Operations

You can use these operators for process lists in python.

| Python Expression            | Results                      | Description   |
| :--------------------------- | :--------------------------- | :------------ |
| len([1, 2, 3])               | 3                            | Length        |
| [1, 2, 3] + [4, 5, 6]        | [1, 2, 3, 4, 5, 6]           | Concatenation |
| ['Hi!'] * 4                  | ['Hi!', 'Hi!', 'Hi!', 'Hi!'] | Repetition    |
| 3 in [1, 2, 3]               | True                         | Membership    |
| for x in [1, 2, 3]: print x, | 1 2 3                        | Iteration     |

#### Indexing, Slicing, and Matrixes
Just listing what we did above

>       L = ['spam', 'Spam', 'SPAM!']

| Python Expression | Results           | Description                    |
| :---------------- | :---------------- | :----------------------------- |
| L[2]              | SPAM!             | Offsets start at zero          |
| L[-2]             | Spam              | Negative: count from the right |
| L[1:]             | ['Spam', 'SPAM!'] | Slicing fetches sections       |

#### Built-in List Functions & Methods

Python includes the following list functions −

| Sr.No. | Function          | Description                                |
| :----- | :---------------- | :----------------------------------------- |
| 1      | cmp(list1, list2) | Compares elements of both lists.           |
| 2      | len(list)         | Gives the total length of the list.        |
| 3      | max(list)         | Returns item from the list with max value. |
| 4      | min(list)         | Returns item from the list with min value. |
| 5      | list(seq)         | Converts a tuple into list.                |

Python includes following list methods

| Sr.No. | Methods                 | Description                                        |
| :----- | :---------------------- | :------------------------------------------------- |
| 1      | list.append(obj)        | Appends object obj to list                         |
| 2      | list.count(obj)         | Returns count of how many times obj occurs in list |
| 3      | list.extend(seq)        | Appends the contents of seq to list                |
| 4      | list.index(obj)         | Returns the lowest index in list that obj appears  |
| 5      | list.insert(index, obj) | Inserts object obj into list at offset index       |
| 6      | list.pop(obj=list[-1])  | Removes and returns last object or obj from list   |
| 7      | list.remove(obj)        | Removes object obj from list                       |
| 8      | list.reverse()          | Reverses objects of list in place                  |
| 9      | list.sort([func])       | Sorts objects of list, use compare func if given   |

## Tuples
A tuple is a collection of objects which ordered and immutable. Tuples are sequences, just like lists. The differences between tuples and lists are, the tuples cannot be changed unlike lists and tuples use parentheses, whereas lists use square brackets.

#### Assigning and Accessing Values

Let's do some work with these

>       a = (10,20,50,60,"Fun","Bun,"Run")

And That's it. the indexing of programming is starting with 0. so you can access it's value using
>       <variable>(<index>)
For an example

>       a = (10,20,50,60,"Fun","Bun,"Run")
>       print(a[0])

and you'll get the first item. to get items from 3 to 5

>       a = (10,20,50,60,"Fun","Bun,"Run")
>       print(a[2:5])

#### Basic Tuples Operations
Tuples respond to the + and * operators much like strings; they mean concatenation and repetition here too, except that the result is a new tuple, not a string.

| Python Expression            | Results                      | Description   |
| :--------------------------- | :--------------------------- | :------------ |
| len((1, 2, 3))               | 3                            | Length        |
| (1, 2, 3) + (4, 5, 6)        | (1, 2, 3, 4, 5, 6)           | Concatenation |
| ('Hi!',) * 4                 | ('Hi!', 'Hi!', 'Hi!', 'Hi!') | Repetition    |
| 3 in (1, 2, 3)               | True                         | Membership    |
| for x in (1, 2, 3): print x, | 1 2 3                        | Iteration     |

#### Indexing, Slicing, and Matrixes
It's the same as the lists. but for tuples.

>       L = ('spam', 'Spam', 'SPAM!')

| Python Expression | Results           | Description                    |
| :---------------- | :---------------- | :----------------------------- |
| L[2]              | SPAM!             | Offsets start at zero          |
| L[-2]             | Spam              | Negative: count from the right |
| L[1:]             | ['Spam', 'SPAM!'] | Slicing fetches sections       |

#### Built-in Tuple Functions
Python includes the following tuple functions −

| Sr.No. | Function            | Description                                 |
| :----- | :------------------ | :------------------------------------------ |
| 1      | cmp(tuple1, tuple2) | Compares elements of both tuples.           |
| 2      | len(tuple)          | Gives the total length of the tuple.        |
| 3      | max(tuple)          | Returns item from the tuple with max value. |
| 4      | min(tuple)          | Returns item from the tuple with min value. |
| 5      | tuple(seq)          | Converts a list into tuple.                 |

## Dictionaries
Python dictionaries are a dataset that has a key value pair, and that duo helps so much. Let's start with dictionaries.

#### Assigning, Updating and Deleting dictionaries

we can create a dictionary using 
>       <variable> = {<string>:<string>,...}

for a real section.
>       dic = {"key1":"value1","key2":"value2","key3":"value3","key4":"value4"}

and we can update dictionaries as this
>       dic["key2"]="ChangedValue2"

Adding new entries
>       dic["key5"]="newValue5"

Accessing Values
>       print(dic["key1"])

printing the whole Dictionary
>       print(dic)

Deleting dictionary elements
>       del dic["key3"]

You can Clear the whole Dictionary
>       dic.clear()

Delete the whole dictionary
>       del dic

#### Built-in Dictionary Functions & Methods
Python includes the following dictionary functions

| Sr.No. | Function          | Description                                                                                                        |
| :----- | :---------------- | :----------------------------------------------------------------------------------------------------------------- |
| 1      | cmp(dict1, dict2) | Compares elements of both dict.                                                                                    |
| 2      | len(dict)         | Gives the total length of the dictionary. This would be equal to the number of items in the dictionary.            |
| 3      | str(dict)         | Produces a printable string representation of a dictionary                                                         |
| 4      | type(variable)    | Returns the type of the passed variable. If passed variable is dictionary, then it would return a dictionary type. |

Python includes following dictionary methods

| Sr.No. | Methods                            | Description                                                                    |
| :----- | :--------------------------------- | :----------------------------------------------------------------------------- |
| 1      | dict.clear()                       | Removes all elements of dictionary dict                                        |
| 2      | dict.copy()                        | Returns a shallow copy of dictionary dict                                      |
| 3      | dict.fromkeys()                    | Create a new dictionary with keys from seq and values set to value.            |
| 4      | dict.get(key, default=None)        | For key key, returns value or default if key not in dictionary                 |
| 5      | dict.has_key(key)                  | Returns true if key in dictionary dict, false otherwise                        |
| 6      | dict.items()                       | Returns a list of dict's (key, value) tuple pairs                              |
| 7      | dict.keys()                        | Returns list of dictionary dict's keys                                         |
| 8      | dict.setdefault(key, default=None) | Similar to get(), but will set dict[key]=default if key is not already in dict |
| 9      | dict.update(dict2)                 | Adds dictionary dict2's key-values pairs to dict                               |
| 10     | dict.values()                      | Returns list of dictionary dict's values                                       |

## Date & Time

Here's another fun time to enjoy with python. The guide is getting longer and boring I know, but this is a complete guide so this could get much worse. 'Boring' is not for the masters so lets delete it ;D

Now now no, what is this about. let me show you, python date and time operations are all about, you guessed it, date and time. we can get the current date and time in many many formats and also we can process older dates too.

#### What is Tick?
Time intervals are floating-point numbers in units of seconds. Particular instants in time are expressed in seconds since 12:00am, January 1, 1970(epoch). this is common for all main-stream programming languages and we have to deal with it.

The function time.time() returns the current system time in ticks since 12:00am, January 1, 1970(epoch). Use a print command to check it

first we have to import the time library, then we can proceed.

>       import time
>       print(time.time())

and You'll get some numbers.

#### What is TimeTuple?
This is getting much interesting now, let's talk about time tuple. Here, Many of Python's time functions handle time as a tuple of 9 numbers, as shown below

| Index | Field            | Values                                    |
| :---- | :--------------- | :---------------------------------------- |
| 0     | 4-digit year     | 2008                                      |
| 1     | Month            | 1 to 12                                   |
| 2     | Day              | 1 to 31                                   |
| 3     | Hour             | 0 to 23                                   |
| 4     | Minute           | 0 to 59                                   |
| 5     | Second           | 0 to 61 (60 or 61 are leap-seconds)       |
| 6     | Day of Week      | 0 to 6 (0 is Monday)                      |
| 7     | Day of year      | 1 to 366 (Julian day)                     |
| 8     | Daylight savings | -1, 0, 1, -1 means library determines DST |

Now you should pretty much comfortable with tuples aren't you? so I Don't think this is something hard for you to figure out. in case you didn't let me show you how to retrieve these digits.

The above tuple is equivalent to struct_time structure. This structure has following attributes

| Index | Attributes | Values                                    |
| :---- | :--------- | :---------------------------------------- |
| 0     | tm_year    | 2008                                      |
| 1     | tm_mon     | 1 to 12                                   |
| 2     | tm_mday    | 1 to 31                                   |
| 3     | tm_hour    | 0 to 23                                   |
| 4     | tm_min     | 0 to 59                                   |
| 5     | tm_sec     | 0 to 61 (60 or 61 are leap-seconds)       |
| 6     | tm_wday    | 0 to 6 (0 is Monday)                      |
| 7     | tm_yday    | 1 to 366 (Julian day)                     |
| 8     | tm_isdst   | -1, 0, 1, -1 means library determines DST |

#### Working with Dates and Times
Let's get down to the coding section. Here I'll show how to do the codings for some and you can figure out the rest for sure.

>       import time
>       localtime = time.localtime(time.time())
>       print(localtime)

And you'll get something like this.

>     time.struct_time(tm_year=2020, tm_mon=7, tm_mday=15, tm_hour=17, tm_min=27, tm_sec=19, tm_wday=2, tm_yday=197, tm_isdst=0)

Explaining the whole time.struct_time tuple. So let's deal with this now. I'm refering to the chart above and let's print out some dates.

>       import time
>       Year = time.localtime(time.time())[0]
>       Month = time.localtime(time.time())[1]
>       Day = time.localtime(time.time())[2]
>       Hour = time.localtime(time.time())[3]
>       Minuites = time.localtime(time.time())[4]
>       Seconds = time.localtime(time.time())[5]
> 
>       print("Today is %g/%g/%g and the time is %g:%g:%g " % (Day,Month,Year,Hour,Minuites,Seconds))

And The result will be

>       Today is 15/7/2020 and the time is 17:32:50

Something like this. This is my time period. And that's pretty much it for date and time.. Moving on.

## Functions
Let's speak about functions. These are the most important code sections of any programing language. The reason why is functions functionality, That's awkward to say but any how. Functions store some code in them and we can run that code section anytime we call a function. It could be a calculation or anything like that. And also we can pass values in variables so the function can preform more things dynamically.

#### Defining Functions
That's not hard at all, but first let me tell you something, most of the developer guides start with basic functions when teaching functions, but that's not my way so let's dig deeper with a huge step forward. This is the boilerplate for functions.

>       def <function-name>(<variables-to-pass>):
>           <statements>

And That's it you're a master of functions. but that's too little? yeah that's the hardest part. now let's explore a practical use case but first let me explain.
* def is the keyword to define functions
* < function-name > is where you put your function's name to call it with, start it with a simple (lowercase) letter and don't add spaces (It's an identifier)
* < variables-to-pass > can have several or infinite variables that we have to pass values to when we're calling the function
* < statements > Is where the code goes

Now here's an example for you

>       def printagreeting(name,age):
>           statement = "Hello There %s, " % (name)
>           if (age < 18):
>               statement += "You're %g aren't you cuty pie" % (age)
>           elif (age < 50):
>               statement += "You're %g and It's an age full of responsibities" % (age)
>           else:
>               statement += "You're an Old Man!"
>           print(statement)

Now It's done defining. Let's call and see how it works.

#### Calling Functions

For calling a function, you have to address it with the name it made followed by brackets and in those brackets, variables to pass. here we have two variables to pass, name and age. You can create functions without variables but you have to put brackets anyways something like

>       example()

or

>       <function-name>(<values>)

let's call our function we just made.

>       printagreeting("Tecinpact",22)

That's how you call it, and this should be printed out after that.

>       Hello There Tecinpact, You're 22 and It's an age full of responsibities

#### return value from a function

This is something important and this makes the function behaves in a way that's different from the above example. return makes the function returns a value so we can assign them in to a variable.

You can do anything with functions, and remember these make our lives easier than ever.

>       def printagreeting(name,age):
>           statement = "Hello There %s, " % (name)
>           if (age < 18):
>               statement += "You're %g aren't you cuty pie" % (age)
>           elif (age < 50):
>               statement += "You're %g and It's an age full of responsibities" % (age)
>           else:
>               statement += "You're an Old Man!"
>           return(statement)

did you noticed that I switched that print to a return? So now I can use the function as this.

>       returnedvalue = printagreeting("Tecinpact",22)

and the function now assigns the value to the returnedvalue variable. so we can use it in the program for something else than printing to the console.

## Reading data from user in the console

This is a short and simple but a compulsory part on programming, that's the user's input. so we can ask the user for inputs when the code running using raw_input method. Try this example to understand the capabilities.

>       str = raw_input("Enter your input: ")
>       print ("Received input is : %s", % (str))

This is short and sweet so you can see it for your self.

## Files I/O
Here we came to a part where we can write to files using python. If you're imaginative inough, you can even automate writing codes from other languages using the knowledge you gathered from this article. Let's start. Here, I'm only explaining what you really need, and nothing else.

Concept is simple, you have to open a file, read or write, then you can close it.

#### Opening and Closing Files

Simple as it seems, Python has a open and close function to do it, but opening is a bit different, you can use python to open in various modes, but one's you're really want it 
* r - for read only
* w - read and write but overwrites existing data
* a - for appending new lines.

Here's the complete list if you are interested in it.

| Sr.No. | Modes | Description                                                                                                                                                                                                                                |
| :----- | :---- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1      | r     | Opens a file for reading only. The file pointer is placed at the beginning of the file. This is the default mode.                                                                                                                          |
| 2      | rb    | Opens a file for reading only in binary format. The file pointer is placed at the beginning of the file. This is the default mode.                                                                                                         |
| 3      | r+    | Opens a file for both reading and writing. The file pointer placed at the beginning of the file.                                                                                                                                           |
| 4      | rb+   | Opens a file for both reading and writing in binary format. The file pointer placed at the beginning of the file.                                                                                                                          |
| 5      | w     | Opens a file for writing only. Overwrites the file if the file exists. If the file does not exist, creates a new file for writing.                                                                                                         |
| 6      | wb    | Opens a file for writing only in binary format. Overwrites the file if the file exists. If the file does not exist, creates a new file for writing.                                                                                        |
| 7      | w+    | Opens a file for both writing and reading. Overwrites the existing file if the file exists. If the file does not exist, creates a new file for reading and writing.                                                                        |
| 8      | wb+   | Opens a file for both writing and reading in binary format. Overwrites the existing file if the file exists. If the file does not exist, creates a new file for reading and writing.                                                       |
| 9      | a     | Opens a file for appending. The file pointer is at the end of the file if the file exists. That is, the file is in the append mode. If the file does not exist, it creates a new file for writing.                                         |
| 10     | ab    | Opens a file for appending in binary format. The file pointer is at the end of the file if the file exists. That is, the file is in the append mode. If the file does not exist, it creates a new file for writing.                        |
| 11     | a+    | Opens a file for both appending and reading. The file pointer is at the end of the file if the file exists. The file opens in the append mode. If the file does not exist, it creates a new file for reading and writing.                  |
| 12     | ab+   | Opens a file for both appending and reading in binary format. The file pointer is at the end of the file if the file exists. The file opens in the append mode. If the file does not exist, it creates a new file for reading and writing. |

#### The file Object Attributes
What are these? These are what you can do with these files. So, Let's Explore.

| Sr.No. | Attribute      | Description                                                            |
| :----- | :------------- | :--------------------------------------------------------------------- |
| 1      | file.closed    | Returns true if file is closed, false otherwise.                       |
| 2      | file.mode      | Returns access mode with which file was opened.                        |
| 3      | file.name      | Returns name of the file.                                              |
| 4      | file.softspace | Returns false if space explicitly required with print, true otherwise. |

Let's write some files then.

#### Write the file

Let's open a file using read and write with overwriting in the directory of the script.

>       file = open("thisIsAFile.txt", "w")

Now let's write some data to it.

>       file.write( "Hello World! This is a file written without a hand.")

Let's close it now.

>       file.close()

Let's read the file now,

#### Read the file

>       file = open("thisIsAFile.txt", "r")
>       fileText = file.read()
>       print(fileText)
>       file.close()

now the fileText variable holds what's inside the file.

#### Rename the file

It's Simple and straight forward. You have to import the os module first.

>       import os
>       os.rename(<current_file_name>, <new_file_name>)

Let's nome our file to another name

>       import os
>       os.rename("thisIsAFile.txt","anotherfile.txt")

#### Let's Delete the file

This is also a funtion of the os module so first we have to import it and then we can proceed

>       import os
>       os.remove("thisIsAFile.txt")

#### Let's explore some OS module functions which will get in handy

| Module      | Description                                                                                     | Usage               |
| :---------- | :---------------------------------------------------------------------------------------------- | :------------------ |
| os.mkdir()  | You can use the mkdir() method of the os module to create directories in the current directory. | os.mkdir("newdir")  |
| os.chdir()  | You can use the chdir() method to change the current directory.                                 | os.chdir("newdir")  |
| os.getcwd() | The getcwd() method displays the current working directory.                                     | os.getcwd()         |
| os.rmdir()  | The rmdir() method deletes the directory, which is passed as an argument in the method.         | os.rmdir('dirname') |

And You're Golden with File I/O

## Error handling
In programming, we run into all sorts of errors eventually, so we need a fool proof option to make the program run no matter what. So there's a simple boilerplate we can use

>       try:
>          You do your operations here.
>       except:
>          If there is any exception, then execute this block.
>       else:
>          If there is no exception then execute this block.
>       finally:
>          This would run always after everything above

Let's explore

You can add a try block and add you code in that, so if something went wrong it would brake the program there and run the except block. If there are no errors or so the else block will run, and finally block would always run it's code. you can ditch anything else the try block so it's something you can tailor to your needs.

## Object Oriented Python

This would be the final topic I'm covering in this series. This is a huge topic but I'm explaining briefly.

Classes are something like functions but they can have their own objects. for an example consider a class in a school, we'll assume that there is a class called "grade 2" whenever the headmaster says "come here g2" the grade 2 students have to stand up and say "I'm here". this is a imaginative exercise, so considering this case, the headmaster once gathered the whole school and said loudly, "Come here g2" and all of the grade 2 students said "I'm here". now this is a idiotic but a powerful story, no the moral of the story: class grade 2 is like the classes in python, they have certain functions to run whenever they were called, and the students of that class are like Objects in python. those objects has to obey and  follow the  class rules until they are in that class. and that's the main concept.

#### Defining classes

it's easy, you just have to use the class keyword followed by the class name and the code block

>       class <class-name>:
>           def __init__(self,<variables>):
>               <initialization-code>
>           <other-codes>

That init function in compulsory and this is where you write your initialization code of a class. let's dig deeper with an example with everything. I made this guide all by my self for you guys to make it easy to understand everything if you followed it correctly, if you have troubles even after this tutorial, follow it again with proper attention. If you got stucked, just contact me. 

now let's do something with it, I'm covering everything basic and you're imagination is the sky here.

Let's make a class for an animal clinic, it contains a class for dogs and cats, every animal that brings there must have an object of their own. someone brought there 2 dogs Saly and Mary also with 2 cats Pipi and Popo, mary had two injections previously.

Let's create a class forthem with a function to bark and meaw so we can make them bark and meaw anytime we want, also lets add another function to give them an Injection. Follow my code and most of them, you'll understand, I'll explain the basics and the hard parts, from this, you'll get to know how to create and ingerit classes with objects, how to call functions and store values for objects.

>       class dog:
>           def __init__(self, name, age, injections=0):
>               self.name = name
>               self.age = age
>               self.injections = injections
>       
>           def bark(self):
>               print("Woof Woof")
>       
>           def inject(self, times):
>               print("%s Injected %g times" % (self.name, times))
>               self.injections += times     
>       
>       class cat:
>           def __init__(self, name, age, injections=0):
>               self.name = name
>               self.age = age
>               self.injections = injections
>       
>           def meaw(self):
>               print("meaw meaw")
>       
>           def inject(self, times):
>               print("%s Injected %g times" % (self.name, times))
>               self.injections += times    
>       
>       Saly = dog("Saly", 2)
>       Mary = dog("Mary", 3, 2)
>       Pipi = cat("Pipi", 1)
>       Popo = cat("Popo", 5)
>       
>       Saly.bark()
>       Mary.inject(2)
>       Pipi.inject(1)
>       Popo.meaw()
>       
>       animals = [Saly, Mary, Pipi, Popo]
>       for pet in animals:
>           print("Name : ", pet.name)
>           print("age : ", pet.age)
>           print("injections : ", pet.injections)

Now this is a greate example on how classes and objects work, if you don't get it, I don't know what will, But, It's harder for beginners to get thesee concepts in their minds, so try and try. Let me explain What's going on here first.

First I made two classes with for cats and dogs. I'll explain from the begining, first I defined the class and defined it's first funciton __ init __ to initialize the class, that first argument self is must be there in every funcion you define in a class (you can see it). and I added extra 3 variables, name age and injections. I did something strange here, injection=0 adds a variable called injection and set's it's default value to 0 so if we didn't enter a value there, that variable will set to 0 by default. and in that init function, I made every variable define to it's local variable, This is called scoping and there are two scopes. global and local, you can use local variables to assign variables that are only accessable within that function or class, then there are global variables, which can be accesses by anywhere in the code. now you can create global variables in the code, everything that's not within a function, loop, class etc... are defined globally. after that ends, I made two more funcitons with bark and inject to print barking sound and incriment the injections and print that injected several times. It's the same for the cats also but I changed bark to meaw

After classes I made four variables and made them equal to the name of the function and passed the values defined in the __ init __ section and officially these variables are now objects. now I can call their function as I did after I assigning them, These would run their functions as usual.

Then I made a list of the objects called animals and added a for loop for each object in animals, here you can see in the results, that I accessed the values of the objects in it. and inspect carefully, this is the most simplest form I can imagine for object oriented python.

And the results are 

>       Woof Woof
>       Mary Injected 2 times
>       Pipi Injected 1 times
>       meaw meaw
>       Name :  Saly
>       age :  2
>       injections :  0
>       Name :  Mary
>       age :  3
>       injections :  4
>       Name :  Pipi
>       age :  1
>       injections :  1
>       Name :  Popo
>       age :  5
>       injections :  0

Run these examples for your self and see for your self.

# What's Next
Well, my friends, You are officially done with this course, you can attend a free test and get a certificate from us on this course, If you're interested, just use our mail tecinpactagencies@gmail.com to contact us. Also python is a huge programming language and there are so much more libraries modules and so much more for you to try out and learn, Explore the world and maybe you'll find your passion with this language.

# Conclusions
Here, I brought you a full python tutorial with examples that are easy to follow. It's a plesure to help beginers with their career but These tutorials take about 3-4 Days worth of work and so much effort and time, so It's greate if you can show some love by sharing these with others. Remember sharing is careing.