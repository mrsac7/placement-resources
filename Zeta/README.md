# Zeta
> Collection of coding questions asked by Zeta during placements at IITs

## Questions Index

* [Buying A Laptop](#1-buying-a-laptop) [IIT-BHU'22]
* [Unique Paths](#2-unique-paths) [IIT-BHU'22]
* [Candy Shops](#2-candy-shops) [IIT-BHU'22]

## 1. Buying A Laptop

You want to buy a laptop. Every laptop consists of the following parameters:

1. $Price$
2. $Rating$

Your task is to buy a laptop with the highest rating within the price range $X$ and $Y$. 

You are given $Q$ tasks. Each query consisting of the price range required. You have to print the highest rating that can be bought within that price range.

### Example

Consider $N = 2$. 

For $1^{st}$ laptop, $Price = 10$, $Rating = 3$ <br>
For $2^{nd}$ laptop, $Price = 15$, $Rating = 5$. 

Now we have $Q = 3$.

First query, $X = 10$, $Y = 15$. So, we have to find the highest rated laptop in the price range from $10$ to $15$ inclusive. So, maximum rating = $5$.

Second query, $X = 11$, $Y = 15$. So, we have to find the highest rated laptop in the price range from $11$ to $15$ inclusive. So, maximum rating = $5$.

Third query, $X = 10$, $Y = 14$. So, we have to find the highest rated laptop in the price range from $10$ to $14$ inclusive. So, maximum rating = $3$.

### Function Description

Complete the `solve` function. This function takes the following $4$ parameters and returns array of integers where $i^{th}$ integer denotes the answer for the $i^{th}$ query.

* $N$: Denotes the number of laptops.
* $arr$: $N$ arrays, each contain $P$ and $R$ denoting price and rating of each laptop.
* $Q$: Number of queries.
* $query$: $Q$ arrays, each contain two integers $X$ and $Y$ denoting the price range in which you want to buy.

### Input Format

* The first line contains $N$ denoting the number of laptops.
* Each of the next $N$ lines contain $P$ and $R$ denoting price and rating of laptop.
* The next line contains $Q$ denoting the number of tasks.
* Each of the next $Q$ lines contain two integers $X$ and $Y$ denoting the price range in which you want to buy.

### Output Format

For each task $Q$ print the highest rating that can be bought within the range. If you cannot get any laptop within the range, print $-1$.

### Constraints

* $1 \leq N \leq 10^6$
* $1 \leq Q \leq 10^6$
* $0 \leq R, \ P \leq 10^9$
* $0 \leq X \leq Y \leq 10^9$

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
1000 300
1100 400
1700 500
2000 600
3
1000 1400
1700 1900
0 2000
```

</td>
<td>

```shell
400                         
500
600
```

</td>
</tr>
</table>

$\textbf{Explanation}$

For query $1$, you can buy $2^{nd}$ laptop with rating $400$.

For query $2$, you can buy $4^{th}$ laptop with rating $500$.

For query $3$, you can buy $5^{th}$ laptop with rating $600$.

---

## 2. Unique Paths

You are given a $2$-D grid of dimension $N \times M$, you have to print the number of unique paths from top left corner to bottom right corner such that the product of all the values in that path is having odd number of divisors. From each cell you can either move only to right or down..

### Input

First line contains $T$ denoting the number of Test cases.

For each test case, first line contains two space separated integers denoting $N$ and $M$. Next $N$ lines contain $M$ space separated integers denoting the values in Grid.

### Output

For each test cases, Print single integers denoting the number of unique paths from top left corner to bottom right corner such that the product of all the values in that path is having odd number of divisors.

Print your answer modulo $(10^9 + 7)$.

### Constraints

* $1 \leq T \leq 10$
* $1 \leq N, \ M \leq 100$
* $1 \leq Value[i, \ j] \leq 30$

*Value[i, j] is value at row i and column j of the Grid.*

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
3 2
1 1
3 1
3 1
```

</td>
<td>

```shell
2                         
```

</td>
</tr>
</table>

$\textbf{Explanation}$

Here we have two unique paths - 

* $1 \rightarrow 3 \rightarrow 3 \rightarrow 1$. Product = $9$. Number of divisors of $9$ are $1$, $3$, $9$ which is odd.
* $1 \rightarrow 1 \rightarrow 1 \rightarrow 1$. Product = $1$. Number of divisor of $1$ is $1$ only, which is odd.



---

## 3. Candy Shops

You are given $N$ shops. Each shop sells only one type of candy. The candy at each shop has some cost $A_i$ and sweetness level $B_i$ associated with it. You are allowed to take only one candy from any store. You do not want to pay more than $K$ coins for a candy.

$\textbf{Note}$

* The candies can go out of stock and can be restocked.
* You cannot buy candy which is out of stock.
* If a candy is out of stock it will not go out of stock again until it is restocked.

Your task is to determine the maximum sum of sweetness level of all candies that you can buy. 

Also, you are given $Q$ queries of the following type:

* $\textbf{Type 1}:$ $\textbf{(1 L R K)}$ You are required to answer the maximum sweetness level of candies between shops $L$ to $R$.
* $\textbf{Type 2}:$ $\textbf{(0 I 0)}$ The candy at shop $I$ is now out of stock.
* $\textbf{Type 3}:$ $\textbf{(0 I 1)}$ The candy at shop $I$ has been restocked.

### Input Format

* The first line contains two integers $N$ and $Q$ denoting the number of shops and the number of queries.
* The second line contains an array $A$ that contains $N$ integers denoting the cost of the $i^{th}$ candy.
* The third line contains an array $B$ that contains $N$ integers denoting the sweetness level of the $i^{th}$ candy.
* The next $Q$ lines denotes a particular type of query.

### Output Format

For each query of type $1$, print the sum of maximum sweetness level.

### Constraints

* $1 \leq N \leq 10^5$
* $1 \leq Q \leq 10^5$
* $1 \leq A_i \leq 10^6$
* $1 \leq B_i \leq 10^6$
* $1 \leq L \leq R \leq N$
* $1 \leq K \leq 10^6$
* $1 \leq I \leq N$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
8 5                        
1 3 4 5 6 3 7 5
4 5 8 2 3 5 2 5
1 1 8 6
0 5 0 
1 1 8 6
0 5 1
1 1 8 10
```

</td>
<td>

```shell
32                         
29
34
```

</td>
</tr>
</table>

$\textbf{Explanation}$

In the $1^{st}$ query, $K$ is $6$. So we can select every candy except the candy at index $7$.

In the $2^{nd}$ query, candy at index $5$ goes out of stock.

In the $3^{rd}$ query, $K$ is $6$ so we can not choose candy at index $7$ and also at index $5$ (out of stock).

In the $4^{th}$ query, candy at index $5$ is restocked.

In the $5^{th}$ query, $K$ is $10$ so we can select every candy

