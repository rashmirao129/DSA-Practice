
# Java If-Else

**Platform:** HackerRank  
**Track:** Java  
**Category:** Introduction  
**Problem:** [Java If-Else](https://www.hackerrank.com/challenges/java-if-else/problem)

## Problem Overview

The objective is to determine whether a given integer N is Weird or Not Weird based on four conditions.

### Conditions

1. If N is odd, print `Weird`.
2. If N is even and in the inclusive range of 2 to 5, print `Not Weird`.
3. If N is even and in the inclusive range of 6 to 20, print `Weird`.
4. If N is even and greater than 20, print `Not Weird`.

## Sample Input

```text
3
```

## Sample Output

```text
Weird
```

## Solution Approach

1. Import the required Java packages.
2. Create a Scanner object to read standard input.
3. Read the integer N using `nextInt()`.
4. Check whether N is odd using the modulus operator `%`.
5. Use `if`, `else if`, and `else` statements to evaluate the remaining conditions.
6. Print either `Weird` or `Not Weird` according to the applicable condition.

## Java Solution

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int N = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        if (N % 2 != 0) {
            System.out.println("Weird");
        }
        else if (N >= 2 && N <= 5) {
            System.out.println("Not Weird");
        }
        else if (N >= 6 && N <= 20) {
            System.out.println("Weird");
        }
        else {
            System.out.println("Not Weird");
        }

        scanner.close();
    }
}
```

## Dry Run

Consider the input:

```text
8
```

| Condition | Evaluation | Result |
|---|---|---|
| `N % 2 != 0` | 8 % 2 != 0 | False |
| `N >= 2 && N <= 5` | 8 is between 2 and 5 | False |
| `N >= 6 && N <= 20` | 8 is between 6 and 20 | True |

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
| 6 | Weird |
| 20 | Weird |
| 21 | Weird |
| 22 | Not Weird |
| 100 | Not Weird |

## Complexity Analysis

- **Time Complexity:** O(1) — a fixed number of conditional checks are performed.
- **Auxiliary Space:** O(1) — only a fixed amount of additional memory is used.

## Concepts Learned

- Conditional statements (`if`, `else if`, `else`)
- Odd and even numbers
- Modulus operator (`%`)
- Comparison operators (`>=`, `<=`, `!=`)
- Logical AND operator (`&&`)
- Boolean expressions
- Decision-making in Java
- Scanner class and standard input
