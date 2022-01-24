# Microsoft Online Assessment

## Task 1
There are N patients (numbered 0 to N - 1) who want to visit the doctor. The doctor has S possible appointment slots, numbered from 1 to S. Each of the paitents has two preferences. Patient K would like to visit the doctor during either slot A[K] or slot B[K]. The doctor can treat only one patient during each slot.

Is it possible to assign every patient to one of their preferred slots so that there will be at most one patient assigned to each slot?

Write a function: 
  bool solution(vector<int> &A, vector<int> &B, int S);
  
that, given two arrays A and B, both of N integers and an integer S, returns true if it is possible to assign every patient to one of their preffered slots, one patient to one slot, and false otherwise.
