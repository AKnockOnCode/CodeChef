# DSCOP

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

### Discount

You are buying an item that costs $N$ rupees.

The shopkeeper gives you a special discount: you may remove  **exactly one digit**  from the decimal representation of $N$. The remaining digits, in the same order, form the new price you have to pay.

Your task is to find the  **minimum possible price**  after removing exactly one digit.

The resulting number may contain leading zeros. However, while printing the answer, leading zeros must not be printed.

### Input Format
- The first line contains an integer $T$, the number of test cases.
- Each of the next $T$ lines contains a single integer $N$.
### Output Format

For each test case, print the minimum price that can be obtained after removing exactly one digit from $N$.

Print each answer on a separate line.

### Constraints
- $1 \le T \le 10^5$
- $10 \le N \le 10^9$
### Sample 1:
Input
Output

```
4
57
908
1005
4321
```

```
5
8
5
321
```

### Explanation:

 **Test Case 1:** 

For $N = 57$:

- Removing $5$ gives $7$.
- Removing $7$ gives $5$.

Therefore, the minimum possible price is $5$.

 **Test Case 2:** 

For $N = 908$:

- Removing $9$ gives $08$, which is printed as $8$.
- Removing $0$ gives $98$.
- Removing $8$ gives $90$.

Therefore, the minimum possible price is $8$.

 **Test Case 3:** 

For $N = 1005$, removing the first digit gives $005$, which is printed as $5$.

Therefore, the minimum possible price is $5$.

 **Test Case 4:** 

For $N = 4321$, the possible prices are $321$, $421$, $431$, and $432$.

Therefore, the minimum possible price is $321$.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-09-28T13:51:10.386Z  

```c_cpp
#include <stdio.h>

int main() {
    int T;
    scanf("%d", &T);
    while (T--) {
    int N;
    scanf("%d", &N);
    int i;
    int temp = N;
    int check = 0;
    int digits = 0
    while (temp){
        digits++;
        temp /= 10;
    }
    temp = N;
    int digit = digits;
    int limits = digits;
    int arr[digits];
    for (i=0;i<limits;i++){
        if (temp/10){
        arr[i]= temp/pow(10, digits-1);
        temp%=pow(10, digits-1);
            digits--;
        }
        else{
        arr[i]=temp;
        }
    }
    int max  = 0;
    while(arr[i]!=0){
        if (arr[i]>max){
            max = arr[i++];
        }
    }
    int used = 0;
    int result = 0;
    for (i=0;i<digit;i++){
        if (arr[i]==max && !used){
            used++;
            continue;
        }
        result = result * 10 + arr[i];
    }
    printf("%d\n", result);
    }
    return 0;
}
```

---

[View on CodeChef](https://www.codechef.com/problems/DSCOP)