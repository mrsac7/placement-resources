# Cult.fit
> Collection of coding questions appearing in online assessment of Cult.fit during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Derek And His New Car](#1-derek-and-his-new-car) [IIT-BHU'22]
* [Count Unique Ordered Alphabets](#2-count-unique-ordered-alphabets) [IIT-BHU'22]
* [Path MEX](#3-path-mex) [IIT-BHU'22]

## 1. Derek And His New Car

Derek is a house painter who is planning to buy a new car within $D$ days after which the Car Sale will end. He currently has no money but has $N$ contracts that his clients have given him. Each client has mentioned the time it will take to paint his house $(Time_i)$ and the money that he'll give Derek on completion $(Money_i)$.

The price of the car he wants to buy during the sale is $M$.

### Task

Determine whether Derek will be able to purchase it before the sale ends.

### Example

$\textbf{Assumption}$

* $D = 5$
* $M = 3$
* $N = 4$
* $Money = [1, \ 2, \ 3, \ 4]$
* $Time = [1, \ 1, \ 1, \ 1]$

$\textbf{Approach}$

You must determine whether Derek will be able to buy the car during the sale.

He can complete all $4$ contracts, the total time taken for completing all the contracts is $4$ days and the total money he will get is $10$.

Hence, the answer will be YES.

### Function Description

Complete the `solve` function. This function takes the following $5$ parameters and returns **YES** or **NO** depending on whether she will be able to top this time or not:

* $D$: Represents the duration of the sale in days
* $M$: Represents the cost of the car
* $N$: Represents the number of painting contracts with Derek
* $Marks$: Represents the money he will receive for each contract
* $Time$: Represents the time taken to complete each contract

### Input Format

* The first line contains $T$ denoting the number of test cases. $T$ also specifies the number of times you have to run the solve function on a different set of inputs. 
* The next line contains three space-separated integers $D, \ M,$ and $N$ denoting the duration of the sale in days, cost of the car, and the number of painting contracts. 
* The next line contains $N$ space-separated integers, denoting the $Money$ array where $Money_i$ denotes the money he'll get on completing the $i^{th}$ contract. 
* The next line contains $N$ space-separated integers, denoting $Time$ array where $Time_i$ denotes the time required for the ith contract. 

### Output format 

For each test case, print YES if he will be able to buy the car else print NO. 

### Constraints 

* $1 \leq T \leq 20$ 
* $1 \leq N \leq 10^5$
* $1 \leq i \leq N$
* $1 \leq Money_i, \ M \leq 10^9$
* $1 \leq Time_i, \ D \leq 100$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
2                               
10 13 4
2 5 8 6
4 6 3 5
5 10 2
9 9
3 3
```

</td>
<td>

```shell
YES                            
NO
```

</td>
  
$\textbf{Explanation}$
  
The first line contains the number of test cases, $T = 2$.
  
**The first test case**
  
Given
  
* $D = 10$
* $M = 13$
* $N = 4$
* $Marks = [2, \ 5, \ 8, \ 6]$
* $Time = [4, \ 6, \ 3, \ 6]$
  
$\textbf{Approach}$
  
In this case, exam duration is $10$ and Secret Marks is $13$. She can choose problems $2$ and $3$ with marks $5$ and $8$ and duration $6$ and $3$ to solve in the given time to get the required marks.

**The second test case**
  
Given
  
* $D = 5$
* $M = 10$
* $N = 2$
* $Marks = [9, \ 9]$
* $Time = [3, \ 3]$
  
$\textbf{Approach}$
  
In this case, she can not achieve the required marks in the given time.

---

## 2. Count Unique Ordered Alphabets

You are given a randomly generated string of characters ranging from $a$ to $z$. You have to tell the number of unique subsequences that can be formed equal to following string $'abcdefghijklmnopqrstuvwxyz'$? 

$\textbf{Note}$: 

A subsequence is unique when at least a single character has its index that is different from all the other subsequences. Print the answer modulo $(10^9 + 7)$ for each test case in a new line. 

### Input format 

* The first line will contain $t$, number of test cases. 

Each test case consists of two lines: 

* First line will contain $n$, size of the string 
* Second line will contain string $s$ of size $n$ 

### Output format 

For each test case, print a single integer which is count of number of unique subsequences possible of $a-z$ format. 

Answer for each test case should come in a new line.

### Constraints

* $1 \leq t \leq 10$
* $1 \leq n \leq 10^5$
* $1 \leq |S| \leq 10^5$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
3                               
27
abcdefghijklmnopqrstuvwxyzz
3
abz
28
abcdefghijklmnopqrstuvwxyyzz
```

</td>
<td>

```shell
2                            
0
4
```

</td>
</tr>
</table>

$\textbf{Explanation}$

**Consider 0 based Indexing**

* The first string has $2$ subsequences of the given type $string[0]$ to $string[25]$ and $string[0]$ to $string[24]$ and $'z'$ letter from index $string[26]$ i.e. 
  - $1^{st}$ $a-z$ subsequence - $string[0:25]$
  - $2^{nd}$ a-z subsequence - $string[0:24]$ + $string[26]$
  
  Hence the output is $2$.
* The second string does not have all the characters till $'z'$. hence the answer is zero.
* In third test case. We can get 4 combinations 
  - $1^{st}$ - $string[0:24]$ + $string[26]$ 
  - $2^{nd}$ - $string[0:24]$ + $string[27]$ 
  - $3^{rd}$ - $string[0:23]$ + $string[25]$ + $string[26]$ 
  - $4^{th}$ - $string[0:23]$ + $string[25]$ + $string[27]$



---

## 3. Path MEX

You are given a rooted tree having $N$ nodes. A tree is a connected undirected graph with $N - 1$ edges. Here root node is node $1$. Each node has some integer value $val_i$ associated with it.

### Task

For each node $i$ $(1 \leq i \leq N)$, print $MEX$ of the path values from the root node to node $i$.

$\textbf{Notes}$:

* Assume $1$-based indexing.
* The $MEX$ of an array is equal to the smallest positive integer that is not present in the array. For example, $MEX(1, \ 2, \ 4, 2 \ 3, \ 6, \ 7)$ = $5$.

### Example

$\textbf{Assumptions}$

* $N = 4$
* $val = [1, \ 3, \ 2, \ 8]$
* $parent = [1, \ 2, \ 2]$

$\textbf{Approach}$

* $Node 1: MEX(1) = 2$
* $Node 2: MEX(1, \ 3) = 2$
* $Node 3: MEX(1, \ 3, \ 2) = 4$
* $Node 4: MEX(1, \ 3, \ 8) = 2$
* Hence, required answer is $[2, \ 2, \ 4, \ 2]$.

### Function Description

Complete the function `solve`. This function takes the following $3$ parameters and returns the required answer.

* $N$: Represents the number of nodes
* $val$: Represents the value of nodes
* $parent$: Represents parent node where $parent_i$ is the parent node of node $i + 1$ $(1 \leq i \leq N - 1)$

### Input Format

* First line denotes the number of test cases $T$, followed by the test cases themselves.
* First line of each test case contains an integer $N$ denoting the number of nodes in the tree.
* Next line contains $N$ integers $val_1, \ val_2, \ ..., val_N$ where $val_i$ denotes the value of the $i^{th}$ node.
* Next line contains $N - 1$ intgers $parent_1, \ parent_2, \ ..., \ parent_{N-1}$ where $parent_i$ value denotes the parent of the $(i + 1)^{th}$ node.

### Output Format

For each test case, print $N$ space-separated integers in a new line, where $i^{th}$ value represents the required $MEX$ value for node $i$.

### Constraints

* $1 \leq T \leq 10^2$
* $1 \leq N \leq 10^4$
* $1 \leq val[i] \leq 10^9$
* $1 \leq parent[i] \leq N$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
1                               
6
1 3 2 2 4 2
1 1 2 2 5
```

</td>
<td>

```shell
2 2 3 4 2 5                     
```

</td>
</tr>
</table>

$\textbf{Explanation}$

* $Node 1:$ $MEX(1) = 2$
* $Node 2:$ $MEX(1, \ 3) = 2$
* $Node 3:$ $MEX(1, \ 2) = 3$
* $Node 4:$ $MEX(1, \ 3, \ 2) = 4$
* $Node 5:$ $MEX(1, \ 3, \ 4) = 2$
* $Node 6:$ $MEX(1, \ 3, \ 4, \ 2) = 2$

Hence, the required answer is $[2, \ 2, \ 3, \ 4, \ 2, \ 5]$

 
