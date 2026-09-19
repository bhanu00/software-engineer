# DSA (Data Structures, Algorithms and Problem Solving)

A structured, easy-to-hard learning schedule for interview preparation. Follow the phases in order — each phase builds on the previous one.

---

## Before You Start

> Good warm-up resources before writing a single line of code.

- [Google India Engineers in a Mock Coding Interview](https://www.youtube.com/watch?v=21pmwl0hrME)
- [How I mastered DSA – Ashish (Article)](https://blog.algomaster.io/p/how-i-mastered-data-structures-and-algorithms)
- [How I mastered DSA – Ashish (Video)](https://www.youtube.com/watch?v=F-ao3Q6I2Fc)
- [How to start LeetCode](https://www.youtube.com/watch?v=Nx4bvwU0DqE)

---

## Language Prerequisites (C#)

Make sure you are comfortable with these before diving into DSA.

- [Learn C# – Microsoft Docs](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/)
- Program Structure, Data Types, User Input/Output
- Conditional Statements (if/else, switch)
- Loops (for, while)
- Methods / Functions, Parameter passing (by value / by reference)

---

## Phase 1 — Foundations (Easy)

> Understand how code runs in memory and master the two most-used data structures.

| # | File | What you will learn |
|---|------|---------------------|
| 1 | [`code-execution.md`](./code-execution.md) | Stack vs Heap, how .NET allocates memory — essential mental model before any DS |
| 2 | [`array.md`](./array.md) | Fixed-size, contiguous memory, O(1) access, traversal, basic operations |
| 3 | [`strings.md`](./strings.md) | Immutability, char arrays, string operations, interview-focused string problems |
| 4 | [`linked-list.md`](./linked-list.md) | Node structure, singly/doubly lists, traversal, insertion, deletion |
| 5 | [`recursion.md`](./recursion.md) | Call stack, base case, recursive case — prerequisite for trees, backtracking, DP |

**Complexity check-in:**
- [Time and Space Complexity – Strivers A2Z](https://www.youtube.com/watch?v=FPu9Uld7W-E)
- [Understanding Algorithmic Complexity](https://blog.algomaster.io/p/57bd4963-462f-4294-a972-4012691fc729)

---

## Phase 2 — Core Patterns (Easy → Medium)

> These patterns solve ~60% of array and string interview problems. Learn them in this order.

| # | File | Pattern | When to use |
|---|------|---------|-------------|
| 1 | [`pattern2-reversal.md`](./pattern2-reversal.md) | Reversal on arrays | Rotating arrays in-place, O(n) time O(1) space |
| 2 | [`reversal-techniques.md`](./reversal-techniques.md) | Reversal on strings, numbers, linked lists | Reverse words in sentence, integer reversal |
| 3 | [`pattern4-prefix-sum.md`](./pattern4-prefix-sum.md) | Prefix Sum | Subarray sum queries in O(1) after O(n) preprocessing |
| 4 | [`string-array-sub-problems.md`](./string-array-sub-problems.md) | Substring / Subsequence / Subarray | Understanding contiguous vs non-contiguous problems |
| 5 | [`pattern1-two-pointer-and-sliding-window.md`](./pattern1-two-pointer-and-sliding-window.md) | Two Pointers + Sliding Window | Pair sum, longest subarray/substring with condition |
| 6 | [`pattern3-expand-around-center.md`](./pattern3-expand-around-center.md) | Expand Around Center | Palindrome counting, longest palindromic substring |
| 7 | [`pattern5-floyd's-cycle-detection.md`](./pattern5-floyd's-cycle-detection.md) | Floyd's Cycle Detection (Fast & Slow Pointers) | Detecting cycles in linked lists |

---

## Phase 3 — Data Structures (Medium)

> Build intuition for hierarchical and priority-based structures.

| # | File | What you will learn |
|---|------|---------------------|
| 1 | [`tree-basic-to-advanced.md`](./tree-basic-to-advanced.md) | Binary trees, BST, traversals (inorder/preorder/postorder), tree DP |
| 2 | [`heap-priority-queue.md`](./heap-priority-queue.md) | Min/Max heap, PriorityQueue in C#, top-K problems, median of stream |

---

## Phase 4 — Graph Algorithms (Medium → Hard)

> Graphs are trees with cycles. DFS/BFS are the backbone of all graph problems.

| # | File | What you will learn |
|---|------|---------------------|
| 1 | [`dfs-algo.md`](./dfs-algo.md) | DFS on trees and graphs, path finding, cycle detection, backtracking base |
| 2 | [`greedy-algo.md`](./greedy-algo.md) | Locally optimal choices, coin change, interval scheduling, when greedy works |

---

## Phase 5 — Advanced Algorithms (Hard)

> These require strong foundations in patterns, recursion, and graphs.

| # | File | What you will learn |
|---|------|---------------------|
| 1 | [`dynamic-programming.md`](./dynamic-programming.md) | Overlapping subproblems, optimal substructure, top-down (memo) and bottom-up (tabulation), 0/1 knapsack, LCS, grid DP |
| 2 | [`bit-manipulation.md`](./bit-manipulation.md) | Binary operations, XOR tricks, bitmask DP, character-level bit tricks |
| 3 | [`naive-string-match-algo.md`](./naive-string-match-algo.md) | Brute-force O(n×m) pattern matching — the baseline to understand KMP |
| 4 | [`knuth-morris-pratt-algo.md`](./knuth-morris-pratt-algo.md) | KMP linear-time pattern matching, LPS array — used in advanced string problems |

---

## Phase 6 — Pattern Consolidation

> A map of all problem-solving patterns in one place. Come back here after completing Phases 1–5.

| # | File | What you will learn |
|---|------|---------------------|
| 1 | [`problem-solving-patterns.md`](./problem-solving-patterns.md) | All patterns indexed — sliding window, BFS/DFS, monotonic stack, topological sort, backtracking, Kadane's, binary search variants |

---

## Practice Resources

| Resource | Link |
|----------|------|
| Striver's A2Z DSA Sheet | [takeuforward.org](https://takeuforward.org/strivers-a2z-dsa-course/strivers-a2z-dsa-course-sheet-2) |
| Love Babbar 450 Problems | [geeksforgeeks.org](https://www.geeksforgeeks.org/dsa-sheet-by-love-babbar/) |
| Ashish's LeetCode Resources | [github.com/ashishps1](https://github.com/ashishps1/awesome-leetcode-resources?tab=readme-ov-file) |
| William Fiset – DS Playlist | [YouTube](https://www.youtube.com/playlist?list=PLDV1Zeh2NRsB6SWUrDFW2RmDotAfPbeHu) |
| Algorithms Playlist | [YouTube](https://www.youtube.com/watch?v=aGjL7YXI31Q&list=PLEbnTDJUr_IeHYw_sfBOJ6gk5pie0yP-0) |
| GFG – Introduction to Algorithms | [geeksforgeeks.org](https://www.geeksforgeeks.org/introduction-to-algorithms/?ref=roadmap) |

---

## Quick Pattern Cheat-Sheet

| Pattern | Trigger phrase in problem |
|---------|--------------------------|
| Two Pointers | sorted array, pair sum, remove duplicates |
| Sliding Window | longest/shortest subarray, substring with condition |
| Prefix Sum | range sum query, subarray sum equals k |
| Reversal | rotate array/string, reverse words |
| Fast & Slow Pointers | cycle detection, middle of list |
| Expand Around Center | palindrome substring |
| DFS / Backtracking | all combinations, permutations, path exists |
| BFS | shortest path, level-order, nearest node |
| Heap | top-K, median stream, scheduling |
| Greedy | interval problems, minimum coins, always-pick-best |
| DP | count ways, min/max cost, subsequences |
| Bit Manipulation | XOR, unique element, subset enumeration |
| KMP / String Match | find pattern in text, multiple matches |

---

> **Disclaimer:** All linked content belongs to their respective owners.
