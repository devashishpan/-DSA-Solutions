**Problem Statement** :\
Write a function that takes in an array of unique integers and returns its powerset.\
The powerset P(X) of a set X is the set of all subsets of X. For example, the powerset of [1,2] is [[], [1], [2], [1,2]].\
Note that the sets in the powerset do not need to be in any particular order.



```python
def powerSet(L):
    if len(L) == 0:
        return [[]]
    else:
        subset = powerSet(L[:-1])
        element = L[-1:]
        return subset + [(i + element) for i in subset]
```


```python
len(powerSet([1,2,3,4,5,6,7,8,9]))
```




    512




```python
powerSet([1,2,3])
```




    [[], [1], [2], [1, 2], [3], [1, 3], [2, 3], [1, 2, 3]]


