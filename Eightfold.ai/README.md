# Eightfold.ai
> Collection of coding questions asked by Eightfold.ai during placements at IITs

## Questions Index

* [Stone Cold Mafia](#1-stone-cold-mafia) [IIT-BHU'22]
* [Connecting The Special Nodes](#2-connecting-the-special-nodes) [IIT-BHU'22]
* [Shopping With Wife](#3-shopping-with-wife) [IIT-BHU'22]

## 1. Stone Cold Mafia

Stone Cold is an American actor, producer, television host, and most importantly a famous professional wrestler. he has invented a new game which he named on himself - Stone Cold Mafia. In the game, you need to arrange his trophies on a tray. The size of tray is $N$ and different types of trophies are $K$.

You want to place these trophies on the tray next to each other such that no trophy of the same type is sitting adjacent. Also, there is a special trophy $X$ which means trophies of type $X$ are allowed to place adjacent to each other.

Find the number of such possible arragements $\textbf{mod} \ 10^9 + 7$.

### Input Format

* First line of input: Conains $T$, where $T$ is number of test cases.
* For every test case: The first line contains $N$, $K$, and $X$, where $N$ is the size of tray, $K$ is the type of trophies available, and $X$ is the special trophy that is allowed to place against.

$\textbf{Note}$: $X$ can be greater than $K$.

### Output Format

For every test case print the number of arrangments $\textbf{mod} \ 10^9 + 7$.

### Constraints

* $1 \leq N \leq 10^5$
* $1 \leq X, K \leq 5$

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
3 2 1
5 4 3
```

</td>
<td>

```shell
5                             
469
```

</td>
</tr>
</table>


---

## 2. Connecting The Special Nodes

You are given a graph of $N$ nodes. The graph consists of connected components. The definition of a connected component being a group of nodes in which any two nodes have a path to each other, direct or indirect. Some of the connected components contain a special node and each component contains at most one special node. You are required to maximize the number of edges in the given graph such that it follows these constraints: 

* No self-loop or multiple edges should be present 
* No connected components with more than one special node should be present
* Each node in the graph should belong to a component with exactly one special node


If you add an edge between two nodes that belong to the same component in the graph, then the total cost involved is $0$. Whereas, if you connect two nodes that belong to different components, then the cost is equal to the product of the sizes of both the components. 

Your task is to maximize the number of new edges in the graph that can be added. Also calculate the minimum cost that will be involved in performing the required task.

### Input format

* First line: Three integers $N$, $M$, and $K$ representing the number of nodes, number of edges, and number of special nodes in the graph respectively
* Next $M$ lines: Two integers $u$ and $v$ representing an undirected edge from the node $u$ to node $v$
* Next line: An empty line
* Next line: $K$ space-separated integers each representing the special nodes in a connected component

### Output Format

Print the maximum number of new edges that can be added to the graph and the minimum cost of doing so.

### Constraints

* $1 \leq N \leq 10^5$
* $1 \leq M \leq 2 \times 10^5$
* $K \leq$ the total number of connected components present in the graph.
* It is guaranteed that for any connected component at most one special node exists.
* The given graph does not contain any self-loops or multiple edges.

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
12 7 2                        
1 2
1 3
4 5
4 6
5 7
9 10
11 12
1 4
```

</td>
<td>

```shell
32 28                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

The given graph consist of 5 connected components. $(1, 2, 3)$, $(4, 5, 6, 7)$, $(8)$, $(9, 10)$, $(11, 12)$. $1$ is the special node in $(1, 2, 3)$ and $4$ is the special node in $(4, 5, 6, 7)$.
There is no special node in $(8)$, $(9, 10)$, $(11, 12)$.

For $(1, 2, 3) :-$ <br />
We can add 1 edge from 2 to 3,  cost = 0 (same component).

For $(4, 5, 6, 7) :-$ <br />
We will add 3 edges from 6 to 5, 6 to 7 and 4 to 7. Now we can't add more edges to this component, cost = 0 (same component).

For the remaining nodes (without special nodes) $:-$ <br />
We will first connect $8$ and $(11, 12)$ with cost $2$ and $2$ edges.

Then $(8, 11, 12)$ and $(9, 10)$ with cost $6$ and $6$ edges. (product of their sizes).

Now we have all the non special nodes completely connected.

We can now connect all the $5$ non special nodes to the component $(4, 5, 6, 7)$ with cost $20$ and $20$ edges.

Hence total cost is $28$ and maximum number of edges that can be added are $32$.


---

## 3. Shopping With Wife

Sam is visiting a shopping mall. If this mall is mapped to a $2D$ plane - each coordinate point inside this mall (including the borders) would represent a shop. The bottom-left and top-right coordinates of this mall are $(x_1, \ y_1)$ and $(x_2, \ y_2)$ respectively.

Sam's wife is standing at a point $(x_c, \ y_c)$ either inside or outside the mall.

Sam, being a careful husband, wants to always be within a distance $R$ from his wife. What are the total number of shops that Sam can visit.

### Input Format

* The first line contains four integers $x_1, \ y_1$, $x_2, \ y_2$ $(x_1 < x_2$ and $y_1 < y_2)$
* The second line contains three integers $x_c, \ y_c, \ R$.

### Output Format

Print one number denoting the number of **shops** that Sam can visit considering above restrictions.

### Constraints

* $-10^5 \leq x_1, y_1, x_2, y_2 \leq 10^5$
* $-10^5 \leq x_c, y_c \leq 10^5$
* $0 \leq R \leq 10^5$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
0 0 1 1                        
-7 0 8
```

</td>
<td>

```shell
3                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

* Shops at $(0, 0)$, $(0, 1)$, $(1, 0)$ inside the mall satsify all the conditions.
* Shop at $(1, 1)$ has distance more than $8$ from wife's location $(-7, 0)$
