# Indeed
> Collection of coding questions asked by Indeed during placements at IITs

## Questions Index

* [Almost Sorted](#1-almost-sorted) [IIT-BHU'22]
* [Shared Interest](#2-shared-interest) [IIT-BHU'22]

### 1. Almost Sorted

An array of integers is $\textbf{almost sorted}$ if at most one element can be deleted from it to make it perfectly sorted, ascending. For example, arrays $[2, 1, 7]$, $[13]$, $[9, 2]$ and $[1, 5, 6]$ are almost sorted because they have $0$ or $1$ elements out of place. The arrays $[4, 2, 1]$, $[1, 2, 6, 4, 3]$ are not because they have more than one element out of place. Given an array of $n$ unique integers, determine the minimum number of elements to remove so it becomes almost sorted.

### Example

$arr = [3, 4, 2, 5, 1]$

Remove $2$ to get $arr' = [3, 4, 5, 1]$ or remove $1$ to get $arr' = [3, 4, 2, 5]$, both of which are almost sorted. The minimum number of elements that must be removed in this case is $1$.

### Function Description

Complete the function `minDeletions`. 

`minDeletions` has the following parameter(s):

* $int \ \ arr[n]$: an unsorted array of integers

$\textbf{Returns}$:
* $int$: the minimum number of items that must be deleted to create an almost sorted array

### Constraints

* $1 \leq n \leq 10^5$
* $1 \leq arr[i] \leq 10^9$

---

### 2. Shared Interest

Given a graph of friends who have different interests, determine which groups of friends have the most interests in common. Then use a little math to determine a value to return.

The graph will be represetned as a series of nodes numbered consecutively from $1$ to $friends_nodes$. Friendships have evolved based on interests which will be represented as weights in the graphs. Any members who share the same interest are said to be connected by that interest. Once the node pairs with the maximum number of shared interests are determined, multiply the $friends_nodes$ of the resutling node pairs and return the maximal product.

### Example

$friends \textunderscore node = 4$

$friends \textunderscore edges = 5$

$friends \textunderscore from = [1, 1, 2, 2, 2]$

$friends \textunderscore to = [2, 2, 3, 3, 4]$

$friends \textunderscore weight = [2, 3, 1, 3, 4]$

| From &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | To &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Weight &nbsp; &nbsp; &nbsp; |
| -------- | -------- | -------- |
| $1$        | $2$    | $2$        |
| $1$        | $2$    | $3$        |
| $2$        | $3$    | $1$        |
| $2$        | $3$    | $3$        |
| $2$        | $4$    | $4$        |

<img src="https://github.com/mrsac7/placement-resources/blob/main/Indeed/gph.png" width="300">

The graph shows the following connections:

| Weight &nbsp; &nbsp; &nbsp; <br /> (Interest) &nbsp; &nbsp; &nbsp; | Connectons &nbsp; &nbsp; &nbsp; |
| -------- | -------- |
| $1$        | $2, 3$   |
| $2$        | $1, 2$   |
| $3$        | $1, 2, 3$   |
| $4$        | $2, 4$   |

* Node pair $(2, 4)$ shares only $1$ interest $(4)$ and node pair $(1, 3)$ shares $1$ intereste $(3)$.
* Node pair $(1, 2)$ shares $2$ interests (interests $2$ and $3$ ) and node pair $(2, 3)$ shares also $2$ interests (interest $1$ and $3$ ). So, the maximum number of shared interests is $2$.
* Multiply the $friends \textunderscore nodes$ of the resulting node pairs: $1 \times 2 = 2$ and $2 \times 3 = 6$
* The maximal product is $6$.

### Function Description

Comeplete the function `maxShared`.

`maxShared` has the following parameter(s):
* $int \ \ friends \textunderscore nodes$: number of nodes
* $int \ \ friends \textunderscore from[friends \textunderscore edges]$: the first part of node pairs
* $int \ \ friends \textunderscore to[friends \textunderscore edges]$: the other part of node pairs
* $int \ \ friends \textunderscore weight[friends \textunderscore edges]$: the interests of node pairs

$\textbf{Returns}$:
* $int$: maximal interger product of all node pairs sharing the most interests.

### Constraints

* $2 \leq friends \textunderscore nodes \leq 100$
* $1 \leq friends \textunderscore edges \leq$ $min(200, \frac{friends \textunderscore nodes \ \times \ (friends \textunderscore nodes - 1)}{2})$
* $1 \leq friends \textunderscore weight[i] \leq 100$
* $1 \leq friends \textunderscore from[i], \ friends \textunderscore to[i] \leq friends \textunderscore nodes$
* $1 \leq friends \textunderscore weight[i] \leq friends \textunderscore edges$
* $friends \textunderscore from[i] \neq friends \textunderscore to[i]$
* Each pair of friends can be connected by zero or more interests.



