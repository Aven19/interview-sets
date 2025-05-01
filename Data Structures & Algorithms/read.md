
# 📚 Data Structures & Algorithms – Solved Interview Questions

This repository contains categorized and fully solved DSA problems commonly asked in technical interviews. Solutions are provided in Python for clarity and ease of understanding.

---

## 📌 Arrays & Strings

### 1. Reverse an Array
```python
def reverse_array(arr):
    return arr[::-1]
```

---

### 2. Longest Substring Without Repeating Characters
```python
def length_of_longest_substring(s):
    char_index = {}
    left = result = 0
    for right, char in enumerate(s):
        if char in char_index and char_index[char] >= left:
            left = char_index[char] + 1
        char_index[char] = right
        result = max(result, right - left + 1)
    return result
```

---

## 📌 Linked Lists

### 3. Detect Cycle in Linked List
```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def has_cycle(head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            return True
    return False
```

---

### 4. Reverse a Linked List
```python
def reverse_list(head):
    prev = None
    current = head
    while current:
        temp = current.next
        current.next = prev
        prev = current
        current = temp
    return prev
```

---

## 📌 Trees & Graphs

### 5. Maximum Depth of Binary Tree
```python
def max_depth(root):
    if not root:
        return 0
    return 1 + max(max_depth(root.left), max_depth(root.right))
```

---

### 6. DFS Traversal of a Graph
```python
def dfs(graph, node, visited=None):
    if visited is None:
        visited = set()
    visited.add(node)
    for neighbor in graph.get(node, []):
        if neighbor not in visited:
            dfs(graph, neighbor, visited)
    return visited
```

---

## 📌 Recursion & Backtracking

### 7. Factorial (Recursion)
```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n - 1)
```

---

### 8. N-Queens Problem (N = 4)
```python
def solve_n_queens(n):
    result = []
    board = [["."] * n for _ in range(n)]

    def is_safe(row, col):
        for i in range(row):
            if board[i][col] == "Q" or                (col - row + i >= 0 and board[i][col - row + i] == "Q") or                (col + row - i < n and board[i][col + row - i] == "Q"):
                return False
        return True

    def backtrack(row):
        if row == n:
            result.append(["".join(r) for r in board])
            return
        for col in range(n):
            if is_safe(row, col):
                board[row][col] = "Q"
                backtrack(row + 1)
                board[row][col] = "."

    backtrack(0)
    return result
```

---

## 📌 Dynamic Programming

### 9. Fibonacci (Memoization)
```python
def fib(n, memo={}):
    if n <= 1:
        return n
    if n not in memo:
        memo[n] = fib(n - 1, memo) + fib(n - 2, memo)
    return memo[n]
```

---

### 10. 0/1 Knapsack
```python
def knapsack(weights, values, W):
    n = len(weights)
    dp = [[0] * (W + 1) for _ in range(n + 1)]
    for i in range(1, n + 1):
        for w in range(W + 1):
            if weights[i - 1] <= w:
                dp[i][w] = max(dp[i - 1][w], values[i - 1] + dp[i - 1][w - weights[i - 1]])
            else:
                dp[i][w] = dp[i - 1][w]
    return dp[n][W]
```

---

## 📌 Searching & Sorting

### 11. Binary Search
```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

---

### 12. Merge Sort
```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)

def merge(left, right):
    result = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    result.extend(left[i:])
    result.extend(right[j:])
    return result
```

---

## 📌 Hashing & Heaps

### 13. Top K Frequent Elements
```python
from collections import Counter
import heapq

def top_k_frequent(nums, k):
    count = Counter(nums)
    return heapq.nlargest(k, count.keys(), key=count.get)
```

---

### 14. Implement Min Heap
```python
import heapq

min_heap = []
heapq.heappush(min_heap, 3)
heapq.heappush(min_heap, 1)
heapq.heappush(min_heap, 2)

print(heapq.heappop(min_heap))  # Output: 1
```

---

## 📌 Greedy Algorithms

### 15. Activity Selection Problem
```python
def activity_selection(activities):
    activities.sort(key=lambda x: x[1])
    count = 1
    last_end = activities[0][1]
    for start, end in activities[1:]:
        if start >= last_end:
            count += 1
            last_end = end
    return count
```

---

### 16. Fractional Knapsack
```python
def fractional_knapsack(weights, values, W):
    items = sorted(zip(weights, values), key=lambda x: x[1]/x[0], reverse=True)
    total_value = 0
    for w, v in items:
        if W == 0:
            break
        if w <= W:
            total_value += v
            W -= w
        else:
            total_value += v * (W / w)
            W = 0
    return total_value
```

---

## 📌 Sliding Window & Two Pointers

### 17. Maximum Sum Subarray of Size K
```python
def max_sum_subarray(arr, k):
    max_sum = window_sum = sum(arr[:k])
    for i in range(k, len(arr)):
        window_sum += arr[i] - arr[i - k]
        max_sum = max(max_sum, window_sum)
    return max_sum
```

---

### 18. Two Sum (Two Pointers)
```python
def two_sum_sorted(arr, target):
    left, right = 0, len(arr) - 1
    while left < right:
        current_sum = arr[left] + arr[right]
        if current_sum == target:
            return [left, right]
        elif current_sum < target:
            left += 1
        else:
            right -= 1
    return []
```

---

## ✅ Contribute

Feel free to fork this repo and add more solved problems! Pull requests are welcome.
