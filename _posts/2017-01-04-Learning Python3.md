---
layout: post
title: Notes of 《Beginning Python》 Chapter 3
date: 2017-01-04
tag: Python
---

Python is the best programming language.

### Notes

{% highlight python %}

#!/usr/bin/python

import math

############################
#         strings          #
############################

#!!!!strings are immutable!!!!

form = "%s, %s"
vals = ('Hi', 'all')
print form % vals # string formatting, similar to 'scanf' in C
print '%-10.2f' % math.pi # (-) left-aligns the value
print '%+d' % 10 # (+) output a sign, will print '+10'
print '%.*s' % (5, '1234567') # (*) set the width

S = 'ababac'
S.find('ab') # return the leftmost index, if it is not found, -1 is returned
S.find('ab', 1, 4) # supplying start and end

seq = ['1', '2', '3', '4', '5']
sep = '+'
print sep.join(seq) # 'join' is the inverse of 'split', will print '1+2+3+4+5'

S = 'ABc'
print S.lower() # 'lower' returns a lowercase version of the string

S = 'ababac'
print S.replace('ab', 'c') # 'ab' replaced by 'c'

S = '1+2+3+4+5'
print S.split('+') # split a string into a sequence, default is spaces or tabs or newlines and so on

S = '123ab333cd321'
print S.strip('123') # remove the char in list where on the left and right of the string, default is spaces

{% endhighlight %}

### String Formatting Conversion Types
<img src="/images/posts/python3/1.png" height="724" width="738">  

### String Formatting Example
<img src="/images/posts/python3/2.png" height="871" width="657">  

