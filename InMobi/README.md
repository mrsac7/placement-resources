# InMobi
> Collection of coding questions asked by InMobi during placements at IITs

## Questions Index

* [Broken Chain](#1-broken-chain) [IIT-BHU'21]
* [Reportee Count](#2-reportee-count) [IIT-BHU'21]
* [Connected Flights](#3-connected-flights) [IIT-BHU'21]

## 1. Broken Chain

### Problem Statement

There is a large broken chain (think of Ship Anchor Chain) with $N$ pieces. Join all the pieces to make chain whole again. Process to join chain is as follows:

1. Picky any two pieces and join those.
2. Repeat this process until all pieces are joined.

Each join operation requires some cost (labour cost, welding cost etc.). Cost of each join operation is equal to sum of the Weights $W$ of pieces which are being joined. Total cost will be sum of costs each step. Find the way to keep $Total cost$ as minimum.

### Input Format

* Value of $N$ in $1$st line
* Comma and space separted $N$ integers in $2$nd line, which denote individual weights of $N$ pieces. 

### Constraints

* $1 \leq N \leq 10^5$
* $1 \leq W \leq 10^5$

### Output Format

* Value of minimum total cost

### Sample Input

```shell
4
8 2 3 4
```

### Sample Output

```shell
31
```

### Explanation

In aboe sample, broken chain has 4 pieces with given weights. Two pieces are joined at a time, for example if $8$ and $2$ are joined, new piece will have weight of $10$. Then it can be joined with any of pieces in any of the next steps.

---

## 2. Reportee Count

### Problem Statement

In a company containing $N$ number of employees with employee ID ranging from $1$ to $N$. Employee with ID $1$ is the CEO. Every employee has exaclty $1$ manager except CEO who doesn't report to anyone. 

Find the total number of reportees (direct + indirect) for everyone.

### Input Format

* First line contains an integer denoting total number of employees $N$
* Next $N - 1$ lines contain two space-separated integers $n_1$ and $n_2$ where $n_2$ is manager of $n_1$

### Constraints

* $2 \leq N \leq 10^5$

### Output Format

* Print $N$ integers separated by space where $1$st integer is total number of reportees of employee with $id = 1$, $2$nd value is total number of reportees of employee with $id = 2$ and so on.

### Sample Input

```shell
5
2 1
3 2
4 1
5 3
```

### Sample Output

```shell
4 2 1 0 0
```

### Explanation

Manager of Employee 2 = 1

Manager of Employee 3 = 3

Manager of Employee 5 = 2

Manager of Employee 6 = 4

This is how the org structure looks like for this example:

<img src="https://github.com/mrsac7/placement-resources/blob/main/Slice/fig1.png" width="250">

---

## 3. Connected Flights

### Problem Statement

There are $n$ cities connected to each other by total $m$ number of flights.

You are given a list of $m$ number of flights where each flight consists of $source, \ destination$ and $price$ i.e. the flight from this $source$ to $destination$ has cost = $price$.

Now given $3$ integers = $src, \ dst$ and $k$

Return the cheapest route from $src$ to $dst$ with at most $k$ stops.

If there is no such route, return $-1$.

### Input Format

* First line contains total number of cities $n$
* Second line contains total number of flights $m$
* Third line contains source city $src$
* Fourth line contains destination city $dst$
* Fifth line contains max number of stops allowed $k$

### Constraints

* $1 \leq n \leq 100$
* $1 \leq src \leq n$
* $1 \leq dst \leq n$
* $src \neq dest$
* $1 \leq k \lt n$
* $Note:$ There is only 1 direct flight between any $2$ cities.

### Output Format

* Return one integer which denotes the total cost of the cheapest route.

### Sample Input

```shell
6
8
0
3
1
0 1 10
0 2 10
0 3 15
0 4 2
1 3 20
2 3 50
4 5 2
5 3 2
```

### Sample Output

```shell
15
```

### Explanation

The flight graph for this example looks like this:

<img src="https://github.com/mrsac7/placement-resources/blob/main/Slice/fig2.png" width="200">

We have to find the cheapest combination of flights froms source = $0$ to destination = $3$ with at max $1$ stop. The cheapest solution is from $0 \rightarrow 4 \rightarrow 5 \rightarrow 3$ which has a total cost = $6$ but this has a total of $2$ stops so we can't choose this path. The best path with at max $1$ stop is $0 \rightarrow 3$ with a total cost of $15$


