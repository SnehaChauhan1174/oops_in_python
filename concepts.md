### day 1 of learning consistently about python
## 14th nov
```
class Value:
    def __init__(self,data):
        self.data=data
    def __repr__(self): # a wrappe function to print objects in a good way
        return f"Value(data={self.data})"
    def __add__(self,other):
        out=Value(self.data+other.data)
        return out
    def __mul__(self,other):
        out=Value(self.data*other.data)
        return out

a=Value(2.0)
b=Value(-3.0)
a.__add__(b)
a*b
```
wrt above code:

How Python Translates a * b

1. Syntactic Sugar: When Python's interpreter sees the * symbol between two objects (a * b), it automatically converts that expression into a hidden method call: a.__mul__(b).
2. Object Lookup: Python checks the class blueprint of the object on the left side of the operator (a, which is an instance of Value) to see if it has a __mul__ method defined.
3. Passing Arguments:
	• self becomes a (the object on the left, where self.data is 2.0).
	• other becomes b (the object on the right, where other.data is -3.0).
4. Returning a New Object: Inside __mul__, Python multiplies the raw numbers (2.0 * -3.0 = -6.0), wraps the result in a brand-new Value object, and returns it—allowing you to chain more operations together later (like (a * b) + c).
5. 
