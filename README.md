# Python-course-1 Variables

 It's a lot easier in Python. There is no declaration of variables required in Python. It's not even possible. If there is need of a variable, you think of a name and start using it as a variable.

Another remarkable aspect of Python: Not only the value of a variable may change during program execution but the type as well. You can assign an integer value to a variable, use it as an integer for a while and then assign a string to the same variable.
In the following line of code, we assign the value 42 to a variable:i = 42 The equal "=" sign in the assignment shouldn't be seen as "is equal to". It should be "read" or interpreted as "is set to", meaning in our example "the variable i is set to 42". Now we will increase the value of this variable by 1: 

>> i = i + 1
 >>> print(i) 
43 
>>> 

As we have said above, the type of a variable can change during the execution of a script. Or to be precise: A new object, which can be of any type, will be assigned to it. We illustrate this in our following example:

i = 42			# data type is implicitly set to integer

 i = 42 + 0.11		# data type is changed to float 

i = "forty"		# and now it will be a string 

Python automatically takes care of the physical representation for the different data types, i.e. an integer values will be stored in a different memory location than a float or a string.Object ReferencesWe want to take a closer look on variables now. Python variables are references to objects, but the actual data is contained in the objects: As variables are pointing to objects and objects can be of arbitrary data type, variables cannot have types associated with them. This is a huge difference to C, C++ or Java, where a variable is associated with a fixed data type. This association can't be changed as long as the program is running. Therefore it is possible to write code like the following in 
Python: 
>>> x = 42

 >>> print(x)
 42

 >>> x = "Now x references a string"  

>>> print(x) 

Now x references a string

 We want to demonstrate something else now. Let's look at the following code: 

>>> x = 42 

>>> y = x

 We created an integer object 42 and assigned it to the variable x. After this we assigned x to the variable y. This means that both variables reference the same object. The following picture illustrates this: What will happen, when we execute
y = 78

after the previous code? Python will create a new integer object with the content 78 and then the variable y will reference this newly created object, as we can see in the following picture: Most probably, we will see further changes to the variables in the flow of our program. There might be for example a string assignment to the variable x. The previously integer object "42" will be orphaned after this assignment. It will be removed by Python, because no other variable is referencing it.
id FunctionYou may ask yourself, how can we see or prove that x and y really reference the same object after the assignment y = x of our previous example?

The identity function id() can be used for this purpose. Every instance (object or variable) has an identity, i.e. an integer which is unique within the script or program, i.e. other objects have different identities.
So, let's have a look at our previous examples and how the identities will change:
 >>> x = 42 

>>> id(x) 10107136 

>>> y = x 

>>> id(x), id(y) (10107136, 10107136) 

>>> y = 78 >>> id(x), id(y) (10107136, 10108288) >>> 
