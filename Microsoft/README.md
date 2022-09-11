# Microsoft

## Questions Index

* [Patients](#1-patients)
* [Robot](#2-robot)

## 1. Patients

There are N patients (numbered 0 to N - 1) who want to visit the doctor. The doctor has S possible appointment slots, numbered from 1 to S. Each of the paitents has two preferences. Patient K would like to visit the doctor during either slot A[K] or slot B[K]. The doctor can treat only one patient during each slot.

Is it possible to assign every patient to one of their preferred slots so that there will be at most one patient assigned to each slot?

Write a function: 

```cpp
bool solution(vector<int> &A, vector<int> &B, int S);
```
  
that, given two arrays A and B, both of N integers and an integer S, returns `true` if it is possible to assign every patient to one of their preffered slots, one patient to one slot, and `false` otherwise.

Examples:

1. Given A = [1, 1, 3], B = [2, 2, 1] and S = 3, the function should return `true`. We could assign patients in the following way: [1, 2, 3], where the K-th element of the array represents the number of the slot to which patient K was assigned. Another correct assignment would be [2, 1, 3]. On the other hand, [2, 2, 1] would be an incorrect assignment as two patients would be assigned to slot 2.

2. Given A = [3, 2, 3], B = [1, 3, 1 2] and S = 3, the function should return `false`. There are only three slots available, but there are four patients who want to visit the doctor. It is therefore not possible to assign the patients to the slots so that only one patient at a time would visit the doctor.

3. Given  A = [2, 5, 6, 5], B = [5, 4, 2, 2] and S = 8, the function should return `true`. For example, we could assign patients in the following way: [5, 4, 6, 2].

4. Given A = [1, 2, 1, 6, 8, 7, 8], B = [2, 3, 4, 7, 7, 8, 7] and S = 10, the function should return `false`. It is not possible to assign all of the patients to one of their preferred slots so that only one patient will visit the doctor during one slot.

Write an **efficient** algorithm for the following assumptions:

* N is an integer within the range [1..100,000];
* S is an integer within the range [2..100,000];
* each element of arrays A and B is an integer within the range [1..S];
* no patient has two preferrences for the same slot, i.e. A[i] ≠ B[i].

---
## 2. Robot

There is a cleaning robot which is cleaning a rectangular grid of size N x M, represented by aray R consisting of N strings. Rows are numbered from 0 to N-1 (from top to bottom) and columns are numbered from 0 to M-1 (from left to right).

The robot stars cleaning in the top-left corner, facing rightwards. It moves in a straight line for as long as it can, i.e. while there is an unccoupied grid square ahead of it. When it cannot move forward, it rotates 90 degrees clockwise and tries to move forward again until it encounteres another obstacle, and so on. Dots in the array (".") represent empty squares and "X"'s represent occupied squares (ones the robot cannot move through). Each square that the robot occupied at least once is considered clean. The robot moves indefinitely. 

Write a function:

```cpp
int solution(vector<string> &A);
```
that, given an array R consisting of N strings, each of length M, representing the grid, returns the number of clean sqaures.

**Examples:**

1. Given A = ["...X..", "....XX", "..X..."], your function should return 6.

<img src="https://github.com/mrsac7/placement-resources/blob/main/Microsoft/g1.png" width="300">

The robot starts at (0, 0), facing rightwards, and moves to (0, 2), where it turns due to the obstacle at (0, 3). Then it goes down from (0, 2) to (1, 2), where it changes direction again due to another obstacle. Next it goes left from (1, 2) to (1, 0), where it turns once because of the grid boundary, then it moves once and turns once more, which makes it stand again at position (0, 0) facing rightwards, just as the beginning, which means it will now repeat the loop indefinitely. The total number of cleaned sqaures is 6.

2. Given A = ["....X..", "X......", ".....X.", "......."], your function should return 15.

<img src="https://github.com/mrsac7/placement-resources/blob/main/Microsoft/g2.png" width="350">

3. Given A = ["...X.", ".X..X", "X...X", "..X.."], your function should return 9.

<img src="https://github.com/mrsac7/placement-resources/blob/main/Microsoft/g3.png" width="275">

4. Given A = ["."], your function should return 1, because there is only one square on the grid and it is cleaned in the first move.

Assume that:

* N and M are integers within the range [1..20];
* top-left cell is empty;
* each string in R consists only of the following characters: "." and/or "X".

In your solution, focus on **correctness**. The performance of your solution will not be the focus of the assessment.


