---
layout: post
title: Notes of 《Beginning Python》 Chapter 4
date: 2017-01-05
tag: Python
---

Python is the best programming language.  

### Summary

**Mapping:** A mapping enables you to label its elements with any immutable object, the most usual types being strings and tuples. The only built-in mapping type in Python is the dictionary.  
**String formatting with dictionaries:** You can apply the string formatting operation to dictionaries by including names (keys) in the formatting specifiers. When using tuples in string formatting, you need to have one formatting specifier for each element in the tuple. When using dictionaries, you can have fewer specifiers than you have items in the dictionary.  
**Dictionary methods:**  Dictionaries have quite a few methods, which are called in the same way as list and string methods.  

### Notes

{% highlight python %}

#!/usr/bin/python

import copy
import math

############################
#       Dictionaries       #
############################

# dictionaries are written like this
phonebook = {'A' : '1', 'BB' : '2', 'CC' : '33'}
# silimar to 'map' in C++
# keys are unique within a dictionary
# keys may be of any immutable type

d = dict(name = 'Gumby', age = 42) # dict function
len(d) # the number of items
d['name'] # the value
d['name'] = 'mg' # change
del d['name'] # delete the item

print "BB's phone number is %(BB)s." % phonebook
# string formatting with dictionaries
# keys can only be strings
# very useful in template systems

d.clear() # remove all items
d['name'] = ['A', 'B', 'C']
cpyd = d.copy() # the original is unaffected
dcpyd = copy.deepcopy(d)
# copy all values and keys and store them in dcpyd
# need import copy
d = dict.fromkeys(['name', 'age'], 'unknown')
# create a new dict with the given keys, all values are 'unknown'(default is None)
d.get('name', 'N/A')
# similar to d['name']. If 'name' is a nonexistent key, will return 'N/A'(default is None)
d.has_key('name')
# 'has_key' checks whether a dictionary has a given key(False or True)
d.items() # returns all the items of the dictionary as a list of items in which each item is of the form(key, value)
d.iteritems() # similar to 'items', but returns an iterator instead of a list
d.keys()
d.iterkeys()
# similar to 'items' and 'iteritems', but returns all keys as a list
d.pop('name') # print d['name'] and remove it
d.popitem() # similar to 'pop'. 'popitem' choose an arbitrary item
d.setdefault('name', 'mg')
# similar to 'get'.when the key is missing, value is the default.Otherwise, is the value in dictionary
d.update({'name': 'wmg', 'birth': '0716'})
# 'update' updates one dictionary with the items of another
d.values() # similar to 'keys', but returns all the values of the dictionary as a list

{% endhighlight %}
