**Sequence unpacking.**

```python
pairs = [(1, 'one'), (2, 'two'), (3, 'three'), (4, 'four')]

for pair in pairs:
    number, name = pair
    print(f'{number} is {name}')

# Or simpler
for number, name in pairs:
    print(f'{number} is {name}')
```

**Range.**

```python
for i in range(5):
    print(i) # 0 1 2 3 4, excludes 5

# can be used underscore for unused variable
for _ in range(5):
    print('Hello, World!')

```

**List Comprehensions.**

```python
squares = [x * x for x in range(10)]
print(squares) # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

**Aggregation.**

```python
def divisors(n):
  return [1] + [x for x in range(2, n) if n % x == 0]

divisors(4) # [1, 2]
divisors(12) # [1, 2, 3, 4, 6]
```

**Higher-Order Functions.**

```python
def reduce(reduce_fn, s, initial):
  reduced = initial
  for x in s:
      reduced = reduce_fn(reduced, x)
  return reduced

reduce(mul, [2, 4, 8], 1) # 64
```

**Membership Testing.**

```python
digits = [1, 8, 2, 8]
print(8 in digits) # True
print(100 not in digits) # True
```

**Slicing.**

```python
digits = [1, 8, 2, 8]
print(digits[1:3]) # [8, 2]
print(digits[2:]) # [2, 8]
print(digits[:3]) # [1, 8, 2]
```
