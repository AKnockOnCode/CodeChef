# MXEVNSUB - Rating 1221

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Maximum Length Even Subarray

You are given an integer $N$. Consider the sequence containing the integers $1, 2, \ldots, N$ in increasing order (each exactly once). Find the maximum length of its contiguous subsequence with an even sum.

### Input Format
- The first line of the input contains a single integer $T$ denoting the number of test cases. The description of $T$ test cases follows.
- The first and only line of each test case contains a single integer $N$.
### Output Format

For each test case, print a single line containing one integer --- the maximum length of a contiguous subsequence with even sum.

### Constraints
- $1 \leq T \leq 10^4$
- $1 \leq N \leq 10^4$
### Subtasks

 **Subtask #1 (100 points):**  original constraints

### Sample 1:
Input
Output

```
3
3
4
5
```

```
3
4
4
```

### Explanation:

 **Example case 1:**  The optimal choice is to choose the entire sequence, since the sum of all its elements is $1 + 2 + 3 = 6$, which is even.

 **Example case 3:**  One of the optimal choices is to choose the subsequence $[1, 2, 3, 4]$, which has an even sum.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-10-04T11:19:56.079Z  

```c_cpp
#include <stdio.h>

int main() {
    int T;
    scanf("%d", & T);
    while (T--) {
        int N;
        scanf("%d", & N);
        int sum = N * (N + 1) / 2;
        if (sum % 2 == 0) {
            printf("%d\n", N);
        }
        else {
            printf("%d\n", N - 1);
        }
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/MXEVNSUB)