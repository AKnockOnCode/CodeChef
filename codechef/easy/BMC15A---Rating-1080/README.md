# BMC15A - Rating 1080

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Practice problem - Apples and oranges

Rushitote went to a programming contest to distribute apples and oranges to the contestants.
He has $N$ apples and $M$ oranges, which need to be divided  **equally**  amongst the contestants. Find the maximum possible number of contestants such that:

- Every contestant gets an equal number of apples; and
- Every contestant gets an equal number of oranges.

Note that every fruit with Rushitote  *must*  be distributed, there cannot be any left over.

For example, $2$ apples and $4$ oranges can be distributed equally to two contestants, where each one receives $1$ apple and $2$ oranges.
However, $2$ apples and $5$ oranges can only be distributed equally to one contestant.

### Input Format
- The first line of input will contain a single integer $T$, denoting the number of test cases.
- The first and only line of each test case contains two space-separated integers $N$ and $M$ — the number of apples and oranges, respectively.
### Output Format

For each test case, output on a new line the answer: the maximum number of contestants such that everyone receives an equal number of apples and an equal number of oranges.

### Constraints
- $1 \leq T \leq 1000$
- $1 \leq N, M \leq 10^9$
### Sample 1:
Input
Output

```
3
1 5
2 4
4 6
```

```
1
2
2
```

### Explanation:

 **Test case $1$:**  There's only one apple, so distributing to more than one person is impossible.

 **Test case $2$:**  As explained in the statement, $2$ people can each receive $1$ apple and $2$ oranges.

 **Test case $3$:**  $2$ people can each receive $2$ apples and $3$ oranges. It's not possible to distribute equally to more than two people.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-11-11T19:25:48.563Z  

```c_cpp
#include <stdio.h>

int gcd(int a, int b) {
    if (a == 0) {
        return b;
    }
    else if (b == 0) {
        return a;
    }
    else {
        gcd(b, a % b);
    }
}

int main() {
    int T;
    scanf("%d", & T);
    while (T--) {
        int N, M;
        scanf("%d %d", & N, & M);
        printf("%d\n", gcd(N, M));
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/BMC15A)