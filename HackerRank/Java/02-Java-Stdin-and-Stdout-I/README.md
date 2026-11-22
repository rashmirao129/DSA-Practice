
# Java Stdin and Stdout I

**Platform:** HackerRank  
**Track:** Java  
**Category:** Introduction  
**Problem:** [Java Stdin and Stdout I](https://www.hackerrank.com/challenges/java-stdin-and-stdout-1/problem)

## Problem Overview

The objective is to read three integers from standard input (stdin) and print them to standard output (stdout).

Each integer must be printed on a separate line.

## Sample Input

```text
42
100
125
```

## Sample Output

```text
42
100
125
```

## Solution Approach

1. Import the Java utility package to access the Scanner class.
2. Create a Scanner object using `System.in` to read standard input.
3. Use `nextInt()` to read three integers.
4. Store the integers in variables `a`, `b`, and `c`.
5. Use `System.out.println()` to print each integer on a separate line.

## Java Solution

```java
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);

        int a = scan.nextInt();
        int b = scan.nextInt();
        int c = scan.nextInt();

        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
    }
}
```

## Dry Run

For the input:

```text
42
100
125
```

| Statement | Value stored |
|---|---:|
| `int a = scan.nextInt();` | 42 |
| `int b = scan.nextInt();` | 100 |
| `int c = scan.nextInt();` | 125 |

The program then prints each variable using `System.out.println()`.

## Complexity Analysis

- **Time Complexity:** O(1) — exactly three integers are read and printed.
- **Auxiliary Space:** O(1) — three integer variables and a Scanner object are used.

## Concepts Learned

- Standard Input (stdin)
- Standard Output (stdout)
- Java Scanner class
- Creating objects using `new`
- `System.in` and `System.out`
- `nextInt()` method
- `println()` method
- Integer variables and data types
