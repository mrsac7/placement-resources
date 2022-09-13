# Atlassian
> Collection of coding questions asked by Atlassian during placements at IITs

## Questions Index

* [Cartridge Recycling](#1-cartridge-recycling) [IIT-BHU'21]
* [Get the Groups](#2-get-the-groups) [IIT-BHU'21]
* [Digit Sum](#3-digit-sum) [IIT-BHU'21]

## 1. Cartridge Recycling

An office supply store has an ink cartridge recycling program. For every cartridge recycled, the customer has two options:

* Option $1$: Can simply earn a certain number of dollars for each cartridge.
* Option $2$: Can combine the cartridges with a certain number of dollars in order to purchase special products called 'parks items'.

A customer is currently enrolled in this program and would like to purhcase the maximum number of 'perks items'. Given a certain number of cartridges and dollars, and how many perks items can the customer buy?

### Example

$cartridges = 10$

$dollars = 10$

$recycleReward = 2$, the amount earned by recycling a single cartridge

$perksCost = 2$, the amount required for a customer to buy a single perks item combined with a recycled cartridge

The best thing the customer can do is to first recycle $3$ cartridges, earning $6$ dollars. After this, $7$ cartridges and $16$ dollars are left. The $7$ cartridges can be combined with $14$ dollars to purchase $7$ perks items. This is the maximum number of perks items that can be bought.

### Function Description

Complete the `maxPerksItems` function.

`maxPerksItems` has the following parameter(s):

* $int \ cartridges$: the number of cartridges on-hand
* $int \ dollars$: the number of dollars on-hand
* $int \ recycleReward$: dollars earned per recycled cartridge
* $int \ perksCost$: dollar cost of a perks item, in addition to recycling a single cartridge.

$\textbf{Returns}:
* $int$: the maximum number of perks items that can be bought

### Constraints

* $1 \leq cartridges, \ dollars \leq 10^9$
* $1 \leq recycleReward, \ perksCost \leq 10^9$


---

## 2. Get the Groups

As new students begin to arrive at college, each receives a unique ID number, $1$ to $n$. Initially, the students do not know one another, and each has a different circle of friends. As the semester progresses, other groups of friends begin to form randomly.

There will be three arrays, each aligned by an index. The first array will contain a $queryType$ which will be either $Friend$ or $Total$. The next two arrays, $students1$ and $students2$, will each contain a student ID. If the query type is $Friend$, the two students become friends. If the query type is $Total$, report the sum of the sizes of each group of friends for the two students.

### Example

$n = 4$

$queryType = ['Friend', \ 'Friend', \ 'Total']$

$student1 = [1, 2, 1]$

$student2 = [2, 3, 4]$

<img src="https://github.com/mrsac7/placement-resources/blob/main/Atlassian/fig.png" width="800">

The queries are assembled, aligned by index:

| Index &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | queryType &nbsp; &nbsp; &nbsp; | student1 &nbsp; &nbsp; &nbsp; | student2 &nbsp; &nbsp; &nbsp; |
| -------- | -------- | -------- | -------- |
| 0        | Friend   | 1        | 2        |
| 1        | Friend   | 2        | 3        |
| 2        | Total    | 1        | 4        |

Students will start as discrete groups ${1}, {2}, {3}$ and ${4}$. Students $1$ and $2$ become friends with the first query, as well as students $2$ and $3$ in the second. The new groups are ${1, 2}, {2, 3}$ and ${4}$ which simplifies to ${1, 2, 3}$ and ${4}$. In the third query, the number of friends for student $1 = 3$ and student $4 = 1$ for a Total $= 4$. Notice that student $3$ in indirectly part of the circle of friends of student $1$ because of student $2$.

### Function Description

Complete the function `getTheGroups`. For a query of type $Total$ with an index of $j$, the function must return an array of integers where the value at each index $j$ denotes the answer.

`getTheGroups` has the following parameter(s):

* $int \ n$: the number of students
* $string \ queryType[q]$: an array of query type strings
* $int \ student1[q]$: an array of student integer ID's
* $int \ student2[q]$: an array of student integer ID's

### Constraints

* $1 \leq n \leq 10^5$
* $1 \leq q \leq 10^5$
* $1 \leq students1[i], students2[i] \leq n$
* $queryType[i]$ are in the set ${'Friend', \ 'Total'}$.

---

## 3. Digit Sum

In a lottery game, a number of tickets ranging from $lowLimit$ to $highLimit$ are distributed to participants. Each coupon code is equal to the sum of the digits of the ticket number. For example, a coupon number $10$ has a code of $1 + 0 = 1$. Each participant holding a coupon code has a chance to win. The lottery prize is split among all winners.

Determine the number of ways to choose the maximum number of winners and the number of participants who will win the lottery.

### Example

$lowLimit = 1$

$highLimit = 10$

* Ticket numbers range from $1$ to $10$ and their corresponding coupon codes (the sum of their digits) are $[1, 2, 3, 4, 5, 6, 7, 8, 9, 1]$.
* For the $8$ coupon codes $2$ to $9$, each has $1$ winner.
* There is one way to have more winners. For coupon code $1$, there are $2$ winners, ticket $1$ and ticket $10$ ( $1 + 0 = 1$ ).
* The answer is $[1, 2]$

### Function Description

Complete the function `waysToChooseSum`.

`waysToChooseSum` has the following parameter(s):
* $long \ lowLimit$: a long integer, the starting number of the lottery coupons
* $long \ highLimit$: a long integer, the ending number fo the lottery coupons

$\textbf{Returns}$:
* $long[2]$: an array of long integers containing the number of ways to choose the maximum number of winners and the number of participants who will win the lottery.

### Constraints

* $1 \leq lowLimit \leq highLimit \leq 10^{18}$



