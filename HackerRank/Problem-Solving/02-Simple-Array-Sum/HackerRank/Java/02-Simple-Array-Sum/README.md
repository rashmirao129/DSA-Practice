
# Simple Array Sum

- **Platform:** HackerRank
- **Language:** Java
- **Difficulty:** Easy
- **Category:** Warm-up
- **Problem Link:** https://www.hackerrank.com/challenges/simple-array-sum/problem

## 1. Problem Goal

Given an array of integers, calculate the sum of all its elements and return the result.

## 2. Approach

1. Initialize a variable called sum with 0.
2. Traverse the array using a for-each loop.
3. Add each element to sum.
4. Return the final sum.

## 3. Java Solution

```java
public static int simpleArraySum(List<Integer> ar) {

    int sum = 0;

    for (int num : ar) {
        sum += num;
    }

    return sum;
}
```

## 4. Sample Input

```text
6
1 2 3 4 10 11
```

## 5. Sample Output

```text
31
```

## 6. Explanation

The array contains six elements:

1 + 2 + 3 + 4 + 10 + 11 = 31

Therefore, the returned sum is 31.

## 7. Complexity Analysis

- **Time Complexity:** O(n)
- **Auxiliary Space:** O(1)

We visit every element exactly once and use only a constant amount of additional memory.

## 8. Concepts Learned

- Java ArrayList
- List<Integer>
- For-each loop
- Array traversal
- Accumulator variable
- Return statements
- Time and auxiliary space complexity
