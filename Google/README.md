# Google

## 1. Cookies

Alice loves cookies. One day while wandering, she came across a cookie-world that has _N_ cookies in it, numbered from _1_ to _N_. 
Each cookie has an energy count of _E<sub>i</sub>_ and is stored at height _H<sub>i</sub>_. Initially, Alice's energy is _K_, and after eating a cookie with energy _E<sub>i</sub>_ her energy increases by _E<sub>i</sub>_.

In each step, Alice can climb to a certain height and can eat a cookie and return to her original position, but climbing requires energy, and she can only climb height _H<sub>i</sub>_ if her energy _K_ is greater than or equal to the height _H<sub>i</sub>_.

**Task**

Determine the maximum number of cookies she can eat and the maximum energy she can attain after each step.

_Notes_

* _1_-based indexing is followed.
* Alice can eat the cookies in any order as long as the cookie she is trying to maximize her energy at each step.

**Example**

_Assumptions_

* _N = 6_
* _H = [6, 1, 3, 9, 15, 30]_
* _E = [3, 5, 1, 2, 4, 3]_
* _K = 9_

_Approach_

Cookies eaten by Alice to maximize her energy after each step are:

* At first, Alice will eat cookie with energy _5_ at a height of _1_ and her energy increases to _9 + 5 = 14_.
* Then Alice will eat cookie with energy _3_ at a height of _6_ and her energy increases to _14 + 3 = 17_.
* Then Alice will eat cookie with energy _4_ at a height of _15_ and her energy increases to _17 + 4 = 21_.
* Then Alice will eat cookie with energy _2_ at a height of _9_ and her energy increases to _21 + 2 = 23_.
* Then Alice will eat cookie with energy _1_ at a height of _3_ and her energy increases to _23 + 1 = 24_.
* Alice will not be able to eat cookie at a height of _30._

Hence, the number of cookies eaten by Alice is _5_.

Therefore the answer is _[5, 14, 17, 21, 23, 24]._

**Function Description**

Complete the `solve` function provided in the editor. This function take the following _4_ parameters and returns an array of integers:

* _N:_ Represents an integer denoting the number of cookies
* _H:_ Represents an integer array denoting the height of _i<sub>th</sub>_ cookie as _H<sub>i</sub>_ (1 ≤ _i_ ≤ N)
* _E:_ Represents an integer array denoting the energy of _i<sub>th</sub>_ cookie as _E<sub>i</sub>_ (1 ≤ _i_ ≤ N)
* _K:_ Represents an integer denoting Alice's initial energy

**Output:**

Print two lines. In the first line, print the maximum number of cookies she can eat and in the next line print _N_ integers denoting the maximum energy she can attain after each step.

**Constraints:**

* 1 ≤ _N_ ≤ 10<sup>5</sup>
* 1 ≤ _H<sub>i</sub>_ ≤ 10<sup>5</sup>
* 1 ≤ _E<sub>i</sub>_ ≤ 10<sup>5</sup>
* 1 ≤ _K_ ≤ 10<sup>5</sup>

