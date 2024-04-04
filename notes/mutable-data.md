**Lists**

```python
suits = ['hearts', 'diamonds', 'clubs', 'spades']

nest = list(suits) # ['hearts', 'diamonds', 'clubs', 'spades'] but not the same object and changes to one will not be reflected in the other

nest[0] = suits # will be the same as suits and all changes will be reflected in both
suits.insert(2, 'Joker') # will be reflected in nest too
print(nest) # [['hearts', 'diamonds', 'Joker', 'clubs', 'spades'], 'diamonds', 'clubs', 'spades']
```
