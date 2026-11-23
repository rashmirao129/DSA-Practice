
# 0014. Longest Common Prefix

**Platform:** LeetCode  
**Problem Number:** 14  
**Difficulty:** Easy  
**Language:** Java  
**Topics:** String, Array  
**Approach:** Vertical Scanning  
**Problem:** [Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)

## Problem Overview

Given an array of strings, find the longest common prefix shared by all strings.

A prefix is a sequence of characters that appears at the beginning of a string.

If no common prefix exists, return an empty string.

## Example 1

**Input:**

```text
strs = ["flower", "flow", "flight"]
```

**Output:**

```text
"fl"
```

**Explanation:**

All three strings begin with the characters `f` and `l`.

The third character differs, so the longest common prefix is `"fl"`.

## Example 2

**Input:**

```text
strs = ["dog", "racecar", "car"]
```

**Output:**

```text
""
```

**Explanation:**

The first characters are different, so there is no common prefix.

## Approach 1: Vertical Scanning

Use the first string as a reference and compare its characters with the corresponding characters in every other string.

1. Check whether the input array is empty.
2. Traverse the first string character by character.
3. Store the current reference character.
4. Compare it with the character at the same index in all other strings.
5. Check whether another string has ended before accessing its character.
6. If a mismatch or shorter string is found, return the substring from index 0 up to the current index.
7. If no mismatch is found, return the first string.

## Java Solution

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {

        if (strs == null || strs.length == 0) {
            return "";
        }

        for (int i = 0; i < strs[0].length(); i++) {

            char currentChar = strs[0].charAt(i);

            for (int j = 1; j < strs.length; j++) {

                if (i >= strs[j].length() ||
                    strs[j].charAt(i) != currentChar) {

                    return strs[0].substring(0, i);
                }
            }
        }

        return strs[0];
    }
}
```

## Dry Run

**Input:**

```text
strs = ["flower", "flow", "flight"]
```

| Index | flower | flow | flight | Result |
|---:|:---:|:---:|:---:|---|
| 0 | f | f | f | Match |
| 1 | l | l | l | Match |
| 2 | o | o | i | Mismatch |

At index 2, a mismatch is detected.

The program returns:

```java
strs[0].substring(0, 2);
```

**Output:**

```text
"fl"
```

## Alternative Approach: Horizontal Scanning

Start with the first string as the prefix.

Compare it with each subsequent string and shorten the prefix until it matches the beginning of that string.

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {

        String prefix = strs[0];

        for (int i = 1; i < strs.length; i++) {

            while (!strs[i].startsWith(prefix)) {

                prefix = prefix.substring(0, prefix.length() - 1);

                if (prefix.isEmpty()) {
                    return "";
                }
            }
        }

        return prefix;
    }
}
```

## Important Java Concepts

- String arrays
- String indexing
- `length`
- `charAt()`
- `substring()`
- `startsWith()`
- Nested `for` loops
- Conditional statements
- Logical OR (`||`)
- String comparison
- Prefix matching

## Complexity Analysis

Let N represent the number of strings, M represent the shortest string length, and S represent the total number of characters across all strings.

- **Time Complexity:** O(N × M), bounded by O(S), for vertical scanning.
- **Auxiliary Space:** O(1), excluding the returned prefix.

## Concepts Learned

- Understanding common prefixes
- Comparing characters across multiple strings
- Vertical Scanning technique
- Horizontal Scanning technique
- Detecting mismatches
- Handling strings of different lengths
- Returning an empty string when no prefix exists
- Time and auxiliary space complexity
