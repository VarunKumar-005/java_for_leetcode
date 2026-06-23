# Binary Search — Interview & CP Cheat Sheet

---

## What Is Binary Search?

> A **divide-and-conquer** search algorithm that repeatedly halves the search space.
> Works **only on sorted arrays**. Time: `O(log n)` | Space: `O(1)`

---

## Core Template (Iterative)

```java
int left  = 0;
int right = nums.length - 1;
int mid   = 0;

while (left <= right) {
    mid = left + (right - left) / 2;   // ✅ Safe mid (avoids overflow)

    if (nums[mid] == target) {
        return mid;                    // 🎯 Target found
    } else if (nums[mid] < target) {
        left = mid + 1;                // 🔼 Search RIGHT half
    } else {
        right = mid - 1;               // 🔽 Search LEFT half
    }
}

return -1;                             // ❌ Target not found
```

---

## Line-by-Line Breakdown

| Line | Code | What It Does |
|------|------|--------------|
| 1 | `int left = 0` | Points to the **start** of the search space |
| 2 | `int right = nums.length - 1` | Points to the **end** of the search space |
| 3 | `while (left <= right)` | Runs as long as a **valid search window exists** |
| 4 | `mid = left + (right - left) / 2` | Finds **midpoint safely** (no integer overflow) |
| 5 | `nums[mid] == target` | Direct **hit** — return index immediately |
| 6 | `nums[mid] < target` | Mid is too **small** → move left pointer right |
| 7 | `nums[mid] > target` | Mid is too **large** → move right pointer left |
| 8 | `return -1` | Search space exhausted — target **doesn't exist** |

---

## Why `left + (right - left) / 2` and NOT `(left + right) / 2`?

```
❌ (left + right) / 2
   → If left = 1_000_000_000 and right = 2_000_000_000
   → left + right = 3_000_000_000 → INTEGER OVERFLOW 💥

✅ left + (right - left) / 2
   → (right - left) is always ≤ array length → SAFE ✅
```

---

## Loop Condition: `left <= right` vs `left < right`

| Condition | Use When |
|-----------|----------|
| `left <= right` | Searching for **exact match** (standard binary search) |
| `left < right` | Searching for a **boundary** (lower/upper bound variants) |

---

## Termination Guarantee

Each iteration, the search space shrinks by **at least half**:
- `left = mid + 1` → eliminates left half
- `right = mid - 1` → eliminates right half

For `n` elements → at most **⌊log₂n⌋ + 1** iterations. Loop always terminates.

---

## Common Variants (Know These for Interviews)

### 1. Lower Bound — First position where `nums[i] >= target`
```java
int left = 0, right = nums.length;
while (left < right) {
    int mid = left + (right - left) / 2;
    if (nums[mid] < target) left = mid + 1;
    else right = mid;
}
return left; // first index >= target
```

### 2. Upper Bound — First position where `nums[i] > target`
```java
int left = 0, right = nums.length;
while (left < right) {
    int mid = left + (right - left) / 2;
    if (nums[mid] <= target) left = mid + 1;
    else right = mid;
}
return left; // first index > target
```

### 3. Search in Rotated Sorted Array
```java
// Check which half is sorted, then decide where target lies
if (nums[left] <= nums[mid]) {          // LEFT half is sorted
    if (nums[left] <= target && target < nums[mid])
        right = mid - 1;
    else
        left = mid + 1;
} else {                                // RIGHT half is sorted
    if (nums[mid] < target && target <= nums[right])
        left = mid + 1;
    else
        right = mid - 1;
}
```

### 4. Binary Search on Answer (CP Favorite)
```java
// When you're minimizing/maximizing a value with a feasibility check
int left = minPossible, right = maxPossible;
while (left < right) {
    int mid = left + (right - left) / 2;
    if (isFeasible(mid)) right = mid;   // try smaller
    else left = mid + 1;
}
return left;
```

---

## Complexity Summary

| Case | Time | Reason |
|------|------|--------|
| Best | `O(1)` | Target is at mid on first check |
| Average | `O(log n)` | Halving each step |
| Worst | `O(log n)` | Target at boundary or absent |
| Space | `O(1)` | No extra data structures |

---

## Must-Know LeetCode Problems

| # | Problem | Pattern |
|---|---------|---------|
| 704 | Binary Search | Classic template |
| 35 | Search Insert Position | Lower bound |
| 34 | First and Last Position | Lower + Upper bound |
| 153 | Find Minimum in Rotated Array | Rotated array |
| 33 | Search in Rotated Sorted Array | Rotated array |
| 74 | Search a 2D Matrix | Flatten + Binary Search |
| 875 | Koko Eating Bananas | Binary search on answer |
| 1011 | Capacity to Ship Packages | Binary search on answer |
| 4 | Median of Two Sorted Arrays | Hard — partition-based BS |

---

## Quick Interview Checklist

```
Before coding Binary Search, ask yourself:
  [ ] Is the array sorted? (or can search space be sorted?)
  [ ] Am I searching for exact value or a boundary?
  [ ] Using left <= right (exact) or left < right (boundary)?
  [ ] Using safe mid formula: left + (right - left) / 2 ?
  [ ] What does return -1 or return left mean in context?
```

---

## One-Line Summary to Recall

> *"Eliminate half the search space each step by comparing mid to target — always use safe mid to avoid overflow."*

---
*Template: Standard Iterative Binary Search | Language: Java*
