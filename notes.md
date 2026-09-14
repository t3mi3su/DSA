# Iterators & Generators 

```python```

## Iterators

```python for **var** in **iterable-collection:**```
  
### Iterable-collection: 
  an object that produces an iterator via the syntax: ```python iter(iterable_collection)```

### Iterator: 
  an object that exposes a series of values, by making subsequent calls to: ```python next(iterator)```
### List iterator:
  next(lst_iter)
  
### String iterator:
  next(str_iter)

## Simulating a **for** loop:

```python
s = "abc"
for item in s:
    print(item)
s = "abc"
s_iter = iter(s)
while ( ):
    item = next(s_iter)
    print(item)

```

