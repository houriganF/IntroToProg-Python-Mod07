# Pickling & Error Handling in Python
**Dev:** *FHourigan*  
**Date:** *02/24/2023*  

## Introduction
### This week we explored the process of reading, writing, appending data from the memory into a file using a custom function. Python actually has several ways to read data from a file; each option has its own best use case. We also took note of the behavior of the cursor and how it can be baked into certain functions. We also introduced the concept of declaring the variable in python only when you need it. The nuances of python are starting to become clearer. It is more forgiving than some other languages. An example is the declaring of a variable inside or outside of a while loop doesn’t change or isolate it from the rest of the code. But this also can be more confusing, in the choices that you have to make when writing your script in python. You need to make the choices and be consistent, to keep things straight for yourself and others. 
## Working with Data in Text Files
### We were given a variety of examples of how you can read, write, and append data using lists, tuples, and dictionaries in both a “while loop” and a “for loop”. Then we were set free to start to write our own python script from scratch. Though the syntax and organizational theory for python are starting to click for me, the intricacies of how to use the code in practice is still challenging to me. For example, when creating my own function, I begin with the sections of concern and the basic functions that we have been using and have learned thus far. However, as I put the code blocks together the errors in my code when I try to run it are difficult for me to fix. Using the debugger is not always clear on what the error is.
## Binary Files – “Pickling”
### The Pickling module is specific to Python and is an existing module that allows you to read and write to binary files. Binary files are another option for working with data in a file. Binary files cannot be opened with a program like notebook or word because they are obscured or unreadable. They are also smaller in their space requirements. We were then tasked with researching this on our own. I found this description on the Python documentation page of the write function of pickling and the load function of unpickling:
```
      pickle.dump(obj, file, protocol=None, *, fix_imports=True, buffer_callback=None)
# Write the pickled representation of the object obj to the open file object file. This is equivalent to Pickler(file, protocol).dump(obj).“ 
      pickle.load(file, *, fix_imports=True, encoding='ASCII', errors='strict', buffers=None)
# Read the pickled representation of an object from the open file object file and return the reconstituted object hierarchy specified therein. 
# This is equivalent to Unpickler(file).load().”
```
### Binary files must be converted by a program to make it readable by a human. You can also load the data from the file in python and then it is turned back into readable data in memory that then can be written to a text file. 

## Try / Except – Error Handling
### Another useful trick for writing our own scripts that we had touched on before, was the use of the Try/Except block of code. This is useful for when you have humans entering data and they can potentially break things by putting in code-breaking inputs. The example given was dividing by zero. You can nest the unique error options within the except sections of the code. The “Exception” block that is more generalized acts as a catch all and will capture all other errors. It makes sense that this exception block must go last, after the other nested except blocks specific to a class. This error handling can be useful if you can anticipate the kind of inputs that will possibly generate an error. Luckily the main ones are already in the documentation for you. While researching pickling I found in the python documentation the common errors for using the pickle module. When writing the code for this week’s assignment, I incorporated these common exceptions into my script. They are as follows:
```
# The pickle module defines three exceptions: 
      exception pickle.PickleError
# Common base class for the other pickling exceptions. It inherits Exception.
      exception pickle.PicklingError
# Error raised when an unpicklable object is encountered by Pickler. It inherits PickleError.
# Refer to What can be pickled and unpickled? to learn what kinds of objects can be pickled.
      exception pickle.UnpicklingError
# Error raised when there is a problem unpickling an object, such as a data corruption or a security violation. It inherits PickleError.
# Note that other exceptions may also be raised during unpickling, including (but not necessarily limited to) AttributeError, EOFError, ImportError, and IndexError.
```

## My Code:

![alt text](https://github.com/houriganF/IntroToProg-Python-Mod07/docs/Code1.jpg?raw=true)

### Figure 7.1: The Script Header, Data, and Processing Sections

