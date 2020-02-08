# Analysis of Algorithms

## Exercise I

Give an analysis of the running time of each snippet of
pseudocode with respect to the input size n of each of the following:

```python
a)  a = 0 [constant]
    while (a < n * n * n): [log n]
      a = a + n * n [constant]
```
O(log n)

```
b)  sum = 0 [constant]
    for i in range(n): [n]
      j = 1 [constant]
      while j < n: [n]
        j *= 2 [constant]
        sum += 1 [constant]
```
O(n^2)

```
c)  def bunnyEars(bunnies):
      if bunnies == 0: [constant]
        return 0 [constant]

      return 2 + bunnyEars(bunnies-1)
```
O(1)

## Exercise II

Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode AND give the runtime complexity of your solution.

1) Take amount of floors, divide via floor (//) by 2 for 'middle' of current set.
2) Assign floors lower than 'middle' to 'lower'
3) Assign floors higher than 'middle' to 'lower'
4) Check if 'middle' floor breaks an egg
  a) if so, take in 'lower' floor set and reset middle to 'middle' of 'lower'
  b) lower and higher resets to above-and-below of middle
  c) repeat these steps until threshold floor was found