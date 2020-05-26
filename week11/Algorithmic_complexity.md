# How fast is fast? An introduction to Algorithmic Complexity

It is all about knowing how different algorithms scale.


Algorithims are a sequences of steps to solve a problem.


When your programming you are always writing algorithms.

How do they scale when you throw loads of data at them.

## Example

I want to know if the number 13 is in this sorted array:

OR

I want to know if any given value is any sorted arrary.

```[3, 8, 9, 11, 26, 32, 34]```

### 7 steps
- One approach is check each element one by one and check if 13 is in there.

### 3 steps
- Find the middle number and check if it is smaller or greater than 13. If it is less (it is, it is 11), check the next middle number on the right side (32). Then check if 26 is 13 (it is not) and now you know that 13 is not in the whole array. This works because it is a sorted array.

## How many guesses to cover this array.

---> 11 ---> 32 ---> 26

                ---> 34

---> 8 ----> 8 ----> 9

               ----> 3

This 3 guesses for an array size 7.
In 4 guesses it can search an array of 15.
In 5 guesses it can search an array of 31.
6 guesses - 63
7 guesses - 127
8 guesses - 255


Guesses | size | familiar number |
---|----|----|
3 | 7 | 8
4| 15 | 16
5| 31 | 32
6| 63 | 64
7| 127 | 128
8| 255 | 256


Graph
y - time
x - size

1st solution is linear x = y ish - this is linear complexity. O(n)


2nd solution is more like a log(x) - logarithmic complexplecity. O(log n)

## How fast is that

Input size | Linear search | Binary search |
--|---|--|
10 | 10 | 4
100 | 100 | 7
1000 | 1000 | 10
1000000 | 1000000 | 20
1000000000 | 1000000000 - 11 days in milliseconds | 30

## Sorting Algorithms

How to do it?

### 2 main ways (really like 20 or more)

```[21, 12, 1, 35, 13, 6, 3, 15]```

## Selection sort

Go over the whole array to find the minimum.

Put that into a new array.

Go over the array to find the minimum.

Put that into the new array.

Repeat until complete.

### Number of operations

-- Not sure this is correct.

1 | 3 | 6 | 12 | 13 | 15|  21 | 35
--|---|---|---|---|---|---|---|
x | x | x| x| x |  x  | x | x|
x | x | x| x| x |  x  | x | |
x | x | x| x| x |  x  |  | |
x | x | x| x| x |    |  | |
x | x | x| x|  |    |  | |
x | x | x| |  |    |  | |
x | x | | |  |    |  | |
x |  | | |  |    | | |


Or like this depending on whether 

1 | 3 | 6 | 12 | 13 | 15|  21 | 35
--|---|---|---|---|---|---|---|
x | x | x| x| x |  x  | x | x|
x | x | x| x| x |  x  | x | x|
x | x | x| x| x |  x  | x | x|
x | x | x| x| x |  x  | x | x|
x | x | x| x| x |  x  | x | x|
x | x | x| x| x |  x  | x | x|
x | x | x| x| x |  x  | x | x|
x | x | x| x| x |  x  | x | x|

This has quadratic complexity, will always eventually be slower than linear.

## Insertion sort

```[21, 12, 1, 35, 13, 6, 3, 15]```

Checks 3 and 15 and sees which one is smaller.

Then puts 3 and 15 in a new array.

```[3, 15]```

Then checks 6 and asks is it smaller or bigger than 3, than 15.

```[3, 6, 15]```

Then checks 13 and checks is it bigger than 3, 6, 15.

```[3, 6, 13, 15]```

And so on.

Number | steps |
---|---
15 | 1




21 | 12 | 1 | 35 | 13 | 6|  3 | 15
--|---|---|---|---|---|---|---|
x | x | x| x| x |  x  | x | x|
x | x | x| x| x |  x  | x | |
x | x | x| x| x |  x  |  | |
x | x | x| x| x |    |  | |
x | x | x| x|  |    |  | |
x | x | x| |  |    |  | |
x | x | | |  |    |  | |
x |  | | |  |    | | |


Also quadratic.

Therefore 

Selection sort and insertion sort are both 0(n^2)

How to improve it?

## Divide and conquer

psuedo python

```python
def solve (input):
  if inpute is simple enough that solution is trivial:
    return solution
  else:
    break input down into input 1 & input 2
    solution1 = solve (input1)
    solution2 = solve (input2)
    merge solution1 & solution2 into solution
    return solution
```

Only 3 steps.

1. What consists of a trivial input to sort?

Input | Output | Trivial?
-|-|-
[] | [] | Y
[2] | [2] | Y
[41] | [41] | Y
[5, 3] | [3, 5] | N

Check if array length is greater than 1.
```python
if len[arr] < 2
```

2. How should we break down the input?

[7, 5, 6, 2, 8] 

```python
left = arr[:len(arr)//2]
right = arr[len(arr)//2:]
```

---> [7, 5, 6] | [2, 8]

3. How do we merge 2 solutions into one?

Because we chose a really simple break down (we just split it in two) we have to think a little bit more about the merging.

They appear like a stack of cards with 5 on top, and 2 on top.

Keep taking the smallest from the two on the top.

2, 5

2, 5, 6

2, 5, 6, 7

2, 5, 6, 7, 8

This piece of code is the smart part.

We call this ```mergesort```

## Merge sort complextiy

```ruby
mergesort([21, 12, 1, 35, 13, 6, 3, 15])


l = 8

left = 21, 12, 1, 35

right = 13, 6, 3, 15

mergesort([21,12,1,35])
-> l = 4
-> lt = 21, 12
-> rt = 1, 35
-> mergesort([21, 12])
->-> l =2 
->-> lt = 21
->-> rt = 12
->-> s1 = [21]
->-> s2 = [12]
->-> return [12, 21]

solution1 = [12, 21]
solution2 = [1, 35]
R[1, 12, 21, 35]

solution1 = [1, 12, 21, 35]

.....

solution2 = [3, 6, 13, 15]

1, 3, 6, 12, 13 , 15, 21, 35

```

### Merge sort complexity

Works out as O(n log n)
