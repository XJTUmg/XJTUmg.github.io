---
layout: post
title: Notes of 《Beginning Python》 Chapter 5
date: 2017-01-12
tag: Python
---

Python is the best programming language.  

### Notes

{% highlight python %}

#!/usr/bin/python

import math

############################
#      Conditionals...     #
############################

x = y = [1, 2, 3]
z = [1, 2, 3]
x == y # True
x == z # True
x is y # True
x is z # False

age = 1
assert 0 < age < 100, 'The age must be realistic'
# program crashes when 0 < age < 100 is False, the string explains the assertion

# 'range' & 'xrange'
# 'range' creates the whole sequence, 'xrange' creates only one number at a time. 'xrange' is more useful.

names = ['a', 'bb', 'ccc']
ages = [1, 22, 33]
for name, age in zip(names, ages):
    print name, 'is', age, 'years old'
# 'for' loop && 'zip' function
# 'zip' function togethers the sequences, and returns a list of tuple.
for index, string in enumerate(names):
    if 'a' in string:
        names[index] = 'change'
# 'enumerate' function creates index-value tuple
for n in range(99, 81, -1):
    if n == (int)(math.sqrt(n)):
        print n
        break
else:
    print "Didn't find it!"
# 'else' only executed if you didn't call 'break', this example will execute 'else'

# list comprehension, here are some examples
print [x * x for x in range(10) if x % 3 == 0]
print [(x, y) for x in range(3) for y in range(3)]

pass # nothing happened
exec "print 'Hello World!'" # execute some code
# scope
scop = {}
exec 'sqrt = 1' in scop
print math.sqrt(4) # 'sqrt' in math
print scop['sqrt'] # 'sqrt' in scop
# eval
# 'eval' evaluates a Python expression
print eval('2 * 3 + (5 + 2) * 2')

{% endhighlight %}

# The Python Comparison Operators  
<dev align = "left">
  <img src="/images/posts/python5/1.png" height="401" width="594">
</dev>

# New Functions  
<dev align = "left">
  <img src="/images/posts/python5/2.png" height="426" width="798">
</dev>
