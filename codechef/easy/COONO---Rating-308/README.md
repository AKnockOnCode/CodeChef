# COONO - Rating 308

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### ScoreBoard

A game has two rounds. A player scores $A$ points in the first round and $B$ points in the second round. The scoreboard displays $C$ as the total score.

Determine whether the displayed total is correct.

### Input Format
- The first line contains an integer $T$, the number of test cases.
- Each test case contains three space-separated integers $A$, $B$, and $C$.
### Output Format

For each test case, print `YES` if the displayed total is correct, or `NO` otherwise, on a separate line.

You may print the answer in any combination of uppercase and lowercase letters.

### Constraints
- $1 \le T \le 100$
- $0 \le A, B, C \le 100$
### Sample 1:
Input
Output

```
4
12 8 20
7 6 12
0 15 15
50 60 100
```

```
YES
NO
YES
NO
```

### Explanation:
- Test case $1$: The total score is $12+8=20$, matching the scoreboard.
- Test case $2$: The total score is $7+6=13$, but the scoreboard displays $12$.
- Test case $3$: The total score is $0+15=15$, matching the scoreboard.
- Test case $4$: The total score is $50+60=110$, but the scoreboard displays $100$.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-11-03T15:40:25.258Z  

```c_cpp
#include <stdio.h>

int main() {
    int T;
    scanf("%d", & T);
    while (T--) {
        int A, B, C;
        scanf("%d %d %d", & A, & B, & C);
        if (A + B == C) {
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

[View on CodeChef](https://www.codechef.com/problems/COONO)