# American Express
> Collection of coding questions asked by American Express during placements at IITs

## Questions Index

* [Digrams](#1-digrams) [IIT-BHU'22]
* [Make Zero](#2-make-zero) [IIT-BHU'22]
* [Merge Lists](#3-merge-lists) [IIT-BHU'22]

## 1. Digrams

We are given a string $S$ consisting of $N$ lowercase letters. A sequence of two adjacent letters inside a string is called a $digram$. The distance between two digrams is the distance between the first letter of the first digram and the first letter of the second digram. For example, in string $S = akcmz$ the distance between digrams $kc$ and $mz$ is $2$. 

We want to find the distance between the furthest **identical** digrams inside string S. 

Write a function: 

```cpp
int solution(string &S);
```

that, given a string $S$ consisting of $N$ letters, returns the distance between the two identical digrams in the string that lie furthest away from each other. If there are no two identical digrams inside S, your function should return $-1$. 

#### Examples: 

1. Given $S = aakmaakmakda$ your function should return $7$. The furthest identical digrams are $ak$'s, starting in positions $2$ and $9$ (enumerating from 1): $a\textbf{ak}maakm\textbf{ak}da$. 
2. Given $S = aaa$ your function should return $1$. The furthest identical digrams are $aa$'s starting at positions $1$ and $2$. 
3. Given $S = codility$ your function should return $-1$. There are no two identical digrams in $S$. 

Write an **efficient** algorithm for the following assumptions: 

* $N$ is an integer within the range $[2.. 3\times10^4]$; 
* string $S$ consists only of lowercase letters ( $a-z$ ).

---

## 2. Make Zero

You are given a string $S$ of length $N$ which which encodes a non-negative number $V$ in a binary form. Two types of operations may be performed on it to modify its value: 

* if $V$ is odd, subtract $1$ from it;
* if $V$ is even, divide it by $2$.

These operations are performed until the value of $V$ becomes $0$. 



For example, if string $S = 011100$, its value $V$ initially is $28$. The value of $V$ would change as follows: 

* $V = 28$, which is even: divide by $2$ to obtain $14$; 
* $V = 14$, which is even: divide by $2$ to obtain $7$; 
* $V = 7$, which is odd: subtract $1$ to obtain $6$; 
* $V = 6$, which is even: divide by $2$ to obtain $3$; 
* $V = 3$, which is odd: subtract $1$ to obtain $2$; 
* $V = 2$, which is even: divide by $2$ to obtain $1$; 
* $V = 1$, which is odd: subtract $1$ to obtain $0$. 

Seven operations were required to reduce the value of $V$ to $O$. 

Write a function: 

```cpp
  int solution(string &S); 
```

that, given a string $S$ consisting of N characters containing a binary representation of the initial value $V$, returns the number of operations after which its value will become $0$.

#### Examples: 

1. Given $S = 011100$, the function should return 7. String $S$ represents the number $28$, which becomes 0 after seven operations, as explained above. 
2. Given $S = 111$, the function should return $5$. String $S$ encodes the number $V = 7$. Its value will change over the following five operations: 
  * $V = 7$, which is odd: subtract $1$ to obtain $6$; 
  * $V = 6$, which is even: divide by $2$ to obtain $3$; 
  * $V = 3$, which is odd: subtract $1$ to obtain $2$; 
  * $V = 2$, which is even: divide by $2$ to obtain $1$; 
  * $V = 1$, which is odd: subtract $1$ to obtain $0$. 
  
3. Given $S = 1111010101111$, the function should return $22$. 
4. Given string $S$ consisting of $1$ repeated $400,000$ times, the function should return $799,999$. 

Write an **efficient** algorithm for the following assumptions: 

* string $S$ consists only of the characters $0$ and/or $1$; 
* $N$, which is the length of string $S$, is an integer within the range $[1..10^6]$; 
* the binary representation is big-endian, i.e. the first character of string $S$ corresponds to the most significant bit; 
* the binary representation may contain leading zeros. 

---

## 3. Merge Lists

Merging a sorted list consisting of $K$ elements with a sorted list consisting of $L$ elements takes $K + L$ milliseconds (ms). The time required to merge more than two lists into one final list depends on the order in which the merges are performed.

For example, consider the following three lists.

* list $P$ consisting of $100$ elements,
* list $Q$ consisting of $250$ elements,
* list $R$ consisting of $1000$ elements.

They can be merged into one final sorted list in three different ways:

1. first merge $P$ with $Q$, then merge the result with $R$; or
2. first merge $P$ with $R$, then merge the result with $Q$; or
3. first merge $R$ with $Q$, then merge the result with $P$.

The times needed to perform the above merges are respectively:

* merge $P$ with $Q$: $350 ms$; result with $R$; $1350 ms$; total: $1700 ms$;
* merge $P$ with $R$: $1100 ms$; result with $Q$; $1350 ms$; total: $2450 ms$;
* merge $Q$ with $R$: $1250 ms$; result with $R$; $1350 ms$; total: $2600 ms$;

The first schema is the fastest ( $1700 ms$ ).

If there are more than three lists to merge, there are even more merge strategies to consider. When the number of lists to merge is fewer than two, no merges are performed and the total merge time is assumed to be 0.

Write a function:

```cpp
  int solution(vector<int> &A);
```

that given an array $A$ of length $N$ describing the lengths of $N$ lists, returns the shortest time (measured in milliseconds) required to merge these lists into one.

For example, given array $A$ consisting of three elements such that:

$A[0] = 100, A[1] = 250, A[2] = 1000$

the function should return $1700$, as explained above.

Write an **efficient** algorithm for the following assumptions:

* $N$ is an integer within the range $[0..10^4]$;
* each element of array $A$ is an integer within the range $[1..10^3]$.
