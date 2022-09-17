# Adobe
> Collection of coding questions appearing in online assessment of Adobe during campus placements at IIT/NITs, and other top engineering colleges in India.


## Questions Index

* [Health Center Networking](#1-health-center-networking) 
* [Supply Station Chain](#2-supply-station-chain) 

## 1. Health Center Networking

In the aftermath of a massive panemic the gorvernment of Arcania has decided to implement reforms to revitalize the health infrastructure of the country. Arcania consists $N$ health centers, each health center $i$ has coordinates $(x[i], \ y[i])$. The government wants to connect the health centers in Arcania, such that in the end, any person who is admitted in any health center can travel to any other health center he/she wants.

Any two health centers can be connected in one of the following ways

* **Medivac Helipad**: The medivac helipad can be built in some health center $i$ with cost $C[i]$. If health center $i$ has a medivac helipad, and health center $j$ has a medivac helipad, then you can travel directly from health center $i$ to health center $j$ and vice versa.
* **Ambulance Lane**: If there is an ambulance lane between health center $i$ and health center $j$, then you can travel between these two health centers in both directions. The cost of building an ambulance lane between health centers $i$ and $j$ is equal to $Dist(i, \ j)$ = $|x[i] - x[j]|$ $+$ $|y[i] - y[j]|$

It is given that you have to build at least one medivac helipad. However, you can choose to build more than one medivac helipad if necessary. Also, you can build as many ambulance lanes as you need, and you can even choose not to build any ambulance lane.

Arcania is affected by an economic slowdown caused by the pandemic. Therefore, the government wants to complete this project in the most economocial manner. Thus, the government has tasked you to find the minimum cost to connect the health center's such that travel is possible from any health center to any health center. Since, the answer can be very large return the answer modulo $(10^9 + 7)$.

### Function Description

Complete the `minimum_cost` function. It has the following parameter(s):

* $int \ \ N$: an integer denoting the number of health centers
* $int \ \ X[n]$: an array of intgers denoting the position of the health center on $X$ axis
* $int \ \ Y[n]$: an array of intgers denoting the position of the health center on $Y$ axis
* $int \ \ Cost[n]$: an array of integers denoting the cost of building Medivac Helipad at a given health center

$\textbf{Returns}$

* $int$: an integer denoting the minimum possible cost so that you can travel from any health center to another MOD $(10^9 + 7)$

### Constraints

* $1 \leq N \leq 1000$
* $0 \leq X[i] \leq 10^9$
* $0 \leq Y[i] \leq 10^9$
* $0 \leq Cost[i] \leq 10^9$

### Sample Tests

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
2                        
1 2
1 2
1 1
```

</td>
<td>

```shell
2                             
```

</td>
</tr>
</table>

$\textbf{Explanation 1}$

The cost of building ambulance lane between the cities is $|2 - 1| + |2 - 1| = 2$ <br>
And you have to build at least one medivac helipad with cost $1$. <br>
So this costs $2$ <br>
So it is better to build $2$ medivac helipads (one in each city) with cost $1 + 1 = 2$

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
2                       
1 2
1 2
1 3
```

</td>
<td>

```shell
3                             
```

</td>
</tr>
</table>

$\textbf{Explanation 2}$

The cost of building ambulance lane between the cities is $|2 - 1| + |2 - 1| = 2$ <br>
And you have to build at least one medivac helipad with cost $1$. <br>
So this costs $3$ <br>
So it is better to build $2$ medivac helipads (one in each city) with cost $1 + 3 = 4$

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
3                       
1 1 1
2 3 4
20 10 40
```

</td>
<td>

```shell
12                             
```

</td>
</tr>
</table>

$\textbf{Explanation 3}$

The best solution is to build one medivac helipad in the second city with cost $10$ <br>
and an ambulance lane between the first city and the second city with cost $|1 - 1| + |2 - 1| = 1$ <br>
and an amublance lane between the thrid city and the second city with cost $|1 - 1| + |2 - 1| = 1$ <br>
So the answer is $10 + 1 + 1 = 12$

## 2. Supply Station Chain

In the aftermath of a massive pandemic the government of Arcania has decided to implement reforms to revitalize the health infrastructure of the country. As a part of one of these reforms the government wants to create a chain of medicine stockpile and supply stations.

The medical supplies manufacturers and wholesalers in Arcania can be decpicted as a collected of $N$ nodes indexed from $0, \ 1, \ 2, \ ..., \ N - 1$. These nodes together form a $\textbf{Tree}$. This tree is rooted at node $0$ which denotes the national drug agency headquarters. Each node has a value depicting their minimum standing inventory written on it. This means that the value of minimum standing inventory for node $i$ is $Val[i]$.

After extensive research the government has devised a threshold parameter $X$. The government plans to use the threshold parameter $X$ to identify **special nodes**. These **special nodes** will serve as a stockpile and supply station of medical supplies in the event of a pandemic. Any node in the tree qualifies to be a **special node** if <ins>XOR of values</ins> of all the nodes in the subtree of this node is <ins>less than or equal to</ins> $X$.

It is further given that a **subtree** of a node $X$ in the tree $T$ consists of node $X$ and all of its descendants in $T$.

Your task is to help the government find the maximum distance between any two **special nodes** so that the government can figure out the minimum standing inventory that needs to be maintained for these supply stations.

$\textbf{Notes}$

* A **Tree** is an undirected graph in which any two vertices are connected by <ins> exactly one </ins> path.
* It is guaranteed that the tree always has at least $2$ special nodes.
* Parent of a node $i$ is given by $Parent[i]$.
* Parent of $0$ is non existent so $Parent[0]$ is always $-1$.

### Function Description

Complete the `findDist` function. It has the following parameter(s):

* $int \ \ N$: an integer denoting the number of nodes
* $int \ \ Parent[n]$: an integer array denoting the parent of each node. $0$ is the root of the noe
* $int \ \ Val[n]$: an integer array denoting the value written on each node
* $int \ \ X$: an integer denoting the threshold parameter

$\textbf{Returns}$

* $int$: an integer denoting the maximum distance between any two special nodes

### Constraints

* $1 \leq N \leq 10^5$
* $1 \leq Parent[i] \leq 10^5$
* $1 \leq Val[i] \leq 10^5$
* $1 \leq X \leq 10^5$

### Sample Tests

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
5                       
-1 0 0 1 1
7 2 2 3 5
3
```

</td>
<td>

```shell
3                             
```

</td>
</tr>
</table>

$\textbf{Explanation 1}$

Special Nodes are nodes indexed $0, \ 2, \ 3$. Max distance is between nodes $2$ and $3$. This distance is $3$.

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
5                       
-1 0 0 1 1
7 2 2 3 5
2
```

</td>
<td>

```shell
1                             
```

</td>
</tr>
</table>

$\textbf{Explanation 2}$

Special Nodes are nodes indexed $0, \ 2$. Max distance is between nodes $0$ and $2$. This distance is $1$.

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
6                       
-1 0 0 1 1 2
7 2 0 3 5 2
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

$\textbf{Explanation 3}$

Special Nodes are nodes indexed $0, \ 2, \ 5$. Max distance is between nodes $0$ and $5$. This distance is $2$.
