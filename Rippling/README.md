# Rippling
> Collection of coding questions asked by Rippling during placements at IITs

## Questions Index

* [So Many Plots](#1-so-many-plots) [IIT-BHU'22]
* [Max Divisor Tree](#2-max-divisor-tree) [IIT-BHU'22]
* [Maximum Force](#3-maximum-force) [IIT-BHU'22]

## 1. So Many Plots

Your friend is a property tycoon and owns many plots of a given area.

However, he wants to merge the plots to make one big plot, for which he goes to an Agent.

The agent tells him that in one operation, any two plots can be merged, and in return, he will receive one plot of are $A_x + A_y$ (where $A_x$ and $A_y$ are the areas of two plots merged in one operation) and the resulting plot will be added to his inventory of plots again, but the cost of one operation is equal to the merged area i.e. $Cost = A_x + A_y$.

This operation can be performed until he is left with one plot.

**Help him merge the plots such that in the end, he is left with one plot whose area is the sum of the all his current plots, but the cost shall remain minimum.**

Also, let him know if it is profitable to merge the plots.

You are given the cost per unit area of each plot.

**The total cost of the plots** = $\sum$ Area * cost per unit area

**He considers it profitable to merge them if the cost to merge the plots is less than the total cost of the plots.**

### Example

$Assumptions$

* $N = 2$
* $array \ plots = [10, 20]$
* $array \ cost_arr = [1, 1]$

$Approach$

**The total costs of the plots** = $\sum$ Area * cost per unit area = $10 \times 1 + 20 \times 1 = 30$

**The cost to merge the plots** $[10, 20]$ is $10 + 20 = 30$

**As Cost to merge the plots is not less than the Total cost of the plots, Therefore it is not profitable to merge them.**

### Function description

Complete the `solution` function. This function takes the following $3$ parameters and print two lines. In the first line print minimum cost to merge all the plots and the next line print $YES$ if it is profitable to merge the plots otherwise print $NO$.

* $N$: Represents the number of plots
* $plots$: Represents the array of length $N$ denoting the areas of each plot
* $costs_arr$: Represents the array of length $N$ denoting the cost per unit area of each plot

### Input

* The first line contains $N$, the number of plots.
* The next line contains $N$ integers, which denote the areas of each plot separated by space.
* The next line contains $N$ integers, denote the Cost per unit area of each plot separated by space.

### Output

Print two lines, print the minimum cost to achieve one plot of the area after merging all the plots and the next line print $YES$ if it is profitable to merge the plots otherwise print $NO$.

### Constraints

* $1 \leq N \leq 10^4$
* $1 \leq A_i \leq 10^4$
* $1 \leq Cost \ per \ unit \ Area \leq 10$

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
5                            
10 20 35 70 150
2 4 6 1 3
```

</td>
<td>

```shell
515                            
YES
```

</td>
</tr>
</table>




---

## 2. Max Divisor Tree

Let a tree exists with the root value $N$. The property of this tree is that each of its nodes branches out to the nodes with a value equal to one of its divisors (except $1$ and the number itself). What maximum height the tree can have?

$Note$: The height of a tree is defined as the number of edges in its longest path from the root to a leaf node.

### Example

Consider $N = 8$. You must determine the maximum height of the tree under the given conditions:

* The root of the tree is $8$. It branches out two nodes with values $2$ and $4$.
* Node $4$ can again branch out a node with value $2$.

Therefore, the maximum height of the tree is $2$. The path looks like this: $8 \rightarrow$ $4 \rightarrow$ $2$

### Function Description

Complete the `solve` function. This function takes the following parameter and returns the answer.
* $N$: Represents the root of the tree.

### Input Format

* The first line and the only line of input consists of an integer $N$ denoting the root value of the tree.

### Output

* Output a single integer denoting the maximum height of the tree

### Constraints

* $1 \leq N \leq 10^6$

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
10                            
```

</td>
<td>

```shell
1                            
```

</td>
</tr>
</table>

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
6666                          
```

</td>
<td>

```shell
3                            
```

</td>
</tr>
</table>

---

## 3. Maximum Force

Alex is studying about Newton Gravitational Force and an idea occured in his mind.

He has $N$ objects placed in a line from $1$ to $N$ and the distance between adjacent objects is $1$ metre. He is interested in knowing the maximum Gravitational Force between all the pairs present between the $L_{th}$ object and the $R_{th}$ object.

You are given Gravitational force (magnitude) between all pairs of different objects and $Q$ queries of the form $L$ and $R$. Alex thought that this is easy so he also wanted to know the maximum product of masses between any two objects in the given range along with the maximum Force.

$Note$: The Force between the same objects is undefined and each object is considered as point object having some mass.

The magnitude of the attractive force $F$ is equal to $G$ (the gravitational constant, a number the size of which depends on the system of units used and which is a universal constant) multiplied by the product of the masses ( $M_1$ and $M_2$ ) and divided by the square of the distance $R$:

i.e. $F = G\frac{M_1 * M_2}{R^2}$, here for the calculation purpose we consider $\textbf{G = 1}$.

### Example

Let's assume that $N$ is $4$ and the forces between all the $4$ objects are as follows :-

Force between $1$ and $2$ is $1$
Force between $1$ and $3$ is $4$
Force between $1$ and $4$ is $3$
Force between $2$ and $3$ is $6$
Force between $2$ and $4$ is $8$
Force between $3$ and $4$ is $4$

Now for query $(1, 3)$ or when $L = 1$ and $R = 3$. The pairs that lie completely in the range are :- $(1, 2),$ $(1, 3), (2, 3)$.


| Pair &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Force &nbsp; &nbsp; &nbsp; <br /> $(Given)$ &nbsp; &nbsp; | Product of mass <br /> $(Force * dist^2)$ |
| -------- | -------- | -------- |
| $(1, 2)$        | $1$   | $(1 \times (2 - 1)^2 = 1$ |
| $(1, 3)$        | $4$   | $(4 \times (3 - 1)^2 = 16$ |
| $(2, 3)$        | $6$   | $(6 \times (3 - 2)^2 = 6$ | 

From the above table we can see that among the pairs that are in the range for this query, maximum force is $6$ and maximum product of masses is $16$.

### Function Description

Complete the `solve` function. This function takes the following $4$ parameters.

* $N$: Represents an integer denoting the number of objects.
* $Q$: Represents an integer denoting the number of queries.
* $Forces$: Represents a double dimensional array with $((N \times (N - 1)) / 2)$ rows and $3$ columns, the $i^{th}$ row describes the $i^{th}$ force realtion.

  - $Forces[i][0]$ Represents an integer denoting the $x^{th}$ object.
  - $Forces[i][1]$ Represents an integer denoting the $y^{th}$ object.
  - $Forces[i][2]$ Represents an integer denoting the force $F$ between the $x^{th}$ and the $y^{th}$ object.
  
* $Queries$: Represents a double dimensional array with $Q$ rows and $2$ columns, the $i^{th}$ row describes the $i^{th}$ query.
  - $Queries[i][0]$ Represents an integer denoting $L_i$.
  - $Queries[i][1]$ Represents an integer denoting $R_i$.
  
 $\textbf{Return Type}$
 
The function returns a double dimension array of $Q$ rows and $2$ columns. The $i^{th}$ row should have the answer for $i^{th}$ query.
 
* $ans[i][0] =$ maximum force for $i^{th}$ query.
* $ans[i][1] =$ maximum product of masses for $i^{th}$ query.

$\textbf{Note}$

* All array are considered to be zero indexed.
* Here $ans$ is just a representational name given to the double dimensional array that you are supposed to return.

### Input Format

* First line: $T$ denoting the number of test cases
* For each test case:
  - First line: $N$ and $Q$ denoting the number of objects and the number of Queries.
  - Next $N * (N - 1) / 2$ lines follow, each line contains $X, Y$ and $F$, where $F$ represents the force between $X_{th}$ and $Y_{th}$ object and $X$ is not equal to $Y$.
  - Next $Q$ lines follow, each line contains space separated integers $L_i$ and $R_i$ denoting the range for the $i${th}$ query.
  
### Output Format

For each test case, print two numbers that indicates the Maximum Gravitational Force and Maximum product of masses separated by space. Outputs of each test case should be printed in separate lines.

### Constraints

* $1 \leq T \leq 10$
* $1 \leq N \leq 10^3$
* $1 \leq Q \leq 10^6$
* $1 \leq F \leq 10^3$
* $1 \leq X \leq Y \leq N$
* $1 \leq L \leq R \leq N$

The sum of $N$ over all test cases does not exceed $2 \times 10^3$

The sum of $Q$ over all test cases does not exceed $2 \times 10^6$

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
1                               
4 3
1 2 1
1 3 4
1 4 3
2 3 6
2 4 8
3 4 4
1 4
1 3
2 4
```

</td>
<td>

```shell
8 32                            
6 16
8 32
```

</td>
</tr>
</table>

### Explanation

In the first query $(1, 4)$:

The maximum of forces $(1, 2), \ (1, 3)$, $(1, 4), \ (2, 3)$, $(2, 4), \ (3, 4)$ is between $(2, 4)$ with value $8$ and the maximum product of masses is between $(2, 4)$ with value $32$.

