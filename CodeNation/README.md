# CodeNation
> Collection of coding questions appearing in online assessment of CodeNation during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Omega Primes](#1-omega-primes) [IIT-BHU'22, IIT-K'22]
* [Root It](#2-root-it) [IIT-BHU'22, IIT-K'22]
* [Shortest Path Function](#3-shortest-path-function) [IIT-BHU'22, IIT-K'22]

## 1. Omega Primes

### Problem Description

Carl is bored of playing with ordinary prime numbers. Thus, he comes up with some special numbers called Omega Primes. 

A number $X$ is called Omega Prime, if there exists no perfect square $Y$ ( $Y > 1$ ) such that $Y$ divides $X$.

For example, $6$ is an Omega Prime because there is no pefect square except $1$ that divides $6$.

On the other hand, $12$ is not an Omega Prime as $4$ (which is a perfect square) is a divisor of $12$.

Carl decides to play a bit more with Omega Primes. He has an array $A$ of integers. Carl wants to find the number of different subsets such that the product of elements for each subset, results in an Omega Prime. Help Carl find this number.

Since this number can be large, output the answer modulo $10^9 + 7$.

### Problem Constratints

$1 \leq Length \ of \ A \leq 2\times10^4$

$1 \leq A[i] \leq 30$

### Input Format

The first argument is the integer array $A$.

### Output Format

Return an integer denoting the number of different desired subsets modulo $10^9 + 7$.

### Example Input

<table>
<tr>
<td> Input 1:</td>
</tr>
<tr>
<td>

```shell
A = [2, 4, 3]                                 
```

</td>
</tr>

<tr>
<td> Input 2:</td>
</tr>
<tr>
<td>

```shell
A = [2, 4, 3]                                 
```

</td>
</tr>

</table>

### Example Output

<table>
<tr>
<td> Output 1:</td>
</tr>
<tr>
<td>

```shell
3                                 
```

</td>
</tr>

<tr>
<td> Output 2:</td>
</tr>
<tr>
<td>

```shell
3                                 
```

</td>
</tr>

</table>

### Example Explanation

<table>
<tr>
<td> Explanation 1: </td>
</tr>
<tr>
<td>

```shell
The different subsets are [0, 2], [0], [2]. (the numbers denote the indices of the array elements)
```

</td>
</tr>

<tr>
<td> Explanation 1: </td>
</tr>
<tr>
<td>

```shell
The different subsets are [0], [1], [2].
Note, the Omega Primes generated are same but the subset used to generate them are different.
```

</td>
</tr>

</table>

---

## 2. Root It

### Probelm Description

You are given a tree with $A$ vertices. At each vertex some number of candies are placed. Vertex $i$ contains $B[i]$ candies, given in the input.

You are also given a $2$-D array $C$ which denotes that there is an undirected edge between $C[i][0]$ and $C[i][1]$.

You have to choose a starting vertex in the beginning or a $root$, and you are only permitted to move from vertex to vertex only if an edge connects them. You are not allowed to visit any visited vertex again.

For every possible selection of the root of the tree, you write the value of $Maximum \ candies \ you \ can \ obtain$ $-$ $Minimum \ candies \ you \ can \ obtain$ using the same root, in your notebook.

$Note:$ While traversing the tree, you can stop at any vertex you want. In other words, it is not necessary to start from the root and end in a leaf.

You have to tell the maximum of all the values written in the notebook.

### Problem Constraints
$1 \leq A \leq 10^5$

$1 \leq B[i] \leq 10^3$

$1 \leq C[i][0], C[i][1] \leq A$

### Input Format

The first argument is the integer $A$.
The second argument is an integer array $B$.
The third argument is a $2$D interger array $C$.

### Output Format

Return the maximum integer written on the notebook.

### Example Input

<table>
<tr>
<td> Input 1:</td>
</tr>
<tr>
<td>

```shell
A = 3                                 
B = [3, 1, 1]
C = [[1, 2], [1, 3]
```

</td>
</tr>

<tr>
<td> Input 2:</td>
</tr>
<tr>
<td>

```shell
A = 2                                 
B = [10, 20]
C = [[1, 2]]
```

</td>
</tr>

</table>

### Example Output

<table>
<tr>
<td> Output 1: </td>
</tr>
<tr>
<td>

```shell
4                                 
```

</td>
</tr>

<tr>
<td> Output 2: </td>
</tr>
<tr>
<td>

```shell
20                                 
```

</td>
</tr>

</table>

### Example Explanation

<table>
<tr>
<td> Exaplanation 1:</td>
</tr>
<tr>
<td>

```shell
The Maximum sum of candies - Minimum sum of candies for each possible selection of root is given below:
Root as vertex 1: Max(sum) - Min(sum) = 4 - 3 = 1
Root as vertex 2: Max(sum) - Min(sum) = 5 - 1 = 4
Root as vertex 3: Max(sum) - Min(sum) = 5 - 1 = 4
Therefore, the maximum among all these values is 4.
```

</td>
</tr>

<tr>
<td> Explanation 2: </td>
</tr>
<tr>
<td>

```shell
Only optimal way is to choose vertex 1 as a root and traverse the edge. So Maximum Sum - Minimum Sum = 20.
```

</td>
</tr>

</table>

---

## 3. Shortest Path Function

### Problem Description

Given a tree with $N$ vertices, find the sum of the following function over all vertices of the tree.

$F(x) =$ (Number of all pair shortest paths that contains $x$ but neither start at $x$ nor end at $x$) modulo $10^9 + 7$.

You are given a $2$-D vector $A$ of size $N - 1$ containing all the edges of the tree. This means $A[i][0]$ is connected to $A[i][1]$.

Since the answer can be very large, output it modulo $10^9 + 7$.

### Problem Constraints

$1 \leq N \leq 10^5$

$1 \leq A[i][0], A[i][1] \leq N$

### Input Format

The first argument is the $2$-D integer array $A$.

### Output Format

Return a single integer as per the problem given above.

### Example Input

<table>
<tr>
<td> Input 1:</td>
</tr>
<tr>
<td>

```shell
A = [[1, 2],                                   
     [2, 3]]
```

</td>
</tr>

<tr>
<td> Input 2:</td>
</tr>
<tr>
<td>

```shell
A = [[1, 2],                                   
     [2, 3],
     [1, 4]]
```

</td>
</tr>

</table>

### Example Output

<table>
<tr>
<td> Output 1: </td>
</tr>
<tr>
<td>

```shell
1                                 
```

</td>
</tr>

<tr>
<td> Output 2: </td>
</tr>
<tr>
<td>

```shell
4                                 
```

</td>
</tr>

</table>

### Example Explanation

<table>
<tr>
<td> Exaplanation 1:</td>
</tr>
<tr>
<td>

```shell
F(1) = 0, F(2) = 1 (Path from 1 to 3), F(3) = 0.     
Hence, their sum is 1.
```

</td>
</tr>

<tr>
<td> Explanation 2: </td>
</tr>
<tr>
<td>

```shell
F(1) = 2, F(2) = 2, F(3) = 0, F(4) = 0.                  
Hence, their sum is 4.
```

</td>
</tr>

</table>


