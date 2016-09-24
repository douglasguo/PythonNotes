- if you import the module, then _`___name___`_ is the module's filename. if you run the module directly as a standalone program, in which case `____name___`_ will be a special default value, ___main___


- dictionary-> hashable in Java, Scripting. Dictionary object in VB
  - cannot have duplicate keys
  - dic values can be any datatype
  - deleting one key value pair: del d[42]

- list 
  - list have order, you can access the first element li[i]
  - adding new elements: 
    - `append`-> add to the end
    - `insert(2,'new')` -> insert to the specified location,
    - `extends`-> concatenate lists, the argument of extends is always a list. append takes only one argument, which can be ansy data type
  - serach a list, use index().
    -  for example `li=['a', 'b', 'new', 'mpilgrim', 'z', 'example', 'new', 'two', 'elements'] li.index('example')` to look for the string 'example'. but it only finds the first item

- Three types of errors
  - syntax error
  - runtime error
  - semantic error

- string operations with math expressions:
  - plus "+" concatenation
  - multiple "*" performs repetition

- If an error occurs during a function call, Python prints the name of the function, the nameof the function that called it, and the name of the function that called that, all the way backto __main__.

- function returns values, void functions-> functions do not return values

- Void functions might display something on the screen or have some other effect, but theydon’t have a return value. If you assign the result to a variable, you get a special valuecalled None.

- somtimes you don'y knwo it's time to end a loop until you get half way through the body. In that case you can use the break statement to jump out of the loop
  - while true:
    - line = input('>')
    - if line == 'done':
      - break
    - print (line)

- floor division and modulus
  - `//` divides two bumbers and rounds down to an integer
  - modulus operator `%` divides two numbers and returns the remainder. For example, you can check whether on number is divisible by another if `x % y` returns zero

- logical operators: and or and not

- any nonzero number is interpreted as True

- if elif else-> chained condition

- keyboard input python 2 raw_input

- checking types 
  - isinstance to verify the type of the argument




- string: the last letter of a string:

  - length=len(fruit)
  - last = fruit[length-1]

- String as immutable:

  - you can't change an existing string

    ```python
    greeting = 'Hello'
    greeting[0]= 'J'-> error
    greeting = 'J'+ greeting[1:]
    ```

- string searching find(word, letter)

  -  S.find(sub [,start [,end]]) second argument tells you where to start and end



- the word "in" is a boolean operator that takes two strings and return True if the first apears as a substring in the second

  - `'a' in 'banana'`
  - `True`

- string comparison-> dictionary order

  - does not handle uppercase and lowercase letters the same why-> convert strings to a standard format, such as all lowercase, before performing comparison

- Python list

  - ```python
    L.reverse()
    ```

    Reversing is fast, so temporarily reversing the list can often speed things up if you need to remove and insert a bunch of items at the beginning of the list:

  - map filter and reduce

    - an operation that combines a sequence of elements into a single value is called **reduce**
    - an operation is called **map** if it mapes a function onto each of the elemens in a sequence
    - another common operation is to select some of the elements form a list and then return a sublist, like the operation only_upper is called a **filter**
    - Most of the list operations can be expressed as a combination of map, filter and reduce

  - list has built in iteration functions iter

    - ·`i = iter(L)`
    - `item = i.next()`
    - `item = i.next()`

  - the for-in statement makes it easy to loop over the items in a list:

    ```python
    for i in L:
    	print item

    ```

    if you need both the index and the item, use enumerate funciton

  - deleting elements: `del remove pop`

  - list and strings

    - `s.split(delimiter)`-> specifies which character to use as a word boundadies

    - join does the reverse for split. it takes a strings and concatenates the element. 

      ```python
      t=['pining',' for', 'the']
      delimiter = ' '
      s = delimiter.join(t)
      ```

    - aliasing: `a='banana' b = 'banana'`. you can make copies to avoid aliasing.

  - you can also impliment other data structures such as stack and queues with list

  - To get a sorted copy, use the built-in **sorted** function:

    ```python
        out = sorted(L)
    ```

- S.strip([chars])
  ​    

      Return a copy of the string S with leading and trailing
      whitespace removed.

- sort(): By default, Python’s sort algorithm determines the order by comparing the objects in the list against each other. You can override this by passing in a callable object that takes two items, and returns -1 for “less than”, 0 for “equal”, and 1 for “greater than”. python has a function for this **cmp**. Return negative if `x< y`, zero if `x==y`, positive if `x>y`. you can also specify a mapping between list items and search keys 

  ​

- Dictionary

  - initialisation of a dictionary: `d = dict()`
  - dictionary as a collection of counters
  - the methods for a dictionary to get a default value if no such key `dict.get(sth,0)`
  - dictionary as a counter: `counts[name] = counts.get(name, 0) + 1`-> check if it exists. if not exists, initilize as one
  - items() returns tuples from the dictionary
  - reverse look up in the dictionary-> you have the value and you want to look for the key

  ```python
  def reverse_lookup(d, v):
  	for k in d:
  		if d[k] == v:
  	return k
  	raise LookupError()
  ```

  - list can appear as values in dictionary
  - a dictionary is implemented using a hashtable and that means that the keys have to be **hashable**. A hash is a function that takes a value (of any kind) and returns an integer. Dictionariesuse these integers, called hash values, to store and look up key-value pairs.



- tuple

  - tuple assignment: `a,b=b,a`

  - To write a tuple containing a single value you have to include a comma, even though there is only one value

    ```python
    tup1=(50,)
    ```

  - tuple as return values: The built-in function divmod takes two arguments and returns a tuple of two values, thequotient and remainder. Here is an example of a function that returns a tuple

  ```python
  def min_max(t):
  	return min(t), max(t)
  ```

  - functions can take a variable number of arguments. A parameter name begins with ***gathers** arguments into a tuple. 

  ```python
  def pritnall(*args):
  	print(args)
  	
  >>> printall(1,2.0,'3')
  (1,2.0,'3')
  ```

  - The complement of ***gather** is **scatter**. For example, dived takes exactly two arguments and it doesn't work with one tuple

  ```python
  t = (7,3)
  divmot(t)-> error
  divmod(*t)
  (2,1)
  ```

  - tuples are more efficient 
  - `zip` is a  built in function that takes two or more sequences and returns a list of tuples where each tuple contains one elementt from each sequence. The most common use of zip is in a for loop:

  ```python
  s='abc'
  t=[0,1,2]
  zip(s,t)
  for pair in zip(s,t):
  	print(pair)
  	
  ('a',0)
  ('b',1)
  ('c',2)
  ```

  - the result is a `zip object` that knows how to iterate through the pais. it is a kind of iterators.

  - you can also use tuple assignment in a for loop to traverse a list of tuples

    ```python
    for left, right in zip(s,t)：
    	print left,right
    ```

  - dictionaryies have a method called `items` that returns a sequence of tuples, where each tuple is a key-value pair. the result is a dict_items object, which is an iterator that iterates the key-value pairs. 

  ```python
  for key, value in d.items():
  	print key,value
  ```

  - Going to the other direction, you can use a list of tuples to initialize a new dictionary

  ```python
  t = [('a',0),('c',2),('b',1)]
  d = dict(t)
  ```

  - combining dict with zip yields a concise way to create a dictionary

    ```python
    d = dict(zip('abc',range(3)))
    ```

  - the method `update` also takes  a list of tuples and adds when, as key-value pairs, to an existing dictionary

  - it is common to use tuples are keys in dictionaries (you cannot use list in dictionaries). for example, a telephone directory might map from last-name, first-name pairs to telephone numbers 

  ```python
  directory[last, first]= number
  ```

  the exrepssion in the brackets is a tuple. we could use tuple assignment to traverse this dictionary

  ```python
  for last, first in directory:
  	print (first, last, directory[last, first])
  ```

  - comparisons between different sequences:

    - strings are more limited than other sequences because the elementshave to be characters. They are also immutable. If you need the ability to change the characters in a string (as opposed to creating a new string), you might want to use a list of characters instead.

    - Lists are more common than tuples, mostly because they are mutable. But there are a few cases where you might prefer tuples:

      - In some contexts, like a return statement, it is syntactically simpler to create a tuple than a list.

      - If you want to use a sequence as a dictionary key, you have to use an immutable type like a tuple or string.

      - If you are passing a sequence as an argument to a function, using tuples reduces the potential for unexpected behavior due to aliasing.

        ​

- files

  - writting `fout = open('output.txt','w')` 
  - writting into the file: `line =' haha'` `out.write(line)`
  - Format operator: the argument `write` has to be string, so if we want to put other values in file, we have to convert them to strings and the easiest way is to use `str` . the d after % denotes that the type of camels is decimal integer. `g` denotes a floating point number. s denotes a string

```python
camels = 42
'%d' % camels
'In %d years I have spotted %g %s.'% (3,0.1,'camels')
```

- filenames and paths

```python
import os
cwd = os.getcwd()
os.path.abspath('memo.txt') # get the absolute path
os.path.exists('memo.txt')
```

- a lot of thins can go wrong when you try to read and write files. it is better to go ahead and try and deal with problems if they happen. 

```python
try:
	fin = open('bad_file')
except:
	print('Something went wrong.')
```

- pipes
  - most of the os pervides a command line interface known as a shell. Any program that you can launch from the shell can also be launched from python using a pipe object, which represents a running program.

  ```python
  cmd = 'ls -l'
  fp = os.open(cmd)
  ```


- Classes

  - different kinds of copies:

  ```python
  import copy
  p2 = copy.copy(p1)
  p3 = copy.deepcopy(p1)
  ```

  - OOP:
    - programs include class and method definitions
    - most of the computation is expressed in terms of operations on objects
    - objects often repesent things in the real world, and methods often correspond to the ways thing in the real world interact
  - methods are the same as functions, but there are two syntatic differences:
    - methods are defined inside a class definition in order to make the relationship between the class and the method explicit
    - the syntax for invoking a method is different from the syntax for calling a function
  - `init` method is special method that gets invoked when an object is instantiated. it is common for the parameters of __init__ to have the same names as the attributes

  ```python
  self.hour=hour
  self.minute= minute
  self.second=second
  ```

  - the __str__ method is a special method that is supposed to return a string representaiton of an object

  ```python
  def __str__(self):
  	return '%.2d:%.2d:%.2d' % (self.hour, self.minute, self.second)
  ```

  when you print an object, ptyon invodes the `str` method

  ```python
  time = Time(9, 45)
  print(time)
  09:45:00
  ```

  - operator overriding: 

    - by defining special methods, you can specify the behaviour of operatos on programmer-defined types. For exmpale, if you define `__add__` for `Time` class, you can use `+` operator on `Time` objects

    ```python
    def __add__(self, other):
    	seconds = self.time_to_int() + other.time_to_int()
    	return int_to_time(seconds)
    ```

    -  chanaging the behaviour of an operator so that it works with the programmer defined types is callsed `operator-overloading`
    -  speciall fucntions in python: http://docs.python.org/3/reference/datamodel.html#specialnames.

  - The goodies:

    - conditional expressions, the following example 

    ```python
    if x > 0:
    	y = math.log(x)
    else:
    	y = float('nan')
    ```

    can also be written as

    ```python
    y = math.log(x) if x > 0 else float('nan')
    ```

    another use is to handle optional arguments

    ```python
    def __init__(self, name, contents=None):
    	self.name = name
    	self.pouch_contents = [] if contents == None else contents
    ```

    - list comphrehension

    ```python
    def only_upper(t):
    	res = []
    	for s in t:
    		if s.isupper():
    		res.append(s)
    	return res
    ```

    can be written as 

    ```python
    def only_upper(t):
    	return [s for s in t if s.isupper()]
    ```

    - generator expression: similar to list comprehension, but with parenthesis instead of square brackets

    ```python
    >>> g = (x**2 for x in range(5))
    >>> g
    <generator object <genexpr> at 0x7f4c45a786c0>
    ```

    the result is a generator object that knows how to itearate through a sequence of values. But unlink list comprehension, it does not compute the values all at once; it waits to be asked.

    ```python
    >>> next(g)
    0
    >>> next(g)
    1
    ```

    - `any` takes a sequence of boolean values and return `True` if any of the values are true.

    ```python
    >>> any([False, False, True])
    True
    ```

    and it is often used with generator expression

    ```python
    >>> any( letter == 't' for letter in 'monty')
    True
    ```

    we can write something like English in the following:

    ```python
    def avoids(word, forbidden):
    	return not any(letter in forbidden for letter in word)
    ```

    - sets

      - The [`sets`](https://docs.python.org/2/library/sets.html#module-sets) module provides classes for constructing and manipulating unordered collections of **unique** elements
      - Most set applications use the [`Set`](https://docs.python.org/2/library/sets.html#sets.Set) class which provides every set method except for [`__hash__()`](https://docs.python.org/2/reference/datamodel.html#object.__hash__). For advanced applications requiring a hash method, the [`ImmutableSet`](https://docs.python.org/2/library/sets.html#sets.ImmutableSet) class adds a [`__hash__()`](https://docs.python.org/2/reference/datamodel.html#object.__hash__) method but omits methods which alter the contents of the set.

    - Counter

      - a counter is like a set, except that if an element apreas more than once, the Counter keeps track of how many times it appears. It is a represnetation of a multiset.

        ```python
        >>> from collections import Counter
        >>> count = Counter('parrot')
        >>> count
        Counter({'r': 2, 't': 1, 'o': 1, 'p': 1, 'a': 1})
        ```

      - counters behave like dictionaries in many ways; they map from each key to the number of time it apears

      - unlike dictionaries, Counters don't raise an exception if you access an element that doesn't appear. Instead, they return 0:

      ```python
      >>> count['d']
      0
      ```

      - Counters provide methods and operators to perform set-like operations, including addition,subtraction, union and intersection. And they provide an often-useful method: `most_common`, which returns a list of value-frequency pairs, sorted from most common toleast:

      - ```python
        >>> count = Counter('parrot')
        >>> for val, freq in count.most_common(3):
        ... 	print(val, freq)
        r 2
        p 1
        a 1
        ```

    - defaultdict

      - the `collections` modle also provides `defaultdict`, which is like a dictionary except that if you access a key that doesn't exist, it can generate a new value on the fly.

      ```python
      if not detect_user_event_footfallGT(e):
          output_dict.setdefault(imsi,[]).append(( e['ts'], detect_user_event_footfallGT(e),'In'))
      else:
          output_dict.setdefault(imsi,[]).append(( e['ts'], 'NotInStaiton','Out'))
          print 'Gotcha'
      ```

      another example from the text

      ```python
      >>> from collections import defaultdict
      >>> d = defaultdict(list)
      >>> t = d['new key']
      >>> t
      []
      ```

      the new list, which we're calling `t`, is also added to the dictionary. So if we modify `t`, the change appears in `d`:

      ```python
      >>> t .append('new value')
      >>> d
      defaultdict(<class 'list'>, {'new key': ['new value']})
      ```

    - named tuples:

      - the normal structure of a class

      ```python
      class Point:
      	def __init__(self, x=0, y=0):
      		self.x = x
      		self.y = y
      	def __str__(self):
      		return '(%g, %g)' % (self.x, self.y)
      ```

      python provides a more concise way to say the same thing:

      ```python
      from collections import namedtuple
      Point = nametuple('Point',['x','y'])
      ```

      the first argument is the name of the class you want to create. the second is a lit of the attributes Point objects should have, as strings. the return value from `nametuple` is a class object

      `Point` automatically provides methods like `__init__` and `__str__` that you don't have to write them.