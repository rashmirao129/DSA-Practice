
# 0003. Longest Substring Without Repeating Characters

**Platform:** LeetCode  
**Problem Number:** 3  
**Difficulty:** Medium  
**Language:** Java  
**Approach:** Brute Force  
**Topics:** String, HashSet, Nested Loops  
**Problem:** [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

## Problem Overview

Given a string `s`, find the length of the longest substring that contains no duplicate characters.

A substring is a continuous sequence of characters from the original string.

The objective is to return the length of the longest valid substring, not the substring itself.

## Example 1

**Input:**

```text
s = "abcabcbb"
```

**Output:**

```text
3
```

**Explanation:**

The longest valid substrings include `"abc"`, `"bca"` and `"cab"`.

Each has a length of 3.

## Example 2

**Input:**

```text
s = "bbbbb"
```

**Output:**

```text
1
```

**Explanation:**

Every character is repeated. The longest valid substring is `"b"`.

## Example 3

**Input:**

```text
s = "pwwkew"
```

**Output:**

```text
3
```

**Explanation:**

One longest valid substring is `"wke"`.

It contains continuous, non-repeating characters.

`"pwke"` is a subsequence, not a substring, because some characters are skipped.

## Approach 1: Brute Force Using HashSet

The Brute Force approach checks possible substrings starting at every index.

A HashSet is used to track the characters already encountered in the current substring.

### Solution Logic

1. Initialise `maxLength` to 0.
2. Use an outer loop to select each starting index.
3. Create a new HashSet for each starting position.
4. Use an inner loop to examine subsequent characters.
5. Retrieve the current character using `s.charAt(j)`.
6. Check whether the character already exists in the HashSet.
7. If a duplicate is found, stop the inner loop using `break`.
8. Otherwise, add the character to the HashSet.
9. Calculate the current substring length using `j - i + 1`.
10. Update `maxLength` whenever a longer valid substring is found.
11. Return `maxLength` after checking all starting positions.

## Java Solution – Brute Force

```java
import java.util.HashSet;

class Solution {
    public int lengthOfLongestSubstring(String s) {

        int maxLength = 0;

        for (int i = 0; i < s.length(); i++) {

            HashSet<Character> set = new HashSet<>();

            for (int j = i; j < s.length(); j++) {

                char ch = s.charAt(j);

                if (set.contains(ch)) {
                    break;
                }

                set.add(ch);

                maxLength = Math.max(maxLength, j - i + 1);
            }
        }

        return maxLength;
    }
}
```

## Understanding Important Java Statements

### 1. HashSet

```java
HashSet<Character> set = new HashSet<>();
```

Creates a HashSet that stores unique characters.

### 2. charAt()

```java
char ch = s.charAt(j);
```

Retrieves the character at index `j`.

### 3. contains()

```java
set.contains(ch)
```

Checks whether the character already exists in the HashSet.

### 4. break

```java
break;
```

Terminates the inner loop when a duplicate character is found.

### 5. add()

```java
set.add(ch);
```

Adds the current character to the HashSet.

### 6. Math.max()

```java
maxLength = Math.max(maxLength, j - i + 1);
```

Returns the larger of the existing maximum length and the current substring length.

### 7. Substring Length

```java
j - i + 1
```

Calculates the length of the current substring.

The `+1` is necessary because both starting and ending indexes are included.

## Dry Run

**Input:**

```text
s = "abcabcbb"
```

Starting from index 0:

| Index i | Index j | Character | HashSet | Action |
|---:|---:|:---:|---|---|
| 0 | 0 | a | [a] | Add a |
| 0 | 1 | b | [a, b] | Add b |
| 0 | 2 | c | [a, b, c] | Add c |
| 0 | 3 | a | [a, b, c] | Duplicate found; break |

The first valid substring is `"abc"` with length 3.

The algorithm repeats this process from the remaining starting indexes.

The maximum length found is 3.

**Output:**

```text
3
```

## Complexity Analysis

- **Time Complexity:** O(n²) average – the outer loop considers every starting index, and the inner loop explores subsequent characters.
- **Auxiliary Space:** O(min(n, |Σ|)) – the HashSet stores unique characters, where n is the string length and |Σ| is the character-set size.

## Concepts Learned

- Java String
- String length using `length()`
- Character access using `charAt()`
- Substring versus subsequence
- HashSet and unique elements
- Nested for loops
- Duplicate detection using `contains()`
- Loop termination using `break`
- Math.max()
- Brute Force problem-solving approach
- Time and auxiliary space complexity

## Optimization

The Brute Force solution has O(n²) average time complexity.

An optimized solution using the Sliding Window technique and HashMap can solve this problem in O(n) average time.

The optimized solution will be documented separately in this problem's README.
