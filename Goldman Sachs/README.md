# Goldman Sachs
> Collection of coding questions asked by Goldman Sachs during placements at IITs

## Questions Index

* [Aptitude Questions](#1-aptitude-questions) [IIT-BHU'22]
* [Crime Investigation](#2-crime-investigation) [IIT-BHU'22]

## 1. Aptitude Questions

Jane is solving aptitude questions as she is preparing for competitive exams. She came across a question where the dimensions of a rectangle were given, and the possible number of sub-rectangles that can be created within that rectangle (including itself) had to be found. She is now wondering if a generic solution can be found for this problem. Can you write a program to help her?

### Constraints

* $0 \lt L \lt 10^5$
* $0 \lt W \lt 10^5$

### Input Format

Single line of input consists of two integers $L$ and $W$ which are the length and width of the rectangle.

### Output Format

Single line of output has the number of sub-rectangles that can be created within the rectangle


### Sample Tests

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
2 2                      
```

</td>
<td>

```shell
9                             
```

</td>
</tr>
</table>

$\textbf{Explanation 1}$

From the given dimension, length and width are $2$ and $2$ respectively. The following sub-rectangles can be formed.

<img src="https://github.com/mrsac7/placement-resources/blob/main/Goldman%20Sachs/ex1.png" width="500">

Hence, the number of sub-rectangles that can be created is $4 + 2 + 2 + 1 = 9$

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
3 2                      
```

</td>
<td>

```shell
18                             
```

</td>
</tr>
</table>

$\textbf{Explanation 2}$

Length = $3$ and Width = $2$. The following sub-rectangles can be created.

<img src="https://github.com/mrsac7/placement-resources/blob/main/Goldman%20Sachs/ex2.png" width="600">

Hence, total $18$ sub-rectangles can be created within the given rectangle.


---

## 2. Crime Investigation

CID Menaka is investigating a crime. As part of the evidence, she found a partially burnt envelope. The envelope had one word (of length $N$ ) and one number $X$ written on it, but the word was not readable as a few $M$ letters in the word were burnt out. Gathering more evidence, Menaka put together $K$ different possiblities for each of the missing letters. When she made a list of all possible words using the $K$ possibilites for each missing letter and sorted them alphabetically, she realized that the $X^{th}$ word would be the word written on the envelope.

Write a program to help Menaka identify the word, given the required inputs.

### Input Format

* The first line of input contains the integers $N$, $M$, $K$, and $X$ denoting, the length of the word, number of missing letters, the possibilities for each missing letter, and the number on the envelope, respectively.

* The second line of input contains the word on the envelope, consisting of lowercase letters of the English alphabet and the character $'\\#'$  representing the missing letters

* The following $M$ lines contain the $K$ possibilities (as a single word of length $K$ ) for each missing letter, with the $i^{th}$ line corresponding to the $i^{th}$ missing letter.

### Output Format

Single line of output contains the word on the envelope.

### Constraints

* $1 \leq N \leq 500$
* $1 \leq M \leq N$
* $1 \leq K \leq 26$
* $1 \leq X \leq 10^9$
* $X$ will always be less than or equal to the total number of words that are possible.

### Sample Tests

<table>
<tr>
<td> Sample Input 1 </td>
<td> Sample Output 1 </td>
</tr>
<tr>
<td>

```shell
7 1 4 2                      
ba#king
ncsr
```

</td>
<td>

```shell
banking                             
```

</td>
</tr>
</table>

$\textbf{Explanation 1}$

The length of the word is $7$, of which $1$ letter is missing.

There are $4$ possibilities for the missing letter, and the $2nd$ sorted word is the required word

The word is: $ba\\#king$

The missing letter could be one of $n$, $c$, $s$, or $r$

Possible words are: $banking$, $backing$, $basking$ or $barking$

Arranging in alphabetical order: $backing$, $banking$, $barking$, $basking$

So the $2nd$ word, $'banking'$ is the original word on the envelope, printed as output.

<table>
<tr>
<td> Sample Input 2 </td>
<td> Sample Output 2 </td>
</tr>
<tr>
<td>

```shell
4 2 2 1                      
##sk
ka
yn
```

</td>
<td>

```shell
ansk                             
```

</td>
</tr>
</table>

$\textbf{Explanation 2}$

The length of the word is $4$, of which $2$ letters are missing. 

There are $2$ possibilities for each missing letter, and the $1st$ sorted word is the required word

The word is: $\\#\\#sk$

The first missing letter could be $k$ or $a$

The second missing letter could be $y$ or $n$

So possible word options are: $kysk$, $knsk$, $aysk$, $ansk$

Arranging in alphabetical order: $ansk$, $aysk$, $knsk$, $kysk$

So the $1st$ position word, $'ansk'$ is the original word, printed as output.


