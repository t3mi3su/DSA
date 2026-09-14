# Iterators & Generators 

```python```

## Iterators

for **var** in **iterable-collection:**
  ___
  ___
  ___
  
### Iterable-collection: 
  an object that produces an iterator via the syntax: iter(iterable_collection)

### Iterator: 
  an object that exposes a series of values, by making subsequent calls to: next(iterator)
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
s_next = next(s_iter)
```

