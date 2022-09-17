# Navi
> Collection of coding questions appearing in online assessment of Navi during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Rail Fence Cipher](#1-rail-fence-cipher) [IIT-BHU'22]
* [Leaky Bucket](#2-leaky-bucket) [IIT-BHU'22]
* [Minimum Steps!](#3-minimum-steps) [IIT-BHU'22]


## 1. Rail Fence Cipher

### Problem Statement

Rail Fence Cipher is a form of transposition cipher. In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, the moving up when the bottom rail is reached. When the top rail is reached, the message is written downwards again until the whole "plain-text" is written out.

### Input Format

* First line takes a single word input.
* Second line takes input as array depth.

### Constraints

* Print the cipher-text

### Output Format

* Value of minimum total cost

### Sample Input

```shell
CODEATDOSELECT
3
```

### Sample Output

```shell
CASCOETOEETDDL
```

### Explanation

For plain-tex "WEAREDISCOVEREDFLEEATONCE" and array depth as $3$. The output cipher-text will be "WECRLTEERDSOEEFEAOCAIVDEN". Spaces are neglected while encrypting.

<img src="https://github.com/mrsac7/placement-resources/blob/main/Navi/cip.png" width="400">

---

## 2. Leaky Bucket

### Problem Description

The **leaky bucket** algorithm is based on congestion control in computer networks.

The main concept of the leaky buket algorithm is that the output data flow remains constant despite the variant input traffic, such as the water flow in a bucket with a small hole at the bottom. In case the bucket contains water (or packets) then the output follows a constant rate, while if the bucket is full any additional load will be because of spillover.

Print the total spillover in the network.

### Input Format

* The first line takes input as bucket size.
* The second line takes input as transmission rate of bucket (leak rate).
* The third line takes input as total transmission time.
* The fourth line contain an array of data transmitted over the network at each transmission time.

### Ouptput Format

* Print the total packet loss (spillover).

### Sample Input

```shell
100
50
4
120 110 120 100
```

### Sample Output

```shell
200
```

$\textbf{Note}$: Bucket size will always be greater than transmission rate.

### Explanation

Suppose for the above test case if $120$ is taken as input to the bucket, there is an overflow $\textbf{20 units}$ as the bucket size is $100$ and $50$ units is transmitted over the network as the transmission rate is $50$. The leftover $50$ units will be added to the next transmission cycle. So the next cycle will have $110 + 50 = 160$ units thus spilling $\textbf{60 units}$ and transferring $50$ units. Now we have $50$ units for third cycle that gets added up with $120$ new units amounting to $170$ units. We will spill $\textbf{70 more units}$ in $3$rd interval and transferring $50$ units thus again left with $50$ units for 4th interval which will further add $100$ units to the buckets thus again spilling of $50$ units. Thus making a total spill of $200$ units. 

---

## 3. Minimum Steps!

### Problem Description

Given a string $str$, Your task here is to find the minimum number of characters to be inserted to convert it to palindrome.

### Input Format

* Single line containing a string $s$

### Constraints

* $1 \leq s.length \leq 50$
* All characters of $s$ are lower case English letters.

### Ouptput Format

* The minimum number of steps to make $s$ palindrome

### Sample Input

```shell
doselect
```

### Sample Output

```shell
5
```

