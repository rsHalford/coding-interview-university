# [Cracking the Facebook Coding Interview: Problem Walkthough](https://www.youtube.com/watch?v=4UWDyJq8jZg)

## "Given a list of people with their birth and death years, find the year with the highest population."

## 1. Identify Any Clues

- Assumption not everybody will be alive at the same time.
- Data is structured within an array.

## 2. Draw An Example

- Large enough
- No special cases

| Birth | Death |
| ----- | ----- |
| 2000  | 2010  |
| 1803  | 1844  |
| 1985  | 2003  |
| 1963  | 1998  |
| 1753  | 1810  |
| 1980  | 2005  |
| 1840  | 1922  |
| 1840  | 1935  |
| 1963  | 2007  |
| 1900  | 2000  |
| 1933  | 2016  |
| 1789  | 1859  |

## 3. Create A Brute Force Algorithm

- Don't code.

- Go through all years and check how many are alive in each year.
  - Between the years: 1753 (minimum birth year) - 2016 (maximum birth year)

### Runtime

#### First Attempt

- O( P) for minimum birth year.
  - P = people.
- O( P) for maximum death year.
- O(Y * P).
  - Y = range from first birth year to last death year.
  - P = how many people were alive then.

Runtime = O(PY).

- Now you would explain the brute force to the interviewer and ask if it would be okay to continue through to coding your brute force.
  - Unless you think there is a more optimal way.

## 4. Optimise

### BUD Optimisation

- Walk though your brute force example.
  - Population didn't change from 1753 until 1789.
- So only now need to check the years where someone was born or had died.
  - So not every year between the minimum birth year and maximum death year.
- Only need to take into account the unique years.

- O(P * P) to go through each person and determine how many people were alive in their birth year and how many were alive in their death year.
  - => O(P<sup>2</sup>)
  - Can be improved.

- O(U * P).
  - U = unique years.

#### Unnecessary Work?

- The highest population will always be during a birth year.
  - So why check all the death years?
  - Won't effect Big O, but will reduce runtime slightly.

- Try a different way of representing the data.
  - Draw a number line.
  ```
  1750____x______y_____z____________y_______x_________z__________2016
          ^_________________________________^
                 ^__________________^
                       ^______________________________^
  ```

#### Solve It Manually
- It doesn't matter who dies when. Just that the population number decrements that year.
  - Draw a new number line.
  ```
  1750___B_______B__________B___B______B__________B______________2016
                      D         D              D   D         D  D
         1       2    1     2   2      3       2  32         1  0
  ```
- Walking through the number line to see highest population is a new agorithm.
  - In linear time => O(N).
  - ? = Ask interviewer if this death is dealt with as a death year decrement or if the decrement is recorded for the following year's population number.
    - Going with a next year decrement.

### New Algorithm

- Create a table for each year.
- Add +1 at each birth year and -1 for each year after a death year.

| Birth | Death |
| ----- | ----- |
| 2000  | 2010  |
| 1803  | 1844  |
| 1985  | 2003  |
| 1963  | 1998  |
| 1753  | 1810  |
| 1980  | 2005  |
| 1840  | 1922  |
| 1840  | 1935  |
| 1963  | 2007  |
| 1900  | 2000  |
| 1933  | 2016  |
| 1789  | 1859  |

| Year | Delta |
| ---- | ----- |
| 1753 | 1     |
| 1789 | 1     |
| 1803 | 1     |
| 1811 | -1    |
| 1840 | 1     |
| 1840 | 1     |
| 1845 | -1    |
| 1860 | -1    |
| 1900 | 1     |
| 1923 | -1    |
| 1933 | 1     |
| 1936 | -1    |
| 1963 | 1     |
| 1963 | 1     |
| 1980 | 1     |
| 1985 | 1     |
| 1999 | -1    |
| 2000 | 1     |
| 2001 | -1    |
| 2004 | -1    |
| 2006 | -1    |
| 2008 | -1    |
| 2011 | -1    |
| 2017 | -1    |

- Walk through to find the highest population.

| Year | Delta | Total |
| ---- | ----- | ----- |
| 1753 | 1     | 1     |
| 1789 | 1     | 2     |
| 1803 | 1     | 3     |
| 1811 | -1    | 2     |
| 1840 | 1     | 3     |
| 1840 | 1     | 4     |
| 1845 | -1    | 3     |
| 1860 | -1    | 2     |
| 1900 | 1     | 3     |
| 1923 | -1    | 2     |
| 1933 | 1     | 3     |
| 1936 | -1    | 2     |
| 1963 | 1     | 3     |
| 1963 | 1     | 4     |
| 1980 | 1     | 5     |
| 1985 | 1     | 6     |
| 1999 | -1    | 5     |
| 2000 | 1     | 6     |
| 2001 | -1    | 5     |
| 2004 | -1    | 4     |
| 2006 | -1    | 3     |
| 2008 | -1    | 2     |
| 2011 | -1    | 1     |
| 2017 | -1    | 0     |

## 5. Walk Through: What's the final runtime?

- O(P + Y + P + Y).
  - P = from minimum birth year to maximum death year.
  - Y = create array from minimum birth year to maximum birth year.
  - P = walking through the people calculating the changes in delta.
  - Y = go through the array and get the running sum down the years.

Total runtime = O(P + Y)

## 6. Implement

- On the whiteboard make sure you have enough space.
- Write horizontally.
- See if it's okay to not use a Person class.
  - As it only contains two variables in birth and death year.
- Code top level method first and not the helper funcitons.

  ```
  int getPopulationPeak(Person[] people) {
    // Modularise getM__Birth for loops
    int firstBirth = getMinBirth(people);
    int lastBirth = getMaxBirth(people);
    int[] deltas = getDeltas(people, firstBirth, lastBirth);
    int peakYear = getMaxRunningSumIndex(deltas);
    return peakYear + firstBirth;
  }

  // Use hand once objects have been defined. Person[] = P[].
  int[] getDeltas(P[] people, int firstBirth; int lastBirth) {
    int[] deltas = new int[lastBirth - firstBirth];
    for (P person : people) {
      addDelta(delta, p.birth, 1)
      addDelta("   ", .death, -1) // Using shorthand notation.
    }
    return dealtas;
  }

  int getMaxRunningSumIndex(int[] deltas]) {
    int runningSum = 0;
    int maxRunningSum = 0;
    int yearOfPeak = 0;
    for (int year = 0; year < deltas.length; year++) {
      runningSum += deltas[year];
      if (runningSum > maxRunningSum) {
        maxRunningSum = runningSum;
        yearOfPeak = year;
      }
    }
    return yearOfPeak;
  }
  ```

## 7. Test

1. Walk through logic.
    ```
    int[] getDeltas(P[] people, int firstBirth; int lastBirth) {
      int[] deltas = new int[lastBirth - firstBirth];
      for (P person : people) {
        addDelta(delta, p.birth, 1)
    --> addDelta(delta, p.death, -1)
      }
      return dealtas;
    }
    ```
    - As stated [before](#solve-it-manually), it's decrement the year after the death year.
    - `addDelta(delta, p.death + 1, -1)`

2. Unusual or none standard code?
3. Hot spots?
    - Maths can cause problems.
    - `[lastBirth - firstBirth + 1]`
4. Small test cases.
    - Using small year range allows you to run through the code quickly. Compared to the original example table created.
    ```
    2000, 2001
    2001, 2002

    [lastBirth - firstBirth + 1]    // = 2
    ```
    ```
    2000, 2001 - 0 : 1
    2001, 2002 - 1 : 1

    addDelta(delta, p.birth-firstBirth, 1)
    addDelta(delta, p.death-firstBirth, 1)
    ```
5. Special and edge cases.
6. Found a bug? Fix it carefully.
