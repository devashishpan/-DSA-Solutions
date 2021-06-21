**Problem Statement:**\
The Fibonacci sequence is defined as follows:\the first number of the sequence is 0, the
second number is 1 and the nth number is the sum of the (n - 1)th and (n - 2)th numbers. Write a
function that takes in an integer n and returns the nth Fibonacci number.\
**Important note**: the Fibonacci sequence is often defined with its first two numbers as F0 = 0 and
F1= 1. For the purpose of this question, the first Fibonacci number is F0; therefore, getNthFib(1) is
equal to F0, getNthFib(2) is equal to F1, etc..


```python
#using reursion
def getfib(num):
    if num < 0 :
        print("Invalid number!!")
    elif num == 0:
        return 0
    elif num == 1 or num == 2:
        return 1
    else:
        return getfib(num-1) + getfib(num-2)
```


```python
#using loop
def getfib2(num):
    a,b = 0,1
    if num < 0:
        return "Invalid Number!"
    elif num == 0 :
        return a
    elif num == 1 or num == 2 :
        return b
    else:
        for i in range(num-1):
            a,b = b,a+b
        return b
```


```python
%timeit getfib(35)
```

    5.51 s ± 107 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)
    


```python
%timeit getfib2(35)
```

    3.5 µs ± 259 ns per loop (mean ± std. dev. of 7 runs, 100000 loops each)
    

As we can see the first approach takes 5.51 seconds to deliver the output while the second approach takes 3.5 micro-seconds to do the same operation. 


```python

```
