# Swiggy
> Collection of coding questions asked by Swiggy during placements at IITs

## Questions Index

* [Activate Fountain](#1-activate-fountain) [IIT-BHU'22]
* [Perfect Substring](#2-perfect-substring) [IIT-BHU'22]
* [Balanced Tree](#3-balanced-tree) [IIT-BHU'22]

## 1. Activate Fountain

Fountains are installed at every position along a one-dimensional garden of length $n$. Array $locations[]$ represents the coverage limit of these fountains. The $i^{th}$ fountain (where $1 \leq i \leq n$ ) has a coverage limit of $locations[i]$ that can range from the position $max(i - locations[i], \ 1)$ to $min(i + locations[i], \ n)$. In other words, the fountains do not reach outside the boundaries of the garden. In the beginning, all the fountains are switched off. Determine the minimum number of fountains that need to be activated to cover the $n$ length garden by water.

### Example

$n = 3$

$locations[] = {1, \ 2, \ 1}$, then

For position $1$: $locations[1] = 0$, $max(1 - 1, \ 1)$ to $min(1 + 1, \ 3)$ gives range = $1$ to $2$

For position $2$: $locations[2] = 2$, $max(2 - 2, \ 1)$ to $min(2 + 2, \ 3)$ gives range = $1$ to $3$

For position $1$: $locations[3] = 1$, $max(3 - 1, \ 1)$ to $min(3 + 1, \ 3)$ gives range = $2$ to $3$

<img src="https://github.com/mrsac7/placement-resources/blob/main/Swiggy/ftn.png" width="500">

For the entire length of this garden to be covered, only the fountain at position $2$ needs to be activated.

### Function Description

Complete the function `fountainActivation`.

`fountainActivation` has the following parameter:

* $int \ \ locations[n]$: the fountain locations

$\textbf{Returns}$

* $int$: the minimum number of fountains that must be activated

### Constraints

* $1 \leq n \leq 10^5$
* $0 \leq locations[i] \leq min(n, \ 100)$ (where $1 \leq i \leq 10^5$ )


---

## 2. Perfect Substring

A string comprised of digits from $0$ to $9$ contains a perfect substring if all the elements within a substring occur exactly $k$ times. Calculate the number of perfect substrings in $s$.

### Example

$s = 1102021222$

$k = 2$

The $6$ perfect substrings are:

1. $s[0:1] = 11$
2. $s[0:5] = 110202$
3. $s[1:6] = 102021$
4. $s[2:5] = 0202$
5. $s[7:8] = 22$
6. $s[8:9] = 22$

### Function Description

Complete the function `perfectSubstring`.

`perfectSubstring` has the following parameters:

* $str \ \ s$: a string where the value of each element $s[i]$ described by the character at position $i$ (where $0 \leq i \lt n)
* $int \ \ k$: an integer that denotes the required frequency of the substring

$\textbf{Returns}$

* $int$: an integer that represents the number of perfect substrings in the given string

### Constraints

* $1 \leq sizeof (s) \leq 10^5$
* $0 \leq s[i] \leq 9$ (where $0 \leq i \lt n$ )
* $1 \leq k \leq 10^5$




---

## 3. Balanced Tree

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

