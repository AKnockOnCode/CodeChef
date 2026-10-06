# FINE - Rating 335

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Overspeeding Fine

Chef was driving on a highway at a speed of $X$ km/hour.

To avoid accidents, there are fine imposed on overspeeding as follows:

- No fine if the speed of the car $\leq 70$ km/hour.
- Rs $500$ fine if the speed of the car is strictly greater than $70$ and $\leq 100$.
- Rs $2000$ fine if the speed of the car is strictly greater than $100$.

Determine the fine Chef needs to pay.

### Input Format
- The first line of input will contain a single integer $T$, denoting the number of test cases.
- Each test case consists of a single integer $X$ denoting the speed of Chef's car.
### Output Format

For each test case, output the fine paid by Chef.

### Constraints
- $1 \leq T \leq 200$
- $1 \leq X \leq 200$
### Sample 1:
Input
Output

```
7
40
110
70
100
69
101
85

```

```
0
2000
0
500
0
2000
500

```

### Explanation:

 **Test case $1$:**  The speed is $\leq 70$. Thus, Chef does not need to pay any fine.

 **Test case $2$:**  The speed is greater than $100$. Thus, Chef needs to pay $2000$ as fine.

 **Test case $3$:**  The speed is $\leq 70$. Thus, Chef does not need to pay any fine.

 **Test case $4$:**  The speed is greater than $70$ and $\leq 100$. Thus, Chef needs to pay $500$ as fine amount.

 **Test case $5$:**  The speed is $\leq 70$. Thus, Chef does not need to pay any fine.

 **Test case $6$:**  The speed is greater than $100$. Thus, Chef needs to pay $2000$ as fine.

 **Test case $7$:**  The speed is greater than $70$ and $\leq 100$. Thus, Chef needs to pay $500$ as fine amount.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-10-06T09:59:57.009Z  

```c_cpp
#include <stdio.h>

int main() {
    int T;
    scanf("%d", &T);
    while (T--) {
    int X;
    scanf("%d", &X);
    if (X<=70){
        printf("0\n");
    }
    else if (X>100){
        printf("2000\n");
    }
    else{
        printf("500\n");
    }
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/FINE)