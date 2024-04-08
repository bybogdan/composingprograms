**Object&Classes**

```python
class Account:
        def __init__(self, account_holder):
            self.balance = 0
            self.holder = account_holder

        def deposit(self, amount):
            self.balance = self.balance + amount
            return self.balance



a = Account("Alice")
b = Account("Bob")

b is a # False
a.deposit(100) # 100
b.deposit(50) # 50
a.deposit(200) # 300
a.balance # 300
```
