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

## Computational Problem
- Definition:
- 	When stating a problem:
  	1. Define a set of legal inputs
  	2. Define the required outputs, for each input 

## Algorithms
- Definition:
- 	continued
### Analyzing Algorithms
* **Correctness**: An algorithm is correct if for **every** valid input, it:
  	* terminates (halts)
  	* provides the desired output
* **Performance**: Measure the resources an algorithm requires. Common resources:
	* time of computation
 	* pace (memory use)
  * disk use, disk-memory communication, number of processors (in a parallel program), amount of communication (in a distributed program)
 
## Primality Testing
- Definition: Let num > and = be an integer. We say that num is prime, if its only divisors are 1 and num.
- 	Ex: 13 is a prime. 12 is not a prime.
- Definition: Let num > and = to be an integer, and let d and k be two divisors of num -> We say that k and d are complementary divisors of num -->
  	**d x k = num**
- 	Ex: 4 and 25 are complementary divisors of 100.


### Version 1
- 	Check the entire list: num
- 	```python
   	def is_prime1(num):
   		initialize a counter to zero
   		for current_number in range from 1 to num + 1:
   			if the remainder of the number divided by current_number is equal to 0:
   				add to the counter
   				return the counter
### Version 2
- 	Check the first half of num: num/2
- 	Syntax: check ```for current_number in range (1, num//2 + 1):``` and if the count = 1, then the number is a prime number.


### Version 3
- 	Check until the square root of num: num^1/2
- 	Syntax: check ```for current_number in range (1, int(math.sqrt(num) + 1):``` and if the count = 1, then the number is a prime number.

## Runtime Analysis
We define an abstract measure for analyzing the runtime of an algorithm:
1. Analyze the runtime as a **function** of the **size of the input** -> find **T(n)**
2. Use the **random-access machine (RAM)** model of computation -> basically a **pseudocode** language
     - Any number occupies constant storage and can be read and/or written in constant time
     - Each primitive operation takes constant time
       (primitive operations: +, -, x, =, square root, etc.)
3. Make **asymptotic** analysis -> **find the order of growth of T(n).**

- Basically: when analyzing **runtime** of an algorithm: find **the asymptotic number of primitive operations** that the algorithms performs, as **a function of its input size.**
- Example: calculating runtime of Version 1, Version 2, Version 3:
  	- T1(n) = 1 + 2 + (5 + 5 + ... + 5 -> n times) + 2 = 5n + 5
  	- T2(n) = 1 + 3 + (5 + 5 + ... + 5 -> n/2 times) + 2 = 5(n/2) + 6
  	- T3(n) = 1 + 4 + (5 + 5 + ... + 5 -> sqrt(n) times) + 2 = 5(sqrt(n)) + 7



