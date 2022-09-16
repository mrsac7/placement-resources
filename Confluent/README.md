# Confluent
> Collection of coding questions asked by Confluent during placements at IITs

## Questions Index

* [HackTree](#1-hack-tree) [IIT-BHU'22]
* [VM Pricing](#2-vm-pricing) [IIT-BHU'22]

## 1. Hack Tree

You are given a tree with $n$ nodes. Each node has a value has a value assigned with it. The cost of a path is defined as the summation of all the values assigned to nodes that belong to the path.

The root of the tre is node number $1$.

**Cost of path example**

<img src="#">


A vertical path in a tree is the path that is going up towards the root of the tree. It is not necessary for the path to end at the root.

Given a tree with $n$ nodes an an integer $k$. Find the number of vertical paths such that the (cost of the path) $\\% \ k = 0$ where $\\%$ represents the modulo operation.

$\textbf{Note}$: The modulo operation returns the remainder of a division after one number is divided by another. For example: $5 \\% 2 = 1$.

### Example

$k = 2$

$tree = $

There are a total of $8$ vertical paths:

1. $1$
2. $2$
3. $4$
4. $2 \rightarrow 1$
5. $4 \rightarrow 1$
6. $3$
7. $3 \rightarrow 4$
8. $3 \rightarrow 4 \rightarrow 1$

But only $(2 \rightarrow 1)$, $(4 \rightarrow 1)$, $(3 \rightarrow 4)$ have (cost of the path) $\\% k = 0$.

Hence the answer is $3$.

### Function Description

Complete the function `countVerticalPaths`.

`countVerticalPaths` has the following parameters:

* $cost$: the array representing the value of each node
* $edge_nodes$: number of nodes in the tree
* $edge_from$: integer array where the $i^{th}$ integer denotes one endpoint of the $i^{th}$ edge.
* $edge_to$: integer array where the $i^{th}$ integer denotes the other endpoint of the $i^{th}$ edge
* $k$: an integer

$\textbf{Returns}$

* $int$: the number of vertical paths with (cost of the path) $\\% k = 0$
* $\textbf{Note}$: The tests are generated in such a way that the returned value fits in int32

### Constraints

* $1 \leq n \leq 2 \times 10^5$
* $0 \leq cost[i] \leq 10^8$
* $1 \leq k \leq 10^5$

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
2 3 0 3 0
5 4
2 3
3 1
3 4
3 5
3
```

</td>
<td>

```shell
7                        
```

</td>
</tr>
</table>

$\textbf{Explanation}$

There are $7$ vertical paths following the given condition:

<img src="#">

These paths are:

1. $4$
2. $4 \rightarrow 3$
3. $2$
4. $2 \rightarrow 3$
5. $5$
6. $3$
7. $5 \rightarrow 3$

Hence the answer is $7$.

---

## 2. VM Pricing

A cloud 
