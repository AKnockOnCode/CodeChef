# KITCHENSPICE - Rating 390

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

### Spice Level

Each item in Chef’s menu is assigned a spice level from $1$ to $10$. Based on the spice level, the item is categorised as:

- MILD: If the spice level is less than $4$.
- MEDIUM: If the spice level is greater than equal to $4$ but less than $7$.
- HOT: If the spice level is greater than equal to $7$.

Given that the spice level of an item is $X$, find the category it lies in.

### Input Format
- The first line of input will contain a single integer $T$, denoting the number of test cases.
- Each test case consists of an integer $X$ — the spice level of the item.
### Output Format

For each test case, output on a new line, the category that the item lies in.

You may print each character in uppercase or lowercase. For example, `HOT`, `hot`, `Hot`, and `hOT` are all considered the same.

### Constraints
- $1 \leq T \leq 1000$
- $1 \leq X \leq 10$
### Sample 1:
Input
Output

```
4
4
1
6
9

```

```
MEDIUM
MILD
MEDIUM
HOT

```

### Explanation:

 **Test case $1$:**  The spice level is greater than $4$ but less than $7$. Thus, it is in `MEDIUM` category.

 **Test case $2$:**  The spice level is less than $4$. Thus, it is in `MILD` category.

 **Test case $3$:**  The spice level is greater than $4$ but less than $7$. Thus, it is in `MEDIUM` category.

 **Test case $4$:**  The spice level is greater than $7$. Thus, it is in `HOT` category.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-11-05T17:24:31.295Z  

```c_cpp
#include <stdio.h>

int main() {
    int T;
    scanf("%d", &T);
    while (T--) {
    int X;
    scanf("%d", &X);
    if (X<4){
        printf("MILD\n");
    }
    else if (X>6){
        printf("HOT\n");
    }
    else{
        printf("MEDIUM\n");
    }
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/KITCHENSPICE)