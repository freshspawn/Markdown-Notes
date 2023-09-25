## Closures

Closure is an inner function that remembers and has access to variables in the local scope in which it was created, even after outer function finishes executing

Ex:

```python
def outer_func():
    message= 'Hi'

    def inner_func():
        print(message)

    return inner_func

my_func = outer_func()
my_func() # SHould print Hi

```