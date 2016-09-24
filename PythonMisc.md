- > The following special forms using leading or trailing underscores are recognized (these can generally be combined with any case convention):
  > - _single_leading_underscore: weak "internal use" indicator. E.g. "from M import *" does not import objects whose name starts with an underscore.
  > - single_trailing_underscore_: used by convention to avoid conflicts with Python keyword, e.g.
  >
  > `Tkinter.Toplevel(master, class_='ClassName')`
  >
  > - double_leading_underscore: when naming a class attribute, invokes name mangling (inside class FooBar, boo becomes _FooBar__boo; see below).
  >
  > - double_leading_and_trailing_underscore: "magic" objects or attributes that live in user-controlled namespaces. E.g. __init__, __import__ or __file__. Never invent such names; only use them as documented.
  >
  > - While you can call these methods directly (`[10, 20].__len__()` for example), the presence of the underscores is a hint that these methods are intended to be invoked indirectly (`len([10, 20])` for example). Most python operators have an associated "magic" method (for example, `a[x]` is the usual way of invoking `a.__getitem__(x)`).
  >
  >   ​

- The use of generators:

  - generator funcions allow you to declear a function that behaves like an iterator, i.e. it can be used in a for loop

  ```python
  # Build and return a list
  def firstn(n):
      num, nums = 0, []
      while num < n:
          nums.append(num)
          num += 1
      return nums

  sum_of_first_n = sum(firstn(1000000))
  ```

  This program sums up the first n numbers. But there is a huge waste in memory becuase we need to keep all the n-1 numbers

  ```python
  # Using the generator pattern (an iterable)
  class firstn(object):
      def __init__(self, n):
          self.n = n
          self.num, self.nums = 0, []

      def __iter__(self):
          return self

      # Python 3 compatibility
      def __next__(self):
          return self.next()

      def next(self):
          if self.num < self.n:
              cur, self.num = self.num, self.num+1
              return cur
          else:
              raise StopIteration()

  sum_of_first_n = sum(firstn(1000000))
  ```

  This will perform as we expect, but we have the following issues:

  - there is a lot of boilerplate
  - the logic has to be expressed in a somewhat convoluted way

  Furthermore, this is a pattern that we will use over and over for many similar constructs. Imagine writing all that just to get an iterator.

  Finally, the generator method:

  ```python
  # a generator that yields items instead of returning a list
  def firstn(n):
      num = 0
      while num < n:
          yield num
          num += 1

  sum_of_first_n = sum(firstn(1000000))
  ```

