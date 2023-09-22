## First Class Functions
* A programming lang has first-class functions if it treats functions as first-class citizens

### First Class Citizens/Objects
* An entity that supports all the operations genreally avaiablel to other entities. These operations typically include being passed as arguments, returned from function, and assigned to variable


For example, we can set variable in python to be a function name. We can pass functions as arguemnts 


#### Higher Order Functions

Take in a function as a parameter or return a function as a result

Ex:

```python
#We create a custom map function which is a higher order function
def my_map(func,arg_list):
    result = []
    for i in arg_list:
        result.append(func(i))
    return result


squares = my_map(square, [1,2,3,4,5])

```