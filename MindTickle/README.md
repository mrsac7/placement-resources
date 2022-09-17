# MindTickle
> Collection of coding questions appearing in online assessment of MindTickle during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Total Prime Factors](#1-total-prime-factors) [IIT-BHU'22]
* [Unique Number](#2-unique-number) [IIT-BHU'22]
* [Efficient Mining Algorithm](#3-efficient-mining-algorithm) [IIT-BHU'22]
* [Math Game](#4-math-game) [IIT-BHU'22]

### 1. Total Prime Factors

Given $2$ numbers low and high. Find $2$ numbers $(x, \ y)$ such that:

1. $low \leq x \lt y \leq high$
2. Total number of unique prime factors of $x$ and $y$ is maximum.

If there are multiple answers give $(x, \ y)$ pair with the smallest $x$. If there are no such numbers return $[-1, \ -1]$.

### Constraints

* $2 \leq low \leq high \leq 1000$

### Sample Tests

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
aaa                        
aa
```

</td>
<td>

```shell
1                             
```

</td>
</tr>
</table>

$\textbf{Explanation 1}$

All the numbers in the given range have the following prime factors:

$5: \ 5$ <br />
$6: \ 2, \ 3$ <br />
$7: \ 7$ <br />
$8: \ 2$ <br />
$9: \ 3$ <br />
$10: \ 2, \ 5$ 

From all the possible combinations only $(5, \ 6)$, $(6, \ 7)$, $(6, \ 10)$, $(7, \ 10)$ and $(9, \ 10)$ has total $3$ unique prime factors.

$(5, \ 6): \ 2, \ 3, \ 5, \ 7$ <br />
$(6, \ 7): \ 2, \ 3, \ 7, \ 7$ <br />
$(6, \ 10): \ 2, \ 3, \ 5, \ 7$ <br />
$(7, \ 10): \ 2, \ 5, \ 7, \ 7$ <br />
$(9, \ 10): \ 2, \ 3, \ 5, \ 7$

In this case the answer is $(5, \ 6)$ as that has the smallest $x$.

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
11 15                       
```

</td>
<td>

```shell
14 15                             
```

</td>
</tr>
</table>

$\textbf{Explanation 2}$

All the numbers in the given range have the following prime factors:

$11: \ 11$ <br />
$12: \ 2, \ 3$ <br />
$13: \ 13$ <br />
$14: \ 2, \ 7$ <br />
$15: \ 3, \ 5$ 

From all the possible combinations only $(14, \ 15)$ has total $4$ unique prime factors.

$(14, \ 15): \ 2, \ 3, \ 5, \ 7$

In this case the answer is $(5, \ 6)$ as that has the smallest $x$.

---

### 2. Unique Number

Gojo found a new concept about unique number and unique string.

Unique string: suppose we have two string $S$ and $t$. $S$ is a unique string of $t$ if we concat $S$ for $k$ $(k \geq 0)$ times we can generate $t$ string. For example $t = 'abab'$, Unique strings for $t$ are $'ab'$ and $'abab'$.

Unique number: Suppose we have two strings $s$ and $t$. Number of common unique strings of $s$ and $t$ is called Unique number.

Gojo is given $2$ strings, help Gojo to find unique number for these strings.

### Input

* First line contains non-empty string $s$ with all lowercase latin letters.
* Second line contains non-empty string $t$ with all lowercase latin letters.
* Length of $s$ and $t$ will not exceed $10^5$.

### Output

Print Unique number for given two strings.

### Sample Tests

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
aaa                        
aa
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
abab                       
aba
```

</td>
<td>

```shell
0                             
```

</td>
</tr>
</table>

$\textbf{Explanation}$

Here unique strings for $'aaa'$ are $'a'$ and $'aaa'$. Unique string for $'aa'$ are $'a'$ and $'aa'$. So number of common unique strings is $1$ $('a')$.


---

### 3. Efficient Mining Algorithm

Miners are trying to mine a cryptocurrency which is based on the amount of coal they have and the quantity of energy that they can consume from the coal. They are provided with two arrays:

- one indicating the amount of coal they have as separate reservoirs, and
- the energy that can be mined required for mining.

The cryptocurrency can be mined if the following constraint is satisfied:
&nbsp; &nbsp; &nbsp; &nbsp; **minimum of the energy requirement array >= maximum of the coal amount array**

**However they can add or subtract 1 to any index of any array, but doing any operation will result in a unit cost.**

The miner want themselves to be as efficient as possible, your task is to help miner solve this problem with minimum cost that can be required so that a given cryptocurrency can be mined.

### Input Format

* The first line contains two space-separated integers $n$, $m$ denoting the size of the arrays.
* The second line will contain $n$ space-separated integers representing content of the array $coal[c]$ (size = $n$) (indicating the amount of coal as an array).
* The third line will contain $m$ space-separated integers representing content of the array $energy[e]$ (size = $m$) (amount of energy required as an array).

### Constraints

* $1 \leq n, \ m \leq 10^4$
* $1 \leq c_i \leq 10^{12}$
* $1 \leq e_i \leq 10^{12}$

### Sample Tests

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
3 3                       
1 2 3
```

</td>
<td>

```shell
4                             
```

</td>
</tr>
</table>

$\textbf{Explanation 1}$

Consider $1$ based indexing remove $1$ coal from $c_2$ coal array becomes $[2, 3, 3]$, $max = 3$, add $1$ energy again to $e_1$, energy array becomes $[2, 2, 3]$, add $1$ energy again to $e_1$, energy array is $[3, 2, 3]$, add $1$ energy to $e_2$, the energy array becomes $[3, 3, 3]$, $min = 3$. Thus by $4$ operations, minimum of energy requirement array >= maximum of coal amount array.

Though there are other ways also possible to make this condition true but $4$ will be our most optimal answer.

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
3 3                       
2 4 3
8 5 9
```

</td>
<td>

```shell
0                             
```

</td>
</tr>
</table>

---

### 4. Math Game

MindTickle is organising a game for its employees and in this game each individual is given $n$ number $b_1, \ b_2, \ ..., \ b_n$. Where they can perform at most $m$ operations. In each operation a person can multiply one of the numbers by $p$. Where the individuals have to make $b_1 \ | \ b_2 \ | \ ... \ | \ b_n$ as large as possible, where $|$ denotes the bitwise $OR$. Amit, an employee at MindTickle, is not good at problem-solving, so he needs your help to find the maximum possible value of $b_1 \ | \ b_2 \ | \ ... \ | \ b_n$ after performing at most $m$ operations optimally.

### Constraints

* $1 \leq n \leq 2 \times 10^5$
* $1 \leq m \leq 10$
* $2 \leq p \leq 8$
* $0 \leq b_i \leq 10^9$

### Input Format

* The first line contains three integers $n$, $m$, and $p$ 
* The second line contains $n$ integers $b_1, \ b_2, \ ..., \ b_n$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
3 1 2                       
1 1 1
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

Any possible choice of doing one operation will result the same three numbers $1$, $1$, $2$ so the result is $1 \ | \ 1 \ | \ 2 = 3$
