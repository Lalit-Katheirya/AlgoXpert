# AlgoXpert
This repository contains JavaScript based examples of many popular algorithms and data structures.
# Algorithms Explorer

**A complete interactive algorithms reference with editable JavaScript, live visualizations, and complexity analysis.**

Open `algorithms-explorer.html` in any modern browser to explore, edit, and run every algorithm.

---

## Table of Contents

1. [How to Use](#how-to-use)
2. [Math](#math)
3. [Sets](#sets)
4. [Strings](#strings)
5. [Searches](#searches)
6. [Sorting](#sorting)
7. [Graphs](#graphs)
8. [Trees](#trees)
9. [Cryptography](#cryptography)
10. [Uncategorized](#uncategorized)
11. [Algorithm Paradigms](#algorithm-paradigms)
12. [Complexity Cheat Sheet](#complexity-cheat-sheet)

---

## How to Use

1. Open `algorithms-explorer.html` in Chrome / Firefox / Edge.
2. Select a **category** from the left sidebar.
3. Click an **algorithm chip** at the top.
4. Read the **definition**, **complexity**, and **description**.
5. Edit the **JavaScript code** on the right.
6. Click **Run / Apply** (or **Animate** for Sorting & Searching).
7. Use **Restore** to reset the original code, **Copy** to copy it.

---

## Math

### Bit Manipulation

**Definition:** Techniques that operate directly on the binary representation of numbers using bitwise operators (`&`, `|`, `^`, `~`, `<<`, `>>`).

| Operation | Code | Meaning |
|-----------|------|---------|
| Get bit | `(n >> i) & 1` | Read the i-th bit |
| Set bit | `n \| (1 << i)` | Turn the i-th bit ON |
| Clear bit | `n & ~(1 << i)` | Turn the i-th bit OFF |
| Multiply by 2 | `n << 1` | Left shift |
| Divide by 2 | `n >> 1` | Right shift |
| Make negative | `~n + 1` | Two’s complement |

**Complexity:** Time O(1) · Space O(1)

**Example:**
```js
getBit(0b1010, 1)  // → 1
setBit(0b1000, 1)  // → 0b1010 (10)
mul2(5)            // → 10
```

---

### Factorial

**Definition:** `n! = n × (n-1) × … × 1`. The product of all positive integers ≤ n.

**Complexity:** Time O(n) · Space O(1)

**Example:**
```
5! = 5 × 4 × 3 × 2 × 1 = 120
```

---

### Fibonacci Number

**Definition:** Sequence where each number is the sum of the two preceding ones:  
`F(0)=0, F(1)=1, F(n)=F(n-1)+F(n-2)`.

**Complexity:**  
- Iterative / DP → Time O(n) · Space O(1)  
- Closed-form (Binet) → Time O(1) (approximate for large n)

**Example:**
```
F(10) = 55
Sequence: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55
```

---

### Prime Factors

**Definition:** The prime numbers that multiply together to give the original number.

**Complexity:** Time O(√n) · Space O(log n)

**Example:**
```
84 = 2 × 2 × 3 × 7
primeFactors(84) → [2, 2, 3, 7]
```

---

### Primality Test (Trial Division)

**Definition:** Determine whether a number is prime by checking divisibility from 2 up to √n.

**Complexity:** Time O(√n) · Space O(1)

**Example:**
```
isPrime(17) → true
isPrime(15) → false
```

---

### Euclidean Algorithm (GCD)

**Definition:** Greatest Common Divisor of two integers — the largest positive integer that divides both without remainder.  
Based on: `GCD(a, b) = GCD(b, a % b)`.

**Complexity:** Time O(log min(a,b)) · Space O(1)

**Example:**
```
GCD(48, 18) = 6
```

---

### Least Common Multiple (LCM)

**Definition:** Smallest positive integer divisible by both numbers.  
Formula: `LCM(a,b) = |a × b| / GCD(a,b)`.

**Complexity:** Time O(log min(a,b)) · Space O(1)

**Example:**
```
LCM(12, 18) = 36
```

---

### Sieve of Eratosthenes

**Definition:** Efficient algorithm to find **all prime numbers** up to a given limit n by iteratively marking multiples of each prime.

**Complexity:** Time O(n log log n) · Space O(n)

**Example:**
```
sieve(30) → [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
```

---

### Is Power of Two

**Definition:** Check if a number can be expressed as 2^k.  
Bitwise trick: `n > 0 && (n & (n-1)) === 0`.

**Complexity:** Time O(1) · Space O(1)

**Example:**
```
isPowerOfTwo(16) → true   // 2^4
isPowerOfTwo(18) → false
```

---

### Pascal’s Triangle

**Definition:** Triangular array where each number is the sum of the two numbers directly above it.  
Row n contains the binomial coefficients C(n,0) … C(n,n).

**Complexity:** Time O(n²) · Space O(n²)

**Example:**
```
Row 0: 1
Row 1: 1 1
Row 2: 1 2 1
Row 3: 1 3 3 1
Row 4: 1 4 6 4 1
```

---

### Fast Powering (Exponentiation by Squaring)

**Definition:** Compute base^exp in logarithmic time by repeatedly squaring.

**Complexity:** Time O(log exp) · Space O(1)

**Example:**
```
fastPow(2, 10) → 1024
fastPow(3, 5)  → 243
```

---

### Horner’s Method

**Definition:** Efficient way to evaluate a polynomial:  
`a₀ + a₁x + a₂x² + … = a₀ + x(a₁ + x(a₂ + …))`.

**Complexity:** Time O(n) · Space O(1)

**Example:**
```
Polynomial: 2x³ + 3x² + 5  at x=2
horner([5, 0, 3, 2], 2) → 33
```

---

### Euclidean Distance

**Definition:** Straight-line distance between two points in Euclidean space:  
`√(Σ(aᵢ − bᵢ)²)`.

**Complexity:** Time O(d) · Space O(1) (d = dimensions)

**Example:**
```
euclideanDistance([0,0], [3,4]) → 5
```

---

## Sets

### Cartesian Product

**Definition:** All ordered pairs (a, b) where a ∈ A and b ∈ B.

**Complexity:** Time O(|A| × |B|) · Space O(|A| × |B|)

**Example:**
```
A = [1,2], B = ['a','b']
→ [[1,'a'], [1,'b'], [2,'a'], [2,'b']]
```

---

### Fisher–Yates Shuffle

**Definition:** Algorithm that generates a uniform random permutation of a finite sequence (in-place).

**Complexity:** Time O(n) · Space O(1)

**Example:**
```
fisherYates([1,2,3,4,5]) → e.g. [3,1,5,2,4]
```

---

### Power Set

**Definition:** The set of **all subsets** of a given set (including empty set and itself).  
Size of power set = 2ⁿ.

**Complexity:** Time O(2ⁿ) · Space O(2ⁿ)

**Example:**
```
powerSet([1,2,3]) →
[[], [1], [2], [1,2], [3], [1,3], [2,3], [1,2,3]]
```

---

### Permutations

**Definition:** All possible **orderings** of a set of elements (without repetitions).  
Number of permutations of n distinct items = n!.

**Complexity:** Time O(n!) · Space O(n!)

**Example:**
```
permutations([1,2,3]) →
[[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
```

---

### Combinations

**Definition:** All ways to choose k elements from n elements where **order does not matter**.  
Number = C(n,k) = n! / (k!(n-k)!).

**Complexity:** Time O(C(n,k)) · Space O(C(n,k))

**Example:**
```
combinations([1,2,3,4], 2) →
[[1,2],[1,3],[1,4],[2,3],[2,4],[3,4]]
```

---

### Longest Common Subsequence (LCS)

**Definition:** The longest sequence that appears in both strings **in the same order** (not necessarily contiguous).

**Complexity:** Time O(m×n) · Space O(m×n)

**Example:**
```
LCS("ABCDGH", "AEDFHR") → 3  (sequence "ADH")
```

---

### Maximum Subarray (Kadane’s Algorithm)

**Definition:** Find the contiguous subarray within a 1-D array that has the largest sum.

**Complexity:** Time O(n) · Space O(1)

**Example:**
```
[-2, 1, -3, 4, -1, 2, 1, -5, 4]
Maximum subarray = [4, -1, 2, 1] → sum = 6
```

---

### 0/1 Knapsack

**Definition:** Given items with weights and values, maximize total value without exceeding capacity W. Each item can be taken **at most once**.

**Complexity:** Time O(n×W) · Space O(n×W)

**Example:**
```
weights = [1,3,4,5], values = [1,4,5,7], W = 7
Maximum value = 9  (items with weight 3 and 4)
```

---

## Strings

### Hamming Distance

**Definition:** Number of positions at which two strings of **equal length** differ.

**Complexity:** Time O(n) · Space O(1)

**Example:**
```
hammingDistance("karolin", "kathrin") → 3
hammingDistance("10110", "11100")     → 2
```

---

### Palindrome Check

**Definition:** A string that reads the same forwards and backwards (ignoring case and non-alphanumeric characters).

**Complexity:** Time O(n) · Space O(1)

**Example:**
```
isPalindrome("A man a plan a canal Panama") → true
isPalindrome("hello") → false
```

---

### Levenshtein Distance (Edit Distance)

**Definition:** Minimum number of single-character edits (insertions, deletions, or substitutions) required to change one string into another.

**Complexity:** Time O(m×n) · Space O(m×n)

**Example:**
```
levenshtein("kitten", "sitting") → 3
(kitten → sitten → sittin → sitting)
```

---

### Knuth–Morris–Pratt (KMP) Algorithm

**Definition:** Efficient substring search that uses a precomputed Longest Proper Prefix which is also Suffix (LPS) array to avoid re-examining characters.

**Complexity:** Time O(n + m) · Space O(m)

**Example:**
```
KMP("ababcababa", "aba") → [0, 5, 7]
```

---

### Rabin–Karp Algorithm

**Definition:** Substring search that uses a **rolling hash** to quickly compare the pattern with substrings of the text.

**Complexity:** Average O(n + m) · Worst O(n×m) · Space O(1)

**Example:**
```
rabinKarp("abracadabra", "abra") → [0, 7]
```

---

## Searches

### Linear Search

**Definition:** Sequentially check each element until the target is found or the list ends. Works on **unsorted** data.

| Case | Complexity |
|------|------------|
| Best | O(1) |
| Average | O(n) |
| Worst | O(n) |
| Space | O(1) |

**Example:**
```
Array: [4, 2, 7, 1, 9]
Search 7 → found at index 2
```

---

### Binary Search

**Definition:** Requires a **sorted** array. Repeatedly divide the search interval in half.

| Case | Complexity |
|------|------------|
| Best | O(1) |
| Average / Worst | O(log n) |
| Space | O(1) |

**Example:**
```
Sorted: [1, 3, 5, 7, 9, 11]
Search 7 → mid comparisons → found at index 3
```

---

### Jump Search (Block Search)

**Definition:** Jump ahead by fixed steps of size √n, then perform linear search in the identified block. Requires sorted array.

**Complexity:** Time O(√n) · Space O(1)

---

### Interpolation Search

**Definition:** Improved binary search for **uniformly distributed** sorted arrays. Estimates the probable position of the target.

**Complexity:** Average O(log log n) · Worst O(n) · Space O(1)

---

## Sorting

### Bubble Sort

**Definition:** Repeatedly steps through the list, compares adjacent elements and swaps them if they are in the wrong order. Largest elements “bubble” to the end.

| Case | Complexity |
|------|------------|
| Best | O(n) (already sorted + early exit) |
| Average / Worst | O(n²) |
| Space | O(1) |

**Stable:** Yes

---

### Selection Sort

**Definition:** Find the minimum element in the unsorted portion and swap it with the first unsorted element. Repeat.

| Case | Complexity |
|------|------------|
| Best / Average / Worst | O(n²) |
| Space | O(1) |

**Stable:** No

---

### Insertion Sort

**Definition:** Build a sorted prefix one element at a time by inserting each new element into its correct position.

| Case | Complexity |
|------|------------|
| Best | O(n) (nearly sorted) |
| Average / Worst | O(n²) |
| Space | O(1) |

**Stable:** Yes · Excellent for small or nearly-sorted arrays.

---

### Merge Sort

**Definition:** Divide the array into two halves, recursively sort them, then merge the two sorted halves.

| Case | Complexity |
|------|------------|
| Best / Average / Worst | O(n log n) |
| Space | O(n) |

**Stable:** Yes · Guaranteed performance.

---

### Quick Sort

**Definition:** Pick a pivot, partition the array so smaller elements go left and larger go right, then recurse on both sides.

| Case | Complexity |
|------|------------|
| Best / Average | O(n log n) |
| Worst | O(n²) (already sorted + bad pivot) |
| Space | O(log n) |

**Stable:** No · Usually the fastest in practice.

---

### Heap Sort

**Definition:** Build a max-heap, repeatedly extract the maximum and place it at the end of the array.

| Case | Complexity |
|------|------------|
| Best / Average / Worst | O(n log n) |
| Space | O(1) |

**Stable:** No

---

### Counting Sort

**Definition:** Count occurrences of each distinct value, then reconstruct the sorted array. Efficient when the range of values (k) is small.

**Complexity:** Time O(n + k) · Space O(k)

**Stable:** Yes (with proper implementation)

---

### Radix Sort

**Definition:** Sort integers digit by digit starting from the least significant digit, using a stable sort (usually counting sort) for each digit.

**Complexity:** Time O(n × d) · Space O(n + k)  
(d = number of digits)

---

## Graphs

### Breadth-First Search (BFS)

**Definition:** Explore the graph **level by level** using a queue. Guarantees the shortest path in unweighted graphs.

**Complexity:** Time O(V + E) · Space O(V)

**Example order (start A):**
```
A → B, C → D → E
```

---

### Depth-First Search (DFS)

**Definition:** Explore as **deep as possible** along each branch before backtracking. Implemented with a stack or recursion.

**Complexity:** Time O(V + E) · Space O(V)

---

### Dijkstra’s Algorithm

**Definition:** Find the **shortest paths** from a single source vertex to all other vertices in a weighted graph with **non-negative** edge weights.

**Complexity:** Time O((V + E) log V) with binary heap · Space O(V)

---

### Bellman–Ford Algorithm

**Definition:** Compute shortest paths from a single source. Works with **negative** edge weights and can detect negative cycles.

**Complexity:** Time O(V × E) · Space O(V)

---

### Floyd–Warshall Algorithm

**Definition:** Find shortest paths between **all pairs** of vertices. Uses dynamic programming.

**Complexity:** Time O(V³) · Space O(V²)

---

### Kruskal’s Algorithm (MST)

**Definition:** Find a **Minimum Spanning Tree** by sorting all edges and adding them if they don’t form a cycle (Union-Find).

**Complexity:** Time O(E log E) · Space O(V)

---

### Topological Sort

**Definition:** Linear ordering of vertices in a **Directed Acyclic Graph (DAG)** such that for every edge u → v, u appears before v.

**Complexity:** Time O(V + E) · Space O(V)

---

## Trees

### Tree DFS (Preorder / Inorder / Postorder)

**Definition:**  
- **Preorder:** Root → Left → Right  
- **Inorder:** Left → Root → Right (gives sorted order for BST)  
- **Postorder:** Left → Right → Root  

**Complexity:** Time O(n) · Space O(h) (h = height)

---

### Tree BFS (Level-Order)

**Definition:** Visit nodes level by level from top to bottom using a queue.

**Complexity:** Time O(n) · Space O(n)

---

## Cryptography

### Caesar Cipher

**Definition:** Simple substitution cipher that shifts each letter by a fixed number of positions in the alphabet.

**Example:**
```
Encrypt("Hello", 3) → "Khoor"
Decrypt("Khoor", 3) → "Hello"
```

**Complexity:** Time O(n) · Space O(n)

---

### Rail Fence Cipher

**Definition:** Transposition cipher. Write the message in a zigzag pattern on a number of “rails”, then read row by row.

**Complexity:** Time O(n) · Space O(n)

---

### Polynomial Hash (Rolling Hash)

**Definition:** Hash function of the form  
`h = (c₀·bⁿ⁻¹ + c₁·bⁿ⁻² + … + cₙ₋₁) mod m`  
Used in Rabin–Karp and string matching.

**Complexity:** Time O(n) · Space O(1)

---

## Uncategorized

### Tower of Hanoi

**Definition:** Move n disks from peg A to peg C using auxiliary peg B. Rule: never place a larger disk on a smaller one.

**Complexity:** Time O(2ⁿ) · Space O(n)

**Moves for n=3:** 7 moves.

---

### Valid Parentheses

**Definition:** Check whether a string containing `()[]{}` is correctly matched and nested using a stack.

**Complexity:** Time O(n) · Space O(n)

**Example:**
```
"()[]{}" → true
"(]"     → false
"{[]}"   → true
```

---

### N-Queens Problem

**Definition:** Place n queens on an n×n chessboard so that no two queens attack each other (same row, column, or diagonal).

**Complexity:** Time O(n!) · Space O(n)

---

### Jump Game

**Definition:** Each element represents the maximum jump length from that position. Determine if you can reach the last index (greedy).

**Complexity:** Time O(n) · Space O(1)

---

### Best Time to Buy and Sell Stock

**Definition:** Given daily prices, find the maximum profit from a single buy and a single sell (one pass).

**Complexity:** Time O(n) · Space O(1)

**Example:**
```
prices = [7,1,5,3,6,4]
Buy at 1, sell at 6 → profit = 5
```

---

## Algorithm Paradigms

| Paradigm | Idea | Examples |
|----------|------|----------|
| **Brute Force** | Try all possibilities | Linear Search, Travelling Salesman |
| **Greedy** | Choose best option at each step | Dijkstra, Prim, Kruskal, Jump Game |
| **Divide & Conquer** | Break into sub-problems, solve, combine | Merge Sort, Quick Sort, Binary Search, GCD |
| **Dynamic Programming** | Build solution from smaller sub-solutions | Fibonacci, Knapsack, LCS, Floyd-Warshall |
| **Backtracking** | Build candidates and abandon as soon as invalid | N-Queens, Hamiltonian Cycle, Power Set |

---

## Complexity Cheat Sheet

| Notation | Name | Rough meaning (n = 10⁶) |
|----------|------|-------------------------|
| O(1) | Constant | Instant |
| O(log n) | Logarithmic | ~20 operations |
| O(n) | Linear | 1 million ops |
| O(n log n) | Linearithmic | ~20 million ops |
| O(n²) | Quadratic | 10¹² (too slow) |
| O(n³) | Cubic | Usually only for tiny n |
| O(2ⁿ) | Exponential | Only for n ≤ 20–25 |
| O(n!) | Factorial | Only for n ≤ 10–12 |

---

## File Structure

```
artifacts/
├── algorithms-explorer.html   ← Main interactive app (all algorithms)
├── algorithms-visualizer.html ← Older tabbed version (Sorting + Searching + Graph)
├── sorting-visualizer.html    ← Sorting only
├── searching-visualizer.html  ← Searching only
├── graph-visualizer.html      ← Graph BFS/DFS only
└── README.md                  ← This file
```

---

## Credits

Built as a pure client-side educational tool.  
No frameworks · No build step · Just open the HTML file and learn.

**Happy coding & happy learning!**
