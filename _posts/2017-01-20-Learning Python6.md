---
layout: post
title: Notes of 《Beginning Python》 Chapter 6
date: 2017-01-20
tag: Python
---

Python is the best programming language.  

### Summary

**Abstraction:** Abstraction is the art of hiding unnecessary details. You can make your program more abstract by defining functions that handle the details.  
**Function definition:** Functions are defined with the def statement. They are blocks of statements that receive values (parameters) from the “outside world” and may return one or more values as the result of their computation.  
**Parameters:** Functions receive what they need to know in the form of parameters—variables that are set when the function is called. There are two types of parameters in Python: positional parameters and keyword parameters. Parameters can be made optional by giving them default values.  
**Scopes:** Variables are stored in scopes (also called namespaces). There are two main scopes in Python: the global scope and the local scope. Scopes may be nested.  
**Recursion:** A function can call itself—and if it does, it’s called recursion. Everything you can do with recursion can also be done by loops, but sometimes a recursive function is more readable.  
**Functional programming:** Python has some facilities for programming in a functional style. Among these are lambda expressions and the *map*, *filter*, and *reduce* functions.  

### Notes

{% highlight python %}

#!/usr/bin/python

import copy
import math

############################
#        Abstraction       #
############################

# use 'def' to creat a function
def hello(name):
    'Hello World!' # docstring, stored in '__doc__'
    return 'Hello, ' + name + '!'

print hello('mg')
print hello.__doc__

# two variables(n & names) refer to the same 'list'
def change(n):
    n[0] = 'bb'

names = ['aa', 'bb', 'cc']
change(names)
print names # will print '['bb', 'bb', 'cc']'

# to avoid this, copy the list
names = ['aa', 'bb', 'cc']
change(names[:]) # copy the list
print names # will print '['aa', 'bb', 'cc']'

# can modify only the parameter objects themselves
# can't rebind parameters or affect variables outside the function
def inc(x):
    return x + 1
a = 1
a = inc(a) # now, a = 2

# other way to call function
def hello1(greeting = 'Hello', name = 'Nobody'): # default
    return greeting + ', ' + name + '!'
print hello1(name = 'mg', greeting = 'Hello') # keyword parameters
print hello1(name = 'mg')
print hello1() # will print 'Hello, Nobody!'

# use '*' to gather up the rest of the positional parameters, tuple
def print_params(title, *params):
    print title
    print params
print_params('Params:', 1, 2, 3) # params = (1, 2, 3)

# '**' dictionaries
def print_params_2(title, *params, **dics):
    print title
    print params
    print dics
print_params_2('Params:', 1, 2, name = 'mg', birth = '0716')

# globals() return a dictionary which stored global variables
def combine(parameter):
    print parameter + globals()['parameter']
parameter = 'b'
combine('a') # will print 'ab'

# 'global' defines a global variables
x = 1
def change_global():
    global x
    x = x + 1
change_global()
print x # x = 2

# Recursion
def factorial(n):
    if (n == 1):
        return 1
    else:
        return n * factorial(n - 1)
print factorial(4)

# 'map' & 'filter' & 'reduce'
# in 'functools' module with Python3
map(str, range(10)) # equivalent to [str(i) for i in range(10)]
def func(x):
    return x.isalnum()
    # 'True' if variable 'x' only contains letters and numbers
seq = ['foo', 'x41', ' x', '**']
filter(func, seq) # return ['foo', 'x41']
                  # equivalent to [x for x in seq if x.isalnum()]
filter(lambda x: x.isalnum(), seq) # 'lambda' lets you define simple functions in-line
numbers = [1, 2, 3, 4, 5, 6, 7]
reduce(lambda x, y: x + y, numbers)
# 'reduce' conbines the first two elements of a sequence with a given function, combines the result with the third element, and so on until the entire sequence has been processed and a single result remains

{% endhighlight %}
