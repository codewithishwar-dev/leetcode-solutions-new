# 2914. Minimum Number of Changes to Make Binary String Beautiful

**Difficulty:** Medium  
**Topics:** Greedy, String  
**Language:** Java

## Problem

Given a binary string `s` of even length, return the minimum number of character changes required to make the string beautiful.

A beautiful string can be partitioned into substrings such that:
- Each substring has an even length.
- Each substring contains only `0`s or only `1`s.

[LeetCode Problem Link](https://leetcode.com/problems/minimum-number-of-changes-to-make-binary-string-beautiful/)

## Approach: Greedy

Since every valid substring must have an even length, we can divide the string into consecutive pairs.

For each pair:
- If both characters are identical (`00` or `11`), no changes are required.
- If the characters are different (`01` or `10`), exactly one change is required.

Count the mismatched pairs to get the minimum number of changes.

## Java Solution

```java
class Solution {
    public int minChanges(String s) {
        int changes = 0;

        for (int i = 0; i < s.length(); i += 2) {
            if (s.charAt(i) != s.charAt(i + 1)) {
                changes++;
            }
        }

        return changes;
    }
}
```

## Example

**Input:**
```text
s = "1001"
```

**Pair Processing:**
```text
10 | 01
```

Both pairs contain different characters, so one change is required for each pair.

**Output:**
```text
2
```

## Complexity Analysis

- **Time Complexity:** O(n) — Each pair is processed once.
- **Space Complexity:** O(1) — Only a counter is used.

## Key Takeaways

- Greedy algorithm.
- Fixed-size pair processing.
- String traversal.
- Identifying independent operations.
- Optimal linear-time solution.

**Pattern:** Greedy + String + Pair Processing
