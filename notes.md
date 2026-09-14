# Iterators & Generators 

```python```

## Iterators

```for **var** in **iterable-collection:**```
  
### Iterable-collection: 
  an object that produces an iterator via the syntax: ```iter(iterable_collection)```

### Iterator: 
  an object that exposes a series of values, by making subsequent calls to: ```next(iterator)```
### List iterator:
  next(lst_iter)
  
### String iterator:
  next(str_iter)

## Simulating a **for** loop:

```python
""" Default """
s = "abc"
for item in s:
    print(item)

""" Using Iterator to simulate """
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

