# Lab 2: More Python Review 
## Notes
- TA office hours on Brightspace
- PTC 10am-8pm 1-on-1 tutoring
- Recitations have started

- In exams, you will be asked to write memory images 

## Operator Overloading
- dunder method (can be called using pre-existing operators e.g +, -, *
- ex. __add__
- Note the return value: you get an object, not just integer if you use __add__
### 
## List comprehension
- Lets you create a list from an iterable object
- [x for x in range(5) if some condition]
- [(thing to be stored) for (elemment) in (iterable collection) if (condition)]
## Memory Images
## Shallow copies 
- Create a new list but the indices/slots point to the already existing objects
- Mutating either the original/copy will affect the other
-   other_other_list = [1,[2,2], ["python"]]
-   Shallow_copy = copy.copy(other_other_list) -> will point to the values of the original list array
-   Other methods (these will also create a shallow copy): list comprehension, list multiplication, list slicing, copy.copy
-   ex.  [[0] * 3] * 3

## Deep copies
- Create new copies of every object within each original list
- You can mutate both original or copied list without affecting each other
- copy.deepcopy(other_other_list)

