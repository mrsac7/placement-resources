# VMware
> Collection of coding questions asked by VMware during placements at IITs

## Questions Index

* [Backspace String Compare](#1-backspace-string-compare) [IIT-BHU'22]
* [Connected Groups](#2-connected-groups) [IIT-BHU'22]

## 1. Backspace String Compare

Two strings are said to be the same if they are of the same length and have the same character at each index. Backspacing in a string removes the previous character in the string.

Given two string containing lowercase English letters and the character $'\\#'$ which represents a backspace key, determine if the two final strings are equal. Return $1$ if they are equal or $0$ if they are not. Note that backspacing an empty string results in an empty string.

### Example

$s_1 = axx\\#bb\\#c$

$s_2 = axbd\\#c\\#c$

In the first string, one $'x'$ and one $'b'$ are backspaced over. The first string becomes $axbc$. The second string also becomes $axbc$. The answer is $1$.

### Function Description

Complete the function `compareStrings`.

`compareStrings` has the following parameter(s):

* $string \ \ s_1$: the first string
* $string \ \ s_2$: the second string

$\textbf{Returns}$

* $int$: either $0$ or $1$

### Constraints

* $1 \leq length \ \ of \ \ s_1 \leq 2 \times 10^5$
* $1 \leq length \ \ of \ \ s_2 \leq 2 \times 10^5$
* Both $s_1$ and $s_2$ contain lowercase English letters and/or the character $'\\#'$ only.

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
yf#c#                        
ayy#k#pp##
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

Both the string $s_1$ and $s_2$ result in $y$ after processing backspaces.

---

## 2. Connected Groups

Relationships between people may be represented in a matrix as a series of binary digits. For example, the direct relationships for person $0$ with persons $0$ through $5$ might be shown as $101100$. This means that person $0$ knows persons $0$, $2$ and $3$, the indices of each of the $1$ values. A relationship is transitive. In other words, if person $0$ knows perons $2$ and person $2$ knows person $3$, then person $0$ knows person $3$ through person $2$. A group is composed of all of the people who know one another, whether direcly of transitively.

### Example

Consider the following relationships matrix:

<img src="#">

Persons $0$ and $1$ are connected, while person $2$ is not. There are $2$ groups.

Determine the number of groups represented in a matrix.

### Function Description

Complete the function `countGroups`.

`countGroups` has the following parameter(s):

* $string \ \ related[n]$: an array of strings of binary digits $related[i]$ that represent connections of people 

$\textbf{Returns}$

* $int$: an integer that represents the number of groups of people

### Constraints

* $1 \leq n \leq 300$
* $0 \leq i \lt n$
* $|related| = n$
* Each $related[i]$ contains a binary string of $n$ zeros and ones. $related$ is a square matrix.

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
1100
1110
0110
0001
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

Squares highlighting a connection between two people are highlighted in green. Each of the people is known to self, so they are highlighted in gray.

<img src="#">

There are $n = 4$ people numbered $related[0]$ through $related[3]$.

There are $2$ pairs who directly know each another: $(related[0]$, $related[1])$ and $(related[1]$, $related[2])$. 

Because a relation is transitive, the sets of people $\\{related[0]$, $related[1]$, $related[2]\\}$ is considered a single group.

The remaining person, $related[3]$, does not know any other people and is a separate group.

There are a total of $2$ groups.

