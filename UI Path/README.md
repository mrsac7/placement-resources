# UI Path
> Collection of coding questions asked by UI Path during placements at IITs

## Questions Index

* [Grouping Marbles](#1-grouping-marbles) [IIT-BHU'22]
* [Maximum Common Companies](#2-maximum-common-companies) [IIT-BHU'22]
* [Paths to a Goal](#3-paths-to-a-goal) [IIT-BHU'22]

## 1. Grouping Marbles

Grouping marbles is a number game that involves arranging different sets of marbles by their size.

More formally, a player is given $n$ marbles, each having a unique number from $1$ to $n$ associated with it. Initially, these marbles are divided into $3$ groups $groupA$, $groupB$, and $groupC$ of sizes $n_1$, $n_2$ and $n_3$ respectively.

Arrange them in such a way that if we sort each individual group independently in increasing order and create a list by appending to the list:

* All the elements of $groupA$ from smallest to largest
* Followed by all the elements of $groupB$ from smallest to largest
* Followed by all the elements of $groupC$ from smallest to largest

then, the resultant list contains all numbers from $1$ to $n$ sorted in increasing order.

This can be done through a series of moves. In one moe, the player moves one marble from one group to some other group. The task is to return the minimum number of moves in which the player can obtain the desired arrangement.

$\textbf{Note}$: The sizes of the $3$ groups need not remain the same after the series of moves Also, it is possible that after the series of moves, some groups do not have any marbles. It is guaranteed that initially, each marble is part of one and only one group.

For example,

Given $n = 7$, 

$n_1 = 2$, $groupA = [2, 3]$, 

$n_2 = 3$, $groupB = [1, 4, 6]$,

$n_3 = 2$, $groupC = [5, 7]$

the minimum number of moves required to obtain the desired arragement would be $2$. This can be done by first moving $1$ from $groupB$ to $groupA$ and then moving $5$ from $groupC$ to $groupB$.

### Function Description

Complete the function `getMinMoves`.

`getMinMoves` has the following parameter(s):

* $groupA[groupA[0],...groupA[n_1 - 1]]$: An array of integers corresponding to the marbles initially present in $groupA$.
* $groupB[groupB[0],...groupB[n_2 - 1]]$: An array of integers corresponding to the marbles initially present in $groupB$.
* $groupC[groupC[0],...groupC[n_3 - 1]]$: An array of integers corresponding to the marbles initially present in $groupC$.

$\textbf{Returns}$

* $int$: an integer corresponding to the minimum number of moves needed to obtain the desired arrangement.

### Constraints

* $1 \leq n_1, \ n_2, \ n_3 \leq 2 \times 10^5$
* $1 \leq n_1 + n_2 + n_3 \leq 2 \times 10^5$


---

## 2. Maximum Common Companies

There are $friends \textunderscore nodes$ friends, numbered from $1$ to $friends \textunderscore nodes$, who buy wholesale products from different companies. There are $friends \textunderscore edges$ pairs of friends where each pair of friends is connected by the common company they buy products from. Companies are numbered from $1$ to $100$. Note that if $x[i]$ and $y[i]$ are connected by a company $c[i]$, and $y[i]$ and $z[i]$ are also connected by the company $c[i]$, then $x[i]$ and $z[i]$ are also said to be connected by $c[i]$. Find the maximal product of $x[i]$ and $y[i]$ that share the largest group of friends which is connected by a common company.

### Example

| From &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | To &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Company &nbsp; &nbsp; &nbsp; |
| -------- | -------- | -------- |
| 1        | 2   | 51       |
| 7        | 3   | 51       |
| 5        | 6   | 51       |
| 10       | 8   | 51       |
| 6        | 9   | 51       |
| 2        | 3   | 51       |

Everyone uses the same company, but not everyone is connected. A graphical representation is:

<img src="https://github.com/mrsac7/placement-resources/blob/main/Ui%20Path/max.png" width="500">

the largest group is $[1, 2, 3, 7]$ and its largest elements are $3$ and $7$. Their product is $21$.

### Function Description

Complete the function `countCompanies`.

`countCompanies` has the following parameter(s):

* $friends \textunderscore nodes$: an integer the number of friends
* $friends \textunderscore from[n]$: an integer array where each element denotes the first friend in the pair
* $friends \textunderscore to[n]$: an integer array where each element denotes the second friend in the pair
* $friends \textunderscore weight[n]$: an integer array where each element denotes a company used by both friends

$\textbf{Returns}$

* $int$: an integer that represetns the product of the maximum two friend numbers in the largest group

### Constraints

* $2 \leq friends \textunderscore nodes \leq 100$
* $1 \leq friends \textunderscore edges \leq$ $min(200, \frac{friends \textunderscore nodes \ \times \ (friends \textunderscore nodes - 1)}{2})$
* $1 \leq friends \textunderscore weight[i] \leq 100$
* $1 \leq friends \textunderscore from[i], \ friends \textunderscore to[i] \leq friends \textunderscore nodes$
* $1 \leq friends \textunderscore weight[i] \leq friends \textunderscore edges$
* $friends \textunderscore from[i] \neq friends \textunderscore to[i]$
* Each pair of friends can be connected by more than one compnay.

---

## 3. Paths to a Goal

Given a number line from $0$ to $n$ and a string denoting a sequence of moves, determine the number of subsequence of those moves that lead from a give point $x$ to end at another point $y$. Moves will be given as a sequence of $l$ and $r$ instructions. An instruction $l = left \ movement$, so from position $j$ the new position is $j - 1$, and an instruction $r = right \ movement$, so from position $j$ the new position woulbe $j + 1$.

For example, given a number line from $0$ to $6$, and a sequence of moves $rrlrlr$, the number of subsequnce that lead from $1$ to $4$ on the number line is $3$, as shown below:

<img src="https://github.com/mrsac7/placement-resources/blob/main/UI%20Path/path.png" width="500">

$\textbf{Note}$: Subsequnces are created by deleting $0$ or more elements from a sequnce without changing the order. Return the answer modulo $(10^9 + 7)$.

### Function Description

Complete the function `distinctMoves`. The function must returm an integer that represents the number of distinct subsequnces. As the number may be large, return the value modulo $(10^9 + 7)$.

`distinctMoves` has the following parameter(s):

* $s$: a string that represents a sequence of moves
* $n$: an integer that represents the upper bound of the number line
* $x$: an integer that represents the starting point
* $y$: an integer that represents the ending point

### Constraints

* $1 \leq |s| \leq 10^3$
* $0 \leq x, \ y \leq n \leq 2500$
