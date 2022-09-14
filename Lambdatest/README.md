# Lambdatest
> Collection of coding questions asked by Lambdatest during placements at IITs

## Questions Index

* [Lifting Weights](#1-lifting-weights) [IIT-BHU'22]
* [Connected Sum](#2-connected-sum) [IIT-BHU'22]

## 1. Lifting Weights

Ollie is new to the gym and is figuring out the maximum weights she can lift. The maximum capacity of the barbell is given as $maxCapacity$. Each barbell plate has a weight, given by $weights[i]$. Now Ollie has to select as many plates as she can but the total weight of the selected plates should not exceed $maxCapacity$. What is the maximum weight of plates Ollie can add to the barbell?

For example, given barbell plates of weights of $1$, $3$ and $5 \ lbs$ and a barbell of maximum capacity $7 \ lbs$ - the right plates to insert would be $1$ and $5 \ lbs$ $(1 + 5 = 6)$, thus making the right answer $6$.

### Function Description

Complete the `weightCapacity` function.

`weightCapacity` has two parameters:

* $weights$: An array of $n$ integers, where the value of each element $weights[i]$ is the weight of eac place $i$ (where $0 \leq i \lt n$\).
* $maxCapacity$: An integer, the capacity of the barbell.

$\textbf{Returns}$

* $int$: an integer denoting the maximum capacity of items that she can lift.

### Constraints

* $1 \leq n \leq 42$
* $1 \leq maxCapacity \leq 10^9$
* $1 \leq weights[i] \leq 10^9$

---

## 2. Connected Sum

Given a number of nodes and a list of connected pairs, determine the weights of each isoalted set of nodes assuming each node weighs $1$ unit. Then for each weight calculated, sum the ceiling of its square root and return the final sum.

### Example

$graph \textunderscore nodes = 10$

$graph \textunderscore from = [1, 1, 2, 3, 7]$

$graph \textunderscore to = [2, 3, 4, 5, 8]$

<img src="https://github.com/mrsac7/placement-resources/blob/main/Lambdatest/cnt.png" width="500">

There are $graph \textunderscore edges = 5$ edges to consider. There are $2$ isolated sets with more than one node, $\\{1, 2, 3, 4, 5\\}$ and $\\{7, 8\\}$. The ceilings of their square roots are $\sqrt{5} \approx 2.236$ and $ceil(2.236) = 3$, $\sqrt{2} \approx 1.414$ and $ceil(1.414) = 2$. The other three isolated nodes are separate and the sqaure root of their weights is $\sqrt{1} = 1$ respectively. The sum is $3 + 2 + (3 \times 1) = 8$.

### Function Description

Complete the function `connectedSum`. 

`connectedSum` has the following parameter(s):

* $int \ \ graph \textunderscore nodes$: the number of nodes
* $int \ \ graph \textunderscore from[graph \textunderscore edges]$: an array of integers that represents one end of an edge
* $int \ \ graph\\_to[graph\\_edges]$: an array of integers that represents the other end of an edge

$\textbf{Returns}$
* $int$: an integer that denotes the sum of the values calculated

### Constraints

* $2 \leq graph\\_nodes \leq 10^5$
* $1 \leq graph\\_edges \leq 10^5$
* $1 \leq graph\\_from[i], \ graph\\_to[i] \leq n$
* $graph\\_from[i] \neq graph\\_to[i]$


