## Hello Python!

Unlike in C, which is a _compiled language_, Python is an _interpreted language_, where you need not separately compile your program. Instead, you run your program in the _Python Interpreter_.
```python
print("hello, world")
# You can run this program in your terminal by typing `python hello.py`
```

However, speed is a tradeoff. Because C allows you, the programmer, to make decisions about memory management, it may run faster than Python – depending on your code. While C only runs your lines of code, Python runs all the code that comes under the hood with it when you call Python’s built-in functions.

## Libraries and Packages
- You can import the cs50 library as follows:
    ```python
    import cs50
    ```
- You also have the option of importing only specific functions from the CS50 library as follows:
    ```python
    from cs50 import get_float, get_int, get_string
    ```

## Formatting

```python
name = input("Enter your name: ")
print("hello, " + name)
print("hello, ", name)
print(f"hello, {name}")
```
The `f` is required to include the `name` properly formatting.

## Positional Parameters and Named Parameters

Functions in C like `fread`, `fwrite`, and `printf` use positional arguments, where you provide arguments with commas as separators. You, the programmer, must remember what argument is in which position. These are referred to as **positional arguments**.

In Python, _named parameters_ allow you to provide arguments without regard to positionality.
For example:- 
```python
print(*objects, sep=' ', end='\n', file=None, flush=False)
```

## Variables

Variable declaration is simplified too. In C, you might have `int counter = 0;`. In Python, this same line would read `counter = 0`. You need not declare the type of the variable.

Python favors `counter += 1` to increment by one, losing the ability found in C to type `counter++`.

### Types

Data types in Python do not need to be explicitly declared. 
In Python, commonly used types include:

```python
  bool
  float
  int
  str
```

Notice that `long` and `double` are missing. Python will handle what data type should be used for larger and smaller numbers.

## Conditionals


## OOPs

It’s possible to have certain types of values not only have properties or attributes inside of them but have functions as well. In Python, these values are known as _objects_.

In C, we could create a `struct` where you could associate multiple variables inside a single self-created data type. In Python, we can do this and also include functions in a self-created data type. When a function belongs to a specific _object_, it is known as a _method_.

## Loops

## Abstraction

