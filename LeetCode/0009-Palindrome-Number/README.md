
# 0009. Palindrome Number

**Platform:** LeetCode  
**Problem Number:** 9  
**Difficulty:** Easy  
**Language:** Java  
**Topics:** Math, Number Manipulation  
**Problem:** [Palindrome Number](https://leetcode.com/problems/palindrome-number/)

## Problem Overview

Given an integer `x`, determine whether it is a palindrome.

A palindrome number reads the same from left to right and from right to left.

The solution returns `true` if the number is a palindrome and `false` otherwise.

## Examples

| Input | Output |
|---:|---|
| 121 | true |
| -121 | false |
| 10 | false |
| 1221 | true |
| 0 | true |

## Approach 1: String Conversion

Convert the integer into a String, reverse it using StringBuilder, and compare the reversed String with the original.

### Java Solution

```java id="5uofx6"
class Solution {
    public boolean isPalindrome(int x) {

        String original = Integer.toString(x);

        String reversed = new StringBuilder(original)
                              .reverse()
                              .toString();

        return original.equals(reversed);
    }
}
```

### Complexity Analysis

- **Time Complexity:** O(log₁₀ n) – the number of characters is proportional to the number of digits.
- **Auxiliary Space:** O(log₁₀ n) – additional String storage is used.

## Approach 2: Mathematical Half Reversal – Optimized

Reverse only half of the integer's digits and compare the two halves.

This approach avoids converting the integer into a String and prevents overflow from reversing the entire integer.

### Solution Approach

1. Return `false` for negative numbers.
2. Return `false` for non-zero numbers ending in zero.
3. Initialise `reversedHalf` to zero.
4. While `x` is greater than `reversedHalf`, extract the last digit using `% 10`.
5. Append the extracted digit to `reversedHalf`.
6. Remove the last digit from `x` using integer division by 10.
7. Compare the two halves.
8. For odd-length numbers, ignore the middle digit using `reversedHalf / 10`.

### Java Solution – Optimized

```java id="cr4wzm"
class Solution {
    public boolean isPalindrome(int x) {

        if (x < 0 || (x % 10 == 0 && x != 0)) {
            return false;
        }

        int reversedHalf = 0;

        while (x > reversedHalf) {

            int digit = x % 10;

            reversedHalf = reversedHalf * 10 + digit;

            x = x / 10;
        }

        return x == reversedHalf || x == reversedHalf / 10;
    }
}
```

## Dry Run

**Input:**

```text id="cxkhf8"
x = 121
```

| Iteration | x | Digit | Reversed Half | x After Division |
|---:|---:|---:|---:|---:|
| 1 | 121 | 1 | 1 | 12 |
| 2 | 12 | 2 | 12 | 1 |

The loop ends when `x` is no longer greater than `reversedHalf`.

Final comparison:

```text id="f0p3qq"
1 == 12 || 1 == 12 / 10
false || true
```

**Output:**

```text id="t8lcq5"
true
```

## Understanding Important Java Operators

| Operator | Purpose |
|---|---|
| `%` | Returns the remainder |
| `/` | Performs integer division when both operands are integers |
| `==` | Checks equality |
| `||` | Logical OR |
| `&&` | Logical AND |
| `!=` | Checks inequality |

## Important Edge Cases

| Input | Expected Output | Reason |
|---:|---|---|
| 0 | true | Zero is a palindrome |
| 7 | true | Single-digit number |
| 121 | true | Reads the same backwards |
| 1221 | true | Even-length palindrome |
| 12321 | true | Odd-length palindrome |
| -121 | false | Negative numbers are not palindromes |
| 10 | false | Non-zero numbers ending in zero cannot be palindromes |
| 123 | false | Reversed number is different |

## Complexity Analysis – Optimized Solution

- **Time Complexity:** O(log₁₀ n) – approximately half of the digits are processed.
- **Auxiliary Space:** O(1) – only a fixed number of integer variables are used.

## Concepts Learned

- Palindrome numbers
- Integer manipulation
- Number reversal
- Modulus operator (`%`)
- Integer division (`/`)
- While loops
- Conditional statements
- Logical operators
- StringBuilder and String reversal
- Integer overflow considerations
- Optimising number-based algorithms
