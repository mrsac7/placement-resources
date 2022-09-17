# Observe.ai
> Collection of coding questions appearing in online assessment of Observe.ai during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Intelligent Robots](#1-intelligent-robots) [IIT-BHU'22]
* [Fake Palindrome](#2-fake-palindrome) [IIT-BHU'22]

## 1. Intelligent Robots

Krisha is very much fascinated about Robots, so she bought $N$ robots. Each robot is having some intelligence, let's say the $i^{th}$ robot is having intelligence $P_i$. While she was playing with robots, she found a way to transer the intelligence of one robot to another. In this process she observed that, if $X$ amount of intelligence is transferred from $i^{th}$ robot to $j^{th}$ then, $K$ percent of intelligence which is getting transferred gets dissipated in this process. So she need your help to make the intelligence of all Robots equal and maximum possible.

### Input

* First line contains $T$, denoting the number of Test Cases.
* First line of each test case contains two space separated integers $N$ and $K$, denoting the Number of Robots and the Percentage of power getting dissipated.
* Second line of each test case contains $N$ space separated integers $P_1$, $P_2$, $P_3$, ..., $P_N$ denoting the initial intelligence of each Robots.

### Ouput

For each test case, print a single line float value (round to $4$ decimal places) denoting the maximum intelligence of each robots.

### Constraints

* $1 \leq T \leq 50$
* $1 \leq N \leq 10^5$
* $1 \leq K \leq 99$
* $0 \leq P_i \leq 10^5$, $(1 \leq i \leq N)$

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
3 50
1 2 3
```

</td>
<td>

```shell
1.7500                         
```

</td>
</tr>
</table>

$\textbf{Explanation}$

Robot $3$ will transfer its $1.25$ intelligence to Robot $1$. So the new intelligence of Robot $3$ is $1.75$ and Robot $1$ is 

$1.625$ $(1 + 0.5 \times 1.25)$ <br>
Robot $2$ will transfer its $0.25$ intelligence to Robot $1$. So the new intelligence of Robot $3$ is $1.75$ and Robot $1$ is 

$1.75$ $(1.625 + 0.5 \times 0.25)$ <br>
So the intelligence of each Robot is $1.75$, which is maximum possible.



---

## 2. Fake Palindrome

You are given a string $A$.

## Task

Determine the number of *different* substrings of string $A$ which are fake palindromes.

$\textbf{Notes}$

* *Palindrome*: A string is called a palindrome if you reverse the string yet the order of letters remains the same. For example, MADAM.
* *Fake palindrome*: A string is called a fake palindrome if any of its permutations is a palindrome. For example $AAC$ is a fake palindrome, but $ACD$ is not.
* *Substring*: A substring is a contiguous sequence (non-empty) of characters within a string.
* Two substrings are considered the *same* if their starting indices and ednding indices are equal.

### Example

$\textbf{Assumption}$

$A =$ $'BBCA'$

$\textbf{Approach}$

There are $6$ substrings of $A$ which are fake palindromes:

* Fake Palindromes are $'B'$, $'B'$, $'C'$, $'A'$, $'BB'$, $'BBC'$. All substrings are already a palindrome except $'BBC'$, whose characters can be shuffled to make a palindrome $'BCB'$.

### Function Description

Complete the `Palindrome` function. The function takes the following parameter and returns the number of different substrings which are fake palindromes:

* $S$: Represents a string $A$

### Input Format

* The first line contains an integer $T$ denoting the number of test cases. $T$ also denotes the number of times you have to run the `Palindrome` function on a different set of inputs.
* For each test case:
    - The first line contains a string $S$.

### Ouput Format

For each test case in a new line, print a single integer representing the number of fake palindrome substrings.

### Constraints

* $1 \leq T \leq 10$
* $1 \leq |S| \leq 2 \times 10^5$

String contains only first $20$ uppercase $('A'$ - $'T')$ English letters.


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
ABAB
AAA
AAB
ABCD
CABC
```

</td>
<td>

```shell
7                         
6
5
4
4
```

</td>
</tr>
</table>


