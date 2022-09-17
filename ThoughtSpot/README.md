# ThoughtSpot
> Collection of coding questions appearing in online assessment of ThoughtSpot during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Balanced Tree](#1-balanced-tree) [IIT-BHU'22]
* [Minimum Segments](#2-minimum-segments) [IIT-BHU'22]
* [Remove Integers](#3-remove-integers) [IIT-BHU'22]

## 1. Balanced Tree

Given a rooted tree consisting of $n$ nodes, and the nodes numbered from $1$ to $n$ where each node has some number of stones on it represented by the array stones, modify this tree by placing any number of stones on any node any number of times.

We define a $\textbf{balancedTree}$ as a tree where the absolute difference between the number of stones between each pair of adjacent nodes is less than or equal to $1$. Find the minimum number of extra stones required to modify the given tree into a $\textbf{balancedTree}$.

The goal is to modify this tree such that it becomes a $\textbf{balancedTree}$.

### Example

Consider the following tree

<img src="https://github.com/mrsac7/placement-resources/blob/main/Swiggy/tr.png" width="500">

The optimal way to balance the above tree is to add $2$ stones to node $'3'$, $1$ stones to node $'2'$, and $4$ stones to node $'1'$. After doing so, we will get a $\textbf{balancedTree}$, and the minimum number of stones required to do it $2 + 1 + 4 = 7$.

### Function Description

Complete the function `findMinStones`. 

`findMinStones` has the following parameters:

* $tree \textunderscore nodes$: integer denoting the total number of nodes in the tree
* $int \ \ tree \textunderscore from [tree \textunderscore nodes - 1]$: integer array denoting the nodes which share an edge with nodes of $tree \textunderscore to$ array
* $int \ \ tree \textunderscore to [tree \textunderscore nodes - 1]$: integer array denoting the nodes which share an edge with nodes of $tree \textunderscore from$ array
* $int \ \ stones[tree \textunderscore nodes]$: integer array denoting the number of stones on each node


$\textbf{Returns}$

* The function must return an integer value, the minimum number of extra stones required to balance the tree.

### Constraints

* $1 \leq n \leq 2 \times 10^5$
* $0 \leq stones[i] \leq 10^9$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
5 4                             
1 2
2 3
2 4
3 5
5
1 5 7 8 3
```

</td>
<td>

```shell
10                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

<img src="https://github.com/mrsac7/placement-resources/blob/main/Swiggy/exp.png" width="500">

Following are the optimal changes that will make the given tree balanced using minimum stones:

* Add $2$ stones to node $'2'$
* Add $5$ stones to node $'1'$
* Add $3$ stones to node $'5'$

After performing the above $3$ operations, the tree will get balanced. The number of stones used is $2 + 5 + 3 = 10$.

---

## 2. Minimum Segments

Given is an array consisting of $n$ intervals. The $i^{th}$ interval is of type $(a[i], \ b[i])$. Also given is an integer $k$. Add exactly one segment $(a, \ b)$ to the array such that $b - a \leq k$ and the modified array can be separated into the minimum number of connected sets.

A set of segments $(a[1], \ b[1])$, $(a[2], \ b[2])$,..., $(a[n], \ b[n])$ is connected if every point in the segment $(min(a[1], a[2],..., a[n]$, $max(b[1], b[2],..., b[n]))$ is covered by some segment $(a[i], \ b[i])$ in the set.

### Example

The set $[(1, \ 2), \ (2, \ 3), \ (1, \ 5)]$ is connected while the set $[(1, \ 2), \ (3, \ 4)]$ is not because point $2.5$ is not convered by any segment.

Let's consider the array $a = [(1, \ 5)$, $(2, \ 4)$, $(6, \ 6)$, $(7, \ 14)$, $(16, \ 19)]$ and given $k = 2$; Add a segment $(5, \ 7)$ into the array. After adding the segment, separate the array into $2$ connected sets:

* $(1, \ 5)$, $(2, \ 4)$, $(6, \ 6)$, $(7, \ 14)$
* $(16, \ 19)$

However, if we add a segment $(14, \ 16)$ into the array, then we have to separate the array using $3$ connected sets:

* $(1, \ 5)$, $(2, \ 4)$
* $(6, \ 6)$
* $(7, \ 14)$, $(14, \ 16)$, $(16, \ 19)$

So, $2$ connected sets is the minimum answer that we can achieve.

### Function Description

Complete the function `minimumDivision`.

`minimumDivision` has the following parameter(s):

* $a$: an integer array of first parameters of intervals
* $b$: an integer array of second parameters of intervals
* $k$: an integer denoting the maximum range of the segment that can be added

$\textbf{Returns}$

* $int$: an integer denoting the minimum number of sets needed to separate the array after adding one segment.

### Constraints

* $1 \leq n \leq 2 \times 10^5$
* $1 \leq a[i] \leq b[i] \leq 10^9$
* $1 \leq k \leq 10^9$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
4                             
1 2 5 10
2 4 8 11
2
```

</td>
<td>

```shell
2                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

The original intervals are $(1, \ 2)$, $(2, \ 4)$, $(5, \ 8)$, $(10, \ 11)$. Add the segment $(4, \ 5)$ into the array since $5 - 4 \leq 2$. 

After that, we can separate the array into $2$ connected sets:

* $(1, \ 2)$, $(2, \ 4)$, $(5, \ 8)$
* $(10, \ 11)$


---

## 3. Remove Integers

Given the first $2^N$ integers in which $K$ of them are special. We want to remove all the $2^N$ integers. 

There are $3$ choices to remove integers, starting with $2^N$ integers:

1. If the current part contains $L$ integers and $X$ of them are special, the cost of removing all the $L$ integers is $L \times X \times P$ where $P$ is a constant.

2. If the current part contains $L$ integers and none of them is special, the cost of removing all the $L$ integers is $Q$, where $Q$ is a constant.

3. If the current part contains $L$ integers, and $L$ is divsible by $2$, then we have $2$ choices:
    - Calculate the cost of this part by using method $1$ or method $2$
    - Divide this part into two parts containing $\frac{L}{2}$ integers each, then add the costs of those two parts together.
  
Find the minimum cost of removing all $2^N$ integers, modulo $(10^9 + 7)$.

$\textbf{Note}$: We cannot reshuffle integers while dividing the current part into two smaller parts. If the current part contains integers $[1, \ 2, \ 3, \ 4]$, the only correct way to divide it is $[1, \ 2]$ and $[3, \ 4]$.

### Example

$N = 2$ <br />
$P = 2$ <br />
$Q = 1$ <br />
$special\\_integers = [1, \ 3]$

Start with the first $2^N$ integers: $[\textbf{1}, \ 2, \ \textbf{3}, \ 4]$ in which integers $1$ and $3$ are special, shown in bold.

Consider the entire array:

* The length of the segment is $4$, there are $2$ special integers, and $P = 2$. Using method $1$ costs $4 \times 2 \times 2 = 16$.
* Method $3$ can also be used since the length of the segment is divisible by $2$.
* The cost of removing all elements at once is $16$.

Method 3:

Divide the array into two parts: $[\textbf{1}, \ 2]$ and $[\textbf{3}, \ 4]$.

* The part $[\textbf{1}, \ 2]$ contains $1$ special integer.
  - Using method $1$ on this part costs $2 \times 1 \times 2 = 4$.
  - Method $3$ can also be used.
  
* Similarly, the part $[\textbf{3}, \ 4]$ contains $1$ special integer.
  - Using method $1$ costs $2 \times 1 \times 2 = 4$.
  - Method $3$ can also be used.
  
* Hence, we can remove all the integers in $4 + 4 = 8$ with these two segments.

Method 3 again:

Now divide the segments $[\textbf{1}, \ 2]$ and $[\textbf{3}, \ 4]$ into two parts each, yielding $[\textbf{1}]$, $[2]$, $[\textbf{3}]$ and $[4]$.

* Each of the parts with a special number costs $1 \times 1 \times 2 = 2$
* Each of the parts without a special number costs 1.
* The total cost is $2 + 1 + 2 + 1 = 6$.

The minimum cost is $6$.

### Function Description

Complete the function `removeIntegers`.

`removeIntegers` has the following parameters:

* $int \ \ N$: array values range from $1$ to $2^N$, inclusive
* $int \ \ P$: the cost of a special number
* $int \ \ Q$: the cost of a segment with no special numbers
* $int \ \ special\\_integers[K]$: the special numbers

$\textbf{Returns}$

* $int$: the minimum cost to remove all integers, modulo $(10^9 + 7)$.

### Constraints

* $1 \leq N \leq 30$
* $1 \leq P, \ Q \leq 10^4$
* $1 \leq K \leq 10^5$
* $1 \leq special\\_integers[i] \leq 2^N$

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
2
1
8
1 2 3 4 5 6 7 8
```

</td>
<td>

```shell
16                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

The optimal approach is:

Using method $3$: $[\textbf{1}, \ \textbf{2}, \ \textbf{3}, \ \textbf{4}]$ and $[\textbf{5}, \ \textbf{6}, \ \textbf{7}, \ \textbf{8}]$ 

Using method $3$: $[\textbf{1}, \ \textbf{2}]$, $[\textbf{3}, \ \textbf{4}]$, $[\textbf{5}, \ \textbf{6}]$, $[\textbf{7}, \ \textbf{8}]$

Using method $3$: $[\textbf{1}]$, $[\textbf{2}]$, $[\textbf{3}]$, $[\textbf{4}]$, $[\textbf{5}]$, $[\textbf{6}]$, $[\textbf{7}]$, $[\textbf{8}]$

Special integers are marked with the bold case.

Each part costs $1 \times 1 \times 2 = 2$.

Total cost = $2 \times 8 = 16$.
