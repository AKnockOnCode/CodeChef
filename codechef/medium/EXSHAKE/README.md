# EXSHAKE

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

### Exun Handshake

$N$ groups of participants are trying to reach the annual Exun symposium. Group $i$ has $A_i$ people.

By tradition, everyone at the symposium shakes hands with everyone else exactly once as a sign of sportsmanship, whether they are from the same group or not. So if $P$ people attend in total, there are $\frac{P(P-1)}{2}$ handshakes.

The ceremony takes a long time, and the organisers only have time for $M$ handshakes. They will invite some of the groups (a group comes in full or not at all) so that the total number of handshakes is at most $M$.

Find the maximum number of groups that can be invited.

Inviting no groups at all is allowed, and gives $0$ handshakes.

### Input Format
- The first line of input contains a single integer $T$, denoting the number of test cases.
- Each test case consists of two lines of input. The first line of each test case contains two space-separated integers $N$ and $M$. The second line contains $N$ space-separated integers $A_1, A_2, \ldots, A_N$.
### Output Format

For each test case, output on a new line the maximum number of groups that can be invited.

### Constraints
- $1 \leq T \leq 100$
- $1 \leq N \leq 100$
- $0 \leq M \leq 10^8$
- $1 \leq A_i \leq 100$
### Sample 1:
Input
Output

```
4
4 10
3 1 4 2
3 0
2 5 3
5 45
2 2 2 2 2
3 0
4 1 1

```

```
2
0
5
1
```

### Explanation:

Test case $1$: Inviting the groups with $1$ and $2$ people gives $3$ people and $\frac{3 \cdot 2}{2} = 3$ handshakes. Any $3$ groups bring at least $1 + 2 + 3 = 6$ people, which means at least $15 > 10$ handshakes.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-10-21T14:36:30.299Z  

```c_cpp
#include <stdio.h>
#include <stdlib.h>
int compare(const void *a, const void *b) {
    int x = *(const int *)a;
    int y = *(const int *)b;
    return (x > y) - (x < y); 
}
int main() {
    int T;
    scanf("%d", &T);
    while (T--) {
    int N, M;
    scanf("%d %d", &N, &M);
    int i;
    int arr[N];
    for (i=0;i<N;i++){
        scanf("%d", &arr[i]);
    }
    qsort(arr, N, sizeof(int), compare);
    int sum = 0, group = 0;
    for (i=0;i<N;i++){
        sum += arr[i];
        if ((sum*(sum-1)/2)<=M){
            group++;
        }
        else{
            break;
        }
    }
    printf("%d\n", group);
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/EXSHAKE)