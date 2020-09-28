---
marp: true
header: '![image](https://www.psau.edu.sa/themes/psau/logo.png)'
footer: College of Computer Engineering and Sciences  - September 2020
---

 # <!-- fit --> IEEEXTREME Competition Training 

## Dr. Khalil Chebil 
---
# Content
- Problem Solving Challenge
- Solving Techniques
- Practice Problems
    - Maximum Subsequence Problem
---
# Problem Solving Challenge
>- Hard to design algorithms that are 
    - Correct 
    - Efficient 
    - Implementable
>- Need to know about
    - Design and modeling techniques
    - Resources - don't reinvent the wheel

----
# First example: Computing $a^n$ 
>Iterative Brute Force Solution O(n) 
```java
int pow(int a, int n){
    int res=1;
    for(int i=0;i<n;i++)
        res*=a;
    return res;
}
```
----
#  Computing $a^n$ (cont.)
>Recursive Solution O(n) 
```java
int pow(int a, int n){
    if(n==0)
      return 1;
    return a*pow(a,n-1);
  } 
```
----
#  Compute $a^n$ (cont.)
>Decrerase and conquer Solution

```java
int pow(int a, int n){
    if(n==0)
      return 1;
    if(n==1)
      return a;
    if(n%2==0){
      int m=pow(a,n/2);
      return m*m;
    }  
    return a*pow(a,n-1);
}
```
![bg right 90%](./assets/fig1.PNG)

----
# Second example: Maximum Subsequence Problem
```java
int maxSubSum(int[]a){
    int maxSum = 0; 
    for( int i = 0; i < a.length; i++ ) 
        for( int j = i; j < a.length; j++ ) 
        { 
            int thisSum = 0; 
            for( int k = i; k <= j; k++ ) 
                thisSum += a[ k ]; 
            if( thisSum > maxSum )
                maxSum = thisSum; 
        } 
    return maxSum; 
  }
````