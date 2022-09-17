# Visa
> Collection of coding questions appearing in online assessment of Visa during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Equal Levels](#1-equal-levels) [IIT-BHU'22]
* [Portfolio Balances](#2-portfolio-balances) [IIT-BHU'22]
* [Travelling is Fun](#3-travelling-is-fun) [IIT-BHU'22, IIT-M'22, IIT-D'22, IIT-P'22]

## 1. Equal Levels

Two signals are being generated as part of a simulation. A program monitors the signals. Whenever the two signals become equal at the same time, the frequency is noted. A record is maintained for the maximum simultaneous frerquency seen so far. Each time a higher simutaneous frequency is noted, this variable $(maxequal)$ is updated to the higher frequency. 

$\textbf{Note}$:

* Both signals start at time $t = 0$, but their durations might be different. In this case, the comparison of equality is performed only until the end of the shorter signal.
* If both signals have equal frequencies at a given time but the frequency is less than or equal to the current maixmum frequency, $maxequal$, is not updated.

The running times of both signals are given, denoted by $n$ and $m$ respectively. During the course of the simulation, how many times is the $maxequal$ variable updated?

### Example

$signalOne = [1, \ 2, \ 3, \ 3, \ 3, \ 5, \ 4]$ <br>
$signalTwo = [1, \ 2, \ 3, \ 4, \ 3, \ 5, \ 4]$

<img src="https://github.com/mrsac7/placement-resources/blob/main/Visa/ex1.png" width="500">

Each of the first three signals match and are increasing, so $maxequal$ is updated $3$ times to $1$, $2$ and then $3$.

At the fourth time, they are not equal.

At the fifth, they are equal to $3$. Since $maxequal$ contains $3$ already, it is not updated.

At the sixt time, both signals are equal to $5$. This is greater than $maxequal = 3$, so now $maxequal = 5$.

At the final time, signals are equal to $4$. Since $4$ is less than $maxequal$, it is not updated.

$maxequal$ was updated a total of $4$ times.

### Function Description

Complete the `updateTimes` function.

`updateTimes` has the following parameter(s):

* $int \ \ signalOne[n]$: the frequencies of the first signal
* $itn \ \ signalTwo[m]$: the frequencies of the second signal

$\textbf{Returns}$

* $int$: the number of updates

### Constraints

* $1 \leq n \leq 10^5$
* $0 \leq signalOne[i] \leq 10^9$
* $1 \leq m \leq 10^5$
* $0 \leq signalTwo[i] \leq 10^9$

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
1 2 3 4 1
5
5 4 3 4 1
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

<img src="https://github.com/mrsac7/placement-resources/blob/main/Visa/ex.png" width="500">

The frequencies are equal during three periods, with frequencies $3$, $4$ and $1$. <br>
The maximum frequency is updated twice at $3$, and $4$, since $4$ is greater than $3$. <br>
It is not updated when their values are $1$ because $1$ is less than the current $maxequal = 4$.

---

## 2. Protfolio Balances

An investor opens a new account and wants to invest in a number of assets. Each asset begins with a balance of $0$, and its value is stored in an array using $1-based indexing. Periodically, a constribution is received and equal investments are made in a subset of the portfolio. Each contribution will be given by $investment \ amount$, $start \ index$, $end \ index$. Each investment in that range will receive the contribution amount. Determine the maximum amount invested in any one investment after all contributions.

For example, start with an array of $5$ elements: $investments = [0, \ 0, \ 0, \ 0, 0]$. The variables $left$ and $right$ represent the starting and ending indices, inclusive. Another variable, $contribution$, is the new funds to invest per asset. The first investment is at index $1$.

```
left    right   contri-    investment
                bution    [ 0,  0,  0,  0,  0]
1       2       10        [10, 10,  0,  0,  0]
2       4       5         [10, 15,  5,  5,  0]
3       5       12        [10, 15, 17, 17, 12]
```

In the first round, a contribution of $10$ is made to investments $1$ and $2$. In the second, round, a contribution of $5$ is made to assets $2$, $3$ and $4$. Finally, in the third round, a contriubtion of $12$ is added to investments $3$, $4$ and $5$. The maximum investment in any one asset is $17$.

### Function Description

Complete the `maxValue` function.

`maxValue` has the following parameter(s):

* $int \ \ n$: the number of investments available
* $int \ \ rounds[o][3]$: each $rounds[i]$ contain $3$ integers, $[left, \ right, \ contribution]$

$\textbf{Returns}$

* $int$: the maximum investment in any one asset

### Constraints

* $3 \leq n \leq 10^7$
* $1 \leq o \leq 2 \times 10^5$
* $1 \leq left \leq right \leq n$
* $0 \leq contributions \leq 10^9$

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
3
1 2 100
2 5 100
3 4 100
```

</td>
<td>

```shell
200                         
```

</td>
</tr>
</table>

$\textbf{Explanation}$

Perform the following sequence of $o = 3$ rounds of investments on $investments = [0, \ 0, \ 0, \ 0, \ 0]$:

1. Add $contribution = 100$ to every asset in the inclusive range $[1, \ 2]$, resulting in $investments = [100, \ 100, \ 0, \ 0, \ 0]$.
2. Add $contribution = 100$ to every asset in the inclusive range $[2, \ 5]$, resulting in $investments = [100, \ 200, \ 100, \ 100, \ 100]$.
3. Add $contribution = 100$ to every asset in the inclusive range $[3, \ 4]$, resulting in $investments = [100, \ 200, \ 200, \ 200, \ 100]$.

Return the maximum value in the final list, $200$, as the answer.

---

## 3. Travelling is Fun 

A traveler is planning a vacation. To visit the cities, there must be a road to travel. The traveler constructs a map and checks whether there are routes available. The roads data is available in the form of two arrays containing origin cities and destination cities respectively. Two cities are directly connected if the values at origin and destination share a common divisor greater than a defined-threshold. Connections are transitive. If city $1$ is connected to cities $2$ and $3$, cities $2$ and $3$ are connected.

Determine whether there is a route between origin and destination cities and create a true/false path array. The route does not have to be direct.

### Example

* $numCities = 6$
* $threshold = 2$
* $originCities = [1, \ 2, \ 3]$
* $destinationCities = [4, \ 5, \ 6]$

To draw the map, first determine the divisors of all cities:

* The greatest common divisor of the cities $1$ and $4$ is $1$ which is less than the threshold $2$. So, the rout between $1$ and $4$ is not connected.
* The greatest common divisor of the cities $2$ and $5$ is $1$ which is less than the threshold $2$. So, the rout between $2$ and $5$ is not connected.
* The greatest common divisor of the cities $3$ and $6$ is $3$ which is less than the threshold $2$. So, the rout between $3$ and $6$ is connected.


<img src="https://github.com/mrsac7/placement-resources/blob/main/Visa/exp.png" width="500">

The travaler wants to know whether any paths exists from cities $1$ to $3$, $4$ to $6$, $3$ to $2$ and from $6$ to $5$.

Let the return array be $paths$, then:

* $paths[0] = 0 because no path exists from city $1$ to city $4$.
* $paths[1] = 0 because no path exists from city $2$ to city $5$.
* $paths[2] = 1 because a path exists from city $3$ to city $6$.

Therefore, the true/false array of her results would be $paths = [0, \ 0, \ 1]$.

### Function Description

Complete the function `connectedCities`.

`connectedCities` must return a true/false array where each $paths[i]$ contains $1$ if a route between $originCities[i]$ and $destinationCities[i]$ exists, or $0$ if it does not.

`connectedCities` has the following parameter(s):

* $int \ \ numCities$: the number of cities
* $int \ \ threshold$: the threshold value
* $int \ \ originCities[q]$: an array of integers
* $int \ \ destinationCities[q]$: an array of integers

### Constraints

* $2 \leq numCities \leq 2 \times 10^5$
* $0 \leq threshold, \ q \leq numCities$
* $1 \leq originCities[i], \ destinationCities[i] \leq numCities$, where $0 \leq i \lt q$
* $origincities[i] \neq destinationCities[i]$, where $0 \leq i \lt q$




     
    
