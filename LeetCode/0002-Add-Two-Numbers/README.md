
# 0002. Add Two Numbers

**Platform:** LeetCode  
**Problem Number:** 2  
**Difficulty:** Medium  
**Language:** Java  
**Topics:** Linked List, Mathematics, Recursion (related concept)  
**Problem:** [Add Two Numbers – LeetCode](https://leetcode.com/problems/add-two-numbers/)

## Problem Overview

Given two non-empty linked lists representing two non-negative integers, add the numbers and return the sum as a new linked list.

Each linked-list node contains a single digit. The digits are stored in reverse order, meaning the head node contains the ones digit.

The result must also be returned in reverse order.

## Example 1

**Input:**

```text
l1 = [2, 4, 3]
l2 = [5, 6, 4]
```

**Explanation:**

The first linked list represents 342.

The second linked list represents 465.

342 + 465 = 807.

**Output:**

```text
[7, 0, 8]
```

## Example 2

**Input:**

```text
l1 = [0]
l2 = [0]
```

**Output:**

```text
[0]
```

## Example 3

**Input:**

```text
l1 = [9, 9, 9, 9, 9, 9, 9]
l2 = [9, 9, 9, 9]
```

**Explanation:**

9999999 + 9999 = 10009998.

The result is stored in reverse order.

**Output:**

```text
[8, 9, 9, 9, 0, 0, 0, 1]
```

## Solution Approach

Use an iterative linked-list traversal with carry handling.

1. Create a dummy node to serve as the starting point of the result list.
2. Maintain a `current` reference to track the last node in the result.
3. Initialise `carry` to 0.
4. Traverse both linked lists while at least one list has nodes remaining or a carry exists.
5. Start each addition with the carry from the previous iteration.
6. Add the current digit from each list, when available.
7. Calculate the result digit using `sum % 10`.
8. Calculate the next carry using `sum / 10`.
9. Create a new node containing the calculated digit.
10. Advance the current reference and the input-list references.
11. Return `dummy.next`, which points to the actual result list.

## Java Solution

```java
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {

        ListNode dummy = new ListNode(0);
        ListNode current = dummy;

        int carry = 0;

        while (l1 != null || l2 != null || carry != 0) {

            int sum = carry;

            if (l1 != null) {
                sum += l1.val;
                l1 = l1.next;
            }

            if (l2 != null) {
                sum += l2.val;
                l2 = l2.next;
            }

            int digit = sum % 10;
            carry = sum / 10;

            current.next = new ListNode(digit);
            current = current.next;
        }

        return dummy.next;
    }
}
```

## Dry Run

**Input:**

```text
l1 = [2, 4, 3]
l2 = [5, 6, 4]
```

The numbers represented are 342 and 465.

342 + 465 = 807.

| Iteration | l1 digit | l2 digit | Carry in | Sum | Result digit | Carry out |
|---:|---:|---:|---:|---:|---:|---:|
| 1 | 2 | 5 | 0 | 7 | 7 | 0 |
| 2 | 4 | 6 | 0 | 10 | 0 | 1 |
| 3 | 3 | 4 | 1 | 8 | 8 | 0 |

The result linked list is:

```text
7 → 0 → 8 → null
```

**Output:**

```text
[7, 0, 8]
```

## Important Java Concepts

### 1. ListNode

Represents an individual linked-list node containing a digit and a reference to the next node.

### 2. null

Indicates that a linked-list reference does not point to another node.

### 3. Dummy Node

A helper node that simplifies construction of the result linked list.

### 4. new ListNode(digit)

Creates a new node containing the calculated digit.

### 5. Carry

Stores the extra value generated when the sum of digits is greater than or equal to 10.

### 6. Modulus Operator (%)

Extracts the last digit of the sum.

### 7. Integer Division (/)

Calculates the carry using integer division.

### 8. dummy.next

Returns the actual result list, excluding the helper dummy node.

## Complexity Analysis

Let `m` and `n` represent the lengths of the two input linked lists.

- **Time Complexity:** O(max(m, n)) – each input node is visited once, with possible one additional carry iteration.
- **Auxiliary Space:** O(1) – a fixed number of extra variables and references are used, excluding the result list.
- **Output Space:** O(max(m, n) + 1) – the new linked list stores the sum digits.

## Concepts Learned

- Singly Linked Lists
- Node creation and constructors
- Linked-list traversal
- Node references and `next`
- Dummy nodes
- null checking
- Addition using carry
- Modulus operator
- Integer division
- Creating a new linked list
- Time and auxiliary space complexity
