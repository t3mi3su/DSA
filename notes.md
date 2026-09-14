# Iterators & Generators 

```python```

## Iterators

For loop: ```for **var** in **iterable-collection:**```
  
### Iterable-collection: 
- an object that produces an iterator via the syntax: ```iter(iterable_collection)```

### Iterator: 
- an object that exposes a series of values, by making subsequent calls to: ```next(iterator)```
  
### List iterator:
  ```next(lst_iter)```
- Continued
### String iterator:
  ```next(str_iter)```

## Simulating a **For** loop:

```python
# For loop
s = "abc"
for item in s:
    print(item)

# Implementation: Using Iterator as a For loop
s = "abc"
s_iter = iter(s)
end = False # Boolean to break out of loop
while ( ):
  try:
    item = next(s_iter)
    print(item)

  except StopIteration: # except: used for when a stop-iteration is raised after a next(s_iter); will break out of loop, terminates entire block and go into except
    end = True # try to avoid using break -- can use Boolean instead 
```

## Simulating the range(...) function
```python
# Range
for elem in range(0, 10, 2):
  print(elem)

# Implementation: using Iterator
for elem in my_range(0, 10, 2):
  print(elem)
def my_range(start, stop, step): # three argument call
  res = [] #empty list
  curr = start #current
  while (curr < stop):
    res.append(curr)
    curr += step
  return res

# Implementation: using a Generator function
for elem in my_range(0, 10, 2):
  print(elem)
def my_range(start, stop, step):
	curr = start
	while (curr < stop):
	yield curr # instead of executing all values, it executes one value at a time everytime it goes through the for loop (takes less time)
	curr += step
# Main stack runtime: 5 variables * 2 frames = 10 variables/spaces
# More space efficient
```
### Implementation Drawbacks:
- The implementation is valid but there are problems
- Time concern: a lot of time spent to run ```my_range(0, 10, 2)``` before running ```iter(my_range(0, 10, 2))```
- We need only a single value (we don't need the memory of all the values in the range)
### Alternative (Better) Implementation:
- Continued

## Generators:

```python
# Yield Example
def f():
	x = 1
	yield x
	x += 1
	yield x
	x += 1
	yield x
```
* g = f()
  	* g --> <generator object f at 0x1234567>
	* next(g) --> 1
	* next(g) --> 2

* Generator is an iterator, that allows to break the execution:
* When **yield** is reached, a snapshot/moment of the active data frame is taken and stored (together with the line numer/position of where the execution can resume later).
	* Yield returns one value at a time and pauses the function.
 	* Using yield, the generator function pauses its execution and keep its state/value between iterations.
* When **next** is called
* Generators are **lazy evaluation** to produce an implicit iterable sequence. This means:
	* Each element is produced **only when/if** it is needed
 	* The entire sequence is never built and fully stores in the memory

# Asymptotic Analysis
  


