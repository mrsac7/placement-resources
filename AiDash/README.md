# AiDash
> Collection of coding questions appearing in online assessment of AiDash during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Jump To The Flag](#1-jump-to-the-flag) [IIT-BHU'22, IIT-R'22]
* [Whole Minute Dilemma](#2-whole-minute-dilemma) [IIT-BHU'22, IIT-G'22]
* [Longest Increasing Subsequence](#2-longest-increasing-subsequence) [IIT-BHU'22]

## 1. Jump To The Flag

A climber is trying to reach a flag that is some height above the ground. In the attempt to reach the flag, the climber can make any number of jumps up the rock wall where the flag is mounted. Movements can only be made up the wall, and the climber must end at exactly the height of the flag.

There are $2$ types of jumps:

1. A jump of height $1$.
2. A jump of height $bigjump$.

Determine the minimum number of jumps it will take the climber to reach the flag's exact height.

### Example

* $flagHeight = 8$
* $bigjump = 3$

The climber starts at height $0$, takes two jumps of height $bigjump$ and two of height $1$ to reach exactly $8$ units in $4$ jumps.

### Function Description

Complete the function `jumps`.

`jumps` has the following parameter(s):

* $int \ \ flagHeight$: an integer, the flag height
* $int \ \ bigjump$: an integer, the height of the second type of jump

$\textbf{Returns}$

* $int$: an integer, the minimum number of jumps necessary

### Constraints

* $1 \leq bigjump, flagHeight \leq 10^9$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
3                        
1
```

</td>
<td>

```shell
3                         
```

</td>
</tr>
</table>

### Solution

<details>
  <summary>Show</summary>
  
  ```cpp
  int jumps(int flagHeight, int bigJump) {
    return flagHeight / bigJump + flagHeight % bigJump;
  }
  ```
  
</details>

---

## 2. Whole Minute Dilemma

A music player allows users to choose songs to play, but only in pairs and only pairs of songs with durations that add up to a multiple of $60$ seconds (e.g. $60, \ 120, \ 180$\). Given a list of song durations, calculate the total number of different song pairs that can be chosen.

### Example

$n = 3$

$songs = [40, \ 20, \ 60]$

One pair of songs can be chosen whose combined duration is a multiple of a whole minute $(40 + 20 = 60)$ and the return value would be $1$> While the third song is a single minute long, songs must be chosen in pairs.

### Function Description

Complete the function `playlist`. 

`playlist` has the following parameter(s):

* $int \ \ songs[n]$: array of integers representing song durations in seconds

$\textbf{Returns}$

* $int$: the number of songs pairs that add up to a multiple of a minute

### Constraints

* $1 \leq n \leq 10^5$
* $1 \leq songs[i] \leq 1000$, where $0 \leq i \lt n$

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
10 50 90 30
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

The first and second songs pair to $60$ seconds. The third and fourth songs pair to $120$ seconds. No other pairs will satisfy the requirement.

### Solution

<details>
  <summary>Show</summary>
  
  ```cpp
  long playlist(vector<int> songs) {
    int N = songs.size(), M = 60;
    vector<int> A(65);
    long ans = 0;
    for (int i = 0; i < N; i++) {
      int x = (M - songs[i] % M) % M;
      ans += A[x];
      A[songs[i] % M]++;
    }
    return ans;
  }
  ```
  
</details>

---

## 3. Longest Increasing Subsequence

A sub-sequence is a sequence that can be created by deleting zero or more elements from the original sequence while maintaining order.

A sequence $S$ is said to be increasing if every element in the sequence is greater than the previous element in that sequence, i.e. for every element $S[i + 1], \ S[i] < S[i + 1]$. Mathematically, for the sequence $S = (S[1], \ ..., \ S[n - 1])$, $S[i] < S[i + 1]$ $\forall \ i \in [1, \ n - 1]$.

You will be given an array of integers and must determine the length of the longest increasing subsequence.

For example, your array $S = [1, \ 2, \ 2, \ 3, \ 1, \ 6]$. Two examples of strictly increasing subsequences of that array are $(1, \ 2)$, $(1, \ 2, \ 3)$. Note that the $2$ cannot repeat in the second subsequence as $2 \nless 2$. The longest increasing subsequence has a length of $4$: $LIS = [1, \ 2, \ 3, \ 6]$.

### Function Description

Complete the function `findLIS`. The function must return the length of the longest increasing subsequence that can be created from the array.

`findLIS` has the following parameter(s):

* $s[s[0], \ ..., \ s[n - 1]]$: an array of integers

### Constraints

* $1 \leq n \leq 1000$
* $1 \leq s[i] \leq 10^6$

### Sample Test

<table>
<tr>
<td> Sample Input </td>
<td> Sample Output </td>
</tr>
<tr>
<td>

```shell
3                        
1 4 3
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

Inputs are $s = [1, \ 4, \ 3]$. Increasing subsequences are $[1, \ 4]$ and $[1, \ 3]$.

The longest increasing sub-sequence has $2$ elements.

### Solution

<details>
  <summary>Show</summary>
  
  ```cpp
  int findLIS(vector<int> S) {
    int N = S.size();
    vector<int> v = {0};
    for (auto x: S) {
      int j = lower_bound(v.begin(), v.end(), x) - v.begin();
      if (j == v.size()) v.push_back(x);
      else v[j] = x;
    }
    return (int) v.size() - 1;
  }
  ```
  
</details>


