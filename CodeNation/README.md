# CodeNation
> Collection of coding questions asked by CodeNation during placements at IITs

## Questions Index

* [Omega Primes](#1-omega-primes)
* [Root It](#2-root-it)
* [Shortest Path Function](#3-shortest-path-function)

## 1. Omega Primes

#### Problem Description

Carl is bored of playing with ordinary prime numbers. Thus, he comes up with some special numbers called Omega Primes. 

A number $X$ is called Omega Prime, if there exists no perfect square $Y$ ( $Y > 1$ ) such that $Y$ divides $X$.

For example, $6$ is an Omega Prime because there is no pefect square except $1$ that divides $6$.

On the other hand, $12$ is not an Omega Prime as $4$ (which is a perfect square) is a divisor of $12$.

Carl decides to play a bit more with Omega Primes. He has an array $A$ of integers. Carl wants to find the number of different subsets such that the product of elements for each subset, results in an Omega Prime. Help Carl find this number.

Since this number can be large, output the answer modulo $10^9 + 7$.

#### Problem Constratints

$1 \leq len(A) \leq 2\times10^4$

$1 \leq A[i] \leq 30$

#### Input Format

The first argument is the integer array $A$.

#### Output Format

Return an integer denoting the number of different desired subsets modulo $10^9 + 7$.

#### Example Input

```shell
Input 1:
  A = [2, 4, 3]
Input 2:
  A = [2, 2, 2]
```

#### Example Output

```shell
Output 1:
  3
Output 2:
  3
```

#### Example Explanation

```shell
Explanation 1:
  The different subsets are [0, 2], [0], [2]. (the numbers denote the indices of the array elements)
Output 2:
  The different subsets are [0], [1], [2].
  Note, the Omega Primes generated are same but the subset used to generate them are different.
```

---

## 2. Root It

---

## 3. Shortest Path Function
