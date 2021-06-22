**Problem Statement**:\
You're given two positive integers representing the height of a staircase and the maximum number of steps that you can advance up the staircase at a time.\
Write a function that returns the number of ways in which you can climb the staircase.\
For example,\
if you were given a staircase of height = 3 and maxSteps = 2 you could climb the staircase in 3 ways.\
You could take 1 step, 1 step, then 1 step,\
you could also take 1 step, then 2 steps ,\
and you could take 2 steps, then 1 step


```python
def countWays(height, maxSteps):
    if height < 0:
        return 0
    if height == 0:
        return 1
    ways = 0
    for steps in range(1, maxSteps + 1):
        ways += countWays(height - steps, maxSteps)
    return ways
```


```python
countWays(4,2)
```




    5




```python
countWays(20,19)
```




    524287


