
# 0001. Two Sum

**Platform:** LeetCode  
**Problem Number:** 1  
**Difficulty:** Easy  
**Language:** Java  
**Approach:** Brute Force  
**Topics:** Array, Nested Loops  
**Problem:** [Two Sum – LeetCode](https://leetcode.com/problems/two-sum/)

## Problem Overview

Given an integer array `nums` and an integer `target`, find the indices of two distinct elements whose sum equals the target.

The same array element cannot be used twice.

The problem guarantees exactly one valid answer. The indices can be returned in any order.

## Example 1

**Input:**

```text
nums = [2, 7, 11, 15]
target = 9
```

**Output:**

```text
[0, 1]
```

**Explanation:**

The values at indices 0 and 1 are 2 and 7.

Since 2 + 7 = 9, return `[0, 1]`.

## Example 2

**Input:**

```text
nums = [3, 2, 4]
target = 6
```

**Output:**

```text
[1, 2]
```

**Explanation:**

The values at indices 1 and 2 are 2 and 4.

Since 2 + 4 = 6, return `[1, 2]`.

## Example 3

**Input:**

```text
nums = [3, 3]
target = 6
```

**Output:**

```text
[0, 1]
```

**Explanation:**

Both elements have the value 3 but exist at different indices.

Since 3 + 3 = 6, return `[0, 1]`.

## Approach 1: Brute Force

The Brute Force approach uses two nested `for` loops to compare every possible pair of elements.

### Solution Logic

1. Use the outer loop to select the first element.
2. Use the inner loop to select another element, starting from the next index.
3. Add the two selected elements.
4. Check whether their sum equals the target.
5. If the sum matches, return their indices.
6. If no matching pair is found, return an empty integer array.

### Java Solution

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        for (int i = 0; i < nums.length; i++) {

            for (int j = i + 1; j < nums.length; j++) {

                if (nums[i] + nums[j] == target) {
                    return new int[]{i, j};
                }
            }
        }

        return new int[0];
    }
}
```

## Understanding Important Java Statements

### 1. `nums.length`

Returns the number of elements in the array.

### 2. `j = i + 1`

Starts the inner loop from the next index to avoid using the same element twice.

### 3. `nums[i] + nums[j] == target`

Checks whether the sum of the two selected elements equals the target.

### 4. `return new int[]{i, j}`

Creates and returns a new integer array containing the two matching indices.

### 5. `return new int[0]`

Creates an empty integer array. This is a fallback return statement because the method must return an `int[]`.

## Dry Run

**Input:**

```text
nums = [2, 7, 11, 15]
target = 9
```

| i | j | nums[i] | nums[j] | Sum | Result |
|---:|---:|---:|---:|---:|---|
| 0 | 1 | 2 | 7 | 9 | Match found |

Since the sum equals the target, the program executes:

```java
return new int[]{0, 1};
```

**Output:**

```text
[0, 1]
```

## Complexity Analysis

- **Time Complexity:** O(n²) – two nested loops compare possible pairs of elements.
- **Auxiliary Space:** O(1) – no additional data structure is used. The returned array contains a fixed number of elements.

## Concepts Learned

- Java arrays
- Zero-based indexing
- Array traversal
- Nested `for` loops
- Conditional statements
- Returning integer arrays
- `new int[]{}` array initialization
- Brute Force problem-solving approach
- Time and auxiliary space complexity

## Optimization

The Brute Force approach takes O(n²) time.

An optimized solution using a HashMap can solve this problem in O(n) average time with O(n) auxiliary space.

The HashMap approach is maintained separately for comparison.
