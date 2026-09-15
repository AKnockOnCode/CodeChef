# MISSINGNUM7 - Rating 151

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Missing Number

Chef had $4$ pieces of paper with him, one paper with $1$ written on it, one paper with $2$, one paper with $3$ and finally one paper with $4$.

Now, Chef lost one of the pieces of paper, and noticed that the other numbers on his papers add up to $S$. Find the number on the missing paper.

### Input Format
- The first and only line of input contains a single integer $S$.
### Output Format

Output the number on the missing paper.

### Constraints
- $6 \le S \le 9$
### Sample 1:
Input
Output

```
6

```

```
4

```

### Explanation:

Chef has the papers $1$, $2$ and $3$ with him; as they add up to $6$, so the missing has to be $4$.

### Sample 2:
Input
Output

```
9

```

```
1

```

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-09-15T05:54:32.143Z  

```c_cpp
#include <stdio.h>

int main() {
    int S;
    scanf("%d", &S);
    if (S==6)printf("4\n");
    else if (S==7)printf("3\n");
    else if (S==8)printf("2\n");
    else printf("1\n");
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/MISSINGNUM7)