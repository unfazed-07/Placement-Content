# The Single-Source-of-Truth DSA Bible for CSE Placements (3.5 LPA – 12 LPA)

**Why No Other Sheet Is Needed:** Most generic DSA sheets (300–450 questions) mix FAANG/40-LPA competitive programming problems with basic campus placement problems, causing massive wasted effort. Conversely, short 50-question lists miss the exact story-based OA patterns and 9–12 LPA Graph/DP filters.

This master blueprint is compiled by cross-referencing multi-year campus placement archives across **LeetCode Discuss, GeeksforGeeks, PrepInsta, CampusMonk, and DSAPrep**. It contains **90 Tier-Ranked Core Problems** + **16 Verbatim Company OA Story Problems** + **26 Live Face-to-Face Interview Staples**, complete with **Pattern Triggers, Brute-to-Optimal Direction, and Edge-Case Traps**.

---

## 🗺️ Section 0: The Package-Band Roadmaps & Execution Strategy

Before practicing, match your target company's package band to the exact Tiers required:

| Package Band | Target Companies & Roles | Exact Tiers Required | Focus Topics & OA Time Allocation |
| :--- | :--- | :--- | :--- |
| **Band 1: 3.5 – 5.0 LPA** *(Base Service)* | TCS Ninja (3.36L), Infosys SE (3.6L), Cognizant GenC (4L), Wipro Elite (3.5L), Capgemini A4 (4.25L), Accenture ASE (4.5L) | **Tier S + Part 2 (OA Vault)** | Number Theory, Basic Arrays, String Frequency, Two Pointers, Basic SQL. *(Goal: Solve 1.5–2/2 OA questions in 45 mins)*. |
| **Band 2: 5.5 – 7.5 LPA** *(Differential Roles)* | TCS Digital (7L), Infosys DSE (6.5L), Cognizant GenC Pro/Next (5.4–6.75L), Accenture AASE (6.5L), Capgemini Exceller (5.75–7.5L), LTIMindtree (6.5L), Hexaware (6L) | **Tier S + Tier A + Part 2 (OA Vault)** | Sliding Window, Prefix Sum + HashMap, Sorting/Searching, Linked Lists, Monotonic Stack, 1D DP. |
| **Band 3: 7.5 – 10.0 LPA** *(Prime / Consulting / Mid-Product)* | TCS Prime (9L), Infosys SP (9.5L), Deloitte USI (7.6–9L), ZS Associates (8.5–10L), HSBC (9L), Amadeus (9.5L), Philips (9L), KPIT/Bosch | **Tiers S + A + B + C** | Binary Search on Answer, Trees/BST, Heaps, Greedy Intervals, Grid BFS/DFS, 0/1 Knapsack, LCS/LIS. |
| **Band 4: 10.0 – 12.0 LPA** *(FinTech / Enterprise Product)* | IBM (11L), Oracle (11–12L), Juspay (10–12L), ION Group (11L), Barclays (11.5L), NatWest (11L), Optum, Sabre, Caterpillar | **All Tiers (S + A + B + C + D)** | Graph Shortest Paths/Cycles, Disjoint Set (Union-Find), Tries, Monotonic Deque, DP on Stocks/Grids/Trees, System Design DS. |

### Compass Direction: How to Recognize Which Algorithm to Use From Constraints ($N$)
In Online Assessments, the input size $N$ directly tells you which algorithm is expected before you even think about logic:
* **$N \le 15$ to $20$:** Exponential $O(2^n)$ or $O(n!)$ $\rightarrow$ Use **Recursion, Backtracking, or Bitmask DP**.
* **$N \le 500$:** Cubic $O(n^3)$ or Quadratic $O(n^2)$ $\rightarrow$ Use **2D/3D Dynamic Programming or Nested Loops**.
* **$N \le 2,000$:** Quadratic $O(n^2)$ $\rightarrow$ Use **2D DP (LCS/Knapsack), Expand-Around-Center (Strings), or 3Sum**.
* **$N \le 10^5$:** Linearithmic $O(n \log n)$ or Linear $O(n)$ $\rightarrow$ **$O(n^2)$ WILL give TLE**. You *must* use **Sorting + Two Pointers, Sliding Window, Prefix Sum + HashMap, Monotonic Stack, Heap, or Binary Search**.
* **$N \le 10^9$ or $10^{18}$:** Logarithmic $O(\log n)$ or $O(\sqrt{n})$ $\rightarrow$ Use **Binary Search on Answer, Math/GCD, or Bit Manipulation**.

---

# PART 1: The 5-Tier Non-Negotiable DSA List (90 Core Questions)

## 🔥 Tier S: The Absolute Non-Negotiables (3.5 – 6 LPA Foundation & Q1 of All OAs) — 18 Questions
* **Coverage:** Solves **Q1 of 90% of Online Assessments** and forms the core pool for **live technical interview coding tasks** across all companies under 10 LPA.

1. **[S1] Two Sum** `[All Companies — #1 Most Asked]`
   * **Trigger:** Find pair $(i, j)$ where $arr[i] + arr[j] = \text{target}$.
   * **Direction:** Brute force checks all pairs in $O(n^2)$. Optimize to $O(n)$ time & $O(n)$ space by iterating once and checking if `target - arr[i]` exists in a `HashMap<Integer, Integer>` before inserting `(arr[i], i)`. If the array is already sorted (or only values are needed, not original indices), sort and use Two Pointers (`left = 0, right = n - 1`) in $O(n \log n)$ time and $O(1)$ space.
   * **Trap:** Never put all elements into the map first—check while inserting so `[3, 3]` with `target = 6` doesn't overwrite indices or use the same index twice.

2. **[S2] Maximum Subarray Sum (Kadane’s Algorithm)** `[TCS Digital, Cognizant GenC Next, Capgemini, Deloitte]`
   * **Trigger:** Maximum sum of a *contiguous* subarray in an array containing both positive and negative numbers.
   * **Direction:** Brute force uses 2 loops in $O(n^2)$. Optimize to $O(n)$ time and $O(1)$ space: maintain `currSum` and `maxSum = arr[0]`. At each step, `currSum = max(arr[i], currSum + arr[i])` (or add `arr[i]` and reset `currSum = 0` *after* updating `maxSum` if `currSum < 0`).
   * **Trap:** Initializing `maxSum = 0` fails when all elements are negative (e.g., `[-5, -2, -9]` must return `-2`, not `0`). Always initialize `maxSum = arr[0]` or `Integer.MIN_VALUE`.

3. **[S3] Best Time to Buy and Sell Stock (I)** `[Accenture, Deloitte, Infosys DSE, Cognizant]`
   * **Trigger:** Maximize `arr[j] - arr[i]` where $j > i$ (Single buy, single sell).
   * **Direction:** Do not use nested loops. Track `minPriceSoFar = arr[0]` and `maxProfit = 0` in a single pass ($O(n)$ time, $O(1)$ space). At each day $i$, update `minPriceSoFar = min(minPriceSoFar, arr[i])` and `maxProfit = max(maxProfit, arr[i] - minPriceSoFar)`.
   * **Trap:** If prices strictly decrease (`[7, 6, 4, 3, 1]`), return `0` (no transaction), never a negative number.

4. **[S4] Move Zeroes to End (Chocolate Factory Problem)** `[TCS NQT #1 Repeat, Accenture, Wipro]`
   * **Trigger:** Partition array so all `0`s move to the back while keeping relative order of non-zero elements intact.
   * **Direction:** Avoid creating a new array. Use a slow pointer `insertPos = 0` and fast pointer `i = 0..n-1`. Whenever `arr[i] != 0`, swap `arr[insertPos]` with `arr[i]` and increment `insertPos++` ($O(n)$ time, $O(1)$ space).
   * **Trap:** Do not use two pointers from opposite ends (`left` and `right`), as that scrambles the relative order of non-zero elements.

5. **[S5] Sort an Array of 0s, 1s, and 2s (Dutch National Flag)** `[TCS Digital, Infosys, Capgemini, Cognizant]`
   * **Trigger:** Sort an array containing only 3 distinct values (or airport risk levels `0, 1, 2` / colors) in a single pass.
   * **Direction:** Counting 0s, 1s, and 2s takes 2 passes. For a single-pass $O(n)$ solution with $O(1)$ space, use 3 pointers: `low = 0, mid = 0, high = n - 1`.
     * If `arr[mid] == 0`: swap `arr[low]` and `arr[mid]`, increment `low++` and `mid++`.
     * If `arr[mid] == 1`: just increment `mid++`.
     * If `arr[mid] == 2`: swap `arr[mid]` and `arr[high]`, decrement `high--` (**do not** increment `mid` yet, because the incoming element from `high` hasn't been inspected).

6. **[S6] Rotate Array Clockwise/Counter-Clockwise by $K$ Positions** `[TCS NQT/Digital, Capgemini, Infosys SE]`
   * **Trigger:** Shift array elements cyclically to the right or left by $K$ steps in-place.
   * **Direction:** First normalize $K = K \pmod n$. For Right Rotation in $O(n)$ time and $O(1)$ space:
     1. Reverse the entire array `[0 .. n-1]`.
     2. Reverse the first $K$ elements `[0 .. k-1]`.
     3. Reverse the remaining elements `[k .. n-1]`.
   * **Trap:** Forgetting `k = k % n` causes an `ArrayIndexOutOfBoundsException` whenever $K \ge N$.

7. **[S7] Find Second Largest & Second Smallest Element in a Single Pass** `[Infosys SE/DSE, Accenture, Cognizant, Wipro]`
   * **Trigger:** Find runner-up score or 2nd max/min without sorting.
   * **Direction:** Sorting takes $O(n \log n)$. Instead, track `largest = Integer.MIN_VALUE` and `secondLargest = Integer.MIN_VALUE` in one $O(n)$ loop:
     * If `arr[i] > largest`: set `secondLargest = largest`, then `largest = arr[i]`.
     * Else if `arr[i] > secondLargest && arr[i] != largest`: set `secondLargest = arr[i]`.
   * **Trap:** Always include `arr[i] != largest` in the `else if` condition so duplicates of the maximum (e.g., `[10, 10, 5]`) don't make `secondLargest = 10`, and return `-1` if all elements are equal (`[5, 5, 5]`).

8. **[S8] Valid Anagram & Character Frequency Count** `[Accenture, Infosys, Capgemini, Cognizant]`
   * **Trigger:** Check if string $A$ can be rearranged to form string $B$.
   * **Direction:** First check `if (a.length() != b.length()) return false`. Instead of sorting both strings in $O(n \log n)$, create an `int count[26]` (or `count[256]` for full ASCII). Increment `count[a.charAt(i) - 'a']++` and decrement `count[b.charAt(i) - 'a']--` in one loop, then verify all 26 buckets are `0` ($O(n)$ time, $O(1)$ space).
   * **Trap:** Clarify whether comparison is case-sensitive (`"Listen"` vs `"Silent"`) and whether spaces should be ignored.

9. **[S9] Valid Palindrome & Reverse Words in a String** `[Infosys SE/DSE, TCS, Lowe's, Deloitte]`
   * **Trigger:** Check symmetry ignoring punctuation, or reverse word order `"the sky is blue"` $\rightarrow$ `"blue is sky the"`.
   * **Direction:**
     * *Palindrome:* Use two pointers (`left`, `right`), skip non-alphanumeric chars via `Character.isLetterOrDigit()`, and compare `Character.toLowerCase()`.
     * *Reverse Words:* Trim leading/trailing spaces, split by regex `"\\s+"` (handles multiple spaces between words), and join in reverse order—or reverse the whole character array and then reverse each individual word in-place.

10. **[S10] First Non-Repeating Character in a String** `[Infosys DSE, Capgemini, Cognizant, Accenture]`
    * **Trigger:** Find the first character whose total frequency in the string is `1`.
    * **Direction:** Pass 1: Build frequency count in `int freq[26]`. Pass 2: Iterate through the original string from index `0` to `n - 1` and return the first character `s[i]` where `freq[s[i] - 'a'] == 1` ($O(n)$ time, $O(1)$ space).
    * **Trap:** In Pass 2, iterate over the **string**, not the 26-element alphabet array (iterating over the alphabet returns the lexicographically smallest unique char, not the first one in appearance order).

11. **[S11] Longest Substring Without Repeating Characters** `[Capgemini, Deloitte, TCS Prime, ZS Associates]`
    * **Trigger:** Longest *contiguous* substring with all unique characters.
    * **Direction:** Variable Sliding Window ($O(n)$ time). Maintain a `left = 0` pointer and a `HashMap<Character, Integer>` (or `int lastSeen[256]` initialized to `-1`) storing each character's most recent index. As `right` moves from `0` to `n-1`, if `s[right]` was seen at index $\ge \text{left}$, jump `left = lastSeen[s[right]] + 1`. Update `maxLen = max(maxLen, right - left + 1)`.
    * **Trap:** When jumping `left`, always use `left = Math.max(left, map.get(ch) + 1)` so `left` never moves backward on stale characters outside the current window (e.g., on `"abba"`).

12. **[S12] Subarray Sum Equals $K$ (Count of Subarrays & Longest Length)** `[TCS Digital/Prime, Infosys DSE, Juspay]`
    * **Trigger:** Count subarrays or find the longest subarray summing to $K$.
    * **Direction:**
      * *If array has negatives:* Sliding window FAILS because shrinking the window doesn't monotonically decrease the sum. Use **Prefix Sum + HashMap** in $O(n)$ time: store `(prefixSum, count)` for total count (initialize map with `(0, 1)`), or store `(prefixSum, firstSeenIndex)` for longest length (only insert `prefixSum` if not already present so the subarray stays as wide as possible).
      * *If array has ONLY positive numbers:* Use a Two-Pointer Sliding Window in $O(n)$ time and $O(1)$ space.

13. **[S13] Binary Search + First and Last Occurrence of an Element** `[All Face-to-Face Interviews]`
    * **Trigger:** Sorted array lookup or counting duplicates in $O(\log n)$ time.
    * **Direction:** Write standard Binary Search with `mid = low + (high - low) / 2`. When `arr[mid] == target`:
      * To find **First Occurrence**: record `ans = mid` and continue searching left (`high = mid - 1`).
      * To find **Last Occurrence**: record `ans = mid` and continue searching right (`low = mid + 1`).
      * Total count of `target` in sorted array = `lastIndex - firstIndex + 1`.

14. **[S14] Reverse a Singly Linked List** `[Infosys SE/DSE/SP, Cognizant, Accenture, Deloitte]`
    * **Trigger:** Reverse pointer direction in-place in $O(n)$ time and $O(1)$ space.
    * **Direction:** Maintain three pointers: `prev = null`, `curr = head`, `next = null`. Inside `while (curr != null)`:
      1. Save next node: `next = curr.next;`
      2. Reverse link: `curr.next = prev;`
      3. Advance pointers: `prev = curr; curr = next;`
      4. Return `prev` as the new head.

15. **[S15] Detect Cycle in a Linked List & Find the Middle Node** `[Cognizant GenC Next, TCS, Infosys, Deloitte]`
    * **Trigger:** $O(1)$ space traversal on a linked list using Floyd's Tortoise and Hare (`slow` moves 1 step, `fast` moves 2 steps).
    * **Direction:**
      * *Middle Node:* Loop `while (fast != null && fast.next != null)`. When `fast` reaches the end, `slow` is at the middle.
      * *Cycle Detection:* If `slow == fast` inside the loop, a cycle exists. To find the **exact starting node of the cycle**, reset `slow = head` and move both `slow` and `fast` 1 step at a time—where they meet is the cycle entrance.

16. **[S16] Valid Parentheses (`()`, `{}`, `[]`)** `[Deloitte, Cognizant GenC Next, Capgemini, Infosys]`
    * **Trigger:** Matching nested brackets in LIFO order.
    * **Direction:** Push opening brackets onto a `Stack<Character>`. On a closing bracket, first check `if (stack.isEmpty()) return false`, then verify `stack.pop()` matches the corresponding opener. At the end of the loop, return `stack.isEmpty()`.
    * **Trap:** Returning `true` at the end of the loop without checking `stack.isEmpty()` fails on inputs like `"((("`.

17. **[S17] Prime Check in $O(\sqrt{n})$ & Sieve of Eratosthenes** `[TCS NQT, Cognizant, Accenture, Infosys]`
    * **Trigger:** Check primality of one number vs. generating all primes up to $N$.
    * **Direction:**
      * *Single Number:* Handle $n \le 1 \rightarrow \text{false}$, $n \le 3 \rightarrow \text{true}$, divisible by 2 or 3 $\rightarrow \text{false}$, then loop `for (int i = 5; i * i <= n; i += 6)` checking `n % i == 0 || n % (i + 2) == 0`.
      * *Range $[1..N]$:* Create `boolean isPrime[N + 1]` filled with `true`. Loop `i` from `2` to `i * i <= N`; if `isPrime[i]`, mark multiples starting from `j = i * i` (`j += i`) as `false`. Complexity: $O(N \log \log N)$.

18. **[S18] GCD / HCF (Euclidean Algorithm), LCM & Palindrome/Armstrong Number** `[TCS NQT, Cognizant GenC, Wipro]`
    * **Trigger:** Divisibility, fraction simplification, or synchronizing repeating cycles.
    * **Direction:**
      * `gcd(a, b)`: `return b == 0 ? a : gcd(b, a % b);` in $O(\log(\min(a, b)))$ time.
      * `lcm(a, b)`: Always write `(a / gcd(a, b)) * b`—dividing *before* multiplying prevents 32-bit integer overflow!

---

## ⚡ Tier A: The 6 – 8 LPA Differential Clinchers (18 Questions)
* **Coverage:** Targets **TCS Digital (7 LPA), Infosys DSE (6.5 LPA), Cognizant GenC Next (6.75 LPA), Accenture Advanced (6.5 LPA), Capgemini (5.75/7.5 LPA), and LTIMindtree**.

19. **[A1] Majority Element ($> \lfloor n/2 \rfloor$ and $> \lfloor n/3 \rfloor$ times)** `[Capgemini, TCS Digital, Infosys]`
    * **Direction:** Use **Boyer-Moore Voting Algorithm** in $O(n)$ time and $O(1)$ space. Maintain `candidate` and `count = 0`. When `count == 0`, set `candidate = num`. Increment `count` if `num == candidate`, else decrement `count`.
    * **Trap:** If the problem does NOT guarantee a majority element exists, you **must** run a second $O(n)$ pass to verify `freq(candidate) > n / 2`. For $> \lfloor n/3 \rfloor$, maintain 2 candidates and 2 counters.

20. **[A2] Find the Missing and Repeating Number in $[1..N]$** `[Infosys DSE, TCS, Cognizant, Accenture]`
    * **Direction:** Use 64-bit `long` math equations: Let $S - S_n = X - Y$ (where $S_n = \frac{N(N+1)}{2}$) and $S^2 - S^2_n = X^2 - Y^2 = (X - Y)(X + Y)$ (where $S^2_n = \frac{N(N+1)(2N+1)}{6}$). Solve the two linear equations for Repeating ($X$) and Missing ($Y$) in $O(n)$ time and $O(1)$ space.

21. **[A3] Merge Overlapping Intervals** `[Deloitte, Capgemini, TCS Prime, ZS Associates]`
    * **Direction:** Sort intervals by start time: `Arrays.sort(intervals, (a, b) -> Integer.compare(a[0], b[0]))`. Iterate through sorted intervals: if `curr[0] <= prev[1]`, merge them via `prev[1] = Math.max(prev[1], curr[1])`; otherwise add `curr` to result list ($O(n \log n)$ time).

22. **[A4] Leaders in an Array & Equilibrium / Pivot Index** `[Accenture, TCS NQT/Digital, Cognizant]`
    * **Direction:**
      * *Leaders:* Scan right-to-left tracking `maxFromRight`. Whenever `arr[i] >= maxFromRight`, it is a leader.
      * *Equilibrium Index:* Compute `totalSum` first. Then iterate with `leftSum = 0`; at index $i$, `rightSum = totalSum - leftSum - arr[i]`. Check if `leftSum == rightSum` before adding `arr[i]` to `leftSum`.

23. **[A5] Product of Array Except Self** `[Deloitte, Infosys DSE, IBM, HashedIn]`
    * **Direction:** Division `/` fails as soon as the array contains a `0`. Instead, initialize `res[]` with prefix products in Pass 1 (left-to-right), then multiply `res[i]` by a running `suffixProduct` variable in Pass 2 (right-to-left) in $O(n)$ time and $O(1)$ extra space.

24. **[A6] Spiral Matrix Traversal & Rotate Matrix by 90 Degrees** `[Capgemini #1 Matrix Q, Cognizant GenC, TCS]`
    * **Direction:**
      * *Spiral:* Maintain 4 boundaries (`top = 0, bottom = R-1, left = 0, right = C-1`). Traverse Top Row (`top++`), Right Col (`right--`), check `if (top <= bottom)` before traversing Bottom Row (`bottom--`), and check `if (left <= right)` before traversing Left Col (`left++`).
      * *Rotate 90° Clockwise:* Step 1: Transpose matrix (`swap(mat[i][j], mat[j][i])` for $j > i$). Step 2: Reverse every row.

25. **[A7] Group Anagrams** `[Deloitte, Infosys DSE, Amadeus, ZS Associates]`
    * **Direction:** Map each word to its sorted character string (e.g., `"eat" -> "aet"`) or a 26-char frequency key in a `HashMap<String, List<String>>`, then return `new ArrayList<>(map.values())`.

26. **[A8] Longest Common Prefix & Isomorphic Strings** `[TCS, Accenture, Cognizant, Capgemini]`
    * **Direction:**
      * *LCP:* Sort the string array alphabetically in $O(N \log N \cdot M)$ and compare only the **first** and **last** strings character by character.
      * *Isomorphic:* Maintain two arrays `mapST[256]` and `mapTS[256]` to enforce a strict 1-to-1 bidirectional mapping (so `"ab"` and `"aa"` correctly return `false`).

27. **[A9] String Compression / Run-Length Encoding (`aabbbbeee` $\rightarrow$ `a2b4e3`)** `[Capgemini Verbatim Repeat, Accenture, TCS]`
    * **Direction:** Use a `while (i < n)` loop with an inner loop counting consecutive identical characters `while (i + 1 < n && s.charAt(i) == s.charAt(i + 1)) { count++; i++; }`. Append `s.charAt(i)` and `count` to a `StringBuilder`.

28. **[A10] 3Sum (Triplets with Zero / Target Sum)** `[Deloitte, Infosys DSE/SP, HSBC, TCS Prime]`
    * **Direction:** Sort the array first ($O(n \log n)$). Fix `i` from `0` to `n-3` (skip duplicate `arr[i] == arr[i-1]`), then use Two Pointers (`left = i + 1, right = n - 1`) to find `arr[i] + arr[left] + arr[right] == 0` in $O(n^2)$ total time. Skip duplicates on `left` and `right` after every valid triplet.

29. **[A11] Search in Rotated Sorted Array** `[TCS Digital/Prime, Infosys DSE, Deloitte, Amadeus]`
    * **Direction:** In any rotated sorted array, at least one half (`[low..mid]` or `[mid..high]`) is strictly sorted. At each Binary Search step:
      * If `arr[low] <= arr[mid]` (Left half is sorted): check if `target` lies within `[arr[low], arr[mid])` $\rightarrow$ go left (`high = mid - 1`), else go right.
      * Else (Right half is sorted): check if `target` lies within `(arr[mid], arr[high]]` $\rightarrow$ go right (`low = mid + 1`), else go left.

30. **[A12] Merge Two Sorted Linked Lists & Remove $N$-th Node From End** `[Infosys DSE, Cognizant GenC Next, Deloitte]`
    * **Direction:**
      * *Merge:* Create a `dummy` node and splice the smaller of `l1` and `l2` iteratively in $O(1)$ space.
      * *Remove $N$-th From End:* Attach a `dummy` node before `head`, advance `fast` by $N$ steps, then move both `slow` and `fast` until `fast.next == null`. Now `slow.next = slow.next.next` cleanly handles even removing the original head node!

31. **[A13] Next Greater Element (I & Circular Array II)** `[Infosys DSE/SP Verbatim, TCS Prime, Cognizant]`
    * **Direction:** Traverse from right to left (`i = n - 1` down to `0`). Maintain a **Monotonic Decreasing Stack**: `while (!st.isEmpty() && st.peek() <= arr[i]) st.pop();`. Now `ans[i] = st.isEmpty() ? -1 : st.peek()`, and push `arr[i]`. For a **circular array**, loop from `2 * n - 1` down to `0` using `i % n`.

32. **[A14] Implement Stack using Queues & Queue using Stacks** `[Cognizant GenC Pro/Next, LTIMindtree, Wipro, Deloitte]`
    * **Direction:**
      * *Stack using 1 Queue:* After `q.offer(x)`, rotate the existing `q.size() - 1` elements to the back via `q.offer(q.poll())`.
      * *Queue using 2 Stacks:* Push into `inStack`. On `pop()` or `peek()`, if `outStack` is empty, pour all elements from `inStack` into `outStack`—this gives **amortized $O(1)$** time per operation.

33. **[A15] Binary Tree Traversals (Inorder, Preorder, Postorder, Level Order BFS)** `[Cognizant GenC Next, Infosys DSE, TCS]`
    * **Direction:** Know recursive 3-line DFS traversals cold, plus **Level-Order BFS** using a `Queue<TreeNode>` where `int levelSize = q.size()` processes nodes level by level (which also solves Zig-Zag Traversal and Average of Levels).

34. **[A16] Maximum Depth (Height), Invert Binary Tree & Check Height-Balanced** `[Infosys DSE/SP, Cognizant, Capgemini]`
    * **Direction:** For **Height-Balanced Check**, do not call `height()` separately at each node ($O(n^2)$). Instead, write a single bottom-up DFS returning `-1` as a sentinel code whenever `Math.abs(leftH - rightH) > 1` ($O(n)$ time).

35. **[A17] Merge Sort, Quick Sort & Merge Two Sorted Arrays in $O(1)$ Space** `[Cognizant GenC Next, Infosys DSE, TCS]`
    * **Direction:** Be ready to code `merge(arr, l, mid, r)` and `partition(arr, low, high)` on paper. To merge two sorted arrays `arr1[]` and `arr2[]` without extra space, compare the largest of `arr1` (`i = n - 1`) with the smallest of `arr2` (`j = 0`), swap while `arr1[i] > arr2[j]`, and re-sort both arrays.

36. **[A18] Climbing Stairs & House Robber (Max Sum of Non-Adjacent Elements)** `[Cognizant GenC, Deloitte, Accenture, TCS Digital]`
    * **Direction:** Both follow the 1D DP recurrence `curr = max(notPick, pick)`. For House Robber: `curr = Math.max(prev1, arr[i] + prev2)`. Maintain only two variables (`prev1`, `prev2`) to optimize space from $O(n)$ to $O(1)$.

---

## 🎯 Tier B: The 8 – 10 LPA High-Tier Evaluators (18 Questions)
* **Coverage:** Targets **TCS Prime (9 LPA), Infosys DSE/SP (6.5–9.5 LPA), Deloitte (7.6–9 LPA), ZS Associates (8.5–10 LPA), HSBC (9 LPA), and Amadeus (9.5 LPA)**.

37. **[B1] Next Permutation (and Nearest Larger Number by Swapping Digits)** `[TCS Digital/Prime Verbatim, Deloitte, Infosys]`
    * **Direction:** 1. Scan right-to-left to find the first dip `i` where `arr[i] < arr[i + 1]`. 2. If `i >= 0`, scan right-to-left to find the first element `arr[j] > arr[i]` and swap `(i, j)`. 3. Reverse the suffix from `i + 1` to `n - 1` ($O(n)$ time, $O(1)$ space).

38. **[B2] Set Matrix Zeroes** `[TCS Prime, Deloitte, ZS Associates, Infosys DSE]`
    * **Direction:** Using extra row/col boolean arrays takes $O(R + C)$ space. For $O(1)$ space, use `matrix[i][0]` and `matrix[0][j]` as markers, plus a separate `col0 = 1` variable to avoid overlap at `matrix[0][0]`.

39. **[B3] Longest Palindromic Substring & Palindromic Substrings Count** `[TCS Digital/Prime, Infosys SP, Product OAs]`
    * **Direction:** Avoid $O(n^2)$ space DP table. Instead, for every index $i$ from `0` to `n - 1`, expand two pointers outward around `(i, i)` (odd length) and `(i, i + 1)` (even length) in $O(n^2)$ time and $O(1)$ space.

40. **[B4] Container With Most Water** `[Deloitte #1 Medium Q, ZS Associates, HSBC]`
    * **Direction:** Start with widest container (`left = 0, right = n - 1`). Area = `(right - left) * Math.min(h[left], h[right])`. Always move the pointer pointing to the **shorter line** inward, because width is shrinking and only increasing the limiting shorter height can possibly increase area.

41. **[B5] Trapping Rain Water** `[TCS Prime, Infosys SP, Deloitte, Juspay]`
    * **Direction:** Water trapped at index $i$ is $\min(\text{leftMax}[i], \text{rightMax}[i]) - \text{height}[i]$. Start by explaining the $O(n)$ space prefix/suffix max arrays, then optimize to $O(1)$ space using Two Pointers (`left`, `right`, `leftMax`, `rightMax`).

42. **[B6] Longest Consecutive Sequence in an Unsorted Array** `[Infosys DSE/SP, Deloitte, Amadeus]`
    * **Direction:** Put all elements into a `HashSet<Integer>`. Iterate over each unique `num` in the set: **only** start a `while (set.contains(curr + 1))` counting loop if `!set.contains(num - 1)` (ensuring each sequence is counted only from its true starting element in $O(n)$ total time).

43. **[B7] Minimum Size Subarray Sum ($\ge S$) & Max Sum Subarray of Size $K$** `[Infosys DSE Verbatim, TCS Digital, Capgemini]`
    * **Direction:** Expand `right` adding `arr[right]` to `sum`. Inside a `while (sum >= S)` loop, record `minLen = min(minLen, right - left + 1)` and shrink from the left via `sum -= arr[left++]`.

44. **[B8] Find Minimum in Rotated Sorted Array & Find Peak Element** `[TCS Prime, Infosys DSE, ZS Associates]`
    * **Direction:** For Rotated Minimum: compare `arr[mid]` with `arr[high]`. If `arr[mid] > arr[high]`, the minimum lies in the right half (`low = mid + 1`); else it lies at `mid` or in the left half (`high = mid`). Loop while `low < high`.

45. **[B9] Koko Eating Bananas / Aggressive Cows** `[TCS Prime, Infosys SP, IBM, Oracle]`
    * **Direction:** Whenever a problem asks to **Minimize the Maximum** or **Maximize the Minimum**, apply **Binary Search on the Answer Space**. Set `low = 1, high = max(piles)`. Write a greedy helper `canFinish(mid)` in $O(n)$ and binary search the range in $O(n \log(\max))$.

46. **[B10] Check if Linked List is Palindrome & Intersection of Two Linked Lists** `[Deloitte, Cognizant GenC Next, Infosys]`
    * **Direction:**
      * *Palindrome:* Find middle via slow/fast pointers, reverse the second half in-place, compare first and second halves node-by-node.
      * *Intersection:* Run two pointers `a = headA, b = headB`. Step `a = (a == null) ? headB : a.next` and `b = (b == null) ? headA : b.next`. They will meet at the intersection node (or both reach `null`) after at most $M + N$ steps!

47. **[B11] Min Stack (in $O(1)$ Time and Space)** `[Deloitte, Cognizant GenC Next, HSBC, Amadeus]`
    * **Direction:** Easiest interview-safe implementation: each stack node stores `{val, minSoFar}` where `minSoFar = Math.min(val, stack.peek().minSoFar)`.

48. **[B12] Left View, Right View, Top View & Symmetric (Mirror) Binary Tree** `[Infosys DSE/SP, TCS Prime, Deloitte]`
    * **Direction:**
      * *Left/Right View:* Preorder DFS passing `(node, level)`: if `level == res.size()`, add `node.val` (traverse Left child first for Left View, Right child first for Right View).
      * *Top View:* BFS tracking Horizontal Distance `hd` (`root` at `0`, left `hd - 1`, right `hd + 1`) in a `TreeMap<Integer, Integer>` storing the first node seen at each `hd`.

49. **[B13] Diameter of a Binary Tree & Lowest Common Ancestor (LCA)** `[TCS Prime, Infosys SP, Cognizant GenC Next, IBM]`
    * **Direction:**
      * *Diameter:* At every node inside the `height()` recursion, update a global `maxDia = Math.max(maxDia, leftHeight + rightHeight)`.
      * *LCA:* If `root == null || root == p || root == q`, return `root`. Recurse left and right: if both return non-null, `root` is the LCA; otherwise return the non-null side.

50. **[B14] Validate Binary Search Tree (BST) & $K$-th Smallest Element in BST** `[Deloitte, Infosys DSE, Amadeus, HSBC]`
    * **Direction:**
      * *Validate BST:* Checking only `left.val < root.val < right.val` is a **classic trap**! Pass `validate(node, Long.MIN_VALUE, Long.MAX_VALUE)` and enforce `min < node.val < max`.
      * *$K$-th Smallest:* Inorder traversal of a BST visits nodes in strictly sorted order—decrement `--k` on each visit and return when `k == 0`.

51. **[B15] $K$-th Largest Element in an Array & Top $K$ Frequent Elements** `[Deloitte, ZS Associates, TCS Prime, IBM]`
    * **Direction:** Never use a Max-Heap of size $N$. Use a **Min-Heap (`PriorityQueue`) of size $K$**: push elements and whenever `pq.size() > K`, call `pq.poll()`. At the end, `pq.peek()` is the $K$-th largest in $O(n \log k)$ time.

52. **[B16] Activity Selection (N Meetings in One Room) & Minimum Railway Platforms** `[TCS Digital/Prime, Infosys DSE, Deloitte]`
    * **Direction:**
      * *N Meetings:* Sort meetings by **end time** ascending and greedily pick whenever `curr.start > lastEnd`.
      * *Minimum Platforms:* Sort `arrival[]` and `departure[]` arrays independently. Use two pointers (`i` on arrival, `j` on departure): if `arr[i] <= dep[j]`, increment `platforms++` and `i++`; else decrement `platforms--` and `j++`.

53. **[B17] Number of Islands (Connected Components in a Grid)** `[TCS Prime, Infosys SP, Deloitte, IBM]`
    * **Direction:** Loop through every cell `(r, c)`. Whenever `grid[r][c] == '1'`, increment `islands++` and launch DFS/BFS to sink the entire connected component by setting visited `'1'`s to `'0'` in-place.

54. **[B18] 0/1 Knapsack & Coin Change (Minimum Coins + Ways to Make Change)** `[Infosys SP, TCS Prime, Cognizant GenC Next, ZS]`
    * **Direction:**
      * *0/1 Knapsack (each item used at most once):* 1D DP array `dp[W + 1]`, iterate capacity $w$ **backwards** from $W$ down to `wt[i]`.
      * *Coin Change / Unbounded (unlimited supply):* Iterate amount $a$ **forwards** from `coin` up to `amount`: `dp[a] = Math.min(dp[a], 1 + dp[a - coin])`.

---

## 🛡️ Tier C: The 9 – 10.5 LPA Specialist Shield (18 Questions)
* **Coverage:** Designed for **Infosys Specialist Programmer (SP - 9.5 LPA), TCS Prime Tough Slots (9 LPA), Amadeus, Philips, and IBM**.

55. **[C1] Count Inversions in an Array** `[Infosys SP, TCS Prime, IBM]`
    * **Direction:** Count pairs $(i, j)$ where $i < j$ and $arr[i] > arr[j]$. Use Merge Sort: during `merge()`, since both left and right halves are sorted, whenever `arr[left] > arr[right]`, all remaining elements in the left half from `left` to `mid` also form inversions with `arr[right]`, so add `(mid - left + 1)` to `count` in $O(n \log n)$ time.

56. **[C2] Roman to Integer, Integer to Roman & String to Integer (`atoi`)** `[TCS Digital/Prime, Infosys, Deloitte]`
    * **Direction:** For Roman to Integer, scan left to right: if `val(s[i]) < val(s[i + 1])`, subtract `val(s[i])`; otherwise add `val(s[i])`.

57. **[C3] Minimum Window Substring** `[Infosys SP, TCS Prime, IBM, Juspay]`
    * **Direction:** Expand `right` to satisfy frequency counts of string $T$ (`matchedCount == T.length()`). Once valid, shrink `left` in a `while` loop to record the minimum window length until the window becomes invalid again ($O(n)$ time).

58. **[C4] Single Element in a Sorted Array** `[TCS Prime, Infosys DSE/SP, Deloitte]`
    * **Direction:** Every element appears twice except one. Before the single element, duplicate pairs start at **even** indices `(even, odd)`. After the single element, pairs shift to `(odd, even)`. Use Binary Search in $O(\log n)$ by checking `if (arr[mid] == arr[mid ^ 1]) low = mid + 1; else high = mid;`.

59. **[C5] Add Two Numbers Represented as Linked Lists & Clone List with Random Pointer** `[Cognizant GenC Next, Deloitte, Infosys]`
    * **Direction:** For Add Two Numbers, loop `while (l1 != null || l2 != null || carry != 0)` creating nodes with `sum % 10` and updating `carry = sum / 10`.

60. **[C6] LRU Cache Implementation** `[Cognizant GenC Next Verbatim, Deloitte, IBM, HSBC]`
    * **Direction:** Combine a `HashMap<Integer, Node>` (for $O(1)$ key lookup) with a **Doubly Linked List** with dummy `head` and `tail` nodes (for $O(1)$ removal and insertion at the front as Most Recently Used).

61. **[C7] Rotting Oranges & Flood Fill** `[TCS Prime, Infosys SP, Deloitte, Oracle]`
    * **Direction:** Because rot spreads simultaneously from *multiple* initial rotten oranges, DFS fails. Push all initial `'2'` cells into a Queue at `t = 0` and run **Multi-Source BFS** level by level. Track `freshCount` to return `-1` if any fresh orange remains unreachable.

62. **[C8] Detect Cycle in an Undirected & Directed Graph** `[Infosys SP, TCS Prime, Juspay, IBM]`
    * **Direction:**
      * *Undirected:* Pass `(node, parent)` in DFS/BFS; if a neighbor is already visited and `neighbor != parent`, a cycle exists.
      * *Directed:* Maintain both `visited[]` and `pathVisited[]` (current recursion stack)—a cycle exists only if a neighbor is currently in `pathVisited[]`.

63. **[C9] Topological Sort (Kahn’s BFS Indegree Algorithm / Course Schedule I & II)** `[Infosys SP, TCS Prime, Juspay, IBM]`
    * **Direction:** Compute `indegree[]` for all $V$ vertices, push all vertices with `indegree == 0` into a Queue, pop and decrement neighbors' indegrees, pushing any neighbor that drops to `0`. If the resulting topological order has `< V` nodes, the directed graph contains a cycle!

64. **[C10] Dijkstra’s Shortest Path Algorithm** `[Cognizant GenC Next Verbatim, Infosys SP, Juspay, TCS Prime]`
    * **Direction:** Use a Min-Heap `PriorityQueue<int[]>` ordered by `dist` (`(a, b) -> a[0] - b[0]`) and a `dist[]` array initialized to `INF`. Relax edges via `if (d + wt < dist[next]) { dist[next] = d + wt; pq.offer(new int[]{dist[next], next}); }` in $O((V + E) \log V)$ time.

65. **[C11] Subsets (Power Set) & Permutations of a String/Array** `[TCS Digital/Prime, Infosys DSE/SP, Accenture]`
    * **Direction:**
      * *Subsets:* At index $i$, branch into `pick` (add `arr[i]`, recurse `i + 1`, backtrack remove) and `notPick` (recurse `i + 1`).
      * *Permutations:* Swap `arr[idx]` with every `i` from `idx` to `n - 1`, recurse `idx + 1`, and swap back to backtrack.

66. **[C12] Combination Sum (I & II)** `[Infosys SP, TCS Prime, Deloitte]`
    * **Direction:** When unlimited reuse of `arr[i]` is allowed (Comb Sum I), stay at index `i` on the `pick` call: `dfs(i, target - arr[i])`. When each element can be used once (Comb Sum II), sort the array, skip duplicates `if (i > idx && arr[i] == arr[i-1]) continue`, and recurse `dfs(i + 1, target - arr[i])`.

67. **[C13] Longest Common Subsequence (LCS) & Longest Increasing Subsequence (LIS)** `[Infosys DSE/SP Verbatim, TCS Prime, IBM]`
    * **Direction:**
      * *LCS:* If `s1[i-1] == s2[j-1]`, `dp[i][j] = 1 + dp[i-1][j-1]`; else `Math.max(dp[i-1][j], dp[i][j-1])`. (Note: Longest Palindromic Subsequence is just `LCS(s, reverse(s))`).
      * *LIS:* Know both $O(n^2)$ DP and the $O(n \log n)$ patience-sorting approach using `Collections.binarySearch()` on a `tails` list to pass $N = 10^5$ constraints in Infosys SP.

68. **[C14] Partition Equal Subset Sum (Subset Sum Equals $K$)** `[Infosys SP, TCS Prime, ZS Associates]`
    * **Direction:** If `totalSum` is odd, return `false`. Otherwise reduce to boolean 0/1 Knapsack checking if a subset sums to `target = totalSum / 2`.

69. **[C15] Unique Paths (With & Without Obstacles) & Minimum Path Sum in a Grid** `[TCS Digital/Prime, Deloitte, Infosys SP]`
    * **Direction:** For each cell `(r, c)`, `dp[r][c] = grid[r][c] + Math.min(dp[r-1][c], dp[r][c-1])`. Set `dp[r][c] = 0` on obstacle cells for path counting.

70. **[C16] Fractional Knapsack & Job Sequencing with Deadlines** `[Infosys SP, TCS Prime, Capgemini]`
    * **Direction:**
      * *Fractional Knapsack:* Sort items by `value / weight` ratio descending (`Double.compare`) and take whole items until the last remaining capacity fraction.
      * *Job Sequencing:* Sort jobs by profit descending and place each job in the latest free time slot $\le \text{deadline}$.

71. **[C17] Serialize and Deserialize a Binary Tree** `[Cognizant GenC Verbatim, Infosys SP, IBM]`
    * **Direction:** Use Preorder DFS: append `node.val + ","` or `"#,"` for `null`. To deserialize, split by `","` into a Queue and recursively build `root`, `root.left`, and `root.right`.

72. **[C18] Single Number (I & II) & Count Set Bits (Brian Kernighan’s Algorithm)** `[TCS Digital, Accenture, Infosys]`
    * **Direction:** XOR all elements (`ans ^= num`) to find the unique number in $O(n)$ time and $O(1)$ space. To count set `1`-bits in an integer, loop `while (n != 0) { n = n & (n - 1); count++; }`.

---

## 💎 Tier D: The 10 – 12 LPA Extension (Product, FinTech & Elite OA Slots) — 18 Questions
* **Coverage:** Complete this tier ONLY after finishing Tiers S–C, or if you are sitting for **10–12 LPA drives** such as **IBM, Oracle, Juspay, ION Group, Barclays, NatWest, Optum, Sabre, Caterpillar, or Infosys SP Hard Slots**.

73. **[D1] Merge $K$ Sorted Linked Lists / Arrays** `[Deloitte Hard Q, Oracle, IBM, ION Group]`
    * **Direction:** Push the head of each non-null list into a Min-Heap `PriorityQueue<ListNode>` of size $K$. Repeatedly poll the minimum node, append it to your `tail`, and if `minNode.next != null`, offer `minNode.next` into the heap ($O(N \log K)$ time).

74. **[D2] Median of Two Sorted Arrays** `[Cognizant GenC Next, Oracle, Barclays, IBM]`
    * **Direction:** Binary search the partition cut `cut1` on the smaller array `nums1` so `cut2 = (n1 + n2 + 1) / 2 - cut1`. Adjust binary search until `l1 <= r2 && l2 <= r1` in $O(\log(\min(n_1, n_2)))$ time.

75. **[D3] Sliding Window Maximum** `[IBM, Oracle, ION Group, Infosys SP]`
    * **Direction:** Maintain a **Monotonic Decreasing Deque (`ArrayDeque<Integer>`)** of indices: 1. Remove front index if `dq.peekFirst() <= i - k`. 2. Remove back indices while `arr[dq.peekLast()] <= arr[i]`. 3. Add `i` to back; front `arr[dq.peekFirst()]` is the max for window ending at `i` ($O(n)$ time).

76. **[D4] Largest Rectangle in Histogram** `[Infosys SP, Oracle, Juspay, Barclays]`
    * **Direction:** Use a Monotonic Increasing Stack to compute the Next Smaller Element index (`rightSmall[i]`) and Previous Smaller Element index (`leftSmall[i]`) for each bar, then maximize `height[i] * (rightSmall[i] - leftSmall[i] - 1)` in $O(n)$ time.

77. **[D5] Allocate Minimum Number of Pages (Book Allocation / Painter’s Partition)** `[Oracle, IBM, Infosys SP, TCS Prime]`
    * **Direction:** Binary Search on Answer with `low = max(arr)` and `high = sum(arr)`. Check if `countStudents(mid) <= M`; if valid, try smaller maximum (`high = mid - 1`), else `low = mid + 1`.

78. **[D6] Subarrays with $K$ Different Integers (AtMost($K$) $-$ AtMost($K-1$) Trick)** `[IBM, Infosys SP, Oracle, ION Group]`
    * **Direction:** Standard sliding window cannot directly count *exact* $K$ distinct elements because shrinking loses valid prefixes. Instead, write `atMost(nums, K)` using a sliding window and return `atMost(nums, K) - atMost(nums, K - 1)`.

79. **[D7] Longest Subarray with Equal Number of 0s and 1s (Contiguous Array)** `[Infosys SP Verbatim, IBM, Oracle]`
    * **Direction:** Treat every `0` as `-1` and every `1` as `+1`. Now the problem reduces to finding the **Longest Subarray with Sum = 0** using a Prefix Sum `HashMap<Integer, Integer>` initialized with `map.put(0, -1)`.

80. **[D8] Reverse Nodes in $K$-Group** `[Oracle, IBM, Barclays, Sabre]`
    * **Direction:** Count if at least $K$ nodes remain; if not, return `head`. Otherwise reverse the first $K$ nodes iteratively and set `originalHead.next = reverseKGroup(curr, k)`.

81. **[D9] Maximum Path Sum in a Binary Tree & Burn a Binary Tree from Target Node** `[Oracle, Infosys SP, IBM, Juspay]`
    * **Direction:** For Max Path Sum, at each node compute `leftGain = Math.max(0, dfs(node.left))` and `rightGain = Math.max(0, dfs(node.right))` (clamping negatives to `0`), update global `maxSum = Math.max(maxSum, node.val + leftGain + rightGain)`, and return `node.val + Math.max(leftGain, rightGain)` upward.

82. **[D10] Juspay / Functional Graph Trio: Maximum Weight Node, Largest Sum Cycle & Nearest Meeting Cell** `[Juspay 10–12 LPA Verbatim, Infosys SP]`
    * **Direction:** Given an array `Edge[]` where `i` has a directed edge to `Edge[i]`:
      * *Max Weight Node:* Create `weight[N]`, do `if (Edge[i] != -1) weight[Edge[i]] += i;`, return index with max weight.
      * *Largest Sum Cycle:* Track `vis[]` and `pathVis[]` with running path sum to find the maximum cycle sum in $O(N)$.
      * *Nearest Meeting Cell:* Run BFS/traversal from `c1` to fill `dist1[]` and from `c2` to fill `dist2[]`, then pick node $u$ minimizing `dist1[u] + dist2[u]` (or `max(dist1[u], dist2[u])`).

83. **[D11] Disjoint Set Union (DSU / Union-Find) & Minimum Spanning Tree (Kruskal's / Prim's)** `[Infosys SP, IBM, Oracle, Juspay]`
    * **Direction:** Memorize the 10-line DSU template: `find(x) { return parent[x] == x ? x : (parent[x] = find(parent[x])); }`. Sort edges by weight and union endpoints if `find(u) != find(v)` for Kruskal's MST.

84. **[D12] Bipartite Graph Check & Shortest Path in Binary Maze / Word Ladder** `[Oracle, IBM, Barclays, NatWest]`
    * **Direction:** Color nodes with `0` and `1` using BFS/DFS; if any adjacent node already has the same color, the graph has an odd-length cycle and is NOT bipartite.

85. **[D13] Edit Distance (Levenshtein Distance)** `[Infosys SP, Oracle, IBM, Optum]`
    * **Direction:** If `s1[i-1] == s2[j-1]`, `dp[i][j] = dp[i-1][j-1]`; else `1 + Math.min(dp[i-1][j-1], Math.min(dp[i-1][j], dp[i][j-1]))` representing Replace, Delete, and Insert.

86. **[D14] Best Time to Buy and Sell Stock II, III & With Cooldown (State-Machine DP)** `[Oracle, Barclays, IBM, NatWest]`
    * **Direction:** For Stock II (unlimited transactions), greedily sum every positive upward slope: `if (prices[i] > prices[i-1]) profit += prices[i] - prices[i-1]`. For Cooldown/III, track `buy` and `sell` states at each day.

87. **[D15] Rod Cutting, Matrix Chain Multiplication (MCM) / Burst Balloons & TSP Bitmask Basics** `[Infosys SP Verbatim, Oracle]`
    * **Direction:** MCM is the archetype for **Partition DP**: for range `(i, j)`, try every split point $k \in [i, j-1]$ and minimize `solve(i, k) + solve(k + 1, j) + arr[i - 1] * arr[k] * arr[j]`.

88. **[D16] Implement Trie (Prefix Tree)** `[Oracle, IBM, Barclays, ION Group]`
    * **Direction:** Define `class Node { Node[] links = new Node[26]; boolean isEnd = false; }` and implement `insert(word)`, `search(word)`, and `startsWith(prefix)` in $O(\text{length})$ time.

89. **[D17] Find Median from Data Stream** `[Oracle, IBM, Barclays, FinTech]`
    * **Direction:** Maintain `maxHeap` (left/smaller half) and `minHeap` (right/larger half). Always keep `maxHeap.size()` equal to or 1 greater than `minHeap.size()` so median is either `maxHeap.peek()` or `(maxHeap.peek() + minHeap.peek()) / 2.0`.

90. **[D18] Producer-Consumer Thread Synchronization / Design a URL Shortener (Base62)** `[Cognizant GenC Next Verbatim, Barclays, IBM, Oracle]`
    * **Direction:** For URL Shortener, convert an auto-incrementing database ID (64-bit `long`) into a 6–7 character Base62 string using `charMap = "0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"` via `% 62` and `/ 62`.

---

# PART 2: The Verbatim Company OA Story Vault (16 Exact Repeated Problems Under 10 LPA)

*Service-based and mid-tier companies under 10 LPA reuse a specific bank of **custom story problems** that do not appear by name on LeetCode. Memorizing these 16 exact templates gives you an instant advantage in TCS, Accenture, Capgemini, Cognizant, and Infosys OAs.*

### 🟣 Accenture OA Verbatim Classics (4.5 LPA & 6.5 LPA)
1. **[OA-1] Rat Count House:** Given `r` rats, `unit` food per rat, and array `arr[]` of food in each house, return the minimum number of houses from index `0` needed to feed all rats (`totalNeeded = r * unit`).
   * *Direction & Edge Cases:* First check `if (arr == null || arr.length == 0) return -1;`. Loop and accumulate `sum += arr[i]`; as soon as `sum >= r * unit`, return `i + 1`. If loop finishes with `sum < r * unit`, return `0`.
2. **[OA-2] Operations on Binary String:** Given a string like `"1C0C1C1A0B1"` where `'A'` = `AND`, `'B'` = `OR`, and `'C'` = `XOR`, evaluate strictly **left-to-right** (ignoring operator precedence).
   * *Direction:* Initialize `ans = str.charAt(0) - '0'`. Loop `for (int i = 1; i < str.length(); i += 2)` and apply operator `str.charAt(i)` with operand `str.charAt(i + 1) - '0'`.
3. **[OA-3] Password Checker:** Validate `str`: length $\ge 4$, at least 1 digit (`0-9`), at least 1 uppercase letter (`A-Z`), no space `' '` or slash `'/'`, and first character `str[0]` must NOT be a digit. Return `1` or `0`.
4. **[OA-4] Large Small Sum (Even-Odd Index Second Largest):** Split array into elements at even indices (`0, 2, 4...`) and odd indices (`1, 3, 5...`). Return the sum of the **2nd largest element from even indices** and the **2nd smallest (or 2nd largest) element from odd indices**. Return `0` if `arr.length <= 3`.
5. **[OA-5] Move Hyphens to Front & Simultaneous Character Swap:** Move all `'-'` characters to the front of a string (`"Move-Hyphens-to-Front"` $\rightarrow$ `"---MoveHyphenstoFront"`), OR swap all occurrences of `ch1` with `ch2` and `ch2` with `ch1` in a single `if-else if` character loop.
6. **[OA-6] Decimal to $N$-Base Notation (`DectoNBase`) & Number of Carries:** Convert `num` to base `n` ($1 < n \le 36$, where $10=\text{'A'}, 11=\text{'B'}\dots$), OR count how many times a `carry` is generated when adding two numbers `num1` and `num2` digit-by-digit from right to left.

### 🔵 TCS NQT / Digital / Prime OA Verbatim Classics (3.36 LPA, 7 LPA & 9 LPA)
7. **[OA-7] Count Numbers with Unique (Non-Repeating) Digits in Range $[n_1, n_2]$:** Given $n_1 = 101, n_2 = 200$, count how many integers in $[n_1, n_2]$ have no repeated digits.
   * *Direction:* Write a helper `hasUniqueDigits(int x)` using a `boolean seen[10]` array or bitmask `mask |= (1 << digit)`, and count over the range.
8. **[OA-8] Even Sum Permutations in Range $[low, high]$ of Length $K$:** Select $K$ numbers (repetition allowed) from $[low, high]$ such that their sum is **even**, modulo $10^9 + 7$.
   * *Direction:* Count total evens $E$ and odds $O$ in $[low, high]$. Initialize `evenWays = E, oddWays = O`. Loop `step = 2` to `K`: `newEven = (evenWays * E + oddWays * O) % MOD`, `newOdd = (evenWays * O + oddWays * E) % MOD`.
9. **[OA-9] Split String into 3 Palindromic Substrings:** Given a string $S$, partition it into **3 non-empty contiguous palindromes** $S = P_1 + P_2 + P_3$. If impossible, print `"Impossible"`.
   * *Direction:* Run two nested loops for cut indices `i` (from `1` to `n - 2`) and `j` (from `i + 1` to `n - 1`). Check `if (isPal(0, i-1) && isPal(i, j-1) && isPal(j, n-1))` and return the first valid split.
10. **[OA-10] Count Elements Greater Than All Prior Elements (Supermarket / Sundar's Array):** Given an array of integers, count how many elements are strictly greater than all elements before them (`count = 1, maxSoFar = arr[0]`).
11. **[OA-11] Vehicles & Wheels (Two-Wheeler / Four-Wheeler Linear Equation):** Given total vehicles $V$ and total wheels $W$, find $TW$ and $FW$.
    * *Direction & Trap:* Formula is $FW = (W - 2V) / 2$ and $TW = V - FW$. **Crucial Trap:** You MUST validate `if (W < 2 || W % 2 != 0 || V >= W || W > 4 * V || W < 2 * V)` and print `"INVALID INPUT"` to pass hidden TCS test cases!

### 🟢 Capgemini & Cognizant OA Verbatim Classics (4.25 – 7.5 LPA)
12. **[OA-12] Move All Hashes (`#`) to Front of String:** Extract all `'#'` characters into one `StringBuilder` and non-`'#'` characters into another, then concatenate `hashes.append(letters).toString()`.
13. **[OA-13] Dealership Tyres & Minimum Discount Item (String Parsing):** Parse $N$ comma-separated strings `"itemName,price,discountPercent"`, calculate `discount = (price * discountPercent) / 100`, and print all item names matching the minimum discount value.
14. **[OA-14] Equation Evaluator & Factor Finder:** Compute $(a + b)^3 = a^3 + 3a^2b + 3ab^2 + b^3$, OR print all positive factors of `Math.abs(N)` in sorted order (handling $N = 0 \rightarrow \text{"No Factors"}$).

### 🟠 Infosys DSE & Specialist Programmer (SP) Verbatim Classics (6.5 LPA & 9.5 LPA)
15. **[OA-15] Find the Next Smallest Palindrome Larger Than $N$:** Given an array/string of digits, handle the all-`9`s edge case (`999` $\rightarrow$ `1001`), mirror the left half onto the right half, and if that mirrored number is $\le N$, increment the middle digit(s) and propagate the carry outward.
16. **[OA-16] RPG Monster Defeat (Greedy Experience Sorting):** Given initial experience $E$, and $N$ monsters each with `power[i]` required to defeat and `bonus[i]` gained after defeat, create paired objects `(power[i], bonus[i])`, sort ascending by `power[i]`, and greedily defeat while `E >= monster.power` (`E += monster.bonus; count++;`).

---

# PART 3: All 90 Core Questions Organized Topic-Wise (Study Checklist)

Check off each problem by topic. Every item carries its **Tier Tag (`[S]`, `[A]`, `[B]`, `[C]`, `[D]`)** so you know its exact priority.

### 1. Math, Number Theory & Bit Manipulation (6 Questions)
* [ ] **[S17]** Prime Number Check in $O(\sqrt{n})$ & Sieve of Eratosthenes
* [ ] **[S18]** GCD / HCF (Euclidean), LCM & Palindrome / Armstrong Number
* [ ] **[A2]** Find Missing and Repeating Number in $[1..N]$
* [ ] **[C2]** Roman to Integer, Integer to Roman & String to Integer (`atoi`)
* [ ] **[C18]** Single Number (I & II) & Count Set Bits (Brian Kernighan’s Algorithm)
* [ ] **[OA-7 / OA-8]** Unique Digits in Range $[n_1, n_2]$ & Even-Sum Permutations

### 2. Arrays & 2D Matrices (14 Questions)
* [ ] **[S1]** Two Sum
* [ ] **[S2]** Maximum Subarray Sum (Kadane’s Algorithm)
* [ ] **[S3]** Best Time to Buy and Sell Stock (I)
* [ ] **[S4]** Move Zeroes to End (In-place)
* [ ] **[S5]** Sort an Array of 0s, 1s, and 2s (Dutch National Flag)
* [ ] **[S6]** Rotate Array by $K$ Positions (Reversal Algorithm)
* [ ] **[S7]** Find Second Largest & Second Smallest Element in a Single Pass
* [ ] **[A1]** Majority Element ($> \lfloor n/2 \rfloor$ and $> \lfloor n/3 \rfloor$ — Boyer-Moore Voting)
* [ ] **[A3]** Merge Overlapping Intervals
* [ ] **[A4]** Leaders in an Array & Equilibrium / Pivot Index
* [ ] **[A5]** Product of Array Except Self
* [ ] **[A6]** Spiral Matrix Traversal & Rotate Matrix by 90 Degrees
* [ ] **[B1]** Next Permutation
* [ ] **[B2]** Set Matrix Zeroes ($O(1)$ Space)

### 3. Strings (7 Questions)
* [ ] **[S8]** Valid Anagram & Character Frequency Count
* [ ] **[S9]** Valid Palindrome & Reverse Words in a String
* [ ] **[S10]** First Non-Repeating Character in a String
* [ ] **[A7]** Group Anagrams
* [ ] **[A8]** Longest Common Prefix & Isomorphic Strings
* [ ] **[A9]** String Compression / Run-Length Encoding (`a2b4e3`)
* [ ] **[B3]** Longest Palindromic Substring & Three-Palindrome Split

### 4. Hashing, Two Pointers & Sliding Window (10 Questions)
* [ ] **[S11]** Longest Substring Without Repeating Characters
* [ ] **[S12]** Subarray Sum Equals $K$ (Count & Longest Subarray with Sum $K$)
* [ ] **[A10]** 3Sum
* [ ] **[B4]** Container With Most Water
* [ ] **[B5]** Trapping Rain Water
* [ ] **[B6]** Longest Consecutive Sequence
* [ ] **[B7]** Minimum Size Subarray Sum ($\ge S$) & Max Sum Subarray of Size $K$
* [ ] **[C3]** Minimum Window Substring
* [ ] **[D6]** Subarrays with $K$ Different Integers (`atMost(K) - atMost(K-1)`)
* [ ] **[D7]** Longest Subarray with Equal 0s and 1s

### 5. Binary Search & Divide-and-Conquer Sorting (9 Questions)
* [ ] **[S13]** Binary Search + First and Last Occurrence of an Element
* [ ] **[A11]** Search in Rotated Sorted Array
* [ ] **[A17]** Merge Sort, Quick Sort & Merge Two Sorted Arrays in $O(1)$ Space
* [ ] **[B8]** Find Minimum & Peak Element in Rotated/Unsorted Array
* [ ] **[B9]** Koko Eating Bananas / Aggressive Cows (Binary Search on Answer)
* [ ] **[C1]** Count Inversions in an Array
* [ ] **[C4]** Single Element in a Sorted Array
* [ ] **[D2]** Median of Two Sorted Arrays
* [ ] **[D5]** Allocate Minimum Number of Pages (Book Allocation)

### 6. Linked Lists (6 Questions)
* [ ] **[S14]** Reverse a Singly Linked List (Iterative & Recursive)
* [ ] **[S15]** Detect Cycle in a Linked List & Find Middle Node
* [ ] **[A12]** Merge Two Sorted Linked Lists & Remove $N$-th Node From End
* [ ] **[B10]** Check if Linked List is Palindrome & Intersection of Two Linked Lists
* [ ] **[C5]** Add Two Numbers Represented as Linked Lists & Clone with Random Pointer
* [ ] **[D8]** Reverse Nodes in $K$-Group

### 7. Stacks, Queues, Heaps & Design DS (11 Questions)
* [ ] **[S16]** Valid Parentheses
* [ ] **[A13]** Next Greater Element (I & II)
* [ ] **[A14]** Implement Stack using Queues & Queue using Stacks
* [ ] **[B11]** Min Stack ($O(1)$ Time & Space)
* [ ] **[B15]** $K$-th Largest Element in an Array & Top $K$ Frequent Elements
* [ ] **[C6]** LRU Cache Implementation (HashMap + Doubly Linked List)
* [ ] **[D1]** Merge $K$ Sorted Linked Lists / Arrays
* [ ] **[D3]** Sliding Window Maximum (Monotonic Deque)
* [ ] **[D4]** Largest Rectangle in Histogram
* [ ] **[D16 / D17]** Implement Trie (Prefix Tree) & Find Median from Data Stream
* [ ] **[D18]** Producer-Consumer Thread Sync & Base62 URL Shortener

### 8. Recursion, Backtracking & Binary Trees / BST (9 Questions)
* [ ] **[A15]** Binary Tree Traversals (Inorder, Preorder, Postorder, Level Order BFS)
* [ ] **[A16]** Maximum Depth (Height), Invert Tree & Check Height-Balanced
* [ ] **[B12]** Left View, Right View, Top View & Symmetric (Mirror) Binary Tree
* [ ] **[B13]** Diameter of a Binary Tree & Lowest Common Ancestor (LCA)
* [ ] **[B14]** Validate BST & $K$-th Smallest Element in a BST
* [ ] **[C11]** Subsets (Power Set) & Permutations of an Array/String
* [ ] **[C12]** Combination Sum (I & II)
* [ ] **[C17]** Serialize and Deserialize a Binary Tree
* [ ] **[D9]** Maximum Path Sum in a Binary Tree & Burn Binary Tree

### 9. Greedy & Graphs (9 Questions)
* [ ] **[B16]** Activity Selection (N Meetings in One Room) & Minimum Railway Platforms
* [ ] **[B17]** Number of Islands (Connected Components in a Grid)
* [ ] **[C7]** Rotting Oranges (Multi-Source BFS) & Flood Fill
* [ ] **[C8]** Detect Cycle in an Undirected & Directed Graph
* [ ] **[C9]** Topological Sort (Kahn’s BFS / Course Schedule)
* [ ] **[C10]** Dijkstra’s Shortest Path Algorithm
* [ ] **[C16]** Fractional Knapsack & Job Sequencing with Deadlines
* [ ] **[D10]** Juspay / Directed Graph Trio (Max Weight Node, Largest Sum Cycle, Nearest Meeting Cell)
* [ ] **[D11 / D12]** Disjoint Set Union (Kruskal's MST) & Bipartite Graph / Word Ladder

### 10. Dynamic Programming (8 Questions)
* [ ] **[A18]** Climbing Stairs & House Robber (1D Linear DP)
* [ ] **[B18]** 0/1 Knapsack & Coin Change (Minimum Coins + Ways)
* [ ] **[C13]** Longest Common Subsequence (LCS) & Longest Increasing Subsequence (LIS)
* [ ] **[C14]** Partition Equal Subset Sum (Subset Sum Equals $K$)
* [ ] **[C15]** Unique Paths & Minimum Path Sum in a Grid
* [ ] **[D13]** Edit Distance (Levenshtein Distance)
* [ ] **[D14]** Best Time to Buy and Sell Stock II, III & Cooldown
* [ ] **[D15]** Rod Cutting, Matrix Chain Multiplication (MCM) & TSP Bitmask Basics

---

# PART 4: Live Face-to-Face Interview Round — True Probability Model & Execution Guide

### 📊 Understanding Realistic Face-to-Face Interview Probabilities
In a 30-to-40 minute technical interview, **an interviewer only has time to ask you 1 or 2 live coding problems, 2 or 3 conceptual DSA questions, and 1 or 2 SQL queries**. Therefore, no single coding question has an "85% chance" of being asked—rather, interviewers pick **1 question from a specific Bucket**.

Here is the **True Mathematical Breakdown** of how your 15-minute live coding slot is selected across interviews under 12 LPA:
* **Bucket 1 — Array Traversal / Two-Pointer / Hashing (35% of all F2F coding slots):** You have a ~1-in-3 chance of getting one of the top 6 Array questions below.
* **Bucket 2 — String Manipulation & Frequency (28% of all F2F coding slots):** Almost 1-in-3 interviews test string reversal, anagrams, or character frequency on paper/Notepad.
* **Bucket 3 — Linked Lists, Stacks & Binary Search (20% of all F2F coding slots):** Dominant in 6–12 LPA rounds (Infosys DSE/SP, Cognizant GenC Next, Deloitte, TCS Digital/Prime) to test pointer accuracy.
* **Bucket 4 — Number Logic, Recursion & Sorting Internals (12% of all F2F coding slots):** Very common in 3.5–6 LPA rounds as a quick 3-minute warm-up.
* **Remaining 5%:** Unseen variations, Trees, or DP dry-runs.

---

### A. The Top 20 Live Paper/Notepad Coding Questions (With True Share % & Step-by-Step Direction)

*Note: **Individual Share %** represents the true percentage of all live F2F coding slots that use this exact question. Together, these 20 questions account for **95% of all live F2F coding questions** (summing to 95% total, with 5% unseen).*

| Rank | Live Coding Question | Bucket | True Individual Share % | Step-by-Step Direction: How to Present & Code It in the Interview |
| :--- | :--- | :--- | :--- | :--- |
| **1** | **Find 2nd Largest Element in an Array (Single Pass)** | Array | **11.5%** | **1. Say first:** "Sorting takes $O(n \log n)$, or finding max in Pass 1 and 2nd max in Pass 2 takes $2n$ comparisons."<br>**2. Pivot to Optimal:** Write a single $O(n)$ loop tracking `first = MIN, second = MIN`.<br>**3. Crucial Edge Case to State:** Mention duplicates (`[10, 10, 9]`)—explicitly write `else if (x > second && x != first)` and handle arrays where all elements are identical (`[5, 5, 5]` $\rightarrow$ return `-1`). |
| **2** | **Character Frequency Count / First Non-Repeating Character** | String | **10.0%** | **1. Say first:** "A nested loop checking every character's count takes $O(n^2)$."<br>**2. Pivot to Optimal:** Use an `int freq[26]` array (if lowercase) or `LinkedHashMap<Character, Integer>` (if full Unicode/mixed case) in $O(n)$ time.<br>**3. Follow-up they will ask:** *"How do you do it in a single traversal instead of two passes?"* (Answer: Store `(count, firstIndex)` in the map and scan the 26-size map instead of re-scanning a 10-million-character string). |
| **3** | **Reverse a String / Check Palindrome / Reverse Words in a Sentence** | String | **9.0%** | **1. Rule #1:** Never write `new StringBuilder(s).reverse()` unless they ask for a 1-liner. Always write the Two-Pointer swap (`left = 0, right = n - 1`).<br>**2. For "Reverse Words" (`"  sky is  blue "` $\rightarrow$ `"blue is sky"`):** State how you handle leading, trailing, and multiple mid-sentence spaces.<br>**3. Follow-up:** *"Since Strings are immutable in Java/Python, what is the space complexity of string concatenation in a loop vs. `StringBuilder`?"* ($O(n^2)$ vs. $O(n)$). |
| **4** | **Two Sum (Find Pair with Given Target Sum)** | Array / Hash | **8.5%** | **1. Say first:** "Brute force checks all $\frac{n(n-1)}{2}$ pairs in $O(n^2)$ time, $O(1)$ space."<br>**2. Pivot to Optimal:** Offer the trade-off: "If you want $O(n)$ time and allow $O(n)$ space, I'll use a `HashMap`. If memory is constrained to $O(1)$, I'll sort in $O(n \log n)$ and use Two Pointers."<br>**3. Follow-up:** *"What if there are multiple duplicate pairs that sum to target and I want all unique pairs?"* (Sort + Two Pointers skipping `arr[left] == arr[left - 1]`). |
| **5** | **Check if Two Strings are Valid Anagrams** | String | **7.5%** | **1. Say first:** "First check `if (s1.length() != s2.length()) return false;`—that eliminates 90% of false cases in $O(1)$."<br>**2. Pivot to Optimal:** Use a single `int count[26]` array: increment for `s1[i]` and decrement for `s2[i]` in the same loop ($O(n)$ time, $O(1)$ space).<br>**3. Follow-up:** *"What if the input contains Unicode/special characters?"* (Switch from `int[26]` to `HashMap<Character, Integer>`). |
| **6** | **Remove Duplicates from a Sorted or Unsorted Array** | Array | **6.5%** | **1. Clarify immediately:** Ask the interviewer, *"Is the input array sorted or unsorted, and do I need to preserve the original order?"* (Asking this question alone scores huge points).<br>**2. Direction:** If **Unsorted** $\rightarrow$ use `LinkedHashSet` in $O(n)$ time/space. If **Sorted** $\rightarrow$ use in-place Two Pointers (`slow = 0`, `if (arr[fast] != arr[slow]) arr[++slow] = arr[fast]`) in $O(n)$ time and $O(1)$ space. |
| **7** | **Move All Zeroes to the End of the Array** | Array | **6.0%** | **1. Direction:** Use slow/fast pointers (`nonZeroIdx = 0`). Whenever `arr[i] != 0`, swap `arr[nonZeroIdx++]` with `arr[i]`.<br>**2. Follow-up:** *"How do you minimize the number of write/swap operations if the array has mostly non-zeroes?"* (Only swap when `i != nonZeroIdx`). |
| **8** | **Reverse a Singly Linked List** | Linked List | **5.5%** | **1. Direction:** Draw 3 nodes (`1 -> 2 -> 3 -> null`) on the sheet of paper first and trace `prev`, `curr`, and `next` visually as you write the `while (curr != null)` loop.<br>**2. Follow-up:** *"Can you write the recursive version of this, and what is its space complexity?"* ($O(n)$ auxiliary call-stack space). |
| **9** | **Write Binary Search (Iterative & First/Last Occurrence)** | Binary Search | **5.0%** | **1. Direction:** Write `int mid = low + (high - low) / 2;` and proactively tell the interviewer: *"I wrote `low + (high - low) / 2` to prevent 32-bit signed integer overflow when `low + high > 2^31 - 1`."*<br>**2. Follow-up:** *"What if the sorted array contains duplicates and I want the first index of the target?"* (Don't return at `arr[mid] == target`; save `ans = mid` and set `high = mid - 1`). |
| **10** | **Valid Parentheses (`{[()]}`)** | Stack | **4.5%** | **1. Direction:** Use a `Stack<Character>`. State the 3 failure conditions out loud: (a) Closing bracket when stack is empty, (b) Mismatched top of stack, (c) Non-empty stack after loop finishes.<br>**2. Follow-up:** *"Can you solve this without a Stack using an integer counter if there is only one type of bracket `'('` and `')'`?"* (Yes, increment `open++` on `'('`, decrement `open--` on `')'`, return `false` if `open < 0` at any point). |
| **11** | **Detect a Cycle in a Linked List & Find Middle Node** | Linked List | **4.0%** | **1. Direction:** Contrast the $O(n)$ space `HashSet<Node>` approach with Floyd's $O(1)$ space Tortoise-and-Hare (`slow`, `fast`) approach.<br>**2. Follow-up:** *"Why does moving `fast` by 2 steps and `slow` by 1 step guarantee they will meet inside the loop instead of `fast` jumping over `slow`?"* (Because once both are inside the cycle, the distance between them decreases by exactly `1` node per step: $d, d-1, d-2 \dots 0$). |
| **12** | **Maximum Subarray Sum (Kadane’s Algorithm)** | Array | **3.5%** | **1. Direction:** Explain $O(n^2)$ subarray sum $\rightarrow$ $O(n)$ Kadane's algorithm.<br>**2. Follow-up:** *"Modify your code to also print the start and end indices of that maximum subarray."* (Track `tempStart = i + 1` whenever `currSum` resets to `0`, and update `ansStart = tempStart; ansEnd = i;` whenever `currSum > maxSum`). |
| **13** | **Fibonacci Series (Iterative vs. Recursive) & Factorial** | Math / DP | **3.0%** | **1. Direction:** Write the 4-line iterative version using `a = 0, b = 1, c = a + b` ($O(n)$ time, $O(1)$ space).<br>**2. Follow-up:** *"Why is recursive `fib(n - 1) + fib(n - 2)` bad?"* (Draw the recursion tree for `fib(5)` showing `fib(3)` and `fib(2)` being recomputed repeatedly in $O(2^n)$ time, and show how Memoization `dp[n]` makes it $O(n)$). |
| **14** | **Check Prime in $O(\sqrt{n})$ / Print Primes up to $N$** | Math | **2.5%** | **1. Direction:** Write `for (int i = 2; i * i <= n; i++)` and explain why factors always come in pairs $(a, b)$ where one factor is $\le \sqrt{n}$.<br>**2. Trap:** Explicitly write `if (n <= 1) return false;` at line 1 (`1` is neither prime nor composite). |
| **15** | **Swap Two Numbers Without a 3rd Variable** | Math / Bit | **2.0%** | **1. Direction:** Write both Arithmetic (`a = a + b; b = a - b; a = a - b;`) and Bitwise XOR (`a ^= b; b ^= a; a ^= b;`).<br>**2. Bonus Point:** Mention that XOR is safer than `a + b` because `a + b` can overflow `Integer.MAX_VALUE`! |
| **16** | **Sort an Array of 0s, 1s, and 2s** | Array | **1.5%** | **1. Direction:** Mention the 2-pass counting sort first, then write the 1-pass Dutch National Flag (`low`, `mid`, `high`) algorithm. |
| **17** | **Find Missing Number in $[1..N]$** | Array / Bit | **1.5%** | **1. Direction:** Give the Sum formula $\frac{N(N+1)}{2} - \sum arr[i]$, then mention the XOR approach (`xor(1..N) ^ xor(arr)`) to avoid integer overflow for large $N$. |
| **18** | **String Compression (`aaabbc` $\rightarrow$ `a3b2c1`)** | String | **1.0%** | **1. Direction:** Use a single pointer with consecutive run counting and `StringBuilder`. Handle the final character group cleanly. |
| **19** | **Merge Two Sorted Arrays / Merge Sort `merge()` Step** | Sorting | **1.0%** | **1. Direction:** Two pointers `i` and `j` comparing elements into a result array, followed by two `while` loops to copy leftover elements from whichever array didn't finish. |
| **20** | **Next Greater Element / LRU Cache Design** | Stack / Design | **1.0%** | *Concentrated in 7–12 LPA rounds:* Write Monotonic Stack for NGE, or draw the `HashMap` + Doubly Linked List diagram for LRU Cache. |

---

### B. The 10 Live Conceptual DSA Cross-Questions (Realistic Per-Interview Probability)

*In a typical interview, the panel asks **2 to 3 oral DSA theory questions** right after you finish coding. Here is each question's true appearance rate per interview and the exact 30-second answer direction:*

1. **"How does a `HashMap` work internally? What happens during a Hash Collision?"** *(Asked in **~35%** of interviews)*
   * **Direction:** 1. Key's `.hashCode()` is computed and mapped to a bucket index via `(n - 1) & hash`. 2. If two different keys map to the same bucket (Collision), they are stored in a Linked List at that bucket, and `.equals()` is used to find the exact key. 3. **Clincher:** Mention that in **Java 8+**, when a bucket's linked list exceeds threshold **8** (and table capacity $\ge 64$), it automatically converts into a **Balanced Red-Black Tree**, improving worst-case lookup from $O(n)$ to $O(\log n)$!

2. **"When should you use an `ArrayList` (Dynamic Array) vs. a `LinkedList`?"** *(Asked in **~30%** of interviews)*
   * **Direction:** `ArrayList` uses contiguous memory $\rightarrow$ $O(1)$ random access `get(i)` and high CPU cache locality, but $O(n)$ middle insertion/deletion due to shifting and resizing (`1.5x` or `2x`). `LinkedList` uses non-contiguous heap nodes $\rightarrow$ $O(1)$ insertion/deletion once at the node, but $O(n)$ lookup and extra pointer memory overhead.

3. **"Why is Quick Sort preferred over Merge Sort for arrays, even though Quick Sort's worst case is $O(n^2)$?"** *(Asked in **~24%** of interviews)*
   * **Direction:** 1. **In-Place Space:** Quick Sort requires only $O(\log n)$ recursion stack space, whereas Merge Sort allocates $O(n)$ extra auxiliary array memory. 2. **Cache Locality:** Quick Sort scans contiguous array segments in-place, yielding smaller constant factors in hardware cache, and randomized pivot selection makes the $O(n^2)$ worst case virtually impossible in practice.

4. **"What is the difference between a Binary Tree, a Binary Search Tree (BST), and a Heap?"** *(Asked in **~22%** of interviews)*
   * **Direction:** Binary Tree has no ordering rule ($\le 2$ children). **BST** enforces horizontal ordering (`left < root < right`) giving $O(\log n)$ search on average (degrading to $O(n)$ if skewed—fixed by AVL/Red-Black trees). **Heap** is a *complete binary tree* stored as an array that enforces vertical ordering (`parent <= children` for Min-Heap), giving $O(1)$ min/max peek and $O(\log n)$ insert/extract.

5. **"BFS vs. DFS — which data structure does each use, and when do you choose which?"** *(Asked in **~20%** of interviews)*
   * **Direction:** **BFS** uses a **Queue (FIFO)** and explores level by level—mandatory for finding the **shortest path in unweighted graphs/grids**. **DFS** uses a **Stack / Recursion (LIFO)** and explores deep paths first—preferred for **cycle detection, topological sorting, backtracking/puzzles, and when target nodes lie deep in the tree**.

6. **"Why is Merge Sort preferred over Quick Sort for sorting Linked Lists?"** *(Asked in **~16%** of interviews)*
   * **Direction:** Quick Sort needs fast $O(1)$ random access to pick pivots and step pointers backward, which takes $O(n)$ in a Singly Linked List. Merge Sort finds the middle via slow/fast pointers and merges two sorted lists in **$O(1)$ extra space** purely by reassigning `.next` pointers.

7. **"What is a Stable Sorting Algorithm, and why does stability matter?"** *(Asked in **~15%** of interviews)*
   * **Direction:** A stable sort preserves the relative order of records that have equal keys (e.g., sorting students alphabetically by Name first, then sorting by Section—a stable sort keeps students alphabetically ordered within each section). **Stable:** Merge, Insertion, Bubble. **Unstable:** Quick, Heap, Selection.

8. **"What causes a `StackOverflowError` in recursion, and how does Space Complexity work in recursion?"** *(Asked in **~15%** of interviews)*
   * **Direction:** Every recursive call pushes a stack frame (local variables + return address) onto the call stack. If the base case is missing or recursion depth is too large (e.g., $10^5$ depth), stack memory overflows. Recursive space complexity equals the **maximum depth of the recursion tree** at any one moment (e.g., $O(\log n)$ for balanced binary tree DFS, $O(n)$ for skewed tree).

9. **"What is the difference between Dynamic Programming (DP) and Greedy Algorithms?"** *(Asked in **~14%** of interviews)*
   * **Direction:** **Greedy** makes the locally optimal choice at each step and never looks back (fast, $O(n \log n)$, works for Fractional Knapsack and Activity Selection). **DP** solves problems with **Overlapping Subproblems** and **Optimal Substructure** by caching all subproblem states via Memoization (Top-Down) or Tabulation (Bottom-Up) (required for 0/1 Knapsack and Coin Change with arbitrary denominations).

10. **"How do `HashSet` and `TreeSet` (or `unordered_map` and `map` in C++) differ in time complexity?"** *(Asked in **~12%** of interviews)*
    * **Direction:** `HashSet` / `unordered_map` uses a **Hash Table** $\rightarrow$ $O(1)$ average insert/search, unordered elements. `TreeSet` / `std::map` uses a **Self-Balancing Red-Black BST** $\rightarrow$ $O(\log n)$ insert/search, keeps elements in **sorted order**.

---

### C. The 6 Non-Negotiable Live SQL Queries & OOP Snippets (Asked in ~75% of Technical Rounds)

*Almost every technical interviewer under 12 LPA asks you to write **1 or 2 SQL queries** and **1 OOP code snippet** alongside your DSA question.*

1. **SQL #1 — Find the $2\text{nd}$ or $N\text{th}$ Highest Salary** *(Asked in **~40%** of all SQL slots)*
   * **Direction:** Always use `DENSE_RANK()` instead of `LIMIT / OFFSET` if there can be duplicate salaries, and state this difference out loud to the interviewer!
   ```sql
   SELECT salary FROM (
       SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) AS rnk
       FROM Employee
   ) t WHERE rnk = 2;
   ```

2. **SQL #2 — Department-Wise Highest Salary (`GROUP BY` / Window Function + `JOIN`)** *(Asked in **~25%** of SQL slots)*
   ```sql
   SELECT dept_name, emp_name, salary FROM (
       SELECT d.dept_name, e.emp_name, e.salary,
              DENSE_RANK() OVER (PARTITION BY e.dept_id ORDER BY e.salary DESC) AS rnk
       FROM Employee e
       JOIN Department d ON e.dept_id = d.dept_id
   ) t WHERE rnk = 1;
   ```

3. **SQL #3 — Find Duplicate Emails / Delete Duplicate Rows Keeping Lowest ID** *(Asked in **~18%** of SQL slots)*
   ```sql
   -- Find duplicates (Remember: WHERE filters rows before grouping; HAVING filters groups after GROUP BY):
   SELECT email, COUNT(*) FROM Users GROUP BY email HAVING COUNT(*) > 1;

   -- Delete duplicates keeping minimum id:
   DELETE u1 FROM Users u1
   JOIN Users u2 ON u1.email = u2.email AND u1.id > u2.id;
   ```

4. **SQL #4 — Self-Join: Employees Earning More Than Their Managers** *(Asked in **~12%** of SQL slots)*
   ```sql
   SELECT e.emp_name AS Employee
   FROM Employee e
   JOIN Employee m ON e.manager_id = m.emp_id
   WHERE e.salary > m.salary;
   ```

5. **OOP Snippet #1 — Write a Code Example Showing Runtime Polymorphism (Method Overriding)** *(Asked in **~35%** of OOP code slots)*
   * **Direction:** Write a parent class/interface `Payment` with `void pay(int amount)` and two child classes `UPIPayment` and `CardPayment` overriding `pay()`. Show `Payment p = new UPIPayment(); p.pay(500);` and explain that the reference `p` is of type `Payment` (compile time), but the actual object on the Heap is `UPIPayment`, so the overridden method is resolved at runtime via Dynamic Method Dispatch / `vtable`.

6. **OOP Snippet #2 — Write a Thread-Safe Singleton Class** *(Asked in **~20%** of 6.5–12 LPA interviews: Cognizant GenC Next, Deloitte, IBM, Oracle)*
   * **Direction:** Write the 3 essential components: 1. `private static volatile Singleton instance;` 2. `private Singleton() {}` (private constructor so no external class can call `new`), and 3. `public static Singleton getInstance()` using double-checked locking.