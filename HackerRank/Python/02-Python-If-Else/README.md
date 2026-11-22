
# Python If-Else

**Platform:** HackerRank  
**Track:** Python  
**Category:** Introduction  
**Language:** Python 3 (PyPy 3)  
**Problem:** [Python If-Else](https://www.hackerrank.com/challenges/py-if-else/problem)

## Problem Overview

The objective is to determine whether a given positive integer `n` is Weird or Not Weird based on four conditions.

### Conditions

1. If `n` is odd, print `Weird`.
2. If `n` is even and in the inclusive range of 2 to 5, print `Not Weird`.
3. If `n` is even and in the inclusive range of 6 to 20, print `Weird`.
4. If `n` is even and greater than 20, print `Not Weird`.

## Sample Input 0

```text
3
```

## Sample Output 0

```text
Weird
```

## Sample Input 1

```text
24
```

## Sample Output 1

```text
Not Weird
```

## Solution Approach

1. Read the input using Python's `input()` function.
2. Convert the input string into an integer using `int()`.
3. Use the modulus operator `%` to determine whether the number is odd or even.
4. Use `if`, `elif`, and `else` conditional statements to evaluate the four rules.
5. Use chained comparisons to check whether the number falls within the required ranges.
6. Print `Weird` or `Not Weird` according to the applicable condition.

## Python Solution

```python
#!/bin/python3

import math
import os
import random
import re
import sys

if __name__ == '__main__':
    n = int(input().strip())

    if n % 2 != 0:
        print("Weird")
    elif 2 <= n <= 5:
        print("Not Weird")
    elif 6 <= n <= 20:
        print("Weird")
    else:
        print("Not Weird")
```

## Dry Run

Consider the input:

```text
8
```

| Condition | Evaluation | Result |
|---|---|---|
| `n % 2 != 0` | `8 % 2 != 0` | False |
| `2 <= n <= 5` | `2 <= 8 <= 5` | False |
| `6 <= n <= 20` | `6 <= 8 <= 20` | True |

The third condition is satisfied.

Output:

```text
Weird
```

## Additional Test Cases

| Input | Expected Output |
|---:|---|
| 3 | Weird |
| 4 | Not Weird |
| 5 | Not Weird |
| 6 | Weird |
| 20 | Weird |
| 21 | Weird |
| 22 | Not Weird |
| 24 | Not Weird |
| 100 | Not Weird |

## Complexity Analysis

- **Time Complexity:** O(1) — a fixed number of conditional checks are performed.
- **Auxiliary Space:** O(1) — a fixed amount of additional memory is used.

## Concepts Learned

- Python input using `input()`
- Type conversion using `int()`
- String method `strip()`
- Conditional statements (`if`, `elif`, `else`)
- Modulus operator (`%`)
- Comparison operators (`==`, `!=`, `>=`, `<=`)
- Logical operators
- Chained comparisons
- Boolean expressions
- Python indentation
- Main module guard (`if __name__ == '__main__':`)
