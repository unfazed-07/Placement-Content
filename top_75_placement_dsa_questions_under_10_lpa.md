# The Ultimate 80/20 DSA Checklist for Placements (< 10 LPA)

For compensation brackets up to 10 LPA (including TCS Prime/Digital, Infosys SP/DSE, Cognizant GenC Next, Accenture, Capgemini, LTIMindtree, Deloitte, ZS Associates, and emerging product startups), interviewers focus heavily on **Arrays, Strings, Hashing, Two Pointers, Linked Lists, and Standard Trees/DP**. 

Mastering the exact logic behind these **75 curated problems** will cover 80%+ of the coding questions you will face in both Online Assessments (OAs) and live technical interviews.

---

## 1. Arrays & Matrices (The Highest Weightage: ~30% of OAs)
*Almost every OA under 10 LPA has at least one array manipulation or subarray problem.*

- [ ] **Two Sum** (Understand both the HashMap $O(n)$ approach and Two-Pointer $O(n \log n)$ sorted approach)
- [ ] **Best Time to Buy and Sell Stock (I)** (Tracking minimum so far and maximum profit)
- [ ] **Maximum Subarray Sum (Kadane’s Algorithm)** (Crucial—asked directly or disguised as a story problem)
- [ ] **Sort an Array of 0s, 1s, and 2s** (Dutch National Flag Algorithm - $O(n)$ time, $O(1)$ space)
- [ ] **Move Zeroes to End** (Maintaining relative order of non-zero elements in-place)
- [ ] **Rotate Array by $K$ Elements** (Using the 3-step reversal algorithm in $O(1)$ space)
- [ ] **Majority Element ($> \lfloor n/2 \rfloor$ times)** (Moore’s Voting Algorithm)
- [ ] **Find Missing and Repeating Number in an Array** (Using math equations or XOR)
- [ ] **Merge Overlapping Intervals** (Sorting + linear scan)
- [ ] **Next Permutation** (Standard step-by-step pointer manipulation)
- [ ] **Leaders in an Array** (Scanning from right to left)
- [ ] **Equilibrium Index / Find Pivot Index** (Prefix sum concept)
- [ ] **Product of Array Except Self** (Prefix and Suffix products without using the division operator)
- [ ] **Spiral Matrix Traversal** (Boundary pointer manipulation—very common in service/mid-tier product OAs)
- [ ] **Rotate Image / Matrix by 90 Degrees** (Transpose + Reverse rows)
- [ ] **Set Matrix Zeroes** (Using first row and column as markers for $O(1)$ space)

---

## 2. Strings ( ~20% of OAs & Face-to-Face Interviews)
*String parsing, frequency counting, and palindrome checks are absolute favorites for sub-10 LPA technical rounds.*

- [ ] **Valid Palindrome & Palindrome Check after deleting at most one character**
- [ ] **Reverse Words in a Given String** (Handling multiple spaces cleanly)
- [ ] **Valid Anagram** (Using a fixed 26-size frequency array)
- [ ] **Group Anagrams** (Sorting characters as a HashMap key)
- [ ] **Longest Common Prefix** (Sorting and comparing first and last strings)
- [ ] **Longest Palindromic Substring** (Expand around center approach in $O(n^2)$ time and $O(1)$ space)
- [ ] **Isomorphic Strings** (Two-way character mapping)
- [ ] **String Compression / Run-Length Encoding** (e.g., `aaabbc` $\rightarrow$ `a3b2c1`)
- [ ] **Roman to Integer** (Left-to-right comparison logic)
- [ ] **First Non-Repeating Character in a String** (Frequency array / HashMap pass)
- [ ] **Remove All Adjacent Duplicates in String** (Stack or two-pointer simulation)

---

## 3. Hashing, Two Pointers & Sliding Window (~15% of OAs)
*When an OA gives you a $O(n^2)$ brute-force problem that gives TLE (Time Limit Exceeded), the intended solution is almost always one of these.*

- [ ] **Longest Substring Without Repeating Characters** (Sliding Window + Set/Map)
- [ ] **3Sum** (Sorting + Two Pointers while skipping duplicates)
- [ ] **Container With Most Water** (Greedy two-pointer shrinking)
- [ ] **Trapping Rain Water** (Prefix/Suffix max arrays or Two Pointers)
- [ ] **Subarray Sum Equals $K$** (Prefix Sum + HashMap—essential for negative numbers)
- [ ] **Longest Subarray with Sum $K$** (Both positive-only sliding window and positive+negative HashMap approaches)
- [ ] **Longest Consecutive Sequence** (Using a HashSet for $O(n)$ lookup)
- [ ] **Maximum Points You Can Obtain from Cards / Maximum Sum of Distinct Subarrays of Length $K$** (Fixed-size sliding window)
- [ ] **Intersection & Union of Two Sorted/Unsorted Arrays**

---

## 4. Binary Search (~10% of Interviews)
*Interviewers love asking you to write Binary Search on a whiteboard/screen to test how you handle boundary conditions (`low <= high`).*

- [ ] **Standard Binary Search & First and Last Position of Element in Sorted Array**
- [ ] **Search in Rotated Sorted Array** (Identifying which half is sorted)
- [ ] **Find Minimum in Rotated Sorted Array**
- [ ] **Find Peak Element**
- [ ] **Single Element in a Sorted Array** (Index parity check: even/odd index pairing)
- [ ] **Koko Eating Bananas / Aggressive Cows** (The only two "Binary Search on Answer" problems you need for 7–10 LPA roles)

---

## 5. Linked Lists (Top Favorite for Live Technical Interviews)
*Rarely asked in OAs, but heavily asked in live interviews to check pointer manipulation.*

- [ ] **Reverse a Linked List** (Both Iterative and Recursive)
- [ ] **Find the Middle of a Linked List** (Slow and Fast Tortoise-Hare pointers)
- [ ] **Detect Cycle in a Linked List & Find Starting Point of Cycle** (Floyd’s Cycle Detection)
- [ ] **Merge Two Sorted Linked Lists** (In-place pointer stitching)
- [ ] **Remove $N$-th Node From End of List** (Two pointers separated by $N$ steps)
- [ ] **Intersection of Two Linked Lists** (Two pointers switching heads)
- [ ] **Check if Linked List is Palindrome** (Find middle + reverse second half)
- [ ] **Add Two Numbers Represented by Linked Lists** (Carry-forward handling)

---

## 6. Stacks & Queues
- [ ] **Valid Parentheses** (The single most asked stack question in interviews)
- [ ] **Next Greater Element** (Monotonic Stack pattern—solves 5+ variations like Daily Temperatures and Stock Span)
- [ ] **Implement Stack using Queues & Queue using Stacks**
- [ ] **Min Stack** (Supporting `push`, `pop`, and `getMin` in $O(1)$ time)
- [ ] **LRU Cache** (Asked specifically in the 8–10 LPA bracket to test HashMap + Doubly Linked List design)

---

## 7. Recursion, Binary Trees & BSTs
*For sub-10 LPA roles, you do not need complex Red-Black trees or heavy segment trees. Stick to standard traversals and height/view properties.*

- [ ] **Inorder, Preorder, Postorder, and Level Order Traversal (BFS)**
- [ ] **Maximum Depth (Height) of a Binary Tree**
- [ ] **Diameter of a Binary Tree** (Longest path between any two nodes)
- [ ] **Check if a Binary Tree is Height-Balanced**
- [ ] **Symmetric Tree (Mirror Image Check)**
- [ ] **Left View and Right View of a Binary Tree** (Level order or recursion tracking level)
- [ ] **Lowest Common Ancestor (LCA) of a Binary Tree & BST**
- [ ] **Validate Binary Search Tree (BST)** (Using `[min, max]` range constraints)
- [ ] **$K$-th Smallest/Largest Element in a BST** (Inorder traversal property)

---

## 8. Heaps, Greedy & Foundational Graphs
- [ ] **$K$-th Largest Element in an Array** (Min-Heap of size $K$)
- [ ] **Top $K$ Frequent Elements** (HashMap + Heap/Bucket Sort)
- [ ] **Activity Selection / N Meetings in One Room** (Standard Greedy sorting by end time)
- [ ] **Minimum Platforms Required for a Railway Station** (Sorting arrival and departure times)
- [ ] **Number of Islands / Connected Components** (Standard Grid BFS/DFS)
- [ ] **Rotting Oranges** (Multi-source BFS)
- [ ] **Detect Cycle in an Undirected and Directed Graph** (BFS/DFS)

---

## 9. Must-Know Dynamic Programming & Number Theory (OA Classics)
*Sub-10 LPA tests rarely ask 3D DP. They stick to 1D DP, Knapsack, LCS, and basic number theory.*

- [ ] **Climbing Stairs / Fibonacci Number** (Space-optimized 1D DP)
- [ ] **House Robber** (Pick vs. Not-Pick pattern on adjacent elements)
- [ ] **Coin Change** (Minimum coins to make a target sum)
- [ ] **0/1 Knapsack Problem** (Classic 2D/1D table formulation)
- [ ] **Longest Common Subsequence (LCS) & Longest Increasing Subsequence (LIS)**
- [ ] **Sieve of Eratosthenes** (Generating prime numbers up to $N$ in $O(n \log \log n)$)
- [ ] **GCD / HCF using Euclidean Algorithm** ($\gcd(a, b) = \gcd(b, a \pmod b)$)

---

## BONUS: The 5 SQL Queries That Appear in Every < 10 LPA Interview
In the under-10 LPA bracket, **SQL carries almost 30% weightage in the face-to-face technical interview**. Make sure you can write these five queries on paper without syntax errors:

1. **Find the $N$-th (or 2nd) Highest Salary:** Using `DENSE_RANK() OVER (ORDER BY salary DESC)` or `LIMIT 1 OFFSET N-1`.
2. **Department-wise Highest Salary:** Joining `Employee` and `Department` tables using `GROUP BY` or `RANK() OVER (PARTITION BY dept_id ORDER BY salary DESC)`.
3. **Find Duplicate Records in a Table:** Using `GROUP BY email HAVING COUNT(email) > 1`.
4. **Employees Earning More Than Their Managers:** Self-Join (`FROM Employee e JOIN Employee m ON e.manager_id = m.emp_id WHERE e.salary > m.salary`).
5. **INNER JOIN vs. LEFT JOIN Output Prediction:** Knowing exact row counts when tables contain `NULL` or duplicate join keys.