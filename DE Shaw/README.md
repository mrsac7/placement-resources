# DE Shaw
> Collection of coding questions asked by DE Shaw during placements at IITs

## Questions Index

* [Process Scheduling](#1-process-scheduling) 
* [Reach the End in Time](#2-reach-the-end-in-time) 
* [Healthy Dish](#3-healthy-dish) 

## 1. Process Scheduling

Multiprocessor systems use multiple CPUs to perform various tasks. This increases throughput and reduces response time. In this problem, a multiprocessor system has a certain number of processors. Each processor has the ability to schedule a limited number of processes in one second. However, after this scheduling, the processor's ability is reduced to $floor(\frac{ability}{2})$. Given the processor's abilities and the number of processes, what is the minimum time required to schedule all the processes in the system?

### Example

$n = 5$ (number of processors and size of $abitlity[ \ ]$\)

$ability = [3, \ 1, \ 7, \ 2, \ 4]$

$processes = 15$

The optimal solution is:

1. First, the processor with $ability = 7$ schedules $7$ processes in one second. Now, $ability = 3, \ 1, \ 3, \ 2, \ 4]$ because $7$ was reduced to $floor(\frac{7}{2})$. There are $15 - 7 = 8$ remaining processes.
2. Second, the processor with $ability = 4$ is used. After that, $ability = [3, \ 1, \ 3, \ 2, \ 2]$. Remaining processes = $8 - 4 = 4$.
3. Third, a processor with $ability = 3$ is used. Now, $ability = [1, \ 1, \ 3, \ 2, \ 2]$. Remaining processes = $4 - 3 = 1$.
4. Finally, a processor with $ability = 1$ is used to schedule the final process.

Each step requires one second of processing time so the answer is $4$.

### Function Description

Complete the function `minimumTime`. 

`minimumTime` has the following paramter(s):

* $int \ \ ability[n]$: each element denotes the ability of the $i^{th}$ processor
* $Long \ \ processes$: the number of processes to be scheduled

$\textbf{Returns}$

* $int$: the minimum time required to schedule the processes

### Constraints

* $1 \leq n \leq 10^5$
* $1 \leq ability[i] \leq 10^6$
* $1 \leq processes \leq 10^{12}$
* It is guaranteed that the processes can be scheduled using the given multiprocessor system.

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
2 1 5 3 1
17
```

</td>
<td>

```shell
9                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

After choosing the processors with $ability = 2, \ 5$ and $3$ respectively, a total of $10$ processes are scheduled (requiring $3$ seconds, one for each processor). So, there are $7$ remaining processes, and the updated $ability$ array now becomes $[1, \ 1, \ 2, \ 1, \ 1]$. Then choose the processor with $ability = 2$ to schedule $2$ processes (requiring $1$ second). After that, $ability = [1, \ 1, \ 1, \ 1, \ 1]$ and $5$ processes remain. All $5$ processors are used to schedule one process each (requring $5$ seconds). The total time required is $(3 + 1 + 5) = 9$.

---

## 2. Reach the End in Time

A $2$-D grid consisting of some blocked (represented as $'\\#'$\) ans some unblocked (represented as $'.'$\) cells is given. The starting position of a pointer is in the top-left corner of the grid. It is guaranteed that the starting position is in an unblocked cell. It is also guaranteed that the bottom-right cell is unblocked. Each cell of the grid is connected with its right, left, top, and bottom cells (if those cells exist). It takes $1$ second for a pointer to move from a cell to its adjacent cell. If the pointer can reach the bottom-right corner of the grid within $k$ seconds, return the string $'Yes'$. Otherwise, return the string $'No'$.

### Example

$rows = 3$

$grid = ['..\\#\\#', \ '\\#.\\#\\#\\#', \ '\\#...']$

$maxTime = 5$

```
..## 
#.## 
#...
```

It will take the pointer $5$ seconds to reach the bottom right corner. As long as $k \geq 5$, return $'Yes'$.

### Function Description

Complete the function `reachTheEnd`. 

`reachTheEnd` has the following parameter(s):

* $string \ \ grid[r]$: the rows of the grid
* $int \ \ maxTime$: the maximum time to complete the traversal

$\textbf{Returns}$

* $string$: the final string; either $'Yes'$ or $'No'$

### Constraints

* $1 \leq rows \leq 500$
* $0 \leq maxTime \leq 10^6$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
2                             
..
..
3
```

</td>
<td>

```shell
Yes                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

The grid has $2$ rows and $2$ columns and the time within which the pointer needs to reach the bottom-right cell is $3$ seconds. Starting from the top-left cell, the pointer can either move to the top-right unblocked cell or bottom-left unblocked cell then to the bottom-right cell. It takes $2$ seconds to reach the bottom-right cell on either path. Thus, the pointer reaches the bottom-right cell within the $3$ seconds allowed, and $'Yes'$ is returned.


---

## 3. Healthy Dish

Andy operates a famous restaurant in the city. The restaurant makes a special dish which $n$ vegetables as ingredients. Each day Andy has to go to the farmers market and buy the daily vegetable supplies. Each vegetable has some unique nutrition count $(n_i)$ and a cost $(c_i)$. To make the dish super healthy, Andy wants to buy a minimum quantity $(min_i)$ of each vegetable to put in the dish. However, he cannot buy more than a maximum quantity $(max_i)$ of each vegetable since it will spoil the taste.

Having $m$ amount of money to spend, can you help Andy so that he is able to maximize the cumulative nutrient count with at least the minimum quantity of each vegetable in the dish? The dish can not be made if it is not possible to buy minimum quantity of each vegetable reuqired.

### Function Description

Complete the `maximizeNutritioin` function. It has following $5$ parameters.

1. An array of $n$ integers, $cost$, where the value of each element $cost_i$ is the price of $i_{th}$ vegetable (where $0 \leq i \lt n$\).
2. An array of $n$ integers, $nutrients$, where the value of each element $nutrients_i$ is the nutrition count of $i_{th}$ vegetable (where $0 \leq i \lt n$\).
3. An array of $n$ integers, $min\\_quantity$, where the value of each element $min\\_quantity_i$ is minimum quantity of the vegetable Andy needs to buy. (where $0 \leq i \lt n$\).
4. An array of $n$ integers, $max\\_quantity$, where the value of each element $max\\_quantity_i$ is maximum quantity of the vegetable Andy needs to buy. (where $0 \leq i \lt n$\).
5. An integer, $m$, denoting the amount of money Andy has.

$\textbf{Returns}$

* $int$: an integer denoting the maximum amount of nutrition Andy can put in his dish

### Constraints

* $1 \leq n \leq 100$
* $1 \leq cost_i \leq 100$
* $1 \leq nutrients_i \leq 1000$
* $1 \leq min\\_quantity \leq 50$
* $1 \leq max\\_quantity \leq 50$
* $1 \leq m \leq 1000$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
3                             
2 4 3
2 1 3
2 1 1
4 3 1
30
```

</td>
<td>

```shell
14                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

$cost = [2, \ 4, \ 3]$

$nutrients = [2, \ 1, \ 3]$

$min\\_quantity = [2, \ 1, \ 1]$

$max\\_quantity = [4, \ 3, \ 1]$

In this case Andy can buy $4$ quantities of $1st$ vegetable, $3$ quantities of $2nd$ vegetable and $1$ quantity of $3rd$ vegetable. It costs him $23$ unit of money and it gives him $4 \times 2 + 3 \times 1 + 1 \times 3 = 14$ unit of nutrition and this is the maximum nutrition he can get from the shopping in the dish. Though after buying he has $30 - 23 = 7$ unit of money, he can't buy anything more because it crosses the maximum limit after which dish will be spoiled.
