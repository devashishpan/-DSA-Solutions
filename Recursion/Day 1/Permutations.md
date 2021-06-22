**Problem Statement:**\
Write a function that takes in an array of unique integers and returns an array of all permutations of those integers in no particular order.  \
If the input array is empty, the function should return an empty array.


```python
def permutate(l):
    result = []
    if len(l) == 1:
        return l
    else:
        for i,let in enumerate(l):
            for perm in permutate(l[:i] + l[i+1:]):
                if isinstance(perm,list):
                    perm.append(let)
                    result.append(perm)
                else:
                    result.append([let,perm])
    return result
```


```python
len(permute([1,2,3,4,5,6,7,8,9,10]))
```




    3628800




```python
permutate([1,2,3,4])
```




    [[3, 4, 2, 1],
     [4, 3, 2, 1],
     [2, 4, 3, 1],
     [4, 2, 3, 1],
     [2, 3, 4, 1],
     [3, 2, 4, 1],
     [3, 4, 1, 2],
     [4, 3, 1, 2],
     [1, 4, 3, 2],
     [4, 1, 3, 2],
     [1, 3, 4, 2],
     [3, 1, 4, 2],
     [2, 4, 1, 3],
     [4, 2, 1, 3],
     [1, 4, 2, 3],
     [4, 1, 2, 3],
     [1, 2, 4, 3],
     [2, 1, 4, 3],
     [2, 3, 1, 4],
     [3, 2, 1, 4],
     [1, 3, 2, 4],
     [3, 1, 2, 4],
     [1, 2, 3, 4],
     [2, 1, 3, 4]]


