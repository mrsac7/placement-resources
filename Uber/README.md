# Uber
> Collection of coding questions appearing in online assessment of Uber during campus placements at IIT/NITs, and other top engineering colleges in India.

## Questions Index

* [Base 2 To Base 6](#1-base-2-to-base-6) [IIT-BHU'22]
* [Dumb Amaru](#2-dumb-amaru) [IIT-BHU'22]
* [Genie](#3-genie) [IIT-BHU'22]

## 1. Base 2 To Base 6

Given a number in base $2$, convert it into base $6$.

For e.g.

* $1100$ in base $2$ represented as $[false, false, true, true]$ in test #1,
* $12$ in base $10$, and
* $20$ in base $6$ represented as $[0, 2]$ in test #1.

* **[execution time limit] 1 seconds (cpp)**
* **[input] array.boolean base2**
  
  Max length = $100$
  
  if ith position of the array is true that means the ith position of the number is $1$.
  
* **[output] array.integer**
  
  ith position of the array represents the ith position of the number is in base $6$.
  
### Solution

<details>
  <summary>Show</summary>
  
  ```cpp
  vector<int> base2To6Hire2020(vector<bool> base2) {
    vector<int> R = {0};
    int N = base2.size(), A = 2, B = 6;
    reverse(base2.begin(), base2.end());
    
    for (int i = 0; i < N; i++) {
      int x = base2[i];
      for (int j = 0; j < R.size(); j++) {
        int z = R[j] * A + x;
        R[j] = z % b;
        x = z / b;
        if (j == R.size() - 1 && x > 0) 
          R.push_back(0);
      }
    } 
    return R;
  }
  ```
  
</details>
  
---
## 2. Dumb Amaru

Amaru and Kapkan were playing Rainbow $6$ Siege in which Kapkan strategically placed $N$ bombs all over the map.

Each bomb has 3 numbers associated to it $X, L$ and $R$ and can only be defused by finding the maximum value of ( $X \oplus Y$ ) where $\oplus$ represents the bitwise $XOR$ operation and $Y$ can be any number in the interval $[L, R]$.

Amaru is a dumb player who only rushes in, so can you help her in winning by finding the maximum value of ( $X \oplus Y$ ) for all the $N$ bombs?

### Constraints:
* $1 \leq N \leq 5000$
* $1 \leq L \leq R \leq 10^9$
* $1 \leq X \leq 10^9$

  * **[execution time limit] 1 seconds (cpp)**
  * **[input] integer n**
  * **[input] array.integer x**
  * **[input] array.integer l**
  * **[input] array.integer r**
  * **[output] array.integer**
  
### Solution

<details>
  <summary>Show</summary>
  
  ```cpp
  vector<int> FY22CampusDumbAmaru(int n, vector<int> x, vector<int> l, vector<int> r) {
    vector<int> res;
    for (int i = 0; i < n; i++) {
      int X = x[i], L = l[i], R = r[i];
      int ans = 0, val = 0;
      for (int j = 30; j >= 0; j--) {
        if (X >> j & 1) {
          if (val >= L) ans |= (1 << j);
          else if (val >> L & 1) val += (1 << j);
          else ans |= (1 << j);
        }
        else {
          int val0 = val + (1 << j);
          if (val0 <= R) {
            val = val0;
            ans |= (1 << j);
          }
        }
      }
      res.push_back(ans);
    }
    return res;
  }
  ```
  
</details>

---
## 3. Genie

Zasho is a popular genie. Being a genie, he's in the business of granting wishes, and a lot of people ask him for help. However, his power is limited - currently it is $p$ units.

To grant the $i$-th wish, Zasho needs to have at least $x$ units of power. After a wish is granted, his rating changes by $y$ ( $y$ can be positive or negative). Of course, his power should not dip below zero - otherwise he won't be able to grant any wishes. He can choose to grant wishes in any order.

Zasho wants to grant the maximum mumber of wishes possible so that he remains popular. Can you help him figure out how many wishes he should grant?

In other words, find the maximum possible size of the subset of wishes so that Zasho has enough power before starting each, and has non-negative power after completing each wish.

### Constraints:

* $1 \leq n \leq 100, 1 \leq p \leq 30,000$
* The next $n$ lines contain the wishes, one per line. The $i$-th wish is represented as a pair of integers $x$ and $y$ ( $1 \leq x \leq 3\times10^4, -300 \leq y \leq 300$ )

### Example

If the input is

```shell
3 5
4 -5
4 -2
1 3
```

The output is $3$ because order $<2, 3, 1>$ exists for Zasho to fulfil every wish.

  * **[execution time limit] 1 seconds (cpp)**
  * **[input] integer p**
  * **[input] array.integer x**
  * **[input] array.integer y**
  * **[output] array.integer**

