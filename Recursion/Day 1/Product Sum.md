**Problem Statement:**\
Write a function that takes in a "special" array and returns its product sum. A "special" array is a non-empty array that contains either integers or other "special" arrays.  The product sum of a "special" array is the sum of its elements,  where "special" arrays inside it are summed themselves and then multiplied by their level of depth.\
The depth of a "special" array is how far nested it is.\
For instance, 
* the depth of []is 1; 
* the depth of the inner array in [[]] is 2; 
* the depth of the innermost array in [[[]]] is 3.\
Therefore,
* the product sum of [x, y] is x + y; 
* the product sum of [x, [y, z]] is x + 2 * (y + z); 
* the product sum of [x, [y, [z]]] is x + 2 * (y + 3z).


```python
#If one is interested to find the depth of the nested array
depth = lambda L: isinstance(L, list) and max(map(depth, L))+1
```


```python
#let us take an example
a = [5,2,[7,-1],3,[6,[-13,8,[1]],4]]
```


```python
depth(a)
```




    4




```python
#now onto the solution to the problem statement
def findProductSum(L,level=1):
    sum_ = 0
    for item in L:
        if isinstance(item,list):
            level+=1
            k = findProductSum(item,level)
            level=level-1
            sum_= sum_+level*k
        else:
            sum_+=level*item
    return sum_
```


```python
#lets test it
findProductSum(a)
```




    36




```python
#lets verify
5+2+2*(7-1)+3+2*(6+3*(8-13+(4*1))+4)
```




    36


