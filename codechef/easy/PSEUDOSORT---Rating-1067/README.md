# PSEUDOSORT - Rating 1067

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Pseudo Sorted Array

An array $A$ of length $N$ is said to be  *pseudo-sorted*  if it can be made non-decreasing after performing the following operation  **at most once**.

- Choose an $i$ such that $1 \le i \leq N-1$ and swap $A_i$ and $A_{i+1}$

Given an array $A$, determine if it is  *pseudo-sorted*  or not.

### Input Format
- The first line contains a single integer $T$ - the number of test cases. Then the test cases follow.
- The first line of each test case contains an integer $N$ - the size of the array $A$.
- The second line of each test case contains $N$ space-separated integers $A_1, A_2, \dots, A_N$ denoting the array $A$.
### Output Format

For each testcase, output `YES` if the array $A$ is pseudo-sorted, `NO` otherwise.

You may print each character of `YES` and `NO` in uppercase or lowercase (for example, `yes`, `yEs`, `Yes` will be considered identical).

### Constraints
- $1 \leq T \leq 1000$
- $2 \leq N \leq 10^5$
- $1 \leq A_i \leq 10^9$
- Sum of $N$ over all test cases do not exceed $2 \cdot 10^5$
### Sample 1:
Input
Output

```
3
5
3 5 7 8 9
4
1 3 2 3
3
3 2 1

```

```
YES
YES
NO

```

### Explanation:

 **Test case 1:**  The array is already sorted in non-decreasing order.

 **Test case 2:**  We can choose $i = 2$ and swap $A_2$ and $A_3$. The resulting array will be $[1, 2, 3, 3]$, which is sorted in non-decreasing order.

 **Test case 3:**  It can be proven that the array cannot be sorted in non-decreasing order in at most one operation.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-09-22T15:57:20.767Z  

```c_cpp
#include <stdio.h>

int main() {
    int T;
    scanf("%d", & T);
    while (T--) {
        int N;
        scanf("%d", & N);
        int i;
        int arr[N];
        for (i = 0; i < N; i++) {
            scanf("%d", & arr[i]);
        }
        int temp;
        for (i = 0; i < N - 1; i++) {
            if (arr[i] > arr[i + 1]) {
                temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1] = temp;
                break;
            }
        }
        int check = 0;
        for (i = 0; i < N - 1; i++)
        {
            if (arr[i] > arr[i + 1]) check++;
        }
        if (!check) printf("Yes\n");
        else printf("No\n");
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/PSEUDOSORT)