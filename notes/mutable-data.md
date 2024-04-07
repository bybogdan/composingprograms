**Lists**

```python
suits = ['hearts', 'diamonds', 'clubs', 'spades']

nest = list(suits) # ['hearts', 'diamonds', 'clubs', 'spades'] but not the same object and changes to one will not be reflected in the other

nest[0] = suits # will be the same as suits and all changes will be reflected in both
suits.insert(2, 'Joker') # will be reflected in nest too
print(nest) # [['hearts', 'diamonds', 'Joker', 'clubs', 'spades'], 'diamonds', 'clubs', 'spades']
```

**Tuples**

```python
code = ("up", "up", "down", "down") + ("left", "right") * 2
print(len(code)) # 8
print(code) # ('up', 'up', 'down', 'down', 'left', 'right', 'left', 'right')
print(code.count("up")) # 2
print(code.index("left")) # 4
```

**Dictionary**

```python
d = {'name': 'Alice', 'age': 25}
print(d['name']) # Alice

{x: x*x for x in range(3,6)}
# will create a dictionary with keys 3, 4, 5 and values 9, 16, 25
{3: 9, 4: 16, 5: 25}
```

** Local State**

```python
nonlocal x # to access the variable in the outer scope
# nonlocal under the hood do something like this to access the variable in the outer scope
def nonlocal_(x):
    def inner():
        nonlocal x
        x = 10
    inner()
    return x

print(nonlocal_(1)) # 10

# if we don't use nonlocal then the variable will be treated as a local variable
# we reiceve an error if we try to access it before it is defined
def nonlocal_(x):
    def inner():
        x = 10
    inner()
    return x

print(nonlocal_(1)) # UnboundLocalError: local variable 'x' referenced before assignment
```
