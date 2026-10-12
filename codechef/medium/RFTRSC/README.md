# RFTRSC

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

### Rooftop Rescue

A hero must rescue a captive held in building $T$. He starts on the roof of building $S$ in a city with $N$ buildings, numbered from $1$ to $N$.

Only certain pairs of buildings are close enough for him to jump between. You are given $M$ such pairs. For each pair, the hero can jump  **in either direction**, and each jump takes him from one building to the other.

The hero may travel through other buildings to reach the captive. Find the  **minimum number of jumps**  he needs to reach building $T$.

If the destination cannot be reached, print $0$. If $S=T$, print $0$ because no jumps are needed.

### Input Format
- The first line contains two integers $N$ and $M$ — the number of buildings and the number of pairs between which a jump is possible.
- Each of the next $M$ lines contains two integers $U$ and $V$, indicating that the hero can jump between buildings $U$ and $V$.
- The last line contains two integers $S$ and $T$ — the starting building and the building where the captive is held.
### Output Format

Print the minimum number of jumps required to reach building $T$. If it is unreachable, print $0$.

### Constraints
- $1 \le N \le 3500$
- $1 \le M \le 10^6$
- $1 \le U,V,S,T \le N$
### Sample 1:
Input
Output

```
6 6
1 2
2 3
3 6
1 4
4 6
2 5
1 6
```

```
2
```

### Explanation:

The hero can jump from building $1$ to building $4$, then from building $4$ to building $6$.

This takes $2$ jumps. Since he cannot jump directly from building $1$ to building $6$, this is the minimum.

### Sample 2:
Input
Output

```
5 3
1 2
2 3
4 5
1 5
```

```
0
```

### Explanation:

From building $1$, the hero can reach buildings $2$ and $3$. Neither provides a route to buildings $4$ or $5$, so he cannot reach the captive.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-10-12T14:09:06.177Z  

```c_cpp
#include <stdio.h>

int main() {
    int T;
    scanf("%d", &T);
    while (T--) {
    int N;
    scanf("%d", &N);
    int i;
    int arr[N];
    for (i=0;i<N;i++){
        scanf("%d", &arr[i]);
    }
    
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/RFTRSC)