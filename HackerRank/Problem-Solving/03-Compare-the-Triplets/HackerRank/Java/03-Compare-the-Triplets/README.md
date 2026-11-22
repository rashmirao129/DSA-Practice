
# Compare the Triplets

- **Platform:** HackerRank
- **Language:** Java
- **Difficulty:** Easy
- **Category:** Algorithms – Warm-up
- **Problem Link:** https://www.hackerrank.com/challenges/compare-the-triplets/problem

## 1. Problem Goal

Compare Alice's and Bob's ratings across three categories.

- If Alice's rating is greater, Alice receives one point.
- If Bob's rating is greater, Bob receives one point.
- If both ratings are equal, neither receives a point.

Return both scores in a list.

## 2. Approach

1. Initialize Alice's and Bob's scores to zero.
2. Iterate through the three rating positions.
3. Compare Alice's and Bob's ratings at each position.
4. Increase the appropriate score.
5. Store both scores in an ArrayList.
6. Return the result list.

## 3. Java Solution

```java
int aliceScore = 0;
int bobScore = 0;

for (int i = 0; i < 3; i++) {

    if (a.get(i) > b.get(i)) {
        aliceScore++;
    }
    else if (a.get(i) < b.get(i)) {
        bobScore++;
    }
}

List<Integer> result = new ArrayList<>();

result.add(aliceScore);
result.add(bobScore);

return result;
```

## 4. Sample Input

```text
5 6 7
3 6 10
```

## 5. Sample Output

```text
1 1
```

## 6. Explanation

Comparison 1: 5 > 3, Alice gets one point.

Comparison 2: 6 = 6, nobody gets a point.

Comparison 3: 7 < 10, Bob gets one point.

Final scores: Alice = 1, Bob = 1.

## 7. Complexity Analysis

- **Time Complexity:** O(1)
- **Auxiliary Space:** O(1)

Exactly three comparisons are performed. The two scores and result list have fixed sizes.

## 8. Concepts Learned

- Java ArrayList
- List<Integer>
- for loops
- if and else-if conditions
- Comparison operators
- Increment operator (++ )
- Returning a list from a method
- Time and auxiliary space complexity
