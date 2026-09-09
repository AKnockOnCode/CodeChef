# ANUUND - Rating 1198

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Ups and Downs
### Problem description

You will be given a zero-indexed array  **A**. You need to rearrange its elements in such a way that the following conditions are satisfied:

- A[i] ≤ A[i+1] if i is even.
- A[i] ≥ A[i+1] if i is odd.
In other words the following inequality should hold:  **A[0] ≤ A[1] ≥ A[2] ≤ A[3] ≥ A[4]**, and so on. Operations  **≤**  and  **≥**  should alter.
### Input

The first line contains a single integer  **T**  denoting the number of test cases. The first line of each test case contains an integer  **N**, that is the size of the array  **A**. The second line of each test case contains the elements of array  **A** 

### Output

For each test case, output a single line containing  **N**  space separated integers, which are the elements of  **A**  arranged in the required order. If there are more than one valid arrangements, you can output any of them.

### Constraints
- 1 ≤ N ≤ 100000
- Sum of N in one test file ≤ 600000
- 1 ≤ A[i] ≤ 10^9
### Sample 1:
Input
Output

```
2
2
3 2
3
10 5 2
```

```
2 3
2 10 5
```

### Explanation:

 **Example case 1.** 
 **A[0]**  ?  **A[1]**  is satisfied, 2 ? 3.

 **Example case 2.** 
 **A[0]**  ?  **A[1]**  is satisfied, 2 ? 10.
 **A[1]**  ?  **A[2]**  is satisfied, 10 ? 5.
 **Note:**  5 10 2 is also valid answer.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-09-09T05:56:36.667Z  

```c_cpp
#include <stdio.h>
#include <stdlib.h>

int compare(const void *a, const void *b) {
    return (*(int *)a - *(int *)b);
}

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
    qsort(arr, N, sizeof(int), compare);
    i = 2;
    int temp;
    while (i<N){
        temp = arr[i];
        arr[i] = arr[i-1];
        arr[i-1] = temp;
        i += 2;
    }
    for (i=0;i<N;i++){
        printf("%d ", arr[i]);
    }
    printf("\n");
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/ANUUND)