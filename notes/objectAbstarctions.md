# Repr is a way to define how an object is represented as a string

```python
repr(3)
# '3'

repr(min)
# '<built-in function min>'


from datetime import date
tues = date(2011, 9, 12)
repr(tues)
'datetime.date(2011, 9, 12)'
str(tues)

# Can be used as method __repr__ to define how an object is represented as a string

tues.__repr__()
'datetime.date(2011, 9, 12)'


```
