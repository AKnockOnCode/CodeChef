# VALIDMIN - Rating 1132

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Valid Minimum

There are $3$ hidden numbers $A, B, C$.

You somehow found out the values of $\min(A, B), \min(B, C),$ and $\min(C, A)$.

Determine whether there exists any tuple $(A, B, C)$ that satisfies the given values of $\min(A, B), \min(B, C), \min(C, A)$.

### Input Format
- The first line of input will contain a single integer $T$, denoting the number of test cases.
- The first and only line of each test case contains $3$ space-separated integers denoting the values of $\min(A, B), \min(B, C),$ and $\min(C, A)$.
### Output Format

For each test case, output `YES` if there exists any valid tuple $(A, B, C)$, and `NO` otherwise.

You can print each letter of the output in any case. For example `YES`, `yes`, `yEs` will all be considered equivalent.

### Constraints
- $1 \leq T \leq 1000$
- $1 \leq min(A, B), min(B, C), min(C, A) \leq 10$
### Sample 1:
Input
Output

```
3
5 5 5
2 3 4
2 2 4

```

```
YES
NO
YES

```

### Explanation:

 **Test case $1$:**  One valid tuple $(A, B, C)$ is $(5, 5, 5)$.

 **Test case $2$:**  It can be shown that there is no valid tuple $(A, B, C)$.

 **Test case $3$:**  One valid tuple $(A, B, C)$ is $(4, 2, 5)$.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-09-08T06:03:21.454Z  

```c_cpp
#include <stdio.h>

int main() {
    int T;
    scanf("%d", &T);
    while (T--) {
    int A, B, C;
    scanf("%d %d %d", &A, &B, &C);
    if (A<=B && A==C){
        printf("Yes\n");
    }
    else if (B==A && B<=C){
        printf("Yes\n");
    }
    else if (C<=A && C==B){
        printf("Yes\n");
    }
    else {
        printf("No\n");
    }
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/VALIDMIN)