# The Non-Negotiable DSA Master List for CSE Placements (< 10 LPA)

**Target Companies:** TCS (Ninja/Digital/Prime), Infosys (SE/DSE/SP), Cognizant (GenC/GenC Next), Accenture, Capgemini, Deloitte, Wipro, LTIMindtree, ZS Associates, KPIT, Amadeus, Hexaware, and mid-tier product startups (3.5 LPA – 10 LPA).

**The Zero-Fluff Rule:** This list deliberately excludes obscure algorithms (Segment Trees, Fenwick Trees, Heavy-Light Decomposition, Digit DP, KMP, Red-Black Trees) that have a $<1\%$ probability in sub-10 LPA interviews. Every single question among these **72 problems** is a non-negotiable staple that repeatedly appears either directly or wrapped inside a story in campus Online Assessments (OAs) and live technical rounds.

# PART 1: Priority Tier List (Ranked by Interview Frequency)

## 🔥 Tier S: The Absolute Non-Negotiables (18 Questions)

* **Likelihood:** Covers **50%+ of all live technical coding rounds** and **Q1 of almost every Online Assessment**.
* **Rule:** Walking into ANY placement interview without knowing the optimal $O(n)$ or $O(n \log n)$ code for these 18 questions is an immediate risk.

 1. **[S1] Two Sum** — HashMap $O(n)$ lookup & sorted Two-Pointer $O(n \log n)$ approach.
 2. **[S2] Maximum Subarray Sum (Kadane’s Algorithm)** — Handling all-negative arrays cleanly.
 3. **[S3] Best Time to Buy and Sell Stock (I)** — Single-pass tracking of running minimum and max profit.
 4. **[S4] Move Zeroes to End** — In-place two-pointer swap preserving relative order of non-zero elements.
 5. **[S5] Sort an Array of 0s, 1s, and 2s** — Dutch National Flag 3-pointer (`low`, `mid`, `high`) algorithm in a single pass.
 6. **[S6] Rotate Array by $K$ Positions** — In-place $O(1)$ space using the 3-step array reversal trick.
 7. **[S7] Find Second Largest & Second Smallest Element in a Single Pass** — Live interview favorite without sorting.
 8. **[S8] Valid Anagram & Character Frequency Count** — Using a fixed 26-size integer array instead of heavy maps.
 9. **[S9] Valid Palindrome & Reverse Words in a String** — Two-pointer check + trimming extra/multiple spaces between words.
10. **[S10] First Non-Repeating Character in a String** — Frequency array pass in $O(n)$ time.
11. **[S11] Longest Substring Without Repeating Characters** — Variable-size Sliding Window + HashSet/Map.
12. **[S12] Subarray Sum Equals $K$ (Count & Longest Length)** — Prefix Sum + HashMap (works for both positive and negative numbers).
13. **[S13] Standard Binary Search + First & Last Occurrence of an Element** — Writing overflow-safe `mid = low + (high - low) / 2`.
14. **[S14] Reverse a Linked List** — Both Iterative (3-pointer: `prev`, `curr`, `next`) and Recursive approaches.
15. **[S15] Detect Cycle in a Linked List & Find Middle Node** — Floyd’s Slow and Fast (Tortoise-Hare) pointer pattern.
16. **[S16] Valid Parentheses** — Stack matching for `()`, `{}`, `[]`.
17. **[S17] Prime Number Check in $O(\sqrt{n})$ & Sieve of Eratosthenes** — Essential for TCS/Accenture/Cognizant OAs.
18. **[S18] GCD / HCF (Euclidean Algorithm) & Palindrome/Armstrong Number** — Modulo digit extraction without converting to String.

## ⚡ Tier A: The 6–10 LPA OA Differentiators (18 Questions)

* **Likelihood:** Covers **Q2 of Online Assessments** (TCS Digital, Cognizant GenC Next, Accenture Advanced, Deloitte, Capgemini Differentials) and medium-level live interviews.

19. **[A1] Majority Element ($> \lfloor n/2 \rfloor$ times)** — Boyer-Moore Voting Algorithm in $O(n)$ time and $O(1)$ space.
20. **[A2] Find the Missing and Repeating Number in $[1..N]$** — Using mathematical sum/square equations or XOR bit manipulation.
21. **[A3] Merge Overlapping Intervals** — Sorting by start time + linear interval merging.
22. **[A4] Leaders in an Array & Equilibrium Index (Pivot Index)** — Right-to-left scan and Prefix vs. Suffix sum equality.
23. **[A5] Product of Array Except Self** — Prefix and Suffix product passes without using the `/` division operator.
24. **[A6] Spiral Matrix Traversal & Rotate Matrix by 90 Degrees** — 4-boundary pointer traversal and Transpose + Row Reverse.
25. **[A7] Group Anagrams** — Sorting string characters or frequency string as a HashMap key.
26. **[A8] Longest Common Prefix & Isomorphic Strings** — Sorting comparison and two-way character mapping.
27. **[A9] String Compression (Run-Length Encoding)** — In-place conversion like `aaabbc` $\rightarrow$ `a3b2c1`.
28. **[A10] 3Sum** — Sorting + fixing one pointer + Two-Pointer scan while skipping duplicates.
29. **[A11] Search in Rotated Sorted Array** — Identifying the sorted half in $O(\log n)$ time.
30. **[A12] Merge Two Sorted Linked Lists & Remove $N$-th Node From End** — Dummy node stitching and $N$-gap two pointers.
31. **[A13] Next Greater Element** — Monotonic Stack pattern (right-to-left scan).
32. **[A14] Implement Stack using Queues & Queue using Stacks** — Classic live interview data structure design question.
33. **[A15] Binary Tree Traversals (Inorder, Preorder, Postorder, Level Order BFS)** — Recursive + Queue-based BFS.
34. **[A16] Maximum Depth (Height) & Check if Binary Tree is Height-Balanced** — Postorder height calculation in $O(n)$.
35. **[A17] Merge Sort & Quick Sort Implementation** — Writing the `merge()` and `partition()` functions and explaining worst-case $O(n^2)$ vs $O(n \log n)$.
36. **[A18] Climbing Stairs & House Robber (Max Sum of Non-Adjacent Elements)** — The two foundational 1D Dynamic Programming templates.

## 🎯 Tier B: High-Paying Package Clinchers (7–10 LPA Roles) (18 Questions)

* **Likelihood:** Frequently asked in **TCS Prime (9 LPA), Infosys DSE/SP (6.5–9.5 LPA), ZS Associates, Deloitte, and product startups** to filter top 10% candidates.

37. **[B1] Next Permutation** — Finding the breakpoint, swapping with next greater, and reversing the suffix.
38. **[B2] Set Matrix Zeroes** — Using the first row and first column as markers for $O(1)$ space.
39. **[B3] Longest Palindromic Substring** — Expand-around-center technique (handling both odd and even length palindromes).
40. **[B4] Container With Most Water** — Greedy two-pointer shrinking from both ends.
41. **[B5] Trapping Rain Water** — Prefix/Suffix max arrays or Two-Pointer $O(1)$ space optimization.
42. **[B6] Longest Consecutive Sequence** — HashSet lookup starting only at sequence beginnings (`!set.contains(num - 1)`).
43. **[B7] Maximum Sum / Distinct Elements in Subarray of Size $K$** — Fixed-size Sliding Window template.
44. **[B8] Find Minimum & Peak Element in Rotated/Unsorted Array** — Modified Binary Search on slopes.
45. **[B9] Koko Eating Bananas (or Aggressive Cows)** — The standard template for **Binary Search on Answer Space**.
46. **[B10] Check if Linked List is Palindrome & Intersection of Two Linked Lists** — Reversing second half & pointer switching.
47. **[B11] Min Stack** — Supporting `push()`, `pop()`, and `getMin()` in $O(1)$ time.
48. **[B12] Left View, Right View & Symmetric (Mirror) Binary Tree** — Level-order tracking and recursive mirror check.
49. **[B13] Diameter of a Binary Tree & Lowest Common Ancestor (LCA)** — Tracking global max path and bottom-up node discovery.
50. **[B14] Validate Binary Search Tree (BST) & $K$-th Smallest Element in BST** — Range validation `[min, max]` and Inorder property.
51. **[B15] $K$-th Largest Element in an Array & Top $K$ Frequent Elements** — Min-Heap (Priority Queue) of size $K$.
52. **[B16] Activity Selection (N Meetings in One Room) & Minimum Railway Platforms** — Greedy interval sorting vs. chronological arrival/departure sorting.
53. **[B17] Number of Islands (Connected Components)** — Standard 2D Grid BFS/DFS traversal.
54. **[B18] 0/1 Knapsack & Coin Change (Minimum Coins)** — The two essential 2D/target-sum DP problems for OAs.

## 🛡️ Tier C: The 100% Coverage Shield (8.5–10+ LPA & Tough OA Slots) (18 Questions)

* **Likelihood:** Appears as the hardest problem in **Infosys Specialist Programmer (SP), TCS Prime, and product company final technical rounds**.

55. **[C1] Count Inversions in an Array** — Modified Merge Sort counting pairs where `arr[i] > arr[j]` for `i < j`.
56. **[C2] Roman to Integer & String to Integer (`atoi`)** — Edge-case-heavy string parsing.
57. **[C3] Minimum Window Substring** — Hardest variable sliding window problem using two frequency maps.
58. **[C4] Single Element in a Sorted Array** — Binary search using even/odd index pairing parity.
59. **[C5] Add Two Numbers Represented as Linked Lists** — Carry propagation and dummy head management.
60. **[C6] LRU Cache Implementation** — Combining a **HashMap + Doubly Linked List** for $O(1)$ `get` and `put`.
61. **[C7] Rotting Oranges** — Multi-source BFS on a grid tracking minimum time/minutes.
62. **[C8] Detect Cycle in an Undirected & Directed Graph** — BFS/DFS parent tracking and recursion stack (`pathVisited`).
63. **[C9] Topological Sort (Kahn’s BFS Indegree Algorithm) / Course Schedule** — Dependency resolution in Directed Acyclic Graphs.
64. **[C10] Shortest Path in Weighted Graph (Dijkstra’s Algorithm)** — Priority Queue + adjacency list relaxation.
65. **[C11] Subsets (Power Set) & Permutations of an Array/String** — Standard Backtracking recursion tree.
66. **[C12] Combination Sum** — Pick / Not-Pick recursion with target reduction.
67. **[C13] Longest Common Subsequence (LCS) & Longest Increasing Subsequence (LIS)** — Classic DP on strings and subsequences.
68. **[C14] Partition Equal Subset Sum (Subset Sum Equals Target)** — Boolean 0/1 Knapsack variation.
69. **[C15] Unique Paths / Minimum Path Sum in a Grid** — 2D Matrix Dynamic Programming.
70. **[C16] Fractional Knapsack & Job Sequencing with Deadlines** — Value-to-weight ratio Greedy sorting.
71. **[C17] Count Unique-Digit Numbers in Range $[L, R]$** — Famous TCS Digital/NQT & Accenture OA math-hash problem.
72. **[C18] Single Number (XOR) & Count Set Bits (Brian Kernighan’s Algorithm)** — Using `x ^ x = 0` and `n = n & (n - 1)`.

---

# PART 2: All 72 Questions Organized Topic-Wise (For Systematic Practice)

Use this section as your daily study tracker. Each question includes its **Tier Tag (`[S]`, `[A]`, `[B]`, `[C]`)** so you can finish all `[S]` and `[A]` problems inside a topic first before moving to `[B]` and `[C]`.

### 1. Math, Number Theory & Bit Manipulation (5 Questions)

*Asked heavily in TCS NQT/Digital, Accenture, Cognizant, and Capgemini OAs.*

* [ ] **[S17]** Prime Number Check in $O(\sqrt{n})$ & Sieve of Eratosthenes
* [ ] **[S18]** GCD / HCF (Euclidean Algorithm) & Palindrome / Armstrong Number
* [ ] **[A2]** Find Missing and Repeating Number in $[1..N]$ (Math / XOR)
* [ ] **[C17]** Count Numbers with Non-Repeating (Unique) Digits in Range $[L, R]$
* [ ] **[C18]** Single Number (Element appearing once while others appear twice) & Count Set Bits

### 2. Arrays & 2D Matrices (14 Questions)

*Accounts for 30%+ of all coding questions under 10 LPA.*

* [ ] **[S1]** Two Sum
* [ ] **[S2]** Maximum Subarray Sum (Kadane’s Algorithm)
* [ ] **[S3]** Best Time to Buy and Sell Stock (I)
* [ ] **[S4]** Move Zeroes to End (In-place)
* [ ] **[S5]** Sort an Array of 0s, 1s, and 2s (Dutch National Flag Algorithm)
* [ ] **[S6]** Rotate Array by $K$ Positions (Reversal Algorithm)
* [ ] **[S7]** Find Second Largest & Second Smallest Element in a Single Pass
* [ ] **[A1]** Majority Element ($> \lfloor n/2 \rfloor$ times — Moore’s Voting Algorithm)
* [ ] **[A3]** Merge Overlapping Intervals
* [ ] **[A4]** Leaders in an Array & Equilibrium / Pivot Index
* [ ] **[A5]** Product of Array Except Self
* [ ] **[A6]** Spiral Matrix Traversal & Rotate Matrix by 90 Degrees
* [ ] **[B1]** Next Permutation
* [ ] **[B2]** Set Matrix Zeroes ($O(1)$ Space)

### 3. Strings (8 Questions)

*The #1 favorite topic for face-to-face live coding rounds.*

* [ ] **[S8]** Valid Anagram & Character Frequency Count
* [ ] **[S9]** Valid Palindrome & Reverse Words in a String
* [ ] **[S10]** First Non-Repeating Character in a String
* [ ] **[A7]** Group Anagrams
* [ ] **[A8]** Longest Common Prefix & Isomorphic Strings
* [ ] **[A9]** String Compression / Run-Length Encoding (`a3b2c1`)
* [ ] **[B3]** Longest Palindromic Substring (Expand Around Center)
* [ ] **[C2]** Roman to Integer & String to Integer (`atoi`)

### 4. Hashing, Two Pointers & Sliding Window (8 Questions)

*The key to turning $O(n^2)$ TLE solutions into $O(n)$ accepted solutions in OAs.*

* [ ] **[S11]** Longest Substring Without Repeating Characters
* [ ] **[S12]** Subarray Sum Equals $K$ (Count of Subarrays & Longest Subarray with Sum $K$)
* [ ] **[A10]** 3Sum
* [ ] **[B4]** Container With Most Water
* [ ] **[B5]** Trapping Rain Water
* [ ] **[B6]** Longest Consecutive Sequence
* [ ] **[B7]** Maximum Sum / Distinct Elements of Subarray of Size $K$ (Fixed Sliding Window)
* [ ] **[C3]** Minimum Window Substring

### 5. Searching & Sorting (7 Questions)

* [ ] **[S13]** Binary Search + First and Last Position of Element in Sorted Array
* [ ] **[A11]** Search in Rotated Sorted Array
* [ ] **[A17]** Merge Sort & Quick Sort Implementation
* [ ] **[B8]** Find Minimum & Peak Element in Rotated/Unsorted Array
* [ ] **[B9]** Koko Eating Bananas / Aggressive Cows (Binary Search on Answer)
* [ ] **[C1]** Count Inversions in an Array (Merge Sort application)
* [ ] **[C4]** Single Element in a Sorted Array

### 6. Linked Lists (5 Questions)

*Tested in live interviews to evaluate pointer manipulation and `NULL` edge-case handling.*

* [ ] **[S14]** Reverse a Linked List (Iterative & Recursive)
* [ ] **[S15]** Detect Cycle in a Linked List & Find Middle of Linked List (Slow/Fast Pointers)
* [ ] **[A12]** Merge Two Sorted Linked Lists & Remove $N$-th Node From End
* [ ] **[B10]** Check if Linked List is Palindrome & Intersection of Two Linked Lists
* [ ] **[C5]** Add Two Numbers Represented as Linked Lists

### 7. Stacks, Queues & Heaps (6 Questions)

* [ ] **[S16]** Valid Parentheses
* [ ] **[A13]** Next Greater Element (Monotonic Stack)
* [ ] **[A14]** Implement Stack using Queues & Queue using Stacks
* [ ] **[B11]** Min Stack ($O(1)$ time complexity)
* [ ] **[B15]** $K$-th Largest Element in an Array & Top $K$ Frequent Elements (Min-Heap)
* [ ] **[C6]** LRU Cache Implementation (HashMap + Doubly Linked List)

### 8. Recursion, Backtracking & Binary Trees / BST (7 Questions)

* [ ] **[A15]** Binary Tree Traversals (Inorder, Preorder, Postorder, Level Order BFS)
* [ ] **[A16]** Maximum Depth (Height) & Check if Binary Tree is Height-Balanced
* [ ] **[B12]** Left View, Right View & Symmetric (Mirror) Binary Tree
* [ ] **[B13]** Diameter of a Binary Tree & Lowest Common Ancestor (LCA)
* [ ] **[B14]** Validate BST & $K$-th Smallest Element in a BST
* [ ] **[C11]** Subsets (Power Set) & Permutations of an Array/String
* [ ] **[C12]** Combination Sum

### 9. Greedy & Graphs (7 Questions)

* [ ] **[B16]** Activity Selection (N Meetings in One Room) & Minimum Railway Platforms
* [ ] **[B17]** Number of Islands (Connected Components on a Grid)
* [ ] **[C7]** Rotting Oranges (Multi-Source BFS)
* [ ] **[C8]** Detect Cycle in an Undirected & Directed Graph
* [ ] **[C9]** Topological Sort (Kahn’s Algorithm / Course Schedule)
* [ ] **[C10]** Dijkstra’s Shortest Path Algorithm
* [ ] **[C16]** Fractional Knapsack & Job Sequencing with Deadlines

### 10. Dynamic Programming (5 Core Patterns)

*Sub-10 LPA OAs stick strictly to these 5 classical DP patterns.*

* [ ] **[A18]** Climbing Stairs & House Robber (1D Linear DP)
* [ ] **[B18]** 0/1 Knapsack & Coin Change (Minimum Coins / Unbounded Knapsack)
* [ ] **[C13]** Longest Common Subsequence (LCS) & Longest Increasing Subsequence (LIS)
* [ ] **[C14]** Partition Equal Subset Sum (Subset Sum Equals Target)
* [ ] **[C15]** Unique Paths / Minimum Path Sum in a Grid

---

# PART 3: Most Important Questions for the Live Face-to-Face Interview Round

In a live technical interview (25–40 minutes), the interviewer will **not** give you a long 3-page competitive programming problem. Instead, they want to watch you **write clean code on paper or Notepad in 5–8 minutes, dry-run a test case out loud, and answer follow-up questions on time/space complexity, SQL, and OOPs**.

### A. The Top 20 "Write This on Paper/Notepad Right Now" DSA Questions

*In 85%+ of face-to-face interviews under 10 LPA, the live coding task is pulled directly from these 20 problems because they are quick to write and easy for the panel to verify.*

| Rank | Live Coding Task | Interview Likelihood | What the Interviewer Specifically Checks When You Write It |
| :--- | :--- | :--- | :--- |
| **1** | **Find the 2nd Largest Element in an Array** | **~85%** | Do you sort the array in $O(n \log n)$ (bad), or do you use a single-pass `largest` and `secondLargest` check in $O(n)$ while handling duplicates like `[10, 10, 9]`? |
| **2** | **Reverse a String / Check Palindrome / Reverse Words in a Sentence** | **~82%** | Do you use built-in `.reverse()`, or can you write the two-pointer `left < right` character swap from scratch? |
| **3** | **Print Frequency of Characters / First Non-Repeating Character** | **~78%** | Can you use a `HashMap` or a `26`-size integer array (`ch - 'a'`) and iterate cleanly in $O(n)$? |
| **4** | **Check if Two Strings are Anagrams** | **~75%** | Moving from $O(n \log n)$ sorting to $O(n)$ frequency array increment/decrement. |
| **5** | **Two Sum (Find Pair with Given Target Sum)** | **~74%** | Explaining the $O(n^2)$ nested loop first, then optimizing to $O(n)$ using a `HashMap` or $O(n \log n)$ with Two Pointers. |
| **6** | **Remove Duplicates from a Sorted / Unsorted Array** | **~70%** | Using a `HashSet` when unsorted vs. using an in-place slow/fast two-pointer overwrite in $O(1)$ space when sorted. |
| **7** | **Move All Zeroes to the End of the Array** | **~68%** | Doing it in a single pass in $O(1)$ extra space without messing up the relative order of non-zero numbers. |
| **8** | **Reverse a Singly Linked List** | **~65%** | Drawing the 3 pointers (`prev`, `curr`, `next`) on paper and not losing the head reference. |
| **9** | **Write Binary Search** | **~64%** | Writing `mid = low + (high - low) / 2` and explaining why `(low + high) / 2` causes integer overflow for large arrays. |
| **10** | **Valid Parentheses (`{[()]}`)** | **~60%** | Handling edge cases like a string starting with a closing bracket `"]"` or leaving unclosed brackets `"((("` on the stack at the end. |
| **11** | **Detect a Loop in a Linked List / Find the Middle Node** | **~58%** | Explaining why Floyd's Tortoise and Hare (`slow = slow.next`, `fast = fast.next.next`) guarantees meeting inside a cycle. |
| **12** | **Maximum Subarray Sum (Kadane's Algorithm)** | **~55%** | Tracing `currSum` and `maxSum` on an array containing negative numbers like `[-2, 1, -3, 4, -1, 2, 1, -5, 4]`. |
| **13** | **Swap Two Numbers Without Using a 3rd Temporary Variable** | **~54%** | Classic warm-up: using `a = a + b; b = a - b; a = a - b;` or bitwise XOR `a ^= b; b ^= a; a ^= b;`. |
| **14** | **Fibonacci Series (Iterative vs. Recursive) & Factorial** | **~52%** | Explaining why recursive `fib(n)` takes $O(2^n)$ exponential time and how storing previous two states reduces it to $O(n)$ time and $O(1)$ space. |
| **15** | **Check Prime Number / Print Primes up to $N$** | **~50%** | Explaining why the loop only needs to run up to `i * i <= n` ($\sqrt{n}$) instead of `n / 2`. |
| **16** | **Sort an Array of 0s, 1s, and 2s** | **~48%** | Interviewer will first let you count 0s, 1s, and 2s (2 passes), then ask: *"Can you do this in a single traversal?"* (Dutch National Flag). |
| **17** | **Find Missing Number in an Array of $1$ to $N$** | **~46%** | Using $\frac{N(N+1)}{2} - \text{sum}$ and discussing how XOR prevents integer overflow when $N$ is large. |
| **18** | **String Compression (`aaabbc` $\rightarrow$ `a3b2c1`)** | **~42%** | Clean boundary handling for the last character group without throwing an `IndexOutOfBoundsException`. |
| **19** | **Merge Two Sorted Arrays / Merge Sort `merge()` Function** | **~40%** | Two-pointer comparison (`i` and `j`) plus copying leftover elements when one array finishes early. |
| **20** | **Next Greater Element / Stock Buy & Sell** | **~38%** | Explaining how a Monotonic Stack eliminates the inner loop to achieve $O(n)$ amortized complexity. |

---

### B. The 10 Live Conceptual DSA Cross-Questions (Asked Orally Without Coding)

*After you finish writing your code, the interviewer will ask 2–3 oral DSA theory questions to test your fundamentals:*

1. **"How does a `HashMap` work internally? What happens when two keys generate the same hash code (Collision)?"** *(~75% likelihood — Explain hashing, bucket array, `.equals()` vs `.hashCode()`, chaining with Linked Lists, and how Java 8 converts chains of length $>8$ into Balanced Red-Black Trees).*
2. **"When should you use an `ArrayList` (Dynamic Array) vs. a `LinkedList`?"** *(~72% likelihood — ArrayList gives $O(1)$ random access and cache locality; LinkedList gives $O(1)$ insertion/deletion when pointers are known, but $O(n)$ search).*
3. **"Why is Quick Sort preferred over Merge Sort for arrays in practice, even though Quick Sort's worst-case is $O(n^2)$?"** *(~60% likelihood — Quick Sort is in-place requiring $O(\log n)$ stack space and has superior CPU cache locality, whereas Merge Sort requires $O(n)$ auxiliary memory).*
4. **"Why is Merge Sort preferred over Quick Sort for Linked Lists?"** *(~45% likelihood — Linked nodes are scattered in memory so random pivot access is slow, and Merge Sort can merge two linked lists in $O(1)$ extra space by just changing pointers).*
5. **"What is the difference between a Binary Tree, a Binary Search Tree (BST), and a Heap?"** *(~55% likelihood — BST orders left $<$ root $<$ right for $O(\log n)$ search; Heap is a complete binary tree ordered vertically for $O(1)$ min/max retrieval).*
6. **"What is the worst-case time complexity of searching in a BST, and how do we fix it?"** *(~48% likelihood — $O(n)$ when the tree becomes skewed like a linked list; fixed using self-balancing trees like AVL or Red-Black Trees).*
7. **"What is a Stable Sorting Algorithm? Which sorting algorithms are stable?"** *(~42% likelihood — Preserves relative order of duplicate elements. Stable: Bubble, Insertion, Merge. Unstable: Quick, Heap, Selection).*
8. **"BFS vs. DFS — which data structure does each use, and when do you pick one over the other?"** *(~50% likelihood — BFS uses a Queue and finds the shortest path in unweighted graphs; DFS uses a Stack/Recursion and uses less memory on deep trees/backtracking).*
9. **"What causes a `StackOverflowError` in recursion, and how do you prevent it?"** *(~45% likelihood — Missing or unreachable base case filling up the call stack memory).*
10. **"What is the difference between Dynamic Programming (DP) and Greedy Algorithms?"** *(~35% likelihood — Greedy makes a locally optimal choice without reconsidering past choices; DP explores overlapping subproblems to guarantee the global optimum).*

---

### C. The 6 Non-Negotiable Live SQL Queries & OOP Snippets (Asked Alongside DSA)

*In sub-10 LPA interviews, "Live Coding" is split 60% DSA and 40% SQL/OOPs. Never walk into the room without being able to write these 6 blocks on paper:*

1. **SQL #1 — Find the $2\text{nd}$ or $N\text{th}$ Highest Salary (Handling Duplicates):**
   ```sql
   SELECT salary FROM (
       SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) AS rnk
       FROM Employee
   ) t WHERE rnk = 2;
   ```
2. **SQL #2 — Department-Wise Highest Salary (`JOIN` + `GROUP BY`):**
   ```sql
   SELECT d.dept_name, MAX(e.salary) AS max_salary
   FROM Employee e
   JOIN Department d ON e.dept_id = d.dept_id
   GROUP BY d.dept_name;
   ```
3. **SQL #3 — Find Duplicate Emails/Records in a Table:**
   ```sql
   SELECT email, COUNT(*) 
   FROM Users 
   GROUP BY email 
   HAVING COUNT(*) > 1;
   ```
4. **SQL #4 — Self-Join (Find Employees Who Earn More Than Their Managers):**
   ```sql
   SELECT e.emp_name AS Employee
   FROM Employee e
   JOIN Employee m ON e.manager_id = m.emp_id
   WHERE e.salary > m.salary;
   ```
5. **OOP Snippet #1 — Write a Code Example Showing Runtime Polymorphism (Method Overriding):**
   * Be ready to write a 10-line `Parent` and `Child` class where `Parent obj = new Child(); obj.process();` invokes the child's overridden method at runtime.
6. **OOP Snippet #2 — Write a Singleton Class (Only One Instance Allowed):**
   * Frequently asked in 6.5–10 LPA interviews when you mention `private` constructors: create a `private static` instance, a `private` constructor, and a `public static getInstance()` method.