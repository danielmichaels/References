# Classes: Python

Classes are a fundamental building block in python and Object Orientated Programming more broadly. They allow the user to logically group data and functions in way that is easy to use. They can be thought of a *blueprints*; they show what data to pass and methods to act on that data. But, the class does not do anything with this information until called upon.

Functions are called **methods**

Extending the *blueprint* analogy a bit. In construction, a builder could make several houses of the same design by following a blueprint. Also, he could make small changes to each home by altering the original blueprint only slightly. But until a builder comes along to materialise the blueprint it remains just a design outline. This is the same in Python classes. Each class must be 'created' which in software is known as instantiation. And like a builder, sometimes we can omit, add or change some of the original design to suit our needs. 

```PYTHON

class Employee:
	pass
```
To create a class we just use the keyword `class` and name it. In python3 we do not need to add arguments to the base class as shown above -- python2 is different.


The newly coded Employee class is now sitting around and doing nothing; it is not yet instantiated. 

```PYTHON
employee1 = Employee() # this creates (instantiates it)
# nothing prints to screen...

employee1.age = 55 # give our instance an attribute of 'age' and its value of integer 55


print(employee1.age)
# returns 55
``` 

Now we have instantiated Employee and given it some attributes. But this is very brittle and really offers us nothing above what a normal function would.

Inside the class we can call a special method (function that lives inside a class) call `__init__`. It is often referred to as the 'constructor'. The `__init__` method allows us to set default values without explicitly doing so when we instantiate the class later. 

```PYTHON

class Employee:

	def __init__(self):
		pass
```

Above we have created the `__init__` method. It contains the word `self`. This is a reference to.. itself, or the instance in which it will constructed in the future. This will be better explained shortly.

To pass variables to the `__init__` method is similar to normal functions.

```PYTHON
class Employee:

	def __init__(self, name, pay, age):
		self.name = name
		self.pay = pay
		self.age = age
```

In the above code block we added several variables to our `__init__` method. Again, we use the `self` attribute. Why does each value look like:

```
self.value = value
```
This means that for each instance created, the `value` passed in during its creation is unique to that instance and callable. 

```PYTHON
class Test:
	def __init__(self, words):
		self.words = words

test = Test('things')
```

So `self` is basically the same as saying `test.words = words` inside each class *once* it is instantiated. But doing that individually for each instance of  class would defeat the purpose of classes!


```PYTHON
class Employee:

	def __init__(self, name, pay, age):
		self.name = name
		self.pay = pay
		self.age = age
		self.email = name + '@example.com'
```