
# Welcome to Java!

**Platform:** HackerRank  
**Track:** Java  
**Category:** Introduction  
**Problem:** [Welcome to Java!](https://www.hackerrank.com/challenges/welcome-to-java/problem)

## Problem Overview

The objective is to practice printing output to standard output (stdout) using Java.

Print the following two lines:

Hello, World.
Hello, Java.

## Solution Approach

1. Use `System.out.println()` to print a line.
2. Print the first message: `Hello, World.`
3. Print the second message: `Hello, Java.`

## Java Solution

```java
public class Solution {
    public static void main(String[] args) {
        System.out.println("Hello, World.");
        System.out.println("Hello, Java.");
    }
}
```

## Output

```text
Hello, World.
Hello, Java.
```

## Complexity Analysis

- **Time Complexity:** O(1) — a fixed number of statements are executed.
- **Auxiliary Space:** O(1) — no additional data structures are used.

## Concepts Learned

- Java class and main method
- `System.out`
- `println()`
- Standard output (stdout)
