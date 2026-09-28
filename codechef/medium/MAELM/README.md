# MAELM

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

### Matrix Element Match

You are given an $N \times N$ matrix $A$ and an $M \times M$ matrix $B$.

Matrix $B$ is considered present in $A$ if every element of $B$ can be matched with an equal element in $A$,  **regardless of its position**.

Each occurrence in $A$ can be used only once. Therefore, if a value appears multiple times in $B$, it must appear at least the same number of times in $A$.

For example, if `5` appears twice in $B$, then $A$ must also contain at least two occurrences of `5`.

Determine whether all elements of $B$ can be matched in $A$.

### Input Format
- The first line contains an integer $N$ — the size of matrix $A$.
- The second line contains an integer $M$ — the size of matrix $B$.
- Each of the next $N$ lines contains $N$ space-separated integers representing matrix $A$.
- Each of the next $M$ lines contains $M$ space-separated integers representing matrix $B$.
### Output Format

Print `TRUE` if every element of $B$ can be matched with an equal element in $A$, using each occurrence in $A$ at most once.

Otherwise, print `FALSE`.

### Constraints
- $1 \le M \le N \le 500$
- $-10^9 \le A_{i,j}, B_{i,j} \le 10^9$
### Sample 1:
Input
Output

```
3
2
1 7 2
8 3 6
9 5 3
1 2
3 3
```

```
TRUE
```

### Explanation:

Matrix $B$ contains `1`, `2`, `3`, and `3`.

Each of these values is present in matrix $A$, so the answer is `TRUE`.

### Sample 2:
Input
Output

```
3
3
1 2 3
4 5 6
7 8 9
1 2 2
4 5 5
7 8 8
```

```
FALSE
```

### Explanation:

Matrix $B$ requires two occurrences each of `2`, `5`, and `8`.

Matrix $A$ contains only one occurrence of each of these values.

Therefore, all elements of $B$ cannot be matched, and the answer is `FALSE`.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-09-28T14:19:50.419Z  

```c_cpp
#include <stdio.h>
#include <limits.h>
int main() {
    int N, M;
    scanf("%d", &N);
    scanf("%d", &M);
    long long A[N][N];
    long long B[M][M];
    int i, j;
    for (i=0;i<N;i++){
        for (j=0;j<N;j++){
            scanf("%lld", &A[i][j]);
        }
    }
    for (i=0;i<M;i++){
        for (j=0;j<M;j++){
            scanf("%lld", &B[i][j]);
        }
    }
    int a=0, b=0;
    int num = 0;
    while (a<M){
        for (i=0;i<N;i++){
            for (j=0;j<N;j++){
                if (B[a][b]==A[i][j]){
                    num++;
                    A[i][j]=INT_MAX;
                    if (b<M-1){
                        b++;
                    }
                    else{
                        b=0;
                        a++;
                    }
                    continue;
                }
            }
        }
        if (i==N && j==N){
            break;
        }
    }
    if (num==M*M){
        printf("True\n");
    }
    else{
        printf("False\n");
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/MAELM)