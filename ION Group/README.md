# ION Group
> Collection of coding questions appearing in online assessment of ION Group during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Car Race](#1-car-race) [IIT-BHU'22]
* [The Abandoned City](#2-the-abandoned-city) [IIT-BHU'22]

## 1. Car Race

Given $N$ cars with their speed in form of an array $A$, where index represent their position. All cars are participating in a race of infinite length and starts at same time. A car which is standing 
at $i$ position is considered to be ahead of the car which is standing at position $j$ if and only if $i > j$. 

We need to find the total number of overtakes which happen during race. An overtake occurs when car $A$, whose starting position is less than car $B$, finishes the race earlier than car $B$. 

### Example 

If $A = [4, \ 1, \ 2, \ 5]$. Then $2$ overtakes will happen during race. 

* Car $1$, will overtake Car $2$ and Car $3$ as speed of Car $1$ is greater than speed of Car $2$ and Car $3$. 

### Function Description 

Complete the `countOvertake` function. This function takes the following $2$ parameters and returns the number of overtakes during race. 

* $N$ : Represents the number of cars 
* $A$ : Represents the speed of cars. 


### Input : 

1. First line contain an integer $N$, denoting number of cars 
2. Second line contain $N$ space separated integers. 

### Constraints

* $1 \leq N \leq 10^5$
* $1 \leq A[i] \leq 10^6$

### Output

Print one integer denoting total number of overtakes.

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
4                               
2 1 5 6
```

</td>
<td>

```shell
1                            
```

</td>
</tr>
</table>

$\textbf{Explanation}$

Only $1$ overtake will occur between Car $1$ and $2$.

---

## 2. The Abandoned City

You bought a virtual reality glasses. There is only one game installed to it called "The Abandoned City". 

You are lost in an abandoned city. In order to escape, You have to pay a number of golden coins. So, you decided to collect the gold in the houses of that city. The city contains many houses aligned in a straight line. Each house contains a specific amount of golden coins. 

You need to figure out the shortest distance you have to walk until you collect the needed amount of golden coins.

$\textbf{Note}: You can start from any house $i$ and continue your as $i$ to $i + 1$ or $i$ to $i - 1$ but you can't change your direction, and stop at any house.

### Example 
Let's assume that the number of houses is $5$ and coins in those houses are $[1, \ 2, \ 3, \ 4, \ 5]$ and target is 7. 

It can be seen that to collect $7$ coins you will have to travel through atleast $2$ houses. The possible travel options are:- 

1. Start from $3^{rd}$ house, travel right and stop at $4^{th}$ or or start from $4^{th}$ house, travel left and stop at $3^{rd}$ house, thus colectine $7$ coins.
2. Start from $4^{th}$ house, travel right and stop at $5^{th}$ or start from $5^{th}$ house, travel left and stop at $^{4th}$ house, thus collecting $11$ coins. 

Thus the shortest distance you have to walk until you collect $7$ golden coins is $2$. 

### Function description 

narameters and returns the `solve` function. This function takes the following $3$ parameters and returns the minimum distance you have to walk to collect the needed amount of golden coins to get out or $-1$ if no such answer exists.

* $n$: Represents an integer denoting the number of houses. 
* $coins$: Represents an integer array denoting the coins kept in houses. $coins[i]$ denotes the number of coins kept in $i^{th}$ house. 
* $target$: Represents an integer denoting the target. 

### Input Format 

* The first line contains an integer, $n$, denoting the number of houses. 
* Each line $i$ of the $n$ subsequent lines (where $0 \leq i < n$\) contains an integer describing the number of coins of the $i^{th} house. 
* Followed by a line contains an integer, $target$, denoting the number of the golden coins you have to pay to get out of the city. 

### Output Format 

Print the minimum distance you have to walk to collect the needed amount of golden coins to get out or $-1$ if no such answer exists. 

### Constraints

* $1 \leq n \leq 10^5$ 
* $1 \leq target \leq 10^9$
* $1 \leq coins_i \leq 10^5$

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
5
1
2
3
4
13
```

</td>
<td>

```shell
5                            
```

</td>
</tr>
</table>

$\textbf{Explanation}$

In this sample, there are $5$ houses. To escape the city you need to pay $13$ golden coins. The only way to collect the required number of golden coins is to walk the first house to the last house. The total number of golden coins you can get is $15$ which is more than the target. Thus, the answer is $5$.



