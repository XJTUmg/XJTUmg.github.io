---
layout: post
title: Notes of 《Beginning Python》 Chapter 1 ~ 2
date: 2017-01-02
tag: Python
---

Python is the best programming language.

### Chapter 1 ~ 2

#!/usr/bin/python

import math

############################
#          basic           #
############################

# plz use raw_input

x = 1
print "x = " + `x`

print 'C:\\now'
print r'C:\now' # raw string
# print r'C:\' will produce error
# print r'C:\\' is ok
print u'python' # Unicode string 16bit

lis = 'Hello'
print lis[-1] # loop

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print numbers[1 : 3] # will print [2, 3]
print numbers[ : 2]
print numbers[6 : ]
print numbers[0 : 10 : 2] # will print [1, 3, 5, 7, 9]
print numbers[8 : 3 : -1] # will print [9, 8, 7, 6, 5]
# print [1, 2, 3] + 'world' will produce error, different type
print 3 in numbers # will print True/False
print len(numbers), min(numbers), max(numbers) # will print '10 1 10'

name = list('Perl')
name[1 : ] = list('thon') # replace the slice
name[1 : 1] = list('y') # insert elements
print name # will print 'python'

############################
#  list: mutable sequences #
############################

lst = [1, 2, 3]
lst.append(4) # append 4 to the end of lst
lst.extend([3, 6]) # append a list to the end of lst
lst.count(3) # count the occurrences of an element in a list
lst.index(3) # find the index of the first occurrence of a value
lst.insert(2, 3) # insert(index, value)
lst.pop(0) # del an element (by default, the last one) and return it
lst.remove(3) # remove(value), only remove the first occurrence of the value
lst.reverse() # just reverse the element in the list
lst.sort() #sort doesn't return a list
lst = sorted(lst) # sorted return a list
name.sort(key = len) # sorted according to the len
lst.sort(reverse = True) #same as lst.sort() lst.reverse()

############################
#tuple: immutable sequences#
############################

tup1 = tuple([1, 2, 3]) #same as list
tup = (42, ) # must have comma
# the tuple function works in pretty much the same way as list
