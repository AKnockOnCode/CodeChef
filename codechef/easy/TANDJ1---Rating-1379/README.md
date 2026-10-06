# TANDJ1 - Rating 1379

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Tom And Jerry 1

There is a grid of size $10^5 \times 10^5$, covered completely in railway tracks. Tom is riding in a train, currently in cell $(a, b)$, and Jerry is tied up in a different cell $(c, d)$, unable to move. The train has no brakes. It shall move exactly $K$ steps, and then its fuel will run out and it shall stop. In one step, the train must move to one of its neighboring cells, sharing a side. Tom can’t move without the train, as the grid is covered in tracks. Can Tom reach Jerry’s cell after exactly $K$ steps?

 **Note:**  Tom can go back to the same cell multiple times.

### Input Format
- The first line contains an integer $T$, the number of test cases. Then the test cases follow.
- Each test case contains a single line of input, five integers $a, b, c, d, K$.
### Output Format

For each testcase, output in a single line "YES" if Tom can reach Jerry's cell in exactly $K$ moves and "NO" if not.

You may print each character of the string in uppercase or lowercase (for example, the strings "yEs", "yes", "Yes" and "YES" will all be treated as identical).

### Constraints
- $1 \leq T \leq 10^5$
- $0 \leq a, b, c, d \leq 10^5$
- $(a, b) \ne (c, d)$
- $1 \leq K \leq 2 \cdot 10^5$
### Subtasks

 **Subtask #1 (100 points):**  original constraints

### Sample 1:
Input
Output

```
3
1 1 2 2 2
1 1 2 3 4
1 1 1 0 3
```

```
YES
NO
YES
```

### Explanation:

 **Test Case $1$:**  A possible sequence of moves is $(1, 1) \to (1, 2) \to (2, 2)$.

 **Test Case $2$:**  There is a possible sequence in $3$ moves, but not in exactly $4$ moves.

 **Test Case $3$:**  A possible sequence of moves is $(1, 1) \to (1, 0) \to (0, 0) \to (1, 0)$.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-10-06T09:37:44.111Z  

```c_cpp
#include <stdio.h>

#include <math.h>

int main() {
    int T;
    scanf("%d", & T);
    while (T--) {
        int a, b, c, d, k;
        scanf("%d %d %d %d %d", & a, & b, & c, & d, & k);
        int steps = abs(a - c) + abs(b - d);
        if (steps > k || (k-steps) % 2 == 1) {
            printf("NO\n");
        }
        else {
            printf("YES\n");
        }
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/TANDJ1)