---
title: Python Notebook
permalink: /Python/
classes: defualt
excerpt: "My Personal Python Notebook that contains the basic conepts needed for Python Programming, This is a edited version of coodict-python3-in-one-pic"
toc: true
toc_sticky: true
toc_icon: angle-right
toc_label: show table-of-contents
---
This is my personal Python Notebook that I used when I studied the JNCIA-DevOps exam, The primary content on this page was from [coodict/python3-in-one-pic](https://github.com/coodict/python3-in-one-pic) and I just added and edited some information for me to understand more about Python Programming. Other resources was based on the books and videos I shared on this post [What are my resources to pass the JNCIA-DevOps and how did I get it for FREE?](https://divide-and-conquer.network/networking%20automation/What-are-my-resources-to-pass-the-JNCIA-DevOps-and-how-did-I-get-it-for-FREE/)

**NOTE:** This post still needs a lot of changes.
{: .notice--danger}

**In:**
```python
import this
```
**Out:**
    
    The Zen of Python, by Tim Peters
    
    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!
    
**[The Hitchhiker’s Guide to Python!](https://docs.python-guide.org/)**

# What is Python:
 - A high-level application programming language
 - Has many modules and libraries available
 - Automatic memory management
 - Flexibly supports multiple programming paradigms
 - Cross platform
 - Python is an interpreted programming language - No compilation phase is necessary, Programming file is translated into byte code before execution, Byte code is interpreted in python virtual machine.
 
# Why Python for Network Engineers
 - Readable and easy to learn since Python is a dynamically typed language that allows you to create and use Python objects (such as variables and functions) 
 - Widely available and Open Source
 - Many relevant code samples and lots of training resources
 - Lots of training resources

# Statements
 - In General a Python statement does something
 - Satements are often composed of expressions
 - The Strict definition: "A statement can be thought of as the smallest standalone element of an imperative programming language"
 
# Basic Statement Examples
 - print("hello")
 - if x: do_y()
 - return

# Expressions
 - In General expressions can be reduced to some kind of value
 - A statement cannot be part of an expression. Expression is part of a statement
 - for example, "if x = 5:" is not a legal expression, bec assignment is a statement
 
# Basic Statement Examples
 - 3 + 3
 - range(4)
 - [x*2 for x in range()]
list comprehensions are considered expressions, but they also have looping constructions, so they also "do something"

# Difference between comments in python # and “”"
- Comments start with # and are not part of the code.
- String (delimited by """ """) is actually called a docstring and is used on special places for defined purposes (briefly: first thing in module or function describing the module or function) and is actually accessible in the code (so it is a part of the program, it is not a comment).
Ex. 
>>> def my_function():
...  """The function's docstring"""
... 
>>> help(my_function)

        Help on function my_function in module __main__:

my_function()
    The function's docstring



# Helpful Interactive Python Commands
- dir() = return a variable, classes, objects (collectively called "names") available
- dir(name) = return attributes for an object
- help(name) = Built-in help system. Displays docs and info for object


# Python Libraries (Modules, Applications, etc)
- Any python code outside of your script you want to use
- Provide some capability or data you need
- Included with statements ex:
  - from library import name
  - import library


# Python built-in types or Native Data Types
Python has several standard types built in to the interpreter:
 - **None:** The Null object or denotes an object with no value.
 - **Numerics:** int, long, float, complex, and bool (the subclass of int with a True or False value)
 - **Sequences:** str, list, tuple, and range (Sequences are ordered sets of objects/values with an index of non-negative integers. Sometimes it surprises people that string is actually a sequence type. But if you look closely, strings are a series of characters put together)
 - **Mappings:** dict (Python provides one mapping type, called the dictionary, it contains objects that can be indexed by keys. This is often referred to as the associated array or hashing table in other languages. This is a powerful type, because you can refer to the object with a human-readable key. This key will make more sense for the poor guy who is trying to maintain and troubleshoot the code. That guy could be you only a few months after you wrote the code. The object in the dictionary value can also be another data type, such as a list. )
 - **Sets:** set and frozenset (A set is used to contain an unordered collection of objects. Unlike lists and tuples, sets are unordered and cannot be indexed by numbers. But there is one character that makes sets standout as useful: the elements of a set are never duplicated. Ex. duplicate IPs)



# Mutable vs Immutable Objects
**Mutable** - an object that can change its state or contents after it is created
- list, dict, set, byte array

**Immutable** - an object can't be change
Can be check using the built-in function **id()**
- int, float, complex, string, tuple, frozen set [note: immutable version of set], bytes

# I. Native DataTypes
## Number

**In:**
```python

## integer (immutable)
a = 1
b = 0x10            # 16
print(type(a))      # <class 'int'>
```
**Out:**

    <class 'int'>
    

**In:**
```python

## float (immutable)
c = 1.2
d = .5              # 0.5
g = .314e1          # 3.14
print(type(g))      # <class 'float'>
```
**Out:**

    <class 'float'>
    

**In:**
```python
## complex
e = 1+2j
f = complex(1, 2)
print(type(e))      # <class 'complex'>
print(f == e)       # True
```
**Out:**

    <class 'complex'>
    True
    

**In:**
```python
## Operators: + - * / ** // %
print(1 + 1) #addition

print(2 - 2) #substraction

print(3 * 3) #multiplication

print(2 ** 10) #square or exponent

print(5 / 4) #division

print(5 // 4) #exlude the floating point number

print(346 % 7) #returns the remainder after dividing two numbers
## Additional operators: == , != , >= , in , and
a = 2
b = 3
print(a == b) #equal to
print(a != b) #not equal to
print(b >= a) #greater than

my_list = [1,2,3]
print(a in my_list) #'in' to check for containment a=2
print(5 > 3 and 'w' in 'word')
```
**Out:**

    2
    0
    9
    1024
    1.25
    1
    3
    False
    True
    True
    True
    True
    

**In:**
```python
## Casting
### Integer -> Float
print(float.__doc__)

print(float(3))
print(3 / 1)
print(float("3.14"))
```
**Out:**

    float(x) -> floating point number
    
    Convert a string or number to a floating point number, if possible.
    3.0
    3.0
    3.14
    

**In:**
```python
### Float -> Integer
print(int.__doc__)
```
**Out:**

    int(x=0) -> integer
    int(x, base=10) -> integer
    
    Convert a number or string to an integer, or return 0 if no arguments
    are given.  If x is a number, return x.__int__().  For floating point
    numbers, this truncates towards zero.
    
    If x is not a number or if base is given, then x must be a string,
    bytes, or bytearray instance representing an integer literal in the
    given base.  The literal can be preceded by '+' or '-' and be surrounded
    by whitespace.  The base defaults to 10.  Valid bases are 0 and 2-36.
    Base 0 means to interpret the base from the string as an integer literal.
    >>> int('0b100', base=0)
    4
    

**In:**
```python
print(int(3.14))               # 3
print(int("3", base = 10))     # 3
print(int("1010", base = 2))   # 10
print(int("0b1010", base = 0)) # 10
```
**Out:**

    3
    3
    10
    10
    

## Boolean

**In:**
```python
True
False
print(type(True))   # <class 'bool'>
```
**Out:**

    <class 'bool'>
    

## None

**In:**
```python
print(None is None) # True
print(type(None))   # <class 'NoneType'>
```
**Out:**

    True
    <class 'NoneType'>
    

## Byte

**In:**
```python
# Byte
## 0-255/x00-xff
byt = b'abc'
print(type(byt))    # <class 'bytes'>
print(byt[0] == 'a')# False
print(byt[0] == 97) # True
```
**Out:**

    <class 'bytes'>
    False
    True
    

**In:**
```python
## Length
print(len(byt))     # 3
```
**Out:**

    3
    

## String (immutable)

**In:**
```python
s1 = 'Chrisz'
s2 = "Network Automation"
s3 = """
Hello,
All!
"""
print(type(s1))     # <class 'str'>
print("\n%s, %s, %s" % (s1, s2, s3))

#Using variables inside strings (%s vs format)
print ("Hi I\'m %s, I love learning %s" % (s1, s2))
print ("Hi I\'m {}, I love learning {}".format(s1, s2))
```
**Out:**

    <class 'str'>
    
    chrisz, network, 
    Hello,
    All!
    
    Hi I'm chrisz, I love learning network
    Hi I'm chrisz, I love learning network
    
## Qutes on a string
**In:**
```python
print("a double quoted string")
print('a single quoted string')
print('a single quoted string with "double quotes"')
print('a single quoted string with \'single quotes\'')
print("a double quoted string with 'single quotes'")
print("a double quoted string with \"double quotes\"")
```
**Out:**

    a double quoted string
    a single quoted string
    a single quoted string with "double quotes"
    a single quoted string with 'single quotes'
    a double quoted string with 'single quotes'
    a double quoted string with "double quotes"
    

**In:**
```python
## Length
print(len(s1))      # 6
```
**Out:**

    6
    
## Slicing 
- used to extract a substring
Note that index starts at 0. Therefore, the index 1 is actually the second element in the sequence.

**In:**
```python
s = 'study and practice'
print('{0}:{1}'.format(s[:5], s[-8:]))    # study:practice
#{0} it is the = s[:5] and the {1} is the = s[-8:] 
```
**Out:**

    study:practice
    
## Operator: + * and replacing a string
**In:**
```python

print("abc" + "." + "xyz")
print("abc"*3)

s1 = "Christian"
replaced1 = s1.replace('Christian', 'Philip')
print(replaced1)
```
**Out:**

    abc.xyz
    abcabcabc
    Philip
    
## upper() and lower()
**In:**
```python
interface = "Ethernet"
print(interface.lower())
print(interface.upper())
print(interface.capitalize())
```

    ethernet
    ETHERNET
    Ethernet
    
## startswith() and endswith()
**In:**
```python
ipadd = '10.1.1.2'
print(ipadd.startswith('10'))
print(ipadd.endswith('3'))

## other methods can be use are strip() , isdigit(10) = True , count()
```
**Out:**

    True
    False
    
## Casting
**In:**
```python
print(str.__doc__)

print(str(3.14))
print(str(3))
print(str([1,2,3]))
print(str((1,2,3)))
print(str({1,2,3}))
print(str({'python': '*.py', 'javascript': '*.js'}))
```
**Out:**

    str(object='') -> str
    str(bytes_or_buffer[, encoding[, errors]]) -> str
    
    Create a new string object from the given object. If encoding or
    errors is specified, then the object must expose a data buffer
    that will be decoded using the given encoding and error handler.
    Otherwise, returns the result of object.__str__() (if defined)
    or repr(object).
    encoding defaults to sys.getdefaultencoding().
    errors defaults to 'strict'.
    3.14
    3
    [1, 2, 3]
    (1, 2, 3)
    {1, 2, 3}
    {'python': '*.py', 'javascript': '*.js'}
    

# List vs Sets vs Tuples
- list are mutable, can be modified, individual elements can be accessed directly, and can have duplicate values.
- sets are mutable, can be modified, individual elements cannot be accessed directly, and cannot have duplicate values.
- tuples are immutable(sort of), cannot be updated or modified once created, individual elements can be accessed directly, and can have duplicate values.

## List

**In:**
```python
l = ['python', 3, 'in', 'one']
print(type(l))      # <class 'list'>
```
**Out:**

    <class 'list'>
    
### Length
**In:**
```python
print(len(l))       # 4 elements
```
**Out:**

    4
    
### Slicing on list
**In:**
```python
print(l[0])         # 'python'
print(l[-1])        # 'one'
print(l[1:-1])      # [3, 'in']
```
**Out:**

    python
    one
    [3, 'in']
    
### Manipulate contets on a list: append(), insert(), extend(), pop(), remove(), del, index(), sorted(), sort()
**In:**
```python
l.append('pic')     # None
print(l)
# l == ['python', 3, 'in', 'one', 'pic']

l.insert(2, '.4.1') # None
print(l)
# l == ['python', 3, '.4.1', 'in', 'one', 'pic']

l.extend(['!', '!'])
print(l)
# l == ['python', 3, '.4.1', 'in', 'one', 'pic', '!', '!']
```
**Out:**

    ['python', 3, 'in', 'one', 'pic']
    ['python', 3, '.4.1', 'in', 'one', 'pic']
    ['python', 3, '.4.1', 'in', 'one', 'pic', '!', '!']
    

**In:**
```python
print(l.pop())             # '!'
print(l)
# l == ['python', 3, '.4.1', 'in', 'one', 'pic', '!']

print(l.pop(2))           # '.4.1'
print(l)
# l == ['python', 3, 'in', 'one', 'pic', '!']

l.remove("in")
print(l)
# l == ['python', 3, 'one', 'pic', '!']

del l[2]
print(l)
# l == ['python', 3, 'pic', '!']
```
**Out:**

    !
    ['python', 3, '.4.1', 'in', 'one', 'pic', '!']
    .4.1
    ['python', 3, 'in', 'one', 'pic', '!']
    ['python', 3, 'one', 'pic', '!']
    ['python', 3, 'pic', '!']
    

**In:**
```python
print(l.index('pic'))       # 2 since the original l was already altered
print (l[0][3])             #h is on python[0]
```
**Out:**

    2
    h
    

**In:**
```python
ips = ['10.1.1.2','10.1.1.1','10.1.1.9', '10.1.1.4','10.1.5.1']
sorted_ips = sorted(ips) #Sorts the elements on the list(letters & integers)
print(sorted_ips)
# or
ips.sort() #sorts the original list
print(ips)
```
**Out:**

    ['10.1.1.1', '10.1.1.2', '10.1.1.4', '10.1.1.9', '10.1.5.1']
    ['10.1.1.1', '10.1.1.2', '10.1.1.4', '10.1.1.9', '10.1.5.1']
    

## Tuple
are similar to lists, created by enclosing values in parentheses. Like lists, the values in the tuple are retrieved by referencing its index number. Unlike lists, the values cannot be modified after creation

**In:**
```python
tp = (1, 2, 3, [4, 5])
print(type(tp)) # <class 'tuple'>
description = tuple(['router','switch', 1])
print(type(descrip))
```
**Out:**

    <class 'tuple'>
    <class 'tuple'>
    

**In:**
```python
## Length
print(len(tp))  # 4

print(tp[2])    # 3
## Tuples are immutable to the extent that their elements are immutable
tp[3][1] = 6
print(tp)       # (1, 2, 3, [4, 6])
```
**Out:**

    4
    3
    (1, 2, 3, [4, 6])
    

**In:**
```python
## Single element
tp = (1, )      # Not tp = (1)
print(tp)
```
**Out:**

    (1,)
    

**In:**
```python
## Assign multiple values at once
v = (3, 2, 'a')
(c, b, a) = v
print(a, b, c)  # a 2 3
```
**Out:**

    a 2 3
    

## Set
- is an unordered collection data type that is iterable, mutable, and has no duplicate elements. 
**In:**
```python
st = {'s', 'e', 'T'}
print(type(st)) # <class 'set'>
```
**Out:**

    <class 'set'>
    

**In:**
```python
## Length
print(len(st))  # 3
```
**Out:**

    3
    

**In:**
```python
## Empty
st = set()
print(len(st))  # 0
```
**Out:**

    0
    

**In:**
```python
st = {}
print(type(st)) # <class 'dict'>
# set is like a dict with keys but no values,  Use set() for empty sets, use {} for empty dicts for less complication
```
**Out:**

    <class 'dict'>
    
### Manipulate contets on a list: add(), update(), discard(), remove(), pop(), clear()
**In:**
```python
st = set(['s', 'e', 'T'])
st.add('t')     # st == {'s', 'e', 't', 'T'}
st.add('t')     # st == {'s', 'e', 't', 'T'}
st.update(['!', '!'])
print(st)
# st == {'s', 'e', 't', 'T', '!'}

st.discard('t') # st == {'T', '!', 's', 'e'} # No Error
st.remove('T')  # st == {'s', 'e', '!'}      # KeyError
st.pop()        # 's'
print(st)
# st == {'e'}

st.clear()      # st == set()
print(st)
```
**Out:**

    {'T', '!', 's', 't', 'e'}
    {'s', 'e'}
    set()
    

## Dictionary
- is an unordered collection of items. Has Key : Value pair.
**In:**
```python
dic = {}
print(type(dic))    # <class 'dict'>

dic = {'k1': 'v1', 'k2': 'v2'}
print(dic)
```
**Out:**

    <class 'dict'>
    {'k1': 'v1', 'k2': 'v2'}
    

**In:**
```python
## Length
print(len(dic))     # 2
```
**Out:**

    2
    

**In:**
```python
print(dic['k2'])            # 'v2'
print(dic.get('k1'))        # 'v1'
print(dic.get('k3', 'Does not exist'))  # 'Does not exist'

dic['k2'] = 'v3'
print(dic)                  # {'k1': 'v1', 'k2': 'v3'}

print('k2' in dic)          # True
print('v1' in dic)          # False
```
**Out:**

    v2
    v1
    Does not exist
    {'k1': 'v1', 'k2': 'v3'}
    True
    False
    
## dict pop and update
**In:**
```python
dic.pop('k2')
print(dic)                          ##{'k1': 'v1'}
oper = dict(cpu='5%', mem='10%')  ##another way to create dict
oper.update(dic)
print(oper)          ##{'cpu': '5%', 'mem': '10%', 'k1': 'v1'}
```
**Out:**

    {'k1': 'v1'}
    {'cpu': '5%', 'mem': '10%', 'k1': 'v1'}
    
### using items, to simyltaneously access keys and values
**In:**
```python
devices = {'Juniper':'Junos', 'Cisco':'IOS', 'Nokia':'SR OS'}
for brand, os in devices.items():
    print(brand, ':' , os)
```
**Out:**

    Juniper : Junos
    Cisco : IOS
    Nokia : SR OS
    

# III. Flow Control
The if, else, and elif statements control conditional code execution. As one would expect, the format of the conditional statement is as follows:

if expression:
  do something
 
elif expression:
  do something if the expression meets
  
elif expression:
  do something if the expression meets
  
...

else:
  statement

## If

**In:**
```python
hostN = "R1"
if hostN == 'S1':
    print("Device is Switch")
elif hostN == 'FW1':
    print("Device is Firewall")
else:
    print("Device is Router")

import sys
if sys.version_info.major < 3:
    print("Version 2.X")
elif sys.version_info.major > 3:
    print("Future")
else:
    print("Version 3.X")
```
**Out:**

    Device is Router
    Version 3.X
    

## Loop

**for** (The for loop works with any object that supports iteration; this means all the built-in sequence types, such as lists, tuples, and strings, can be used in a for loop. The letter i in the following for loop is an iterating variable, so you can typically pick something that makes sense within the context of your code:

for i in sequence:
  do something


**In:**
```python
a = [100, 200, 300, 400]
for number in a:
    print(number)
```
**Out:**

    100
    200
    300
    400
    

**while** (The while loop will continue to execute until the condition is false, so be careful with this one if you don't want to continue to execute (and crash your process)).
The **with** block or also called context handler, automatically close what has been open, example:
instead of typing manually **f=open()** and **f.close()**, just use **with open()**, 
Open and close are built in the python

**In:**
```python
prod = 1
i = 1
while i < 10:
    prod = prod * i
    i += 1
print(prod)
```
**Out:**

    362880
    

**In:**
```python
## break & continue
for n in range(2, 10):
    if n % 2 == 0:
        print("Found an even number ", n)
        continue
    if n > 5:
        print("n > 5!")
        break
```
**Out:**

    Found an even number  2
    Found an even number  4
    Found an even number  6
    n > 5!
    

**In:**
```python
## continue
for num in range(2, 10):
    if num % 2 == 0:
        print("Found an even number", num)
        continue
    print("Found a number", num)
```
**Out:**

    Found an even number 2
    Found a number 3
    Found an even number 4
    Found a number 5
    Found an even number 6
    Found a number 7
    Found an even number 8
    Found a number 9
    

## Comprehension

**List**

**In:**
```python
s = [2 * x for x in range(10) if x ** 2 > 3]
print(s)

pairs = [(x, y) for x in range(2) for y in range(2)]
print(pairs)
```
**Out:**

    [4, 6, 8, 10, 12, 14, 16, 18]
    [(0, 0), (0, 1), (1, 0), (1, 1)]
    

**Set**

**In:**
```python
s = {2 * x for x in range(10) if x ** 2 > 3}
print(s)

pairs = set([(x, y) for x in range(2) for y in range(2)])
print(pairs)
```
**Out:**

    {4, 6, 8, 10, 12, 14, 16, 18}
    {(0, 1), (1, 0), (0, 0), (1, 1)}
    

**Dict**

**In:**
```python
ls = {s: len(s) for s in ["Python", "Javascript", "Golang"]}
print(ls)

sl = {v: k for k, v in ls.items()}
print(sl)
```
**Out:**

    {'Python': 6, 'Javascript': 10, 'Golang': 6}
    {10: 'Javascript', 6: 'Golang'}
    

## Iterators & Generators

**In:**
```python
python = iter("Python")
print(python)
for i in python:
    print(i)
```
**Out:**

    <str_iterator object at 0x10293f8d0>
    P
    y
    t
    h
    o
    n
    

**In:**
```python
def reverse(data):
    for index in range(len(data)-1, -1, -1):
        yield data[index]
nohtyp = reverse("Python")
print(nohtyp)
for i in nohtyp:
    print(i)
```
**Out:**

    <generator object reverse at 0x1029539e8>
    n
    o
    h
    t
    y
    P
    

# IV. Function
## Definition

**In:**
```python
def f():
    """return 'Hello, World!'"""
    return "Hello, World!"

print(f())
print(f.__doc__)
```
**Out:**

    Hello, World!
    return 'Hello, World!'
    

## Arguments

**In:**
```python
## default arguments
def f(name = "World"):
    """return 'Hello, $name'"""
    return "Hello, {}!".format(name)
print(f())
print(f("Python"))
```
**Out:**

    Hello, World!
    Hello, Python!
    

**In:**
```python
## keyword arguments
def f(v, l = "Python"):
    """return '$v, $l'"""
    return "{}, {}!".format(v, l)
print(f("Hello"))
print(f("Bye", "C/C++"))
```
**Out:**

    Hello, Python!
    Bye, C/C++!
    

**In:**
```python
## arbitrary arguments
def f(*args, con = " & "):
    print(isinstance(args, tuple))
    print("Hello", con.join(args))

f("Python", "C", "C++", con = "/")
```
**Out:**

    True
    Hello Python/C/C++
    

**In:**
```python
def f(*args, **kargs):
    print("args ", args)
    print("kargs ", kargs)
    print("FP: {} & Scripts: {}".format(kargs.get("fp"), "/".join(args)))
    
f("Python", "Javascript", ms = "C++", fp = "Haskell")
```
**Out:**

    args  ('Python', 'Javascript')
    kargs  {'ms': 'C++', 'fp': 'Haskell'}
    FP: Haskell & Scripts: Python/Javascript
    

## Lambda

**In:**
```python
pairs = [(1, 'one'), (2, 'two'), (3, 'three'), (4, 'four')]
pairs.sort(key=lambda pair: pair[1])
print(pairs)
pairs.sort(key=lambda pair: pair[0])
print(pairs)
```
**Out:**

    [(4, 'four'), (1, 'one'), (3, 'three'), (2, 'two')]
    [(1, 'one'), (2, 'two'), (3, 'three'), (4, 'four')]
    

## @decorator

**In:**
```python
def log(f):
    def wrapper():
        print("Hey log~")
        f()
        print("Bye log~")
    return wrapper

@log
def fa():
    print("This is fa!")

# Equal to...
def fb():
    print("This is fb!")
fb = log(fb)

fa()
print("*"*10)
fb()
```
**Out:**

    Hey log~
    This is fa!
    Bye log~
    **********
    Hey log~
    This is fb!
    Bye log~
    

# V. Class(OOP)

## `class`

**In:**
```python
class Animal:
    """This is an Animal"""
    def fly(_):
        print("I can fly!")
a = Animal()
a.fly()          # I can fly!
print(a.__doc__) # This is an Animal
```
**Out:**

    I can fly!
    This is an Animal
    

## `__init__` & `self`

**In:**
```python
class Animal:
    """This is an Animal"""
    def __init__(self, can_fly = False):
        print("Calling __init__() when instantiation!")
        self.can_fly = can_fly
    def fly(self):
        if self.can_fly:
            print("I CAN fly!")
        else:
            print("I can not fly!")
a = Animal()               # Calling __init__() when instantiation!
a.fly()                    # I can not fly!

b = Animal(can_fly = True) # Calling __init__() when instantiation!
b.fly()                    # I CAN fly!
```
**Out:**

    Calling __init__() when instantiation!
    I can not fly!
    Calling __init__() when instantiation!
    I CAN fly!
    

## Instance

**In:**
```python
class Animal:
    pass
class Human:
    pass
a = Animal()
h = Human()
print(isinstance(a, Animal))
print(isinstance(h, Animal))
```
**Out:**

    True
    False

**In:**
```python
class Switch:
    """Info for a switch"""
    def __init__(self, Vendor, Name, Interface):
        self.vendor = Vendor
        self.name = Name
        self.interface = Interface
s1 = Switch("Juniper", "vSRX-01", 5)
print(s1.vendor)
print(s1.name)
print(s1.interface)
print(s1.__doc__)
```
**Out:**

    Juniper
    vSRX-01
    5
    Info for a switch
    

## Inheritance

**In:**
```python
class Animal:
    """This is an Animal"""
    def __init__(self, can_fly = False):
        self.can_fly = can_fly
    def fly(self):
        if self.can_fly:
            print("I CAN fly!")
        else:
            print("I can not fly!")
class Dog(Animal):
    """This is a Dog"""
    def bark(self):
        print("Woof!")
d = Dog()
d.fly()
d.bark()
```
**Out:**

    I can not fly!
    Woof!
    

## Override

**In:**
```python
class Animal:
    """This is an Animal"""
    def __init__(self, can_fly = False):
        self.can_fly = can_fly
    def fly(self):
        if self.can_fly:
            print("I CAN fly!")
        else:
            print("I can not fly!")
class Bird:
    """This is a Bird"""
    def fly(self):
        print("I'm flying high!")
bird = Bird()
bird.fly()    # I'm flying high!
```
**Out:**

    I'm flying high!
    

# VI. Module

## `import`

**In:**
```python
import os
print(os.name)

from sys import version_info as PY_VERSION
print("VERSON: {}.{}".format(PY_VERSION.major, PY_VERSION.minor))

from math import *
print(pi)
```
**Out:**

    posix
    VERSON: 3.5
    3.141592653589793
    

## Search Path

1. current directory
2. `echo $PYTHONPATH`
3. `sys.path`

## Package

**In:**
```python
"""
MyModule/
|--SubModuleOne/
    |--__init__.py
    |--smo.py

# smo.py
def run():
    print("Running MyModule.SubModuleOne.smo!")
"""
from MyModule.SubModule import smo
smo.run()
# Running MyModule.SubModuleOne.smo!
```
**Out:**

    ---------------------------------------------------------------------------

    ModuleNotFoundError                       Traceback (most recent call last)

    <ipython-input-18-81c5d6346237> in <module>
          9     print("Running MyModule.SubModuleOne.smo!")
         10 """
    ---> 11 from MyModule.SubModule import smo
         12 smo.run()
         13 # Running MyModule.SubModuleOne.smo!
    

    ModuleNotFoundError: No module named 'MyModule'


```python

```
