
Is lecture main ham dekhen gay k data structures and sequences kia hti hyn.
>1. **Tuple**
>- Sequence of python objects
>- Fixed length
>- Immutable (once assigned, can not be changed)
>- The easiest way to create them is with comman-separated seuquence of objects/python values having paranthese around them:

```python
tup = (1,2,3,4,5)
```
>in many context of tuples, we can remove paranthesis
```python
tup = 1,2,3,4,5
```
You can also convert any sequence or iterator to a tuple by invoking tuple?
```python
tup = tuple([1,2,3,4,5])
```
`Tuple` of string is as follows
```python
tup = ('string')
tup
```
> Elements can be accessed with square brackets [] as with most other sequence types.
```python
tup[0]  #output: s
```
Nested Tuples: Assignment?
```python
nested_tuple = tuple(['foo', [1, 2], True])
```
>2. **List**
>- Sequence of python objects
>- Mutable
>- Can be defined as a comma-separated sequence of objects between square brackets
```python
a_list = [1,2,3,4,5]
```
>3. **Dictionary**
>- A mapping of unique keys to values
>- Can be defined by using curly braces {} and colons to separate keys and values
```python
a_dict = {'a':1, 'b':2, 'c':3}
```
>4. **Set**
>- An unordered collection of unique elements
>- Can be defined by placing a comma-separated sequence of elements between curly braces
```python
a_set = {1,2,3,4,5}
```
Sets support mathematical set operations like union, intersection, difference, and symmetric difference.
```python
a_set = {1,2,3,4,5}
b_set = {3,4,5,6,7}
a_set.union(b_set)  #output: {1,2,3,4,5,6,7}
a_set.intersection(b_set)  #output: {3,4,5}
```
>5. **Built-In Sequence Functions**\
Python has a handful of useful sequence functions that you should familiarize yourself with and use at any opportunity.
>- `enumerate`: Returns an enumerate object. It contains the index and value of all the items in the sequence as pairs.
```python
seq = [1,2,3,4,5]
for i, value in enumerate(seq):
    print(i, value)
```
>- `sorted`: Returns a new sorted list from the elements of any sequence.
```python
seq = [1,2,3,4,5]
sorted(seq)  #output: [1,2,3,4,5]
```
>- `zip`: “Pairs” up the elements of a number of lists, tuples, or other sequences to create a list of tuples.
```python
seq1 = [1,2,3,4,5]
seq2 = [6,7,8,9,10]
zipped = zip(seq1, seq2)
list(zipped)  #output: [(1,6), (2,7), (3,8), (4,9), (5,10)]
```
>- `reversed`: Returns a sequence of the elements in the order of reverse of the argument sequence.
```python
seq = [1,2,3,4,5]
list(reversed(seq))  #output: [5,4,3,2,1]
```
>- `dict`: Converts a sequence of (key, value) pairs into a dictionary.
```python
mapping = dict(zip(range(5), reversed(range(5))))
mapping  #output: {0:4, 1:3, 2:2, 3:1, 4:0}
```
>- `list`: Converts a sequence or iterator into a list.
```python
list(range(5))  #output: [0,1,2,3,4]
```
>- `all`: Returns True if all elements of the sequence are true (or if the sequence is empty).
```python
all([True, 1, {3}])  #output: True
all([True, 1, {}])  #output: False
```
>- `any`: Returns True if any element of the sequence is true. If the sequence is empty, returns False.
```python
any([True, 1, {}])  #output: True
any([False, 0, {}])  #output: False
```
>- `sum`: Sums the elements of an arbitrary sequence.
```python
sum(range(5))  #output: 10
```
6. **List, Set, and Dictionary Comprehensions**
>- List comprehensions: A list comprehension is a way to quickly construct a list whose contents obey a simple rule. For example, suppose we want to create a list of squares:
```python
squares = []
for x in range(10):
    squares.append(x**2)
```
>- A more concise way of doing this is:
```python
squares = [x**2 for x in range(10)]
```
>- Set comprehensions: A set comprehension looks just like a list comprehension except you use curly braces instead of square brackets.
```python
unique_lengths = {len(x) for x in strings}
```
>- Dictionary comprehensions: A dictionary comprehension looks like a set comprehension except that it uses curly braces containing a key: value pair instead of a single value.
```python
loc_mapping = {val : index for index, val in enumerate(strings)}
```
>- Nested list comprehensions: You can nest list comprehensions, but the input and output sequence lengths will be the same.
```python
all_data = [['John', 'Emily', 'Michael', 'Mary', 'Steven'],
            ['Maria', 'Juan', 'Javier', 'Natalia', 'Pilar']]
names_of_interest = []
for names in all_data:
    enough_es = [name for name in names if name.count('e') >= 2]
    names_of_interest.extend(enough_es)
```
>- A more concise way of doing this is:
```python
result = [name for names in all_data for name in names
          if name.count('e') >= 2]
```

### **Functions**
>1. **Defining and Calling Functions**
>- Functions are defined using the `def` keyword. For example:
```python
def my_function(x, y, z=1.5):
    if z > 1:
        return z * (x + y)
    else:
        return z / (x + y)
```
>- Functions can return multiple values as a tuple. For example:
```python
def f():
    a = 5
    b = 6
    c = 7
    return a, b, c
```
>- Functions can also be called using keyword arguments of the form `kwarg=value`.
```python
def func(a, b=5, c=10):
    print('a is', a, 'and b is', b, 'and c is', c)
func(3, 7)  #output: a is 3 and b is 7 and c is 10
func(25, c=24)  #output: a is 25 and b is 5 and c is 24
func(c=50, a=100)  #output: a is 100 and b is 5 and c is 50
```
>- Functions can be passed to other functions. For example:
```python
def add_numbers(x, y):
    return x + y
def apply_to_one(f):
    """Calls the function f with 1 as its argument"""
    return f(1)
my_addition = apply_to_one(add_numbers)
```
>- Functions can be defined inside other functions. For example:
```python
def my_print(message="my default message"):
    print(message)
def my_print(message="my default message"):
    def print_message():
        print(message)
    print_message()
```
>- Functions can capture local state in the form of *closure*. For example:
```python
def make_adder(n):
    """Returns a function that adds n to its argument"""
    def adder(k):
        return k + n
    return adder
plus_3 = make_adder(3)
plus_5 = make_adder(5)
```
#### ***Anonymous (Lambda) Functions***
>- Python has support for so-called anonymous or lambda functions, which are a way of writing functions consisting of a single statement, the result of which is the return value. They are defined using the `lambda` keyword, which has no meaning other than “we are declaring an anonymous function”. For example:
```python
def short_function(x):
    return x * 2
equiv_anon = lambda x: x * 2
```
>- Lambda functions can be used wherever function objects are required. For example:
```python
def apply_to_one(f):
    """Calls the function f with 1 as its argument"""
    return f(1)
my_double = lambda x: x * 2
x = apply_to_one(my_double)
```
>- Lambda functions are particularly convenient in data analysis because there are many cases where the data transformation functions will be simple, one-line functions. For example:
```python
strings = ['foo', 'card', 'bar', 'aaaa', 'abab']
strings.sort(key=lambda x: len(set(list(x))))
```
>- The `key` argument to `sort` specifies a function that transforms each element before comparison. In this case, we are sorting strings by the number of distinct letters in each string. The `lambda` function passed to `sort` transforms each string into the number of distinct letters. The `set` function builds a collection of distinct letters, and `list` makes it into a list, so that `len` can be applied.

#### ***Errors and Exception Handling***
>- Python has a number of built-in exceptions that are raised when your code encounters an error (something in the program goes wrong). For example, if you try to access a list element with an index that is out of bounds, you’ll get an `IndexError`:
```python
x = [1, 2, 3]
x[10]
```
>- If you try to open a file that doesn’t exist, you’ll get an `IOError`:
```python
open('myfile.txt')
```
>- When these exceptions occur, they usually cause your program to crash. If you don’t handle the exception, your program will crash and you will see a message like:
```python
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```
>- Handling exceptions is one of the most important things that you can do in writing robust programs. If you don’t handle exceptions, your users will see ugly error messages and your program will crash whenever it encounters input that it doesn’t expect. Handling exceptions gracefully allows your program to continue running even if things go wrong.
>- The `try` and `except` statements in Python are used to catch and handle exceptions. For example:
```python
try:
    # use `pass` if you don't want any code to execute
    pass
except Zero
DivisionError:
    print("cannot divide by zero")
except:
    print("something else went wrong")
```
>- The `try` statement works as follows. First, the try clause (the statement(s) between the try and except keywords) is executed. If no exception occurs, the except clause is skipped and execution of the try statement is finished. If an exception occurs during execution of the try clause, the rest of the clause is skipped. Then if its type matches the exception named after the except keyword, the except clause is executed, and then execution continues after the try statement. If an exception occurs which does not match the exception named in the except clause, it is passed on to outer try statements; if no handler is found, it is an unhandled exception and execution stops with a message as shown above.

#### ***Files and the Operating System***
>- Python has a built-in `open` function for reading and writing files. The first argument is a string containing the filename. The second argument is another string containing a few characters describing the way in which the file will be used. mode can be 'r' when the file will only be read, 'w' for only writing (an existing file with the same name will be erased), and 'a' opens the file for appending; any data written to the file is automatically added to the end. 'r+' opens the file for both reading and writing. The mode argument is optional; 'r' will be assumed if it’s omitted. In addition, files can be opened in binary mode by appending 'b' to the mode argument. For example:
```python
f = open('workfile', 'w')
```
>- When you’re done with a file, call `f.close()` to close it and free up any system resources taken up by the open file. It is good practice to use the `with` keyword when dealing with file objects. The advantage is that the file is properly closed after its suite finishes, even if an exception is raised at some point. Using `with` is also much shorter than writing equivalent `try-finally` blocks:
```python
with open('workfile') as f:
    read_data = f.read()
f.closed
```
>- If you’re not using the `with` keyword, then you should call `f.close()` to close the file and immediately free up any system resources used by it. If you don’t explicitly close a file, Python’s garbage collector will eventually destroy the object and close the open file for you, but the file may stay open for a while. Another risk is that different Python implementations will do this clean-up at different times. If you want to be sure the file is closed, then call `f.close()`.
>- `f.read(size)` reads some quantity of data and returns it as a string (in text mode) or bytes object (in binary mode). size is an optional numeric argument. When size is omitted or negative, the entire contents of the file will be read and returned; it’s your problem if the file is twice as large as your machine’s memory. Otherwise, at most size bytes are read and returned. If the end of the file has been reached, `f.read()` will return an empty string ('').
>- `f.readline()` reads a single line from the file; a newline character (`\n`) is left at the end of the string, and is only omitted on the last line of the file if the file doesn’t end in a newline. This makes the return value unambiguous; if `f.readline()` returns an empty string, the end of the file has been reached, while a blank line is represented by `'\n'`, a string containing only a single newline. `f.readlines()` reads the remaining lines from the file object and returns them as a list. The returned list is empty if the end of the file has already been reached. A common pattern when reading a file is to loop over the lines of the file, as in this example:
```python
for line in f:
    print(line, end='')
```
>- `f.write(string)` writes the contents of string to the file, returning the number of characters written.
>- `f.tell()` returns an integer giving the file object’s current position in the file represented as number of bytes from the beginning of the file when in binary mode and an opaque number when in text mode. (Use `f.seek(offset, from_what)` to change the file object’s position.)
>- `f.seek(offset, from_what)` changes the file object’s position. The position is computed from adding offset to a reference point; the reference point is selected by the from_what argument. A from\_what value of 0 measures from the beginning of the file, 1 uses the current file position, and 2 uses the end of the file as the reference point. from\_what can be omitted and defaults to 0, using the beginning of the file as the reference point.
>- `f.close()` closes the file. Like `file objects`, `open()` returns a file object, and is most commonly used with two arguments: `open(filename, mode)`.
>- The `mode` argument is optional; `'r'` will be assumed if it’s omitted. It may be any of the following:
`'r'` : open for reading (default)\
`'w'` : open for writing, truncating the file first\
`'x'` : create a new file and open it for writing\
`'a'` : open for writing, appending to the end of the file if it exists\
`'b'` : binary mode\
`'t'` : text mode (default)\
`'+'` : open a disk file for updating (reading and writing)\
`'U'` : universal newline mode (deprecated)\
>- The `open()` function returns a file object, and is most commonly used with two arguments: `open(filename, mode)`.

#### ***Reading and Writing Files***
>- There is a method for reading or writing one line at a time. Each of these methods returns a string that corresponds to the line of text in the file, minus the newline character. If a file is opened in text mode, `'\n'` is automatically appended to the string when reading from the file. When writing to the file, `'\n'` characters are added to the string. This makes the file easier to read by humans, but if you want to manipulate the data in the file, you’ll have to remove the extra characters.
```python
f = open('workfile', 'r')
f.readline()
f.readline()
f.readline()
f.close()
```
>- The `for` statement is more elegant and concise. It is also much faster than calling `f.readline()` repeatedly, because there is no function call overhead.
```python
for line in f:
    print(line, end='')
```
>- If you want to read all the lines of a file in a list you can also use `list(f)` or `f.readlines()`.
```python
list(f)
f.readlines()
```
>- The `write()` method of file objects does not add line separators to the strings it writes. So if you want to write multiple lines you have to add the new line characters yourself. The easiest way to do this is by using the string `'\n'` as the line separator.
```python
f = open('workfile', 'w')
f.write('This is a test\n')
f.write('This is a test\n')
f.write('This is a test\n')
f.write('This is a test\n')
f.write('This is a test\n')
f.write('This is a test\n')
f.write('This is a test\n')
f.write('This is a test\n')
f.write('This is a test\n')
f.write('This is a test\n')
f.close()
```
>- If you don’t want to have to deal with the file’s `close()` method, you can use the `with` statement. This creates a temporary variable (often called `f`), which is only accessible in the indented block of the `with` statement.
```python
with open('workfile') as f:
    read_data = f.read()
f.closed
```
