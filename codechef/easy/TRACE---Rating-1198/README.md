# TRACE - Rating 1198

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Trace of Matrix

Chef is learning linear algebra. Recently, he learnt that for a square matrix $M$, $\mathop{\rm trace}(M)$ is defined as the sum of all elements on the main diagonal of $M$ (an element lies on the main diagonal if its row index and column index are equal).

Now, Chef wants to solve some excercises related to this new quantity, so he wrote down a square matrix $A$ with size $N\times N$. A square  *submatrix*  of $A$ with size $l\times l$ is a contiguous block of $l\times l$ elements of $A$. Formally, if $B$ is a submatrix of $A$ with size $l\times l$, then there must be integers $r$ and $c$ ($1\le r, c \le N+1-l$) such that $B_{i,j} = A_{r+i-1, c+j-1}$ for each $1 \le i, j \le l$.

Help Chef find the maximum trace of a square submatrix of $A$.

### Input
- The first line of the input contains a single integer $T$ denoting the number of test cases. The description of $T$ test cases follows.
- The first line of each test case contains a single integer $N$.
- $N$ lines follow. For each $i$ ($1 \le i \le N$), the $i$-th of these lines contains $N$ space-separated integers $A_{i,1}, A_{i,2}, \dots, A_{i, N}$ denoting the $i$-th row of the matrix $A$.
### Output

For each test case, print a single line containing one integer — the maximum possible trace.

### Constraints
- $1 \le T \le 100$
- $2 \le N \le 100$
- $1 \le A_{i,j} \le 100$ for each valid $i, j$
### Subtasks

 **Subtask #1 (100 points):**  original constraints

### Sample 1:
Input
Output

```
1
3
1 2 5
6 3 4
2 7 1
```

```
13
```

### Explanation:

 **Example case 1:**  The submatrix with the largest trace is

```
6 3
2 7

```

which has trace equal to $6 + 7 = 13$. (This submatrix is obtained for $r=2, c=1, l=2$.)

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-09-08T16:32:19.929Z  

```c_cpp
#include <stdio.h>

int trace(int N, int arr[N][N], int i, int j){
    if (i>=N || j>=N)
    return 0;
    return arr[i][j] + trace(N, arr, i+1, j+1);
}

int main() {
    int T;
    scanf("%d", &T);
    while (T--) {
    int N, i, j;
    scanf("%d", &N);
    int arr[N][N];
    for (i=0;i<N;i++){
        for (j=0;j<N;j++){
        scanf("%d", &arr[i][j]);
    }}
    int max = arr[0][0];
    for (i=0;i<N;i++){
        for (j=0;j<N;j++){
            if (max<trace(N, arr, i, j)){
                max = trace(N, arr, i, j);
            }
        }
    }
    printf("%d\n", max);
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/TRACE)