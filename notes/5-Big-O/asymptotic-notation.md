# Asymptotic Notation

Asymptotic complexity:
> How does the runtime change as the size of the inputs grows?

- O(n) = Linear time
- O(1) = Constant time ("asymptotically constant")
  - Irrelevant of array length.

---

- Even though O(n<sup>2</sup>) may run faster with small input sizes.
- Once the number of inputs starts to increase, the algorithm can quickly become slower than O(n).

---

#### O(log n)

- Common example: Binary search tree.

```
Find the int 3 in an array [1, 2, 3, 4, 5, 6, 7, 8]

1st run through = [1, 2, 3, (4), 5, 6, 7, 8]
  4 is greater than 3.

=> 2nd run through = [1, (2), 3]
  2 is smaller than 3.

=> 3rd run through = [(3)]
  This took 3 operations.
```

- Therefore, this example would equate to log<sub>2</sub>8
- An array of size 16 => log<sub>2</sub>16 = 4 operations.
  - Only 1 operation longer than that of an array of size 8.

- The upper and lower and lower bounds describe the range of the runtime.
```
To find 4 in array = [1, 2, 3, 4, 5, 6, 7]

1st run through = [1, 2, 3, (4), 5, 6, 7]
  This took only constant time.
```

- This best case runs at Ω(1) ("Omega of one")
  - It will find the element quickly no matter the length of the array.

- The worst case is O(logn)

---

#### O(n)

- Following the same example with finding an element within an array.
  - `Find 1 in array [1, 2, 3]`

- As 1 will be the first number that will be found using a linear approach.
  - This means that the best is still Ω(1) time.
  - As no matter how long this array gets the number 1 will be found first.

- But as a worst case (n being at the end of an array), you would have to walk through all elements of the array to find n.
  - Therefore, this means = O(n).

---

#### O(n log n)

- When sorting an array, the best outcome will be O(n).
  - As every element has to be checked by the algorithm in order to be ordered.
  - With inefficient algorithms having the potential to being of O(n<sup>2</sup>).

Example: Bubble sort
  - Best case => Ω(n)
  - Average / Worst case => Θ(n<sup>2</sup>)

Example: Quick sort
  - Ω(n log n)
  - Θ(n log n)
  - O(n<sup>2</sup>)

#### Θ, Theta

- This notation describes when the algorithms best and worst cases are the same.

- Example: Looking at a variable of array length before walking through the array with an algorithm.
  - Best case = Ω(1)
  - Worst case = O(1)
  - As they're both the same => Θ(1)
