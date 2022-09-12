# Graviton
> Collection of coding questions asked by Graviton during placements at IITs

## Questions Index

* [Valid Equations](#1-valid-equations) [IIT-BHU'21, IIT-K'21]
* [Squid Game](#2-squid-game) [IIT-BHU'21, IIT-K'21]

## 1. Valid Equations

Let $X$ be a set of $N$ variables ( $x_1, x_2,..., x_n$ ). Let $E$ be the set of $M$ linear equations ( $e_1, e_2,..., e_n$ ) on the set $X$. Each equation in $E$ is of the form $x_i = x_j + c_{ij}$ (where $c_{ij}$ are all integers for $1 \leq i, j \leq N$). Given the relevant information (inputs mentioned below), devise an algorithm to determine whether the equations in $E$ are consistent. (i.e. whether an assignment of integers can be made to the variables, which satisfies all the equations in $E$).

### Inputs:

First line denotes the number of test cases $T$, followed by the test cases themselves.

First line of each test case consists of two space separated numbers $N$ and $M$ respectively.

Followed by $M$ lines which define the set $E$.

$m^{th}$ line of these $M$ lines is of the form: $i$ $j$ $c_{ij}$ (used to denote the $m^{th}$ equation of the form: $x_i = x_j + c_{ij}$ ).

### Output:

For each test case in $T$, output a single line:

$YES$, if there exists an assignment of integers for which all equations in $E$ are satisfied

$NO$, otherwise.

### Constraints:

$1 \leq T \leq 20$

$1 \leq N \leq 10^5$

$1 \leq M \leq 3 * 10^5$

$|c_{ij}| \leq 10^9$

<table width="600px">
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
2                                 
2 1
1 2 3
3 2
1 2 3
2 3 2
```

</td>
<td>

```shell
YES                            
YES
```

</td>
</tr>
</table>

---

## 2. Squid Game

You just finished watching Squid Game. As you are a popular programmer. Siren Pictures decided to contact you for a little task for the next season.

Given $N$ players, they want you to make groups following the rules mentioned below:

  1. Each group must have exactly $K$ Players.
  2. A player can be in multiple groups.
  3. $i^{th}$ player cannot be in more than $G_i$ groups.
  4. Two Players having the same first letter in their names, cannot be in the same group.
  
Your task is to find the maximum number of groups that can be formed following the above mentioned rules.

Assume player names to be a single word containing uppercase english alphabets only.

### Inputs:

$T$: Number of test cases

Each test case will have:

  * $N$: Number of players.
  * $K$: Number of players to be included in each group.
  * $P_i$: Name of $i^{th}$ player.
  * $G_i$: Maximum number of groups, $i^{th}$ can be included in.

### Output:

For each test case in T, output a single integer denoting the maximum number of groups that can be made.

### Constraints:

$1 \leq T \leq 20$

$1 \leq K \leq N \leq 10^5$

$G_i \leq 10^4$

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
2                                 
4 2
ABC 3
PQR 4
AA 4
BB 2
4 3
ABC 3
PQR 2
AA 3
```

</td>
<td>

```shell
6                            
0
```

</td>
</tr>
</table>
