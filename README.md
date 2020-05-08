#Crash Course on Python final project

We've covered a bunch of String class methods already, so let's keep building on those and run down some more advanced methods.
The string method lower will return the string with all characters changed to lowercase. The inverse of this is the upper method, which will return the string all in uppercase. Just like with previous methods, we call these on a string using dot notation, like "this is a string".upper(). This would return the string "THIS IS A STRING". This can be super handy when checking user input, since someone might type in all lowercase, all uppercase, or even a mixture of cases.
You can use the strip method to remove surrounding whitespace from a string. Whitespace includes spaces, tabs, and newline characters. You can also use the methods  lstrip and rstrip to remove whitespace only from the left or the right side of the string, respectively.
The method count can be used to return the number of times a substring appears in a string. This can be handy for finding out how many characters appear in a string, or counting the number of times a certain word appears in a sentence or paragraph.
If you wanted to check if a string ends with a given substring, you can use the method endswith. This will return True if the substring is found at the end of the string, and False if not.
The isnumeric method can check if a string is composed of only numbers. If the string contains only numbers, this method will return True. We can use this to check if a string contains numbers before passing the string to the int() function to convert it to an integer, avoiding an error. Useful!
We took a look at string concatenation using the plus sign, earlier. We can also use the join method to concatenate strings. This method is called on a string that will be used to join a list of strings. The method takes a list of strings to be joined as a parameter, and returns a new string composed of each of the strings from our list joined using the initial string. For example, " ".join(["This","is","a","sentence"]) would return the string "This is a sentence".
The inverse of the join method is the split method. This allows us to split a string into a list of strings. By default, it splits by any whitespace characters. You can also split by any other characters by passing a parameter.



String Reference Cheat Sheet
In Python, there are a lot of things you can do with strings. In this cheat sheet, you’ll find the most common string operations and string methods.
String operations
    • len(string) Returns the length of the string
    • for character in string Iterates over each character in the string
    • if substring in string Checks whether the substring is part of the string
    • string[i] Accesses the character at index i of the string, starting at zero
    • string[i:j] Accesses the substring starting at index i, ending at index j-1. If i is omitted, it's 0 by default. If j is omitted, it's len(string) by default.
String methods
    • string.lower() / string.upper() Returns a copy of the string with all lower / upper case characters
    • string.lstrip() / string.rstrip() / string.strip() Returns a copy of the string without left / right / left or right whitespace
    • string.count(substring) Returns the number of times substring is present in the string
    • string.isnumeric() Returns True if there are only numeric characters in the string. If not, returns False.
    • string.isalpha() Returns True if there are only alphabetic characters in the string. If not, returns False.
    • string.split() / string.split(delimiter) Returns a list of substrings that were separated by whitespace / delimiter
    • string.replace(old, new) Returns a new string where all occurrences of old have been replaced by new.
    • delimiter.join(list of strings) Returns a new string with all the strings joined by the delimiter






If the placeholders indicate a number, they’re replaced by the variable corresponding to that order (starting at zero).


# "{0} {1}".format(first, second)

first = "apple"
second = "banana"
third = "carrot"

formatted_string = "{0} {2} {1}".format(first, second, third)

print(formatted_string)

"""Outputs:
apple carrot banana
"""




Formatting expressions
Expr
Meaning
Example
{:d}
integer value
'{:d}'.format(10.5) → '10'
{:.2f}
floating point with that many decimals
'{:.2f}'.format(0.5) → '0.50'
{:.2s}
string with that many characters
'{:.2s}'.format('Python') → 'Py'
{:<6s}
string aligned to the left that many spaces
'{:<6s}'.format('Py') → 'Py    '
{:>6s}
string aligned to the right that many spaces
'{:<6s}'.format('Py') → '    Py'
{:^6s}
string centered in that many spaces
'{:^6s}'.format('Py') → '  Py '






Old string formatting (Optional)
The format() method was introduced in Python 2.6. Before that, the % (modulo) operator could be used to get a similar result. While this method is no longer recommended for new code, you might come across it in someone else's code. This is what it looks like:
"base string with %s placeholder" % variable
The % (modulo) operator returns a copy of the string where the placeholders indicated by %  followed by a formatting expression are replaced by the variables after the operator.
"base string with %d and %d placeholders" % (value1, value2)
To replace more than one value, the values need to be written between parentheses. The formatting expression needs to match the value type.
"%(var1) %(var2)" % {var1:value1, var2:value2}
Variables can be replaced by name using a dictionary syntax (we’ll learn about dictionaries in an upcoming video).
"Item: %s - Amount: %d - Price: %.2f" % (item, amount, price)
The formatting expressions are mostly the same as those of the format() method. 
Check out the official documentation for old string formatting.
Formatted string literals (Optional)
This feature was added in Python 3.6 and isn’t used a lot yet. Again, it's included here in case you run into it in the future, but it's not needed for this or any upcoming courses.
A formatted string literal or f-string is a string that starts with 'f' or 'F' before the quotes. These strings might contain {} placeholders using expressions like the ones used for format method strings.
The important difference with the format method is that it takes the value of the variables from the current context, instead of taking the values from parameters.
Examples:
>>> name = "Micah"
>>> print(f'Hello {name}')
Hello Micah
>>> item = "Purple Cup"
>>> amount = 5
>>> price = amount * 3.25
>>> print(f'Item: {item} - Amount: {amount} - Price: {price:.2f}')
Item: Purple Cup - Amount: 5 - Price: 16.25
Check out the official documentation for f-strings.



enumerate()

f you want to access the elements in a list, along with the index of the element in question? You can do this using the enumerate() function. The enumerate() function takes a list as a parameter and returns a tuple for each element in the list. The first value of the tuple is the index and the second value is the element itself.


list comprehension
You can also use conditionals with list comprehensions to build even more complex and powerful statements. You can do this by appending an if statement to the end of the comprehension. For example, [ x for x in range(1,101) if x % 10 == 0 ] would generate a list containing all the integers divisible by 10 from 1 to 100. The if statement we added here evaluates each value in the range from 1 to 100 to check if it’s evenly divisible by 10. If it is, it gets added to the list.



Lists and Tuples Operations Cheat Sheet
Lists and tuples are both sequences, so they share a number of sequence operations. But, because lists are mutable, there are also a number of methods specific just to lists. This cheat sheet gives you a run down of the common operations first, and the list-specific operations second.
Common sequence operations
    • len(sequence) Returns the length of the sequence
    • for element in sequence Iterates over each element in the sequence
    • if element in sequence Checks whether the element is part of the sequence
    • sequence[i] Accesses the element at index i of the sequence, starting at zero
    • sequence[i:j] Accesses a slice starting at index i, ending at index j-1. If i is omitted, it's 0 by default. If j is omitted, it's len(sequence) by default.
    • for index, element in enumerate(sequence) Iterates over both the indexes and the elements in the sequence at the same time
Check out the official documentation for sequence operations.
List-specific operations and methods
    • list[i] = x Replaces the element at index i with x
    • list.append(x) Inserts x at the end of the list
    • list.insert(i, x) Inserts x at index i
    • list.pop(i) Returns the element a index i, also removing it from the list. If i is omitted, the last element is returned and removed.
    • list.remove(x) Removes the first occurrence of x in the list
    • list.sort() Sorts the items in the list
    • list.reverse() Reverses the order of items of the list
    • list.clear() Removes all the items of the list
    • list.copy() Creates a copy of the list
    • list.extend(other_list) Appends all the elements of other_list at the end of list
Most of these methods come from the fact that lists are mutable sequences. For more info, see the official documentation for mutable sequences and the list specific documentation.
List comprehension
    • [expression for variable in sequence] Creates a new list based on the given sequence. Each element is the result of the given expression.
    • [expression for variable in sequence if condition] Creates a new list based on the given sequence. Each element is the result of the given expression; elements only get added if the condition is true.





Dictionary Methods Cheat Sheet
Definition
x = {key1:value1, key2:value2}
Operations
    • len(dictionary) - Returns the number of items in the dictionary
    • for key in dictionary - Iterates over each key in the dictionary
    • for key, value in dictionary.items() - Iterates over each key,value pair in the dictionary
    • if key in dictionary - Checks whether the key is in the dictionary
    • dictionary[key] - Accesses the item with key key of the dictionary
    • dictionary[key] = value - Sets the value associated with key
    • del dictionary[key] - Removes the item with key key from the dictionary
Methods
    • dict.get(key, default) - Returns the element corresponding to key, or default if it's not present
    • dict.keys() - Returns a sequence containing the keys in the dictionary
    • dict.values() - Returns a sequence containing the values in the dictionary
    • dict.update(other_dictionary) - Updates the dictionary with the items coming from the other dictionary. Existing entries will be replaced; new entries will be added.
    • dict.clear() - Removes all the items of the dictionary
Check out the official documentation for dictionary operations and methods.


OOP :

In object-oriented programming, concepts are modeled as classes and objects. An idea is defined using a class, and an instance of this class is called an object. Almost everything in Python is an object, including strings, lists, dictionaries, and numbers. When we create a list in Python, we’re creating an object which is an instance of the list class, which represents the concept of a list. Classes also have attributes and methods associated with them. Attributes are the characteristics of the class, while methods are functions that are part of the class.







DOCSTRING :

>>> class Apple:
...     def __init__(self, color, flavor):
...         self.color = color
...         self.flavor = flavor
...     def __str__(self):
...         return "This apple is {} and its flavor is {}".format(self.color, self.flavor)
... 
>>> help(Apple)
Help on class Apple in module __main__:

class Apple(builtins.object)
 |  Methods defined here:
 |  
 |  __init__(self, color, flavor)
 |      Initialize self.  See help(type(self)) for accurate signature.
 |  
 |  __str__(self)
 |      Return str(self).
 |  
 |  ----------------------------------------------------------------------
 |  Data descriptors defined here:
 |  
 |  __dict__
 |      dictionary for instance variables (if defined)
 |  
 |  __weakref__
 |      list of weak references to the object (if defined)




>>> def to_seconds(hours, minutes, seconds):
...     """Returns the amount of seconds in the given hours, minutes and seconds."""
...     return hours*3600+minutes*60+seconds
... 



Classes and Methods Cheat Sheet
In the past few videos, we’ve seen how to define classes and methods in Python. Here, you’ll find a run-down of everything we’ve covered, so you can refer to it whenever you need a refresher.
Defining classes and methods

class ClassName:
    def method_name(self, other_parameters):
        body_of_method


Classes and Instances
    • Classes define the behavior of all instances of a specific class.
    • Each variable of a specific class is an instance or object.
    • Objects can have attributes, which store information about the object.
    • You can make objects do work by calling their methods.
    • The first parameter of the methods (self) represents the current instance.
    • Methods are just like functions, but they can only be used through a class.
Special methods
    • Special methods start and end with __.
    • Special methods have specific names, like __init__ for the constructor or __str__ for the conversion to string.
Documenting classes, methods and functions
    • You can add documentation to classes, methods, and functions by using docstrings right after the definition. Like this:

class ClassName:
    """Documentation for the class."""
    def method_name(self, other_parameters):
        """Documentation for the method."""
        body_of_method
        
def function_name(parameters):
    """Documentation for the function."""
    body_of_function


Inheritage:


>>> class Animal:
...     sound = ""
...     def __init__(self, name):
...         self.name = name
...     def speak(self):
...         print("{sound} I'm {name}! {sound}".format(
...             name=self.name, sound=self.sound))
... 
>>> class Piglet(Animal):
...     sound = "Oink!"
... 
>>> class Cow(Animal):
...     sound = "Moooo"
…

>>> hamlet = Piglet("Hamlet")
>>> hamlet.speak()
Oink! I'm Hamlet! Oink!
... 
>>> class Cow(Animal):
...     sound = "Moooo"
... 
>>> milky = Cow("Milky White")
>>> milky.speak()
Moooo I'm Milky White! Moooo



In this code, we've defined a general class called animal, which has an attribute to store the sound that the animal makes. The constructor of the class takes the name that will be assigned to the instance when it's created. There's also a speak method that prints the name of the animal together with the sound the animal makes. Then, we have a piglet class that inherits from the animal class. We set the value of the sound attribute to oink in the piglet class, and that's the only thing we've modified from the original.Everything else is inherited.









OBJECT COMPOSITION:

You can have a situation where two different classes are related, but there is no inheritance going on. This is referred to as composition -- where one class makes use of code contained in another class. For example, imagine we have a Package class which represents a software package. It contains attributes about the software package, like name, version, and size. We also have a Repository class which represents all the packages available for installation. While there’s no inheritance relationship between the two classes, they are related. The Repository class will contain a dictionary or list of Packages that are contained in the repository. Let's take a look at an example Repository class definition:

>>> class Repository:
...      def __init__(self):
...          self.packages = {}
...      def add_package(self, package):
...          self.packages[package.name] = package
...      def total_size(self):
...          result = 0
...          for package in self.packages.values():
...              result += package.size
...          return result



Project goal 
Create a dictionary with words and word frequencies that can be passed to the generate_from_frequencies function of the WordCloud class.
Once you have the dictionary, use this code to generate the word cloud image:


cloud = wordcloud.WordCloud()
cloud.generate_from_frequencies(frequencies)
cloud.to_file("myfile.jpg")

Things to remember 
    • Before processing any text, you need to remove all the punctuation marks. To do this, you can go through each line of text, character-by-character, using the isalpha() method. This will check whether or not the character is a letter.
    • To split a line of text into words, you can use the split() method.
    • Before storing words in the frequency dictionary, check if they’re part of the "uninteresting" set of words (for example: "a", "the", "to", "if"). Make this set a parameter to your function so that you can change it if necessary.
Input file
For the input file, you need to provide a file that contains text only. For the text itself, you can copy and paste the contents of a website you like. Or you can use a site like Project Gutenberg to find books that are available online. You could see what word clouds you can get from famous books, like a Shakespeare play or a novel by Jane Austen.
Jupyter Notebooks Help
Remember that if you need help with Jupyter Notebooks, you can check out this help page.

