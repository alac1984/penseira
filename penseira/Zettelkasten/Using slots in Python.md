29/01/2023 21:58

Tags: [[Python]]

Slots are a more safe and efficient way for data access in Python. To use slots, you should create a class like this:

```python
class Example():
    __slots__ = ("slot_0", "slot_1")
    
    def __init__(self):
        self.slot_0 = "zero"
        self.slot_1 = "one"
        
x1 = Example()
print(x1.slot_0)
# zero
print(x1.slot_1)
# one
```

---
# References

https://wiki.python.org/moin/UsingSlots#:~:text=What%20Is%20%60__slots__%60%20%3F&text=The%20__slots__%20declaration,declared%20in%20__slots__.