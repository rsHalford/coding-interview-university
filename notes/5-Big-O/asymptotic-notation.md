# Asymptotic Notation

### Big Oh

Definition:
```
f(n) is O(g(n)) if C and n₀, for which f(n) <= Cg(n) for all n > n₀
```
##### Example:

f(n) = 4n<sup>2</sup> + 16n + 2

Is f(n) = O(n<sup>4</sup>) ?

=> 4n<sup>2</sup> + 16n + 2 < Cn<sup>4</sup>

Are the following statements true?

| n | 4n<sup>2</sup> + 16n + 2 < n<sup>4</sup> | True? |
| - | ---------------------------------------: | ----- |
| 0 | 2 < 0                                    | False |
| 1 | 22 < 1                                   | False |
| 2 | 50 < 16                                  | False |
| 3 | 86 < 81                                  | False |
| 4 | 130 < 256                                | True! |

=> For C = 1 and n<sub>0</sub> >= 4, 4n<sup>2</sup> + 16n + 2 is True.

=> Is f(n) = O(n<sup>4</sup>) ? Yes.

---

### Big Ω

Definition:
```
f(n) is Ω(g(n)) if C and n₀, for which f(n) >= Cg(n) for all n > n₀
```
##### Example:

f(n) = 4n<sup>2</sup> + 16n + 2

Is f(n) = Ω(n<sup>2</sup>) ?

=> 4n<sup>2</sup> + 16n + 2 > Cn<sup>2</sup>

Are the following statements true?

| n | 4n<sup>2</sup> + 16n + 2 > n<sup>2</sup> | True? |
| - | ---------------------------------------: | ----- |
| 0 | 2 > 0                                    | True  |
| 1 | 22 > 1                                   | True  |
| 2 | 50 > 4                                   | True  |
| 3 | 86 > 9                                   | True  |
| 4 | 130 > 16                                 | True  |

=> For C = 1 and n<sub>0</sub>, 4n<sup>2</sup> + 16n + 2 is always True.

=> Is f(n) => Ω(n<sup>2</sup>) ? Yes.

---

For standard form quadratic equations, an<sup>2</sup> is the dominant force in the function.

When x of Cn<sup>x</sup> becomes greater than a of an<sup>2</sup>. The question, f(n) comapred to Ω(n<sup>x</sup>) (i.e. f(n) > Cg(n)) will always be false.

---

### Big Θ

Definition:
```
f(n) is Θ(g(n)) if both are true;
    1) f(n) is Ω(g(n))
    2) f(n) is O(g(n))
```
#### Example:

f(n) = 4n<sup>2</sup> + 16n + 2

Is f(n) = Θ(n<sup>2</sup>) ?

=> 4n<sup>2</sup> + 16n + 2 = Cn<sup>2</sup> ?

##### For Ω to be True:

f(n) is Ω(n<sup>2</sup>),

=> 4n<sup>2</sup> + 16n + 2 **>** Cn<sup>2</sup>

C = 1, n<sub>0</sub> = 0

=> Always True.

##### For O to be True:

f(n) is O(n<sup>2</sup>),

=> 4n<sup>2</sup> + 16n + 2 **<** Cn<sup>2</sup>

C = 5, n<sub>0</sub> = 17 => Will be True.

**=> Both requirements 1 & 2 are met.**

---

#### Relating to Computer Programs

T(n) = 4n<sup>2</sup> + 16n + 2
- T = runtime
- T(n) = a representation of the time a program takes to execute.
  - E.g.: 4n<sup>2</sup> = nested for loop; 16n = walking through an array; 2 = printing the answer

Therefore, we can know that with n >= 17. The program's runtime, T, will always be slower than Ω(n<sup>2</sup>) and faster than O(5n<sup>2</sup>).
- Ω(n<sup>2</sup>) < T(n) < O(n<sup>2</sup>)
- T(n) = Θ(n<sup>2</sup>)

As when;
- n = 0 => T(n) = 2 "seconds"; as the + 2 in the equation is the only part of the program to run (printing the answer).
- n = 1 to 4 => The runtime is determined predominantly by the linear walk through of the array.
- Then will every increment in n >= 5, the %age of the program's runtime is determined more and more from the nested for loop.

##### Concluding;
- T(n) = 4n<sup>2</sup> + 16n + 2 is Θ(n<sup>2</sup>)
  - Means that when n increases, the determining factor with regards to runtime will be realted to the n<sup>2</sup> portion of the algorithm, and not so much the bn + c processes.
    - This is why although it is always good to make sure bn + c runtimes are optimised or removed, the focus when creating algorithms for a program should be focussed initially on the big players in what determines runtime. In these examples, that has been 4n<sup>2</sup>.
- When creating algorithms, we need to always try to make the upper bounds as lower as possible.
  - This means never seeing anything above O(n<sup>2</sup>) as an option, and trying to reduce this down to faster runtimes, closer to Ω(n).

---

### Logorithms

- log<sub>x</sub>n => O(log<sub>y</sub>n) will always be true.

##### Examples

1. x = y
    - C = 1, n<sub>0</sub> = 0
    - f(n) = log<sub>2</sub>n == O(log<sub>2</sub>n)
2. x < y
    - C = 1, n<sub>0</sub> = 0
    - f(n) = log<sub>2</sub>n <= O(log<sub>8</sub>n)

If an algorithm's runtime, T(n) had a term in it that had log<sub>x</sub>n.
- T(n) is O(log<sub>y</sub>n)
- Meaning that the value of the log bases doesn't matter, regarding runtimes.
- => T(n) = O(logn)

---

### Algorithmic Complexitiy:
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

#### Regarding Θ

- This notation describes when the algorithms best and worst cases are the same.

- Example: Looking at a variable of array length before walking through the array with an algorithm.
  - Best case = Ω(1)
  - Worst case = O(1)
  - As they're both the same => Θ(1)
