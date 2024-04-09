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

**Message Passing and Dot Expressions**

```python
type(Account.deposit)
<class 'function'>
type(spock_account.deposit)
<class 'method'>

Account.deposit(spock_account, 1001)  # The deposit function takes 2 arguments
1011
spock_account.deposit(1000)           # The deposit method takes 1 argument
2011
```

**Class Attributes**

```python
class Account:
        interest = 0.02            # A class attribute
        def __init__(self, account_holder):
            self.balance = 0
            self.holder = account_holder
        # Additional methods would be defined here

        spock_account = Account('Spock')

kirk_account = Account('Kirk')
spock_account.interest
0.02
kirk_account.interest
0.02

Account.interest = 0.04
spock_account.interest
0.04
kirk_account.interest
0.04

kirk_account.interest = 0.08

kirk_account.interest
0.08
spock_account.interest
0.04

Account.interest = 0.05  # changing the class attribute
spock_account.interest     # changes instances without like-named instance attributes
0.05
kirk_account.interest     # but the existing instance attribute is unaffected
0.08
```

**Inheritance**

```python
class Account:
    """A bank account that has a non-negative balance."""
    interest = 0.02
    def __init__(self, account_holder):
        self.balance = 0
        self.holder = account_holder
    def deposit(self, amount):
        """Increase the account balance by amount and return the new balance."""
        self.balance = self.balance + amount
        return self.balance
    def withdraw(self, amount):
        """Decrease the account balance by amount and return the new balance."""
        if amount > self.balance:
            return 'Insufficient funds'
        self.balance = self.balance - amount
        return self.balance


# A subclass of Account
class CheckingAccount(Account):
    """A bank account that charges for withdrawals."""
    withdraw_charge = 1
    interest = 0.01
    def withdraw(self, amount):
        return Account.withdraw(self, amount + self.withdraw_charge)
```

**Multiple Inheritance**

```python
class AsSeenOnTVAccount(CheckingAccount, SavingsAccount):
        def __init__(self, account_holder):
            self.holder = account_holder
            self.balance = 1

# inheritance order matters
# now order to find something is:
# AsSeenOnTVAccount -> CheckingAccount -> SavingsAccount -> Account -> object
```
