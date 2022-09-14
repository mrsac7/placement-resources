# Slice
> Collection of coding questions asked by Slice during placements at IITs

## Questions Index

* [Message Passing](#1-message-passing) [IIT-BHU'22]
* [Team Formation](#2-team-formation) [IIT-BHU'22]

## 1. Message Passing

You are in a corporate and you need to communicate about a strategic mission in-person to all the people in your company. This information can NOT be broadcasted so you have to tell it to each person in a $1-1$ session. It takes $1$ hour to communicate the information from one person to another. At any given point of time, a manager can communicate this vital strategic information to one of his/her direct reports. Let us say we have the following reporting structure: Find out the minimum number of hours in which the information can be communicated to all the members of the organization.

<p align="center">
  <img src="https://github.com/mrsac7/placement-resources/blob/main/Slice/tree.png" width="450">
<p>

In the above tree, 

At the end of hour $1$, $A$ will pass the info to $B$.

At the end of hour $2$, $A$ will pass the info to $E$, $B$ will pass the info to $H$.

At the end of hour $3$, $A$ will pass the info to $G$, $B$ will pass the info to $I$, $E$ will pass the info to $K$.

... and so on.

Find the minimum number of hours in which all the people in the organization are informed of the strategic mission.

### Sample Input

Each line in the input represents an edge between two nodes in the tree separated by a comma.

```shell
A, B
A, C
A, D
A, E
A, F
A, G
B, H
B, I
B, J
H, N
H, O
E, K
E, L
K, P
L, Q
G, M
```

### Sample Output

```shell
6
```

---

## 2. Team Formation

One day the manager at a fintech company decides to create a team for the next project. There are a total of $n$ employees and the skill-level of $i^{th}$ employee is $A_i$.

He thinks that the more employees a project has, the easier it gets to work and the project would be finished in fewer days. So he decides to create a team with the maximum number of employees possible. But there must be a balance factor within the team, so the manager decides to create a team in such a way that the skill-level of each pair of employees within the team would differ by no more than 5.

You task is to help the manager find the maximum number of employees that could be accomodated in the team.

### Example

$n = 8$

$4, 17, 8, 24, 6, 10, 12, 9$

In the example above, there can be a maximum of $4$ members in the team, the team can comprise of employees with skill-level $4, 8, 6, 9$, i.e. employees with indices $1, 3, 5, 8$.

#### Function Description

You will be give the size of the array and the array consisting of the skill level of the employees in the company. You'll have to write a function `computeMaximumTeamMembers` in the editor below. The function must return an integer denoting the maximum number of employees that could be accommodated in the team.

`computeMaximumTeamMembers` has the following parameters:

* $number \textunderscore of \textunderscore employees$: the size of the array of the total number of employees in the company
  
* $skill \textunderscore level$: an array of integers, where each $A[i]$ is the skill level of the employee $i$.
  
### Constraints
  
* $1 \leq n \leq 10^4$
* $1 \leq A_i \leq 10^9$

### Sample Input

```shell
6
1 10 17 12 15 2
```

### Sample Output

```
3
```

### Explanation

The manager can create a team with skills $[17, 12, 15]$.
