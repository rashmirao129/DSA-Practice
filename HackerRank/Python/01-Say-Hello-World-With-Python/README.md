
# Say Hello, World! With Python

**Platform:** HackerRank  
**Track:** Python  
**Category:** Introduction  
**Problem:** [Say Hello, World! With Python](https://www.hackerrank.com/challenges/py-hello-world/problem)

## Problem Overview

The objective is to write a Python program that prints the message `Hello, World!` to standard output (stdout).

No input is required for this challenge.

## Expected Output

```text
Hello, World!
```

## Solution Approach

1. Use the `print()` built-in function to display output.
2. Pass the string `"Hello, World!"` as an argument to `print()`.
3. Use the `if __name__ == '__main__':` condition as the program's entry-point guard.
4. Execute the print statement when the Python file is run directly.

## Python Solution

```python
if __name__ == '__main__':
    print("Hello, World!")
```

## Alternative Solution Using a Variable

```python
if __name__ == '__main__':
    my_string = "Hello, World!"
    print(my_string)
```

## Output

```text
Hello, World!
```

## Complexity Analysis

- **Time Complexity:** O(1) — one fixed message is printed.
- **Auxiliary Space:** O(1) — a fixed amount of additional memory is used.

## Concepts Learned

- Python `print()` function
- Strings and quotation marks
- Variables and assignment
- Standard Output (stdout)
- Conditional statements (`if`)
- Equality comparison operator (`==`)
- Special variable `__name__`
- Main module guard (`if __name__ == '__main__':`)
- Python indentation
