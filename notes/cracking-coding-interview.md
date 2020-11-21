## [Cracking the Coding Interview](https://www.youtube.com/watch?v=rEJzOhC5ZtQ)

### How You Are Judged

#### How did you do relative to other candidates on the same question?

  - Not about how quickly you solved the problem.
  - It's about how quickly you solved it relative to other candidates.
  - Comparing other factors, suc as mistakes made.
  - Don't judge it based on how the interviewer reacts to you.

___

### Resumes and Application Process

#### How to Get an Interview

1. Build something.
    - Don't waste your summers (or free time).
2. Make a "kick-ass" resume.
    - It's simple.

#### How Resumes are Reviewed

1. Pull resume out of a giant stack.
2. Spot-check: company names, positions, projects, schools.
3. Skim bullets to see if you've written real code.

Steps 1-3 take 15-30 seconds, and are followed by either a rejection or interview.

4. Repeat.

#### How a CS Resume Should Look

- Cover letter only if required.
  - Your message, email, phone call reaching out to a recruiter **is** your cover letter.
- One page only.
  - Unless >10 years exp.
  - No objectives or summaries.
- A real resume format.
  - With organised columns.
  - Keep a linear structure.
- Short.
  - 1-2 lines per bullet.
- Focus on accomplishments.
  - Not responsibilities.
- GPA (grade) if at least >3.0 (2:1).
- 3-4 projects.
  - Courses and independent.
  - Finished and unfinished.
- List of technical skills.
  - Keep it short, and just name them. No "fluff."
  - No one cares about MS Office, or your interpersonal skills.
  - Only show soft skills if they can be quantified.

#### Communication Tips

##### Goals
- Answer the question.
  - If you can't match the question, at least speak coherently.
- Deliver a **good** answer.
- Communicate well.
- Preparing for Behavioural Questions
  - Create a preparation grid for projects.
   
  |                   | Project One | Project Two |
  | ----------------- | ----------- | ----------- |
  | Enjoyed           |             |             |
  | Hated             |             |             |
  | Most Challenging  |             |             |
  | Hardest Bug       |             |             |
  |                   |             |             |
  | Mistakes          |             |             |
  | Challenges        |             |             |
  | Influence People  |             |             |
  | Conflict Response |             |             |

  - Prepare to ask them questions. Write up a list of questions you want answering before-hand. These fall into two type:
    - Things you actually want to know.
    - Things that just make you sound good.
        - Their technology, design decisions, their influence.
        - How many meetings do you have per week?
        - How do you spend your typical day?
        - How do decisions get made? Who will lead me? An actual developer?

##### Strategies
Nugget first.
- Lead with your "thesis" / nugget.
  - Grabs the listener's attention.
  - Gives them context for where you're going.
- Example:
  - Question: "What accomplishment's are you most proud of?"
  - Answer: "I'm most proud of the way I re-architected the..."

S.A.R.
- Situation: What was the issue?
- Action: What did you do about it?
- Result: What was the impact?

___

### Technical Skills and Interview Preparation

#### How to Study

- Textbooks (e.g. CLRS) are probably overkill for the interview.
  - Interviewer will probably not remember this information.
  - Interviewer will want to know your aptitude not you knowledge.
- Write on paper/whiteboard and not in an IDE.
  - Even test it on paper first. Similar to an interview.

##### Data Structures

- How to implement.
- When to use (pros / cons).
- Hashtables are the most common to come up in interviews.

|              |        |            |
| ------------ | ------ | ---------- |
| Linked Lists | Stacks | Queues     |
| Trees        | Tries  | Graphs     |
| Vectors      | Heaps  | Hash Tables |

##### Algorithms

- How to implement.
- Space vs Time Complexity.
- Most important are Tree Insert / Find and Depth-First Search.

|                      |                    |
| -------------------- | ------------------ |
| Quick Sort           | Merge Sort         |
| Tree Insert / Find   | Binary Search      |
| Breadth-First Search | Depth-First Search |

##### Concepts

- Not just a concept - know how to code.
- Even if your chosen language doesn't wor directly with it. Practice the concepts by hand.
  - i.e. Bit manipulation, Memory management.

|                      |                              |
| -------------------- | ---------------------------- |
| Threading            | System Design & Scalability  |
| Recursion            | Probability & Combinatronics |
| Memory Management    | Bit Manipulation             |
| Big O Time           | Big O Space                  |

___

### Technical Skills and Mastering the Interview

#### Types of "Serious" Questions

1. Product Design Questions.
    - Mostly for PM and APM.
2. Estimation Questions.
    - Mostly for PM and APM.
3. Software Engineering Questions.
    - Coding and Algorithms.
    - Object Oriented Design.
    - Scalability.

**_Skipping notes for 1 & 2._**

##### Software Engineer Questions

1. Ask questions.
    - Questions are more ambiguous than they appear.
2. Talk out loud.
    - Show them how you think.
3. Think critically.
    - Does you algorithm realy work?
    - What's the space and time complexity?
4. Code slowly and methodically.
    - It's not a race.
5. Test your code.
    - Making careful fixes.

##### What does a "good coder" do?

- Be methodical and don't rush.
- Reasonably bug free.
  - Thorough testing and careful fixing.
  - Check for error conditions.
- Clean coding.
  - Use other functions.
  - Can it be modular?
  - Good use of data structures.
  - Concise and reasonble.

#### Types of Interview Questions

##### Coding & Algorithms

1. Pattern Matching
    - Compare to similar problems.
    - Question: Write code to reverse the order of words in a sentence.
      - "dogs are cute"
      - "cute are dogs"
    - Similar to: reverse characters in a string.
      - "dogs are cute"
      - "etuc era sgod"
    - Answer: Reverse full string, then reverse each word.
2. Simplify & Generalise
    - Solve first for a simplified / tweaked problem.
    - Question: Design algorithm to figure out if you can build a ransom note (array of strings) from a magazine (array of strings).
    - Simplify: What if we used characters instead of strings?
      - Build array of character frequencies.
    - Generalise: How we can extend answer to words?
    - Answer: Build hashtable from word to frequency.
3. Base Case & Build
    - Solve for `n=1`, and build solution for `n=2`.
    - Question: Design algorithm to print subsets of set.

    ```
    {a,b,c}    ->    {},{a},{b},{c},{a,b},{a,c},{b,c},{a,b,c},
    S({})      ->    {}
    S({a})     ->    {},{a}
    S({a,b})   ->    {},{a},{b},{a,b},
    S({a,b,c}) ->    ?
    ```

    - Answer: Build S(n) by cloning S(n-1) and adding n to the cloned sets.
4. Data Structure Brainstorm
    - Try to apply data structure to solve problem.
    - Question: There are 10<sup>10</sup> possible phone #s. Explain how you could efficiently implement assignSpecificNum(num) and assignAnyAvailableNum().
      - Array (sorted)?: Too slow to remove num.
      - Linked list?: Too slow to find specific num.
      - Hash table?: Can't iterate through free nums.
    - Answer: Store free #s in Binary Search Tree. Remove when taken.

##### Object Oriented Design

1. Handle ambiguity.
    - What about the question is ambiguous?
2. Design the core objects.
    - What are the main objects in the system?
3. Analyse relationships.
    - How are the objects related to each other?
4. Investigate actions.
    - What are the main operations?

Question: How would you design the data structures and objects for a restaurant?

1. Is it a single restaurant, or part of a chain?
2. Guest, Party, Table, Server, Host, etc.
3. **Server** and **Host** are both **Employees**.
    - **Employee** class
    - **Party** has an array of each **Guest**.
4. A **Party** is seated at a **Table** by a **Host**.
    - How do you know what **Tables** are availble for **Party**?

##### System Design

1. Handle ambiguity.
    - What about hte question is ambiguous?
2. Make believe.
    - Pretend there wasn't so much data and solve.
3. Get real.
    - Go back to the real problem. What breaks?
4. Solve problems.
    - Solve the issues you just found.

Question: Given millions of documents, find all documents which contain a list of words.

1. Do the words need to be in a specific order?
2. Assume everything can fit on one machine.
3. Must split up data across machines.
4. Divide hash tables by file or by keyword?
    - Once you know how to solve hash tables this is purely a problem solving question.

___

### After Your Interview

- Follow up with your recruiter.
  - No response doesn't mean your application has been rejected.
  - Send a thank you email to your recruiter.
  - Follow up after a week, then a couple more before trying to phone in.
- You will have no idea how well/poorly you did 
- Lots of randomness in the whole process.
  - If you fail, try again.
  - Usually you can reapply in 6-12 months.

---
___

**_If anything is repeated from interviews it'll be left out or added to the previous notes._**

## [Cracking the Facebook Coding Interview: Approach](https://www.youtube.com/watch?v=wCl9kvQGHPI)

### A Typical Technical Interview

- 5 minutes: Prior experiences.
- 45 minutes: Answer 2 questions.
  - Might only have time for 1 question.
- 5 minutes: Ask questions for interviewer.

---

### Behavioural Questions

#### The Pitch / Resume Walkthrough

- Shows of success.
  - Not necessarily what feature you implemented.
  - Could be how your boss asked you to join his start-up.
- Prompt the interviewer.
  - Guide your intereviwer to talk about what you want to talk about.
- Hobbies.
  - When in doubt say what your hobbies are.
  - Frame them in the most positive light.
  - Mention technical hobbies and your accomplishments there (learning a new language, hackerthons).
  - Even non-techincal hobbies can show risk-taking, persistence, and a willingness to take on challenges.

Following a story/timeline of your experiences.

Example:

```
"I am a ___ at ___" => "At university, I studied ___ at ___."
=> "Then I worked for ___ where I ___" => "Then I worked for ___ where I ___"
=> "In my current job, I've accomplished ___" => "Also, outside of work, I ___"
```

#### Your Past Work

[**_Add to grid_**](#goals)

1-2 hard projects:
- Hard / cool.
- You were central.
- Technical depth.
- What did you do?
- What would you do differently?

All past work:
- Challenges, architecture, tradeoffs, mistakes, successes, motivations.
- Teamwork, leadership, conflicts, etc.
- What did you do?
- What would you do differently?

#### What You Should Be Showing Off

- That you're **PASSIONATE**.
- That you're **KNOWLEDGEABLE**.
- That you're a **GOOD TEAMMATE**.

---

### Design Questions

#### Approach

[**_Add to system design_**](#system-design)

##### How To Answer A Question

**W**hat **W**ould **Y**ou **D**o **A**t **W**ork?

1. Scope.
    - Ask questions.
    - Make appropriate assumptions.
2. Key components.
    - Can be somewhat naive.
3. Identify issues.
    - Bottlenecks and tradeoffs.
4. Repair and redesign.

##### How To Act

_Using a whiteboard_

Drive
- Lead the process.
  - Act as the senior engineer.
- Be open about issues.
  - Show that you're constantly analysing and giving each potential issue some thought.

Teamwork
- Be open to feedback.
- Tweak as necessary.

##### How To Prepare

Fundamentaly problem solving questions and not about your knowledge.

- Read about design of major companies.
  - Understand it. Don't try to memorise it.
  - What is Company A's infrastructure, and why have they chosen that approach over one like at Company B?
- Know the key concepts.
  - Task, sharding, caches.
  - Web stack, REST, etc.
- Practice "back-of-the-envelope" calculations.
  - You may need to work out database sizes, number of users, unique URLs, etc.

##### Preparation Takeaways

- Master Big O.
- Implement data structures and algorithms.
- Practice with interview questions.
- Code on paper / whiteboard.
- Mock interviews.

---

### Big O: Loops

- Print 0 through N:
  - Runtime = O(N)
  ```
  for i = 0 to N
    print i
  ```

- Print evens:
  - Runtime = O(N)
  - Although it's techincally O(2N), it's still linear.
  - Drop constants.
  ```
  for i = 0 to N
    if i % 2 == 0:
      print i
  ```

- Print evens, then odds:
  - Runtime = O(N)
  ```
  for i = 0 to N
    if i % 2 == 0:
      print i
  
  for i = 0 to N
    if i % 2 != 0:
      print i
  ```

- Print pairs:
  - Runtime = O(N<sup>2</sup>)
  ```
  for i = 0 to N
    for j = 0 to N:
      print i + ", " + j
  ```

- Print ordered pairs:
  - Runtime = O(N<sup>2</sup>)
  ```
  for i = 0 to N
    for j = i to N:
      print i + ", " + j
  ```

- Print ordered pairs:
  - Runtime = O(A * B)
    - Not O(N<sup>2</sup>)
    - A.length and B.length are separately defined lengths.
  ```
  for i = 0 to A.length
    for j = 0 to B.length
      print A[i] + ", " + B[j]
  ```

#### Loops Example

  ```
  int last-death = Integer.Min

  /* step 1: get last death */
  for (Person person : people) {
    last_death = max(last_death, person.death)
  }

  /* step 2: increment counter for each year someone is alive */
  int[] counter = new int[last_death]
  for (Person person : people) {
    for (int year = person.birth; year < person.death; year++) {
      counter[year]++;
    }
  }

  /* step 3: find population peak */
  int highest_population = 0
  for (int year = 0; year < counter.length; year++) {
    highest_population = max(highest_population, counter[year])
  }
  ```

1. O(N): P = number of people.
2. O(N * L): L = max life span.
3. O(Y): Y = total number of years.

  ```
  =>  O(N + N * L + Y)
  =>  O(N * L + Y)
  ```
- Add when you're combining each separate loop.
- Multiply when the interation/loop has a parent interation/loop.

___

### Big O: Recursion

- Fibonacci
  ```
  1. 

  int fib(int n) {
    if (n == 0 || n == 1) {
      return 1;
    } else {
      return fib(n - 1) + fib(n - 2);
    }
  }

  i.e.:
             fib(6)
      fib(5)        fib(4)
  fib(4) fib(3) fib(3) fib(2)
  ```
  - Height of K.
    - Example above has a height of 6.
  - Each level double the number of nodes.
  - Runtime = O(2<sup>K</sup>)
    - Slightly less for more complex mathematical reasons.

  - Problem: fib(3) and fib(4) are being called twice.
    - How to solve repeated problems using memoisation?

  ```
  2.

  int fib(int n, int[] memo) {
    if (n == 0 || n == 1) {
      return 1;
    } else if (memo[n] == 0) {
      memo[n] = fib(n - 1) + fib(n - 2);
    }
    return memo[n];
  }

  i.e.:
         fib(6)
      fib(5)  x
    fib(4)      x
  fib(3)          x
  ```
  - Height of K.
  - Each level has only one node.
  - Runtime = O(K)

___

### Solving Algorithms

#### What Is Not Expected

_These are nice to aim for but not crucial._

- To know the answers.
- To solve immediately.
- To code perfectly.

#### What Is Expected

_Show the interviewer how you think._

- Be excited about hard problems.
- Drive.
  - Keep trying when stuck.
  - More than just "correct," but a great solution.
- Pay attention to the interviewer.
  - Are their questions hinting towards an issue to be fixed?
- Write real code.
  - No pseudocode.
  - Write according to the rules of the language you've chosen.

#### [How To Approach](https://www.slideshare.net/gayle2/cracking-the-interview-skills-coding-soft-skills-product-management-handouts)

##### 1. Listen

- Pay attention to any information in the problem description.

##### 2. Draw An Example

- Most examples are too small or special cases.
- Debug your example.
- Is it a special case?
- It is big enough?

###### Example: Intersection of Two Sorted Arrays

- Most people will draw;
  ```
  [1, 12, 15, 19]
  [2, 12, 13, 20]
  ```
  - Too small an example of the arrays.
  - Too special-case-y.
    - Same size, one common element, same index.

- Better example to use;
  ```
  [1, 12, 15, 19, 20, 21]
  [2, 15, 17, 19, 21, 25, 27]
  ```
  - Big.
  - No special cases.

##### 3. Brute Force

1. Brute force solution ASAP.
    - If it doesn't work, you've saved time later on spent on your "optimised" algorithm.
2. Don't get an efficient algorithm yet.
3. State a naive algorithm and it's runtime.
4. Optimise.

##### 4. Optimise

- Walk through the brute force with BUD optimisation.
  - Bottlenecks, Unnecessary work, Duplicated work.
- Look back at any information you might have missed.
- Solve it manually, with an exmaple.
  - Reverse engineer your process, to see how you solved it. 
- Solve it "incorrectly."
  - Do you know why it fail?
  - Can this be fixed?
- Make a time vs space tradeoff.
  - Could you use a hash table?

##### BUD Examples: Continuing the intersection

```
[1, 12, 15, 19, 20, 21]
[2, 15, 17, 19, 21, 25, 27]
```
1. What are the bottlenecks?
    - Runtime = O(A * B)?
    - Bottleneck = Searcing.

##### BUD Examples: a<sup>3</sup> + b<sup>3</sup> = c<sup>3</sup> + d<sup>3</sup>

```
1 <= a, b, c, d <= 1000

n = 1000

for a from 1 to n
  for b from 1 to n
    for c from 1 to n
      for d from 1 to n
        if a³ + b³ == c³ + d³
          print a, b, c, d
```

2. What's unnecessary?
   - Looking for d.
    - Runtime = O(N<sup>4</sup>).
    - If you know the other three you can get to d.
    ```
    n = 1000

    for a from 1 to n
      for b from 1 to n
        for c from 1 to n
          d = pow(a³ + b³ - c³, 1/3) // round to int
          if a³ + b³ == c³ + d³ // validate that the value works
            print a, b, c, d
    ```
3. What's duplicated?
    - c, d pairs.
    ```
    n = 1000

    for a, b from 1, 1 to n, n
      for c, d from 1, 1 to n, n
        if a³ + b³ == c³ + d³ // validate that the value works
          print a, b, c, d
    ```
    | c<sup>3</sup> + d<sup>3</sup> | (c, d)            |
    | ----------------------------- | ----------------- |
    | ...                           | ...               |
    | 29855                         | (4, 31)           |
    | 32832                         | (4, 32), (18, 30) |
    | 36001                         | (4, 33)           |
    | ...                           | ...               |
    | 205504                        | (5, 59)           |
    | 216125                        | (5, 60), (45, 50) |
    | 227106                        | (5, 61)           |
    | ...                           | ...               |

- Generate all the c, d pairs upfront.
    - Putting them into a hash table that maps to an a, b list.
    ```
    n = 1000

    for c from 1 to n
      for d from 1 to n
        result = c³ + d³
        append (c, d) to list at value map[result]

    for a from 1 to n
      for b from 1 to n
        list = map.get(result)
        for each pair in list
          print a, b, pair
    ```
    - Runtime = O(N<sup>2</sup>)
      - Once all the c, d pairs are generated, use the hash table directly with a, b.
      ```
      n = 1000

      for c from 1 to n
        for d from 1 to n
          result = c³ + d³
          append (c, d) to list at value map[result]

      for each result, list in map
        for each pair1 in list
          for each pair2 in list
            print pair1, pair2
      ```

##### BUD Examples: Space / Time Tradeoffs => Precomputing

Question: Find rectangle at origin (from top left) with biggest sum.

|    |    |    |    |
| -- | -- | -- | -- |
| 6  | 5  | -9 | 2  |
| -2 | -5 | -2 | 7  |
| 3  | -2 | 10 | 13 |
| -8 | -3 | 1  | -2 |

- Overlap two rectangles and negate where the matrix columns and rows are repeated.

| A  |    |    |
| -- | -- | -- |
| 6  | 5  | -9 |
| -2 | -5 | -2 |

| B  |    |
| -- | -- |
| 6  | 5  |
| -2 | -5 |
| 3  | -2 |

| C  |    |
| -- | -- |
| 6  | 5  |
| -2 | -5 |

`= A + B - C + 10`

- Repeat to get O(N<sup>2</sup>)

| A  |    |    |    |
| -- | -- | -- | -- |
| 6  | 5  | -9 | 2  |
| -2 | -5 | -2 | 7  |

| B  |    |    |
| -- | -- | -- |
| 6  | 5  | -9 |
| -2 | -5 | -2 |
| 3  | -2 | 10 |

| C  |    |    |
| -- | -- | -- |
| 6  | 5  | -9 |
| -2 | -5 | -2 |

`= A + B - C + 13`

##### DIY Examples: Find permutations of s (small string) within b (big string)

3. Duplicates of the letters in the string, s.
    - s = abbc
    - b = babcabbacaabcbabcacbb
      - Walk through b to find each permutation.

**_Actually do DIY this one. Aim for O(S * B)._**

##### 5. Walk Through

- Before coding.
- Go through the approach in detail.
- Do you understand each part?

##### 6. Implement

- Write beautiful code.
  - Write in a straight line.
  - From the top left corner.
  - Use arrows `->` if needed.
- Write TODOs and Error cases as you go.
- Give proper varialbe names.
  - See if the interviewer is okay with future recalls of a variable to be shortened.
    - `number_of_people => num_p`
- Modularise from the beginning.
  - Top-down layout. Not bottom-up.
  - Example: Not modularised.
  ```
  public static boolean canBuildRansomNote1(String magazine, String note) {
    // Count ransom note
    int[] noteCount = new int[26];
    for (int i = 0; i < note.length(); i++) {
      int c = (int) note.charAt(i);
      if (c >= (int) 'a' && c <= ((int) 'z')) {
        c -= (int) 'a';
      } else if (c >= (int) 'A' && c <= ((int) 'Z')) {
        c -= (int) 'A';
      }
      if (0 <= c && c < 26) {
        noteCount[c]++;
      }
    }

    // Count magazine
    int[] magazineCount = new int[26];
    for (int i = 0; i < magazine.length(); i++) {
      int c = (int) magazine.charAt(i);
      if (c >= (int) 'a' && c <= ((int) 'z')) {
        c -= (int) 'a';
      } else if (c >= (int) 'A' && c <= ((int) 'Z')) {
        c -= (int) 'A';
      }
      if (0 <= c && c < 26) {
        magazineCount[c]++;
      }
    }

    // Compare
    for (int i = 0; i < magazineCount.length; i++) {
      if (noteCount[i] > magazineCount[i]) {
        return false;
      }
    }
    return true;
  }
  ```

  - Example: Modularised.
  ```
  public static boolean canBuildRansomNote1(String magazine, String note) {
    int[] noteCount = buildCharFrequencyTable(note); // Count ransom note
    int[] magazineCount = buildCharFrequencyTable(magazine); // Count magazine
    return isIncluded(magaineCount, noteCount); // Compare
  }

  public static int[] buildCharFrequencyTable(String sequence) {
    int[] counter = new int[26];
    for (int i = 0; i < sequence.length(); i++) {
      int c = convertCharToNumber(sequence.charAt(i));
      if (c > 0) {
        counter[c]++;
      }
    }
    return counter;
  }

  public static boolean isIncluded(int[] magaineCount, int[] noteCount) {
    for (int i = 0; i < magaineCount.length; i++) {
      if (noteCount[i] > magaineCount[i]) {
        return false;
      }
    }
    return true;
  }

  public static int convertCharToNumber(char ch) {
    int c = (int) ch;
    if (c >= (int) 'a' && c <= ((int) 'z')) {
      return c - (int) 'a';
    } else if (c >= (int) 'A' && c <= ((int) 'Z')) {
      return c - (int) 'A';
    }
    return -1;
  }
  ```


- Refactor to clean up what's left over.

##### 7. Test (the code not the algorithm)

1. Conceptual test. Walk through your code.
    - What's it doing? Why?
2. Unusual or none standard code?
3. Hot spots.
    - Arithmetic and null nodes.
4. Small test cases.
    - Faster and just as effective as a big test case.
5. Special and edge cases.

Found a bug? Fix it carefully.

##### 5 Approaches

- BUD.
  - Bottlenecks.
  - Unnecessary code.
  - Duplicated work.
- DIY.
  - Do it yourself.
- Simplify and Generalise.
  - Solve a simpler version.
- Base case and Build.
  - Solve for the base cases, then build from there.
- Data structure brainstorm.
  - Try various data structures.

___
