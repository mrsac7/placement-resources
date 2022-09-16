# Confluent
> Collection of coding questions asked by Confluent during placements at IITs

## Questions Index

* [Hack Tree](#1-hack-tree) [IIT-BHU'22]
* [VM Pricing](#2-vm-pricing) [IIT-BHU'22]

## 1. Hack Tree

You are given a tree with $n$ nodes. Each node has a value has a value assigned with it. The cost of a path is defined as the summation of all the values assigned to nodes that belong to the path.

The root of the tre is node number $1$.

**Cost of path example**

<img src="https://github.com/mrsac7/placement-resources/blob/main/Confluent/dsc.png" width="400">

In the above exmaple the cost of path:
* $6 \rightarrow 5 \rightarrow 3$ $= 93$
* $4 \rightarrow 3 \rightarrow 1$ $= 41$


A vertical path in a tree is the path that is going up towards the root of the tree. It is not necessary for the path to end at the root.

Given a tree with $n$ nodes an an integer $k$. Find the number of vertical paths such that the (cost of the path) $\\% \ k = 0$ where $\\%$ represents the modulo operation.

$\textbf{Note}$: The modulo operation returns the remainder of a division after one number is divided by another. For example: $5 \ \\% \ 2 = 1$.

### Example

$k = 2$

$tree = $

<img src="https://github.com/mrsac7/placement-resources/blob/main/Confluent/exp.png" width="400">

There are a total of $8$ vertical paths:

1. $1$
2. $2$
3. $4$
4. $2 \rightarrow 1$
5. $4 \rightarrow 1$
6. $3$
7. $3 \rightarrow 4$
8. $3 \rightarrow 4 \rightarrow 1$

But only $(2 \rightarrow 1)$, $(4 \rightarrow 1)$, $(3 \rightarrow 4)$ have (cost of the path) $\\% \ k = 0$.

Hence the answer is $3$.

### Function Description

Complete the function `countVerticalPaths`.

`countVerticalPaths` has the following parameters:

* $cost$: the array representing the value of each node
* $edge\\_nodes$: number of nodes in the tree
* $edge\\_from$: integer array where the $i^{th}$ integer denotes one endpoint of the $i^{th}$ edge.
* $edge\\_to$: integer array where the $i^{th}$ integer denotes the other endpoint of the $i^{th}$ edge
* $k$: an integer

$\textbf{Returns}$

* $int$: the number of vertical paths with (cost of the path) $\\% \ k = 0$
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

<img src="https://github.com/mrsac7/placement-resources/blob/main/Confluent/stc.png" width="400">

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

A cloud service provider offers quantity discounts based on the number of virtual machines a customer needs. Their offerings vary from $2$ to $2000$ instances. When pricing is requessted, the customer's representative refers to a list of past pricing. Given a list of past price quotes and the number of instances a customer needs, determine the per-instance price for the customer.

The method for determining price is as follows:

* If the number of instances needed is exactly the same as the quantity for a prior customer, the unit price is that price.
* If there is a price for a larger number and a price for a smaller number of instances, linearly interpolate the price of the quantity needed from the unit prices for the closest smaller and larger quantities.
* If the quantities for which there is past data are *all smaller* or *all larger* than the amount needed, then linearly extrapolate the unit price from the $2$ points closest to the quantity needed.
* Sometimes, price quotes lapse. When that happens, the old pricing is overwritten with either a $0$ or a negative number. The quantities associated with zero or negative unit prices must be disregarded.

For example, assume the price breaks occur for $instances = [25, \ 50, \ 100]$ units at $price = [5.0, \ 4.0, \ 3.0]$. A diagram follows with pricing for $75$ and $150$ units. In the graph, price versus quantity for given values are in blue. The target numbers of instances and the linear extrapolation are plotted in red.

<img src="#">

### Function Description

Complete the function `interpolate`. 

`interpolate` has the following parameter(s):

* $n$: an integer that denotes the number of instances required 
* $instances[instances[0], \ ... \, instances[m - 1]]$: an array of integers in increasing order, each a number of instances ordered in the past
* $price[price[0], \ ... \, price[m - 1]]$: an array of floating point numbers where $price[i]$ is the unit price when $instances[i]$ units were purchased.

$\textbf{Returns}$

* $string$: a string representing the expected price per unit rounded to two places after the decimals

$\textbf{Note}$: The interpolate function's array parameters may be vectors, where necessitated by the language.

### Constraints

* $2 \leq n \leq 2000$
* $1 \leq m \leq 100$
* $|instances| = |price| = m$
* $instances[i] < instances[j]$, where $0 \leq i \lt j \lt m$

### Sample Tests

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
25                        
5
10 25 50 100 500
2.46 2.58 2.0 2.25 3.0
```

</td>
<td>

```shell
2.58                        
```

</td>
</tr>
</table>

$\textbf{Explanation 1}$

The follwing arguments are passed to the interpolate function:

$n = 5$

$instances = {10, \ 25, \ 50, \ 100, \ 500}$

$price = {2.46, \ 2.58, \ 2.0, \ 2.25, \ 3.0}$

The quantity $25$ is in the database, so $vmPricing$ returns the unit price associated with that quantity, $2.58$, cast as string.

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
2000                        
5
10 25 50 100 500
27.32 23.13 21.25 18.00 15.50
```

</td>
<td>

```shell
6.13                        
```

</td>
</tr>
</table>

$\textbf{Explanation}$

The following arguments are passed to the interpolate function:

$n = 2000$

$instances = {10, \ 25, \ 50, \ 100, \ 500}$

$price = {27.32, \ 23.13, \ 21.25, \ 18.00, \ 15.50}$

<img src="#">

The quantity $2000$ is not in the database, and is also larger than any amount in the database. The closest two price points to it are $15.5$ for $500$ instances and $18.00$ for $100$ instances. Linear extrapolation from these two points means reducing the price by $2.5$ for every increase in the amount of $400$. There are $3.75$ jumps of $400$ from $500$ to $2000$, or $4.75$ jumps of $400$ from $100$ to $2000$. The unit price for $2000$ is therefore $15.5 - 2.5 \times 3.75$ or $18 - 2.5 \times 4.75$. Both expressions evaluate to $6.125$. The function should round this to a scale of $2$ decimal places and return th rounded result, $6.13$, as a string.
