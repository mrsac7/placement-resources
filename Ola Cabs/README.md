# Ola Cabs
> Collection of coding questions asked by Ola Cabs during placements at IITs

## Questions Index

* [Keypad Strokes](#1-keypad-strokes) [IIT-BHU'22]
* [Age Grouping](#2-age-grouping) [IIT-BHU'22]
* [Branching and Palindrome](#3-branching-and-palindrome) [IIT-BHU'22]

## 1. Keypad Strokes

### Problem Statement

The keypad shows below works as follows:

To type $a$, it requires a single stroke on the $'2'$ button, to type $b$, it requires two strokes on the $'2'$ button, to type $c$, it requires three strokes on the $'2'$ button, to type $d$, it requires a single stroke on the $'3'$ button. It works the same way for the other alphabets.

<p align="center">
  <img src="https://github.com/mrsac7/placement-resources/blob/main/Ola%20Cabs/key.png" width="250">
<p>


For each stroke, one second time is consumed. If two characters are typed using the same button consecutively, one second additional time will be required. You are given a string $str$, print the time taken to type $str$ using the given keypad.

$\textbf{Note}$: The string $str$ can be empty.

### Input Format

The input is given in the following format:

* The first line of the input contains a single integer $N$ denoting the length of $str$.
* The second line contains a string $str$.

### Output Format

Print the time taken to type $str$ using the given keypad.

### Constraints

* $0 \leq N \leq 10^5$.
* All the alphabets of the string are in lower case.

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
3                          
cat
```

</td>
<td>

```shell
6                             
```

</td>
</tr>
</table>

### Explanation

For typing $c$, it takes $3$ strokes on the $'2'$ button, for typing $a$, it takes $1$ stroke on the $'2'$ button. As the $'2'$ button is pressed consecutively for typing $c$ and $a$, there will be $1$ second gap in between. For typing $t$, it takes $1$ stroke on the $'8'$ button.

Total time = $3 + 1 + 1 + 1 = 6$. Thefore, the output is $6$.

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
3                          
dog
```

</td>
<td>

```shell
5                             
```

</td>
</tr>
</table>

---

## 2. Age Grouping

### Problem Statement

There is a class of $N$ students. Given an array named $arr$ of size $N$ which contains the age of all the students. You are given an integer $k$ in the input, and the task is to count the number of unique groups of $k$ students who have the same age, For example:

If $k$ is $2$, then we have to find the total number of unqiue pairs of students who have the same ages.

If $k$ is $3$, then we have to find triplets of unique students who have the same ages, and so on.

Print the number of unqiue groups of $k$ students who have the same age. As the answer can be very large, print answer modulo $10^9 + 7$.

$\textbf{Note}$: The ordering in the grouop of students is not relevant.

### Input Format

The input consists of two lines:

* The first line contains two space-separated integers denoting $N$ and $k$ respectively.
* The second line contains $N$ space-separated integers denoting the ages of $N$ students in the class.

### Output Format

Print the number of unique groups of $k$ students who have the same age. As the answer can be very large, print answer modulo $10^9 + 7$.

### Constraints

* $1 \leq N \leq 10^5$
* $2 \leq k \leq \ N$
* $1 \leq$ age of a student $\leq 10^9$

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
4 2                        
1 2 1 1
```

</td>
<td>

```shell
3                                 
```

</td>
</tr>
</table>

### Explanation

Here, the age of the student $A = 1$

The age of the student $B = 2$

The age of the student $C = 1$

The age of the student $D = 1$

For $k = 2$, all the possible unique pairing among the students are:

$(A, B)$, $(A, C)$, $(A, D)$, $(B, C)$, $(B, D)$, $(C, D)$

The total pairs of unique students of the same age are $3$, i.e. $(A, C)$, $(A, D)$, $(C, D)$. So, the answer is $3$.

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
6 3                        
1 2 1 2 1 2
```

</td>
<td>

```shell
2                                 
```

</td>
</tr>
</table>

---

## 3. Branching and Palindrome

### Problem Statement

Write a program to input a binary search tree and check whether the numbers present in the left view of the tree give a palindrome format or not.

Conditions for making the binary search tree as follows:

* The first key is always the root node.
* The next key if smaller than or equal to the parent node then push it onto the right of the parent node.
* If the eky key is greater than or equal to the parent node then push it onto the right of the parent node.

If the left view of the tree forms a palindrome print the number else print "NOT PALINDROME".

$\textbf{Note}$: The duplicity of keys is allowed.

### Input Format

The input consists of the following format:
* The first line will contain $N$ i.e. the number of nodes.
* Then each $N$ line will contain the value in the node.

### Output Format

Print the number if it is a palindrome and "NOT PALINDROME" if it is not.

### Constraints

* $0 < N < 1000$

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
4                          
4
6
8
4
```

</td>
<td>

```shell
464                               
```

</td>
</tr>
</table>

### Explanation

The input forms the following tree:

<img src="https://github.com/mrsac7/placement-resources/blob/main/Ola%20Cabs/t.png" width="175">

The left view of the tree forms the number $464$. Thus the output is $464$ as it is a palindrome.

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
4                          
3
1
2
1
```

</td>
<td>

```shell
NOT PALINDROME                    
```

</td>
</tr>
</table>
