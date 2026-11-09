# Accenture Complete DSA & Interview Master Sheet (AAEA ~₹11.89 LPA Focus)

## 1. How Accenture Hiring Works at LPU & Tier-1/2 Campuses
Accenture hires across three primary compensation tiers during campus placements. Often, a single unified assessment (or a dedicated **AEH - Advanced Engineering Hiring** drive) determines which role you land based on your coding and technical scores:

1. **ASE / PADA (Packaged App Development Associate):** ~₹4.50 LPA (Solve 1 coding question partially/fully + clear cutoff).
2. **AASE / FSE (Advanced Associate Software Engineer):** ~₹6.50 LPA (Solve both coding questions with clean execution + strong MCQ score).
3. **AAEA / AEH (Advanced Application Engineering Analyst):** ~₹11.89 LPA (Top percentile in Cognitive + Technical MCQs, 100% test cases passed in the Coding Round within rapid time, plus a deeper Technical + Project Interview).

### Latest Assessment Architecture (2024–2026 Pattern)
* **Round 1A: Behavioral, Cognitive & Technical Assessment (90 Mins / 90 MCQs or Gamified + MCQs)**
  * **Sections:** English Verbal (17 Qs), Critical Reasoning (18 Qs), Abstract Reasoning (15 Qs), MS Office & Common Apps (12 Qs), **Pseudocode** (18 Qs - heavily weighted!), **Networking, Security & Cloud** (10 Qs). *(Note: Some recent drives also include 3 short gamified cognitive memory/attention mini-games).*
* **Round 1B: Coding Assessment (45–60 Mins | 2 to 3 Questions)**
  * **Standard Pattern:** 2 DSA questions (1 Easy/Verbatim Accenture Archive + 1 Medium/Hard-Medium Array/String/DP/Tree problem).
  * **New Full-Stack Variant (Reported in late 2025/2026 drives):** 1 DSA Problem + 1 SQL (3-Table `JOIN` query) + 1 Basic HTML/CSS UI manipulation task.
* **Round 2: AI Communication Assessment (30 Mins | Pearson Versant Style)**
  * Reading aloud, repeating audio sentences, unscrambling jumbled sentences, 30-second story retelling, and 60-second extempore speaking.
* **Round 3: Combined Technical + Managerial/HR Interview (30–45 Mins)**

---

## 2. How This Sheet Is Tiered
* **Tier S (The Verbatim OA Archive — 35 Problems):** Exact function-signature problems pulled from Mercer Mettl, HirePro, PrepInsta, and GFG Accenture Archives. Accenture repeats these *word-for-word*. Mastering Tier S guarantees you clear the base coding cutoff in under 10 minutes.
* **Tier A (High-Frequency LeetCode & GFG Standard — 45 Problems):** The core LeetCode Premium tagged questions for Accenture and the 2nd coding question in on-campus drives. Mastering Tier A pushes you from the ₹4.5 LPA bracket into the ₹6.5–₹11.89 LPA bracket.
* **Tier B (AAEA ₹11.89 LPA Differentiators — 28 Problems):** Harder Medium/Hard problems (Trees, Grid Backtracking, Bitwise manipulation, Monotonic Stack, DP) explicitly reported by candidates who cleared the **Advanced Application Engineering Analyst (AAEA)** assessment.
* **Tier C (SQL, Pseudocode Traps & Secondary LeetCode Tags — 22 Items):** Mandatory SQL queries, bitwise pseudocode patterns, and lower-frequency LeetCode tags.

---

# TIER S: The "Verbatim Repeat" Accenture OA Archive (Must Memorize)
*These problems use specific C/C++/Java/Python function signatures on Accenture's compiler. You must know them cold.*

### S1. Rat Count House
* **Signature:** `int calculate(int r, int unit, int arr[], int n)`
* **Problem:** Given `r` rats, each consuming `unit` amount of food, and an array `arr` of size `n` representing food in each house. Find the minimum number of houses (starting from index $0$) required to feed all rats. Return $-1$ if `arr` is null, and $0$ if total food is insufficient.
* **Pattern:** Prefix Sum / Linear Scan ($O(N)$ time, $O(1)$ space).

### S2. Operations Binary String
* **Signature:** `int OperationsBinaryString(char* str)`
* **Problem:** Given a string where odd indices hold operations: `'A'` = Bitwise AND, `'B'` = Bitwise OR, `'C'` = Bitwise XOR, and even indices hold `'0'` or `'1'`. Evaluate sequentially from left to right (ignore operator precedence). Return $-1$ if null.
  * *Example:* `"1C0C1C1A0B1"` $\rightarrow 1 \oplus 0 \oplus 1 \oplus 1 \land 0 \lor 1 = 1$.
* **Pattern:** String Traversal & Bitwise Simulation ($O(N)$ time).

### S3. Password Checker
* **Signature:** `int CheckPassword(char str[], int n)`
* **Problem:** Return $1$ if valid, $0$ if invalid. Conditions: (1) Length $\ge 4$, (2) At least one digit, (3) At least one uppercase letter, (4) Must not contain space `' '` or slash `'/'`, (5) Starting character must not be a digit.
* **Pattern:** Character ASCII Validation ($O(N)$ time).

### S4. Find Count (Absolute Difference)
* **Signature:** `int findCount(int arr[], int length, int num, int diff)`
* **Problem:** Return the number of elements in `arr` having an absolute difference of $\le \text{diff}$ with `num` (i.e., $|arr[i] - num| \le diff$). Return $-1$ if count is $0$.
* **Pattern:** Linear Array Scan ($O(N)$ time).

### S5. Difference of Sum (Divisible vs. Not Divisible)
* **Signature:** `int differenceofSum(int n, int m)`
* **Problem:** Find the sum of all integers from $1$ to $n$ (inclusive) that are **not** divisible by $m$, and subtract the sum of integers from $1$ to $n$ that **are** divisible by $m$.
* **Pattern:** Math / Arithmetic Progression or $O(N)$ Loop.

### S6. Large Small Sum (Even/Odd Index Split)
* **Signature:** `int LargeSmallSum(int arr[], int n)`
* **Problem:** Return the sum of the **second largest** element from even indices ($0, 2, 4, \dots$) and the **second smallest** element from odd indices ($1, 3, 5, \dots$). Return $0$ if $n \le 3$.
* **Pattern:** Two-Pass Tracking or Split & Sort ($O(N)$ time).

### S7. Product Smallest Pair
* **Signature:** `int ProductSmallestPair(int sum, int arr[], int n)`
* **Problem:** Find the two smallest distinct-index elements $arr[j]$ and $arr[k]$ ($j \neq k$) such that $arr[j] + arr[k] \le \text{sum}$, and return their product $arr[j] \times arr[k]$. Return $-1$ if $n < 2$, or $0$ if no such pair exists.
* **Pattern:** Sorting / Min-Tracking ($O(N \log N)$ or $O(N)$ time).

### S8. Decimal to N-Base Notation (`DectoNBase`)
* **Signature:** `char* DectoNBase(int n, int num)`
* **Problem:** Convert decimal `num` to base `n` ($1 < n \le 36$), where remainders $0\text{–}9$ map to `'0'`–`'9'` and $10\text{–}35$ map to `'A'`–`'Z'`.
* **Pattern:** Modulo Division & String Reversal ($O(\log_n(\text{num}))$ time).

### S9. Move Hyphens to Front
* **Signature:** `char* MoveHyphen(char str[], int n)`
* **Problem:** Move all hyphens `'-'` in the string to the front while preserving the relative order of all other characters. Return `null` if string is null.
* **Pattern:** String Filtering / Two Pointers ($O(N)$ time).

### S10. Number of Carries
* **Signature:** `int NumberOfCarries(int num1, int num2)`
* **Problem:** Count the total number of carry operations generated when adding `num1` and `num2` digit-by-digit in base $10$.
* **Pattern:** Digit Extraction (`% 10`, `/ 10`) with Carry State ($O(\log_{10}(\max(A,B)))$ time).

### S11. Replace Character (Mutual Swap)
* **Signature:** `void ReplaceCharacter(char str[], int n, char ch1, char ch2)`
* **Problem:** Replace every occurrence of `ch1` with `ch2` AND every occurrence of `ch2` with `ch1` in `str`.
* **Pattern:** Single-Pass In-Place Character Swap ($O(N)$ time).

### S12. Max Exponents of 2
* **Signature:** `int MaxExponents(int a, int b)`
* **Problem:** Find and return the number in the range $[a, b]$ (inclusive) that has the maximum exponent of $2$ dividing it (i.e., highest power of $2$ factor).
* **Pattern:** Bitwise Trailing Zeroes (`n & -n` or `__builtin_ctz`).

### S13. Calculate Sum of Multiples of 3 and 5
* **Signature:** `int Calculate(int m, int n)`
* **Problem:** Return the sum of all numbers between $m$ and $n$ (inclusive) that are divisible by both $3$ and $5$ (i.e., divisible by $15$).
* **Pattern:** Loop or Arithmetic Progression Sum.

### S14. Matrix Even/Odd Split & Second Largest Sum
* **Problem:** Accept an array of size $N$, split into two sub-arrays: elements at even indices and elements at odd indices. Sort both in ascending order, print them, and print the sum of the second largest numbers from both arrays.
* **Pattern:** Array Partitioning & Sorting ($O(N \log N)$ time).

### S15. Autobiographical Number (`FindAutoCount`)
* **Signature:** `int FindAutoCount(String n)`
* **Problem:** An autobiographical number is a number $N$ where the $0$-th digit counts how many $0$s are in $N$, the $1$-st digit counts how many $1$s are in $N$, etc. (e.g., `"1210"`). If it is autobiographical, return the **count of distinct digits** in `n`; otherwise return $0$.
* **Pattern:** Frequency Array of size $10$ ($O(N)$ time).

### S16. Replace Most Frequent Character
* **Signature:** `char* ChatFrequentcharacter(char str[], char x)`
* **Problem:** Find the most frequent character in `str` and replace all its occurrences with `x`. If there is a tie in frequency, choose the character with the **lower ASCII value**.
* **Pattern:** Hash Map / Frequency Array of size $26$ ($O(N)$ time).

### S17. Max In Array and Its Index
* **Signature:** `void MaxInArray(int arr[], int length)`
* **Problem:** Print the maximum element in the array and its $0$-based index on separate lines.
* **Pattern:** Linear Scan ($O(N)$ time).

### S18. Distinct and Duplicate Integers
* **Signature:** `int DistinctDuplicateDiff(int arr[], int n)`
* **Problem:** Calculate `(Sum of all elements appearing exactly once) - (The duplicate number subtracted once)`.
* **Pattern:** HashMap Frequency Count ($O(N)$ time).

### S19. Add Alternate Nodes in Linked List
* **Signature:** `Node* addAlternateNodes(Node* head)`
* **Problem:** Given a singly linked list, modify it such that each node (starting from the 2nd or 3rd node depending on variant) is updated by adding the value of its alternate node ($2$ steps behind/ahead).
* **Pattern:** Linked List Pointer Manipulation ($O(N)$ time).

### S20. Evaluate Infix Expression String
* **Signature:** `int EvaluateExpression(char* expr)`
* **Problem:** Given a mathematical string expression with integers and `+`, `-`, `*`, `/`, evaluate it respecting operator precedence (`*`, `/` > `+`, `-`) using integer division.
* **Pattern:** Two Stacks (Values & Operators) / LeetCode 227 Basic Calculator II ($O(N)$ time).

### S21. Case Conversion by Majority Count
* **Problem:** Given a string $S$, if the count of uppercase letters is strictly greater than lowercase letters, convert the entire string to uppercase; otherwise, convert the entire string to lowercase.
* **Pattern:** Character Counting ($O(N)$ time).

### S22. Weird Number in Array
* **Problem:** Given an array and integer $K$, count/find "weird numbers"—numbers that are **not** divisible by $K$, but the **sum of their digits** is divisible by $K$.
* **Pattern:** Modulo & Digit Sum ($O(N \log_{10}(\text{maxVal}))$ time).

### S23. Leaders in an Array (Right-Side Dominant)
* **Problem:** Find all elements (or the largest/sum of elements) in an array that are strictly greater than all elements to their right. (Asked in late 2025/2026 Accenture drives).
* **Pattern:** Reverse Traversal tracking `max_from_right` ($O(N)$ time).

### S24. Remove Duplicates Preserving Last/First Relative Order
* **Problem:** Given an array (e.g., `[1, 2, 3, 4, 2, 2, 0, 2, 1]`), return an array where each element appears only once, keeping either the first or last occurrence's relative order (`[4, 3, 0, 2, 1]`).
* **Pattern:** HashSet + Reverse/Forward Traversal ($O(N)$ time).

### S25. Palindrome Numbers in Range
* **Problem:** Print all palindrome numbers between lower bound $L$ and upper bound $U$.
* **Pattern:** Number Reversal Loop.

### S26. Sum of Distance Between Three Points
* **Problem:** Given coordinates $(x_1, y_1), (x_2, y_2), (x_3, y_3)$, calculate the sum of Euclidean distances $\sqrt{(x_2-x_1)^2 + (y_2-y_1)^2} + \dots$
* **Pattern:** Coordinate Geometry (`Math.hypot` / `sqrt`).

### S27. Table Multiples & Sum
* **Problem:** Print the first $10$ multiples of $N$ and their total sum (which equals $55 \times N$).
* **Pattern:** Basic Math ($O(1)$ time).

### S28. Count Specific Digit Occurrences in Range
* **Problem:** Count how many times digit $D$ appears in all numbers from $L$ to $R$.
* **Pattern:** Digit Extraction.

### S29. Reverse Words in a String
* **Problem:** Given `"Welcome to Accenture"`, output `"Accenture to Welcome"`.
* **Pattern:** String Split / Two-Pointer Reversal ($O(N)$ time).

### S30. Find Equilibrium Index of Array
* **Problem:** Find index $i$ such that $arr[0] + \dots + arr[i-1] = arr[i+1] + \dots + arr[n-1]$. Return $-1$ if none exists.
* **Pattern:** Total Sum & Running Left Sum ($O(N)$ time, $O(1)$ space).

### S31. Bulb Switcher / Minimum Flips to Make All 1s
* **Problem:** Given an array of $0$s and $1$s representing bulbs, flipping a bulb flips all bulbs to its right. Find minimum flips to turn all bulbs ON.
* **Pattern:** Greedy State Flip Counter ($O(N)$ time).

### S32. Superior Elements Count
* **Problem:** Count how many elements in `arr` are strictly greater than all elements to their right.
* **Pattern:** Right-to-Left Scan ($O(N)$ time).

### S33. Cake Cut Maximum Pieces
* **Problem:** Given $N$ straight cuts on a circular cake, find the maximum number of pieces possible modulo $10^9 + 7$.
* **Pattern:** Lazy Caterer's Formula: $\frac{N(N+1)}{2} + 1$.

### S34.Minimum Steps to Climb Stairs with $M$ Leap
* **Problem:** Climb $N$ stairs taking either $M$ steps or $1$ step at a time. Return minimum steps: $\lfloor N / M \rfloor + (N \bmod M)$.
* **Pattern:** Greedy Division ($O(1)$ time).

### S35. Magical Numbers ($1$ to $N$ Binary Mapping)
* **Problem:** A number is magical if, when converted to binary, replacing $0$ with $1$ and $1$ with $2$ gives an odd sum of digits. Count magical numbers from $1$ to $N$.
* **Pattern:** Bit Manipulation ($O(N \log N)$ time).

---

# TIER A: High-Frequency LeetCode & GFG Standard Problems (AASE & AAEA Core)
*These 45 problems come directly from LeetCode Premium's Accenture company tags and GeeksforGeeks Accenture tracks. Clearing these quickly in Round 1B is required for AAEA shortlisting.*

### Arrays, Prefix Sum & Hashing
| # | Problem Name | LeetCode / GFG Ref | Core Pattern | Target Complexity |
| :--- | :--- | :--- | :--- | :--- |
| **A1** | **Two Sum** | LC #1 | HashMap (`target - nums[i]`) | $O(N)$ Time, $O(N)$ Space |
| **A2** | **Best Time to Buy and Sell Stock** | LC #121 | Running Minimum & Max Profit | $O(N)$ Time, $O(1)$ Space |
| **A3** | **Max Consecutive Ones** | LC #485 | Running Counter Reset on `0` | $O(N)$ Time, $O(1)$ Space |
| **A4** | **Maximum Subarray (Kadane's Algorithm)** | LC #53 | Dynamic Programming / Running Sum | $O(N)$ Time, $O(1)$ Space |
| **A5** | **Rotate Array (by $K$ steps)** | LC #189 | 3-Step Array Reversal | $O(N)$ Time, $O(1)$ Space |
| **A6** | **Rotate Image ($90^\circ$ Matrix Rotation)** | LC #48 | Transpose + Reverse Rows | $O(N^2)$ Time, $O(1)$ Space |
| **A7** | **Sort Array by Increasing Frequency** | LC #1636 | HashMap + Custom Comparator | $O(N \log N)$ Time |
| **A8** | **Intersection of Two Arrays (I & II)** | LC #349 / #350 | HashSet / Two Pointers | $O(N + M)$ Time |
| **A9** | **Contains Duplicate II (within distance $k$)** | LC #219 | Sliding Window HashSet | $O(N)$ Time, $O(K)$ Space |
| **A10** | **Contiguous Array (Equal $0$s and $1$s)** | LC #525 | Prefix Sum ($0 \rightarrow -1$) + HashMap | $O(N)$ Time, $O(N)$ Space |
| **A11** | **Subarray Sum Equals K** | LC #560 | Prefix Sum Frequency Map | $O(N)$ Time, $O(N)$ Space |
| **A12** | **Plus One** | LC #66 | Carry Propagation | $O(N)$ Time, $O(1)$ Space |
| **A13** | **Largest Number (Form Largest String)** | LC #179 | Custom String Sort (`a+b > b+a`) | $O(N \log N)$ Time |
| **A14** | **Merge Intervals** | LC #56 | Sort by Start Time + Greedy Merge | $O(N \log N)$ Time |
| **A15** | **Find Missing and Repeating Number** | GFG Standard | Math Equations or XOR Buckets | $O(N)$ Time, $O(1)$ Space |

### Strings & Manipulation
| # | Problem Name | LeetCode / GFG Ref | Core Pattern | Target Complexity |
| :--- | :--- | :--- | :--- | :--- |
| **A16** | **Valid Anagram** | LC #242 | Frequency Array of Size $26$ | $O(N)$ Time, $O(1)$ Space |
| **A17** | **First Unique Character in a String** | LC #387 | Two-Pass Frequency Array | $O(N)$ Time, $O(1)$ Space |
| **A18** | **Reverse String II (Every $2k$ chars)** | LC #541 | Stride Loop + Two Pointers | $O(N)$ Time, $O(1)$ Space |
| **A19** | **String to Integer (`atoi`)** | LC #8 | State Parsing & Overflow Clamping | $O(N)$ Time, $O(1)$ Space |
| **A20** | **Longest Palindromic Substring** | LC #5 | Expand Around Center | $O(N^2)$ Time, $O(1)$ Space |
| **A21** | **Longest Substring Without Repeating Chars** | LC #3 | Sliding Window + Last Seen Array | $O(N)$ Time, $O(1)$ Space |
| **A22** | **Group Anagrams** | LC #49 | Sorted String / Char Count Key Map | $O(N \cdot K \log K)$ Time |
| **A23** | **Longest Common Prefix** | LC #14 | Horizontal Scan / Sorting First & Last | $O(N \cdot M)$ Time |
| **A24** | **Isomorphic Strings** | LC #205 | Bidirectional Character Mapping | $O(N)$ Time, $O(1)$ Space |

### Two Pointers, Sliding Window & Binary Search
| # | Problem Name | LeetCode / GFG Ref | Core Pattern | Target Complexity |
| :--- | :--- | :--- | :--- | :--- |
| **A25** | **3Sum** | LC #15 | Sort + Two Pointers + Skip Duplicates | $O(N^2)$ Time, $O(1)$ Space |
| **A26** | **Container With Most Water** | LC #11 | Two Pointers Shrinking Shorter Wall | $O(N)$ Time, $O(1)$ Space |
| **A27** | **Trapping Rain Water** | LC #42 | Two Pointers (`leftMax`, `rightMax`) | $O(N)$ Time, $O(1)$ Space |
| **A28** | **Binary Search / Search in Rotated Array** | LC #704 / #33 | Modified Binary Search | $O(\log N)$ Time, $O(1)$ Space |
| **A29** | **Magic Index ($A[i] = i$ with duplicates)** | CodingNinjas / AAEA | Binary Search with Boundary Skip | $O(\log N)$ Avg Time |
| **A30** | **Koko Eating Bananas** | LC #875 | Binary Search on Answer Space | $O(N \log(\max(P)))$ Time |

### Stacks, Queues & Linked Lists
| # | Problem Name | LeetCode / GFG Ref | Core Pattern | Target Complexity |
| :--- | :--- | :--- | :--- | :--- |
| **A31** | **Valid Parentheses** | LC #20 | Stack Matching (Asked in 2024/2025 OA) | $O(N)$ Time, $O(N)$ Space |
| **A32** | **Next Smaller / Greater Element** | GFG / LC #496 | Monotonic Stack (Asked in July OA) | $O(N)$ Time, $O(N)$ Space |
| **A33** | **Daily Temperatures** | LC #739 | Monotonic Decreasing Stack | $O(N)$ Time, $O(N)$ Space |
| **A34** | **Reverse Linked List (Iterative & Recursive)** | LC #206 | Three Pointers (`prev`, `curr`, `next`) | $O(N)$ Time, $O(1)$ Space |
| **A35** | **Detect & Remove Cycle in Linked List** | LC #141 / #142 | Floyd's Tortoise and Hare | $O(N)$ Time, $O(1)$ Space |
| **A36** | **Merge Two Sorted Lists** | LC #21 | Dummy Node Pointer Weaving | $O(N + M)$ Time, $O(1)$ Space |
| **A37** | **Middle of the Linked List** | LC #876 | Slow and Fast Pointers | $O(N)$ Time, $O(1)$ Space |
| **A38** | **Intersection of Two Linked Lists** | LC #160 | Two Pointers Switching Heads | $O(N + M)$ Time, $O(1)$ Space |

### Math & Standard Dynamic Programming
| # | Problem Name | LeetCode / GFG Ref | Core Pattern | Target Complexity |
| :--- | :--- | :--- | :--- | :--- |
| **A39** | **Climbing Stairs** | LC #70 | Space-Optimized Fibonacci DP | $O(N)$ Time, $O(1)$ Space |
| **A40** | **N-th Tribonacci Number** | LC #1137 | 3-Variable Rolling DP | $O(N)$ Time, $O(1)$ Space |
| **A41** | **Coin Change (Minimum Coins)** | LC #322 | 1D Unbounded Knapsack DP | $O(N \times \text{Amount})$ Time |
| **A42** | **Longest Increasing Subsequence (LIS)** | LC #300 | Patience Sorting + Binary Search | $O(N \log N)$ Time |
| **A43** | **Happy Number** | LC #202 | Cycle Detection on Digit Square Sum | $O(\log N)$ Time |
| **A44** | **Water Bottles (Exchange Empty Bottles)** | LC #1518 | Simulation / Math Division | $O(\log_k N)$ Time |
| **A45** | **Find the Winner of the Circular Game** | LC #1823 | Josephus Problem: $f(n,k) = (f(n-1,k)+k) \bmod n$ | $O(N)$ Time, $O(1)$ Space |

---

# TIER B: Advanced AAEA (~₹11.89 LPA) Differentiators
*These problems come directly from past AAEA / AEH interview experiences (VIT, LPU, SRM, etc.) and the harder half of Accenture's LeetCode tag pool. When Accenture conducts a dedicated AAEA test or evaluates the harder coding slot, these patterns appear.*

### 1. Real Reported AAEA Campus Coding Questions
* **B1. Binary Tree Pruning (Reported in AAEA OA | LC #814):**
  * *Problem:* Given a Binary Tree where each node is `0` or `1` (input often given in level-order with `-1` as null), remove all subtrees that do not contain a `1`.
  * *Pattern:* Post-Order DFS Traversal ($O(N)$ time).
* **B2. Count All Grid Paths Forming String $S$ (Reported in AAEA OA | Variation of LC #79 Word Search):**
  * *Problem:* Given a 2D character grid and a target string $S$, count the total number of valid paths (moving Up, Down, Left, Right without revisiting a cell in the same path) that spell $S$.
  * *Pattern:* DFS Backtracking from every matching starting cell ($O(R \cdot C \cdot 3^{|S|})$ time).
* **B3. Sliding Window Maximum (Reported in SASA/AAEA OA | LC #239):**
  * *Problem:* Given an array `nums` and window size $k$, return the maximum element in every contiguous window of size $k$.
  * *Pattern:* Monotonic Decreasing Deque storing indices ($O(N)$ time, $O(K)$ space).
* **B4. The Celebrity Problem (Reported in 2024 AAEA Campus Drive | GFG / LC #277):**
  * *Problem:* Given an $N \times N$ matrix `M` where `M[i][j] == 1` means person $i$ knows person $j$. A celebrity knows nobody (`0`s in row) but everyone knows them (`1`s in col). Find the celebrity in $O(N)$ time.
  * *Pattern:* Two-Pointer Elimination (`i = 0, j = n - 1`) + Verification Pass ($O(N)$ time, $O(1)$ space).
* **B5. Smallest Number Greater Than $K$ by Removing Digits (Reported in August 2024 AAEA Drive):**
  * *Problem:* Given two integers $N$ and $K$, find the smallest number strictly greater than $K$ formed by removing zero or more digits from $N$ while maintaining the relative order of digits in $N$.
  * *Pattern:* Subsequence Generation / Backtracking with Pruning or Digit DP.
* **B6. Find Original Number from Triple Bit-Flips (Reported in Accenture LeetCode Discuss):**
  * *Problem:* An unknown number $N$ has $k$ bits flipped to form $x$, another $k$ distinct bits flipped to form $y$, and another $k$ distinct bits flipped to form $z$ ($3k$ unique bit positions flipped in total). Given $x, y, z, k$, reconstruct $N$.
  * *Pattern:* Bitwise XOR Analysis: $(x \oplus y) \land (x \oplus z)$ isolates the exact $k$ bits that were flipped in $x$. Flipping those bits in $x$ restores $N$! ($O(1)$ time).
* **B7. Longest Subsequence / Subarray with Consecutive Sum Divisible by $K$ (Reported in 2024 Drive):**
  * *Problem:* Find the longest subarray/subsequence whose sum of consecutive elements is divisible by $K$.
  * *Pattern:* Prefix Sum Modulo $K$ (`(prefixSum % K + K) % K`) with First-Seen Index HashMap (LC #974 variation, $O(N)$ time).

### 2. High-Value LeetCode Medium/Hard Tagged for Accenture
| # | Problem Name | LeetCode Ref | Core Pattern | Target Complexity |
| :--- | :--- | :--- | :--- | :--- |
| **B8** | **Remove K Digits** | LC #402 | Monotonic Increasing Stack + Trim Leading Zeroes | $O(N)$ Time, $O(N)$ Space |
| **B9** | **Maximum Width Ramp** | LC #962 | Monotonic Decreasing Stack + Right-to-Left Scan | $O(N)$ Time, $O(N)$ Space |
| **B10** | **Sum of Subarray Minimums** | LC #907 | Monotonic Stack (Next/Prev Smaller Element Contribution) | $O(N)$ Time, $O(N)$ Space |
| **B11** | **Number of Islands** | LC #200 | Grid BFS / DFS Flood Fill | $O(R \times C)$ Time |
| **B12** | **Letter Combinations of a Phone Number** | LC #17 | Backtracking / Recursion Tree | $O(4^N \cdot N)$ Time |
| **B13** | **Unique Paths (Grid DP)** | LC #62 | 2D / 1D Dynamic Programming or Combinatorics $\binom{m+n-2}{m-1}$ | $O(M \times N)$ Time |
| **B14** | **0/1 Knapsack Problem** | GFG Standard | 1D Space-Optimized DP Array (Right-to-Left) | $O(N \times W)$ Time |
| **B15** | **House Robber (Max Non-Adjacent Sum)** | LC #198 | Rolling 2-Variable DP (`prev1`, `prev2`) | $O(N)$ Time, $O(1)$ Space |
| **B16** | **Lowest Common Ancestor (LCA) of Binary Tree** | LC #236 | Recursive DFS Post-Order | $O(N)$ Time, $O(H)$ Space |
| **B17** | **Binary Tree Level Order / Right Side View** | LC #102 / #199 | BFS Queue tracking level size | $O(N)$ Time, $O(N)$ Space |
| **B18** | **Validate Binary Search Tree (BST)** | LC #98 | Recursive Range Validation `(minVal, maxVal)` | $O(N)$ Time, $O(H)$ Space |
| **B19** | **Diameter of Binary Tree** | LC #543 | DFS Height Calculation tracking `max(L + R)` | $O(N)$ Time, $O(H)$ Space |
| **B20** | **Pow(x, n) (Binary Exponentiation)** | LC #50 | Fast Modulo / Binary Exponentiation | $O(\log N)$ Time, $O(1)$ Space |
| **B21** | **Median of Two Sorted Arrays** | LC #4 | Binary Search on Shorter Array Partition | $O(\log(\min(M, N)))$ Time |
| **B22** | **Longest Valid Parentheses** | LC #32 | Index Stack or Two-Pass Left/Right Counter | $O(N)$ Time, $O(1)$ Space |
| **B23** | **Regular Expression Matching** | LC #10 | 2D Dynamic Programming (`*` and `.` transitions) | $O(M \times N)$ Time |
| **B24** | **Sort an Array (Merge Sort / Heap Sort)** | LC #912 | Divide & Conquer without built-in sort | $O(N \log N)$ Time |
| **B25** | **Course Schedule (Cycle Detection in Graph)** | LC #207 | Kahn's Algorithm (BFS Topological Sort) | $O(V + E)$ Time |
| **B26** | **Kth Largest Element in an Array** | LC #215 | Min-Heap of size $K$ | $O(N \log K)$ Time |
| **B27** | **Longest Common Subsequence (LCS)** | LC #1143 | 2D Dynamic Programming | $O(M \times N)$ Time |
| **B28** | **Edit Distance** | LC #72 | 2D DP (Insert, Delete, Replace) | $O(M \times N)$ Time |

---

# TIER C: SQL, Pseudocode Traps & Secondary Tags (Don't Lose Easy Marks)
*Recent 2025/2026 Accenture assessments and technical interviews heavily test SQL queries and Pseudocode bitwise/recursion trace questions.*

### 1. Must-Know SQL Queries (Asked in OA & Technical Interview)
* **C1. Second Highest / Nth Highest Salary (LC #176 / #177):**
  ```sql
  SELECT DISTINCT salary 
  FROM Employee 
  ORDER BY salary DESC 
  LIMIT 1 OFFSET N-1;
  -- Or using DENSE_RANK():
  WITH Ranked AS (
      SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) AS rnk FROM Employee
  )
  SELECT salary FROM Ranked WHERE rnk = N;
  ```
* **C2. Three-Table JOIN Query (Explicitly asked in 2025/2026 Accenture Coding Assessment):**
  * *Pattern:* Joining `Students`/`Employees`, `Departments`, and `Projects`/`Orders` using `INNER JOIN` or `LEFT JOIN` with a `GROUP BY` and `HAVING` clause.
  ```sql
  SELECT e.emp_name, d.dept_name, p.project_title
  FROM Employees e
  INNER JOIN Departments d ON e.dept_id = d.dept_id
  INNER JOIN Projects p ON e.emp_id = p.emp_id
  WHERE d.dept_name = 'Cloud Engineering';
  ```
* **C3. Department Highest Salary (LC #184):** Use `DENSE_RANK() OVER (PARTITION BY departmentId ORDER BY salary DESC) = 1`.
* **C4. Find Duplicate Emails / Records (LC #182):** `SELECT email FROM Person GROUP BY email HAVING COUNT(email) > 1;`
* **C5. Employees Earning More Than Their Managers (LC #181):** Self-Join (`FROM Employee e JOIN Employee m ON e.managerId = m.id WHERE e.salary > m.salary`).

### 2. Accenture Round 1A Pseudocode Patterns (18 Questions — High Elimination Factor)
Accenture's 18 Pseudocode MCQs follow 4 exact templates. Practice tracing these on paper:
* **C6. Bitwise Precedence & Truthiness Traps:**
  * Expressions like `if (x + (2 & 2) && y + (3 ^ 3))` — Remember: in C-style pseudocode, any non-zero integer is `TRUE`, and `0` is `FALSE`.
  * Key identities: $x \oplus x = 0$, $x \oplus 0 = x$, $x \land x = x$, $x \land 0 = 0$.
* **C7. Nested Loop with `Continue` and `Jump out of the loop` (`break`):**
  * Almost every test has 3–4 questions where `w = w + 5; if (w > y) Continue; w = 1; if (w > z) Jump out of the loop;`. Notice that if `Continue` triggers, `w = 1` is skipped! If `Jump out of the loop` triggers, only the **inner loop** breaks.
* **C8. Multi-Branch Recursion Tree Trace:**
  * Functions like `return x + y + solve(2, y - 5) + solve(x - 10, 1)` where base cases (`if y > 0`) terminate the branches in 1 or 2 steps. Draw the mini tree on paper immediately.
* **C9. Array Adjacent Mutation Loop:**
  * Loops like `for i = 0 to n - 2: arr[i] = arr[i] + arr[i+1]` or `arr[i] = arr[i] - arr[i+1]`.

---

# SECTION 3: Short & High-Yield Interview Guide (Core CS + Technical + HR)

Once you clear the OA and Communication test, the **AAEA / AASE Interview** lasts 20–45 minutes. For the ₹11.89 LPA (AAEA) role, expect 60% Technical/Project + 40% Managerial/HR.

### 1. Most Asked Live Coding / Whiteboard Questions in the Interview
*(Since you practice writing code on paper, use that exact habit here—interviewers often ask you to share your screen on Notepad/IDE and write these):*
1. **Linked List:** Reverse a Singly Linked List, explain Circular Linked List vs. Doubly Linked List, or find the middle element in one pass.
2. **Arrays/Strings:** Find the second largest element in a single pass without sorting, check if a string is a Palindrome/Anagram, or print frequency of characters.
3. **SQL:** Write a query joining two tables, or explain `DELETE` vs. `TRUNCATE` vs. `DROP`, and `WHERE` vs. `HAVING`.

### 2. Core CS Questions (OOPs, DBMS, OS, Cloud & Security)
* **OOPs (Asked in 90% of Accenture Interviews):**
  * Explain the 4 pillars of OOPs with a real-world example from your project.
  * Compile-time (Method Overloading) vs. Runtime Polymorphism (Method Overriding / Virtual Functions).
  * Abstract Class vs. Interface—when do you use which?
  * What is `static`, `final` (Java) / `const` (C++), and how does Garbage Collection / Memory Management work?
* **DBMS:**
  * What are ACID properties? Give an example of Atomicity and Isolation in a bank transfer.
  * Normalization ($1\text{NF}, 2\text{NF}, 3\text{NF}, \text{BCNF}$)—why do we normalize tables?
  * Primary Key vs. Unique Key vs. Foreign Key.
  * Indexing: How does a B-Tree index speed up `SELECT` queries and why does it slow down `INSERT`?
* **Operating Systems & Computer Networks:**
  * Process vs. Thread; Deadlock and its 4 necessary conditions (Mutual Exclusion, Hold & Wait, No Preemption, Circular Wait).
  * What happens when you type `https://www.google.com` in a browser? (DNS $\rightarrow$ TCP 3-Way Handshake $\rightarrow$ TLS/SSL $\rightarrow$ HTTP Request/Response).
* **Cloud & Cybersecurity (Accenture Favorites):**
  * IaaS vs. PaaS vs. SaaS (with Azure/AWS examples).
  * How did you secure your project's APIs or database? (Mention JWT authentication, password hashing with `bcrypt`, SQL Injection prevention via prepared statements, CORS, HTTPS).

### 3. Project Deep-Dive & Behavioral Questions (The Dealbreakers)
Accenture interviewers are trained to probe **teamwork, adaptability, and project ownership**:
1. *"Walk me through your best project architecture from frontend/client to database."* (Ensure your project has full CRUD + authentication + real deployment/GitHub link).
2. *"What was the hardest technical bug or bottleneck you faced in this project, and how did you debug it?"*
3. *"Suppose you have a conflict with a teammate who isn't contributing before a deadline. How do you handle it?"* *(Answer diplomatically: private 1-on-1 conversation to understand their blocker $\rightarrow$ redistribute or pair-program on tasks $\rightarrow$ keep focus on project delivery rather than blaming).*
4. *"Why Accenture, and what do you know about the technologies Accenture currently works on?"* *(Mention Accenture's heavy focus on Cloud First, Generative AI enterprise integration, SAP/Oracle enterprise modernization, and full-stack microservices).*

---

## 4-Week Execution Plan for LPU Drive
* **Week 1:** Finish all **35 Tier S** problems. Write the core function for each in under 10 minutes without looking up syntax.
* **Week 2:** Solve **A1 to A30** (Arrays, Strings, Two Pointers, Binary Search) + practice 50 Pseudocode & Cloud/Networking MCQs.
* **Week 3:** Solve **A31 to A45** + **B1 to B15** (Stacks, Linked Lists, DP, and the reported AAEA Tree/Grid problems).
* **Week 4:** Solve **B16 to B28** + **Tier C SQL Queries**, and do 3 timed mock OAs (2 coding questions in 45 minutes) + review your Resume Projects and OOPs/DBMS notes.