# Dream 11
> Collection of coding questions asked by Dream 11 during placements at IITs

## Questions Index

* [Valid BST Permutations](#1-valid-bst-permutations) [IIT-BHU'22]
* [Quiz Competition](#2-quiz-competition) [IIT-BHU'22]
* [Similar Parity Integers](#3-similar-parity-integers) [IIT-BHU'22]

## 1. Valid BST Permutations

A binary tree is a data structure characterized by the following properties:

* It can be an empty tree where root = null.
* It can consists of a root that contains a value and two sub-trees labelled "left" and "right".
* Each sub-tree also follows the defintion of a binary tree.

A binary tree is a binary search tree (BST) if all the non-empty nodes follow these two rules:

* If a node has a left sub-tree, then all the values in its left sub-tree are smaller than its value.
* If a node has a right sub-tree, then all the values in its right sub-tree are greater than its value.

Given an integer, determine the number of valid BSTs that can be created by nodes numbered from $1$ to that integer. Please see the samples below for diagrams based on $1$, $2$, or $3$ nodes.

### Function Description

Complete the function `numBST`.

`numBST` has the following parameter(s):

* $int \ \ nodeValues[n]$: an array of integers representing the number of nodes values to analyze

$\textbf{Returns}$

* $int[n]$: an array of integers that represent the number of different binary search trees that can be created for each test case. Since the numbers may be large, return the values modulo $(10^\textbf{8} + 7)$

### Constraints

* $1 \leq n \leq 1000$
* $1 \leq nodeValues[i] \leq 1000$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
5                        
1 2 3 4 100
```

</td>
<td>

```shell
1 2 5 14 25666077               
```

</td>
</tr>
</table>

$\textbf{Explanation}$

$n = 1$: Only one tree can be created with one node.

<img src="#">

$n = 2$: Two trees can be created with two nodes.

<img src="#">

$n = 3$: Five trees can be created with three nodes.

<img src="#">

---

## 2. Quiz Competition

A class has a number of students, each with a particular area of knowledge, or talent. Each talent is represented as an integer from $1$ to $talentsCount$. Teams must be formed for a quiz competition, and must have at least one member with each of the talents. The talents are listed in an array, and the students must be chosen consecutively, starting at any element index. For each starting index, determine the minimum number of students that must be selected to have at least one team member with each talent. If it is not possible, return $-1$ for that index.

### Example

$talentsCount = 3$

$talent = [1, \ 2, \ 3, \ 2, \ 1]$

There is no way fewer than 3 students can have at least $3$ talents. The following subarrays of length $3$ or more are possible:

Starting at position $1$: $\textbf{[1, \ 2, \ 3]}$, $[1, \ 2, \ 3, \ 2]$, $[1, \ 2, \ 3, \ 2, \ 1]$ <br>
Starting at position $2$: $[2, \ 3, \ 2]$, $\textbf{[2, \ 3, \ 2, 1]}$ <br>
Starting at position $3$: $\textbf{[3, \ 2, \ 1]}$

No further subarrays of length $3$ or more exists.

Starting at the first position, the shortest subarray with one of each talent value has length $3$. <br>
Starting at element $2$, the shortest subarray has length $4$. <br>
At position $3$, the shortest and only possible subarray has length $3$. <br>

It it not possible to form a team with fewer than $3$ members, so the subarray starting at the last two positions will fail.

The highlighted subarrays are selected. The return array is $[3, \ 4, \ 3, \ -1, \ -1]$.

### Function Description

Complete the function `teamSize`.

`teamSize` has the following parameter(s):

* $talent$: An array of length $n$ where $talent[i]$ denotes the talent of the $i^{th}$ student, where $0 \leq i \lt n$.
* $talentsCount$: An integer, the total number of talents represented

$\textbf{Returns}$

* $int [n]$: an array of integers that represent, for each starting index, the minimum number of students that must be selected to have at least one team member with each talent. If it is not possible, return $-1$ for that index.



### Constraints

* $1 \leq n, \ talentsCount \leq 10^5$
* $1 \leq talent[i] \leq talentsCount

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
8                        
1 1 2 2 3 1 3 2
3
```

</td>
<td>

```shell
5 4 4 3 4 3 -1 -1                 
```

</td>
</tr>
</table>

$\textbf{Explanation}$

$n = 8$ <br>
$talent$ $=$ $[1, \ 1, \ 2, \ 2, \ 3, \ 1, \ 3, \ 2]$ <br>
$talentsCount = 3$

There have to be at least $3$ elements in an subarray to represent each talent. The following subarrays are possible:

Beginning at the first position: $[1, \ 1, \ 2]$, $[1, \ 1, \ 2, \ 2]$, $\textbf{[1, \ 1, 2, \ 2, \ 3]}$, $[1, \ 1, \ 2, \ 2, \ 3, \ 1]$, $[1, \ 1, \ 2, \ 2, \ 3, \ 1, \ 3]$, $[1, \ 1, \ 2, \ 2, \ 3, \ 1, \ 2]$

Second position: $[1, \ 2, \ 2]$, $\textbf{[1, \ 2, \ 2, \ 3]}$, $[1, \ 2, \ 2, \ 3, \ 1]$, $[1, \ 2, \ 2, \ 3, \ 1, \ 3]$, $[1, \ 2, \ 2, \ 3, \ 1, \ 3, \ 2]$

Third position: $[2, \ 2, \ 3]$, $\textbf{[2, \ 2, \ 3, \ 1]}$, $[2, \ 2, \ 3, \ 1, \ 3]$, $[2, \ 2, \ 3, \ 1, \ 3, \ 2]$

Fourth position: $\textbf{[2, \ 3, \ 1]}$, $[2, \ 3, \ 1, \ 3]$, $[2, \ 3, \ 1, \ 3, \ 2]$

Fifith position: $[3, \ 1, \ 3]$, $\textbf{[3, \ 1, \ 3, \ 2]}$

Sixth position: $\textbf{[1, \ 3, \ 2]}$

No further subarrays will have $3$ elements.

The hightlighted subarrays are the shortest for each starting position. The return array of subarray lengths is $[5, \ 4, \ 4, \ 3, \ 4, \ 3, \ -1, \ -1]$

---

## 3. Similar Parity Integers

Given two integers $a$ and $b$, find the number of integers that lie in the range $[a + 1, \ b]$ such that, if the sum of digits at even places is $sumEven$ and the sum of digits at odd places is $sumOdd$, then the parity of $sumEven$ and $sumOdd$ is same.

Since the number may be too large, return the number modulo $(10^9 + 7)$.

$\textbf{Note}$: The positions of digits in a number starts from $0$, that is, if the number is $201921$ then:

* $sumEven$ $=$ $2 + 1 + 2 = 5$
* $sumOdd$ $=$ $0 + 9 + 1 = 10$

### Example

Assume integer $a = 8$ and $b = 13$, now let's check for each integer that lies within this range:

* For integer $9$, the $sumEven = 0$ and $sumOdd = 9$, thus the parity is different.
* For integer $10$, the $sumEven = 1$ and $sumOdd = 0$, thus the parity is different.
* For integer $11$, the $sumEven = 1$ and $sumOdd = 1$, thus the parity is same.
* For itneger $12$, the $sumEven = 1$ and $sumOdd = 2$, thus the parity is same.

The number of integers with the same parity is $2$.

### Function Description

Complete the function `findSameParityIntegers`.

`findSameParityIntegers` has the following parameters:

* $string \ \ a$: denoting the integer $a$
* $string \ \ b$: denoting the integer $b$

$\textbf{Returns}$

* $int$: an integer denoting the number of integers that lie in the range $[a + 1, \ b]$ and satisfy the given condition modulo $(10^9 + 7)$.

### Constraints

* $0 \leq a \lt b\leq 10^{1000}$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
17 22                        
```

</td>
<td>

```shell
3                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

Here $a = 17$ and $b = 22$, now let's check for each integer that lies within this range:

* For integer $18$, the $sumEven = 1$ and $sumOdd = 8$, thus the parity is different.
* For integer $19$, the $sumEven = 1$ and $sumOdd = 9$, thus the parity is different.
* For integer $20$, the $sumEven = 2$ and $sumOdd = 0$, thus the parity is different.
* For integer $21$, the $sumEven = 2$ and $sumOdd = 1$, thus the parity is different.
* For integer $22$, the $sumEven = 2$ and $sumOdd = 2$, thus the parity is different.

Hence, the number of integers with the same parity is $3$.
