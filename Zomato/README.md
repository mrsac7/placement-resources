# Zomato
> Collection of coding questions asked by Zomato during placements at IITs

## Questions Index

* [Anniversary Gift](#1-anniversary-gift) [IIT-BHU'22]
* [Add Operator And Fraction](#2-add-operator-and-fraction) [IIT-BHU'22]
* [Make Matrix Beautiful](#3-make-matrix-beautiful) [IIT-BHU'22, IIT-M'22, IIT-D'22, IIT-P'22]
* [Next Smallest Palindrome](#4-next-smallest-palindrome) [IIT-BHU'22]

## 1. Anniversary Gift

**Find the smallest valid length such that Harry's gift would be awesome.**

Harry wants to give a gift to Ginny to celebrate their anniversary. Of course, he has a sequence $a_1, \ a_2, \ ..., \ a_N$ ready for this occassion. Since the half-heart necklace is kind of cliche, he decided to cut his sequence into two pieces and give here a piece instead. Formally, he wants to choose an integer $l$ and its suffix $x$ with length $N - l$

Harry wants his gift to be awesome. He thinks that it will be awesome if the product of the elements in Ginny's piece is co-prime with the product of the elements in his piece. Can you tell him where to cut the sequence? Find the smallest valid $l$ such that Harry's gift would be awesome.

$\textbf{Note}$: Print $-1$ in case of no length $(l)$ is possible

### Input Format

```
T
N
a1 a2 ... aN
```

The first line of the input contains a single integer $T$ denoting the number of test cases. The description of $T$ test cases follows.
* The first line of each test case contains the integer $N$.
* The second line contains $N$ space-separated integers $a_1, \ a_2, \ ..., \ a_N$.


### Output Format

```
M1
...
MT
```

For each test case, print a single line containing one integer $M$ where Harry should cut the sequence.

Print $-1$ in case of no length $(l)$ is possible.

### Example:

```
Input:
1
5
2 3 4 5 7
Output: 3
Explanation: As 2, 3, 5 and 7 are prime numbers as 
well as 4 is not prime and it's factor 2 is present.
So cutting the string at index 3 will give min l.

```

## 2. Add Operator and Fraction

**Find the kth fraction in the nth step**

You are given two fractions: 0/1 and 1/2. In each step, you will get two adjacent fractions and you need to add them, if and only if, the denominator is equal to or smaller than the number obtained in that step and write it between those two adjacent fractions.

Example:

```
Step 1: 0/1, 1/2 
Step 2: 0/1, 1/2 
Step 3: 0/1, 1/3, 1/2 and so on
```

The add operator is defined as follows:

If (a/b) and (c/d) is added, then the sum is (a+c)/(b+d) which means that their numerator and denominators both are added to each other.

You have to find the $k^{th}$ fraction in the $n^{th}$ step.

$\textbf{Note}$: You will be given the values of $n$ and $k$.

### Input Format

```
N K
```

First line contains two integers $n$ and $k$ where $n$ is the number of steps. It is guaranteed that there is at least $k$ numbers written in the $n^{th}$ step.

### Output Format

```
X/Y
```

Print the answer in the format (int)/(int), like 3/5.

### Example:

```
Input:
5 5
Output: 2/5
Explanation:
0/1, 1/2 first step
0/1, 1/2 second step
0/1, 1/3, 1/2 third step
0/1, 1/4, 1/3, 1/2 fourth step
0/1, 1/5, 1/4, 1/3, 2/5, 1/2 fifth step 
and the fifth fraction is 2/5
```

---

## 3. Make Matrix Beautiful

**Find the number of operations to make a matrix beautiful**

A **beautiful matrix** is a matrix in which the **sum of elements** in each row and column in **equal**.

Given a square matrix of size $N \times M$. Find the **minimum** number of operations(s) that are required to make the matrix beautiful. In one operation you can increment the value of any one cell by $1$.

### Example 1:

```
Input:
N = 2
matrix[][] = {{1, 2},
              {3, 4}}
              
Output = 4
Explanation:
Updated matrix:
4 3
3 4
1. Increment value of cell(0, 0) by 3
2. Increment value of cell(0, 1) by 1
Hence total 4 operation are required.
```

### Example 2:

```
Input:
N = 3
matrix[][] = {{1, 2, 3},
              {4, 2, 3},
              {3, 2, 1}}
Output: 6
Explanation:
Original matrix is as follows:
1 2 3
4 2 3
3 2 1
We need to make increment in such a way
that each row and column has one time 2,
one time 3, and one time 4. For that we
need 6 operations.
```

### Input Format

```
T
N
M(0, 0) M(0, 1) ... M(0, N-1)
.
.
.
M(N-1, 0) M(N-1, 2) ... M(N-1, N-1)
```

First line in input represents the number of test cases $T$, <br>
for each test case, line $1$ contains $N$ which represents the dimension of the square, <br>
and the following $N$ lines contain $N$ space-separated numbers representing the elements of the matrix.

### Output Format

```
M
```

For each test case, print a single line containing one integer $M$ denoting the minimum number of operations to make a matrix beautiful

---

## 4. Next Smallest Palindrome

**Find the next smallest palindrome stricly larger than the given number.**

Given a number, in the form of an array $Num[]$ of size $N$ containing digits from $1$ to $9$ (inclusive). The task is to find the next smallest palindrome strictly larger than the given number.

### Example 1:

```
Input:
N = 11
Num[] = {9, 4, 1, 8, 7, 9, 7, 8, 3, 2, 2}
Output: 9 4 1 8 8 0 8 8 1 4 9
Explanation: Next smallest palindrome is
94188088149.
```

### Example 2:

```
Input:
N = 5
Num[] = {2, 3, 5, 4, 5}
Output: 2 3 6 3 2
Explanation: Next smallest palindrome is
23632.
```

### Input Format

```
N
num1 num2 ... numN
```
* The first line of the input contains an integer $N$
* The second line contains $N$ space-separated integers $num_1, \ num_2, \ ..., \ num_N$.


### Output Format

```
arr1 arr2 ... arrM
```

Print an array of integers denoting the next smallest palindrome stricly larger than the given number.



