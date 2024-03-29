# Sereja and Tree 
Sereja likes to hang around trees. A tree is an undirected graph on N vertices with N-1 edges and no cycles. Sereja has his own peculiar way of comparing two trees. To describe it, let's start with the way Sereja stores a tree. For every tree, Sereja has a value V — the root of the tree, and for every vertex i, he has an ordered list Q[i] with L[i] elements — Q[i][1], Q[i][2], ..., Q[i][L[i]] which are children of the vertex i. Sereja assumes two trees to be equal if their roots are the same and for every i, the ordered list Q[i] is the same in both the trees that Sereja compares.

So if Sereja has tree#1 given as [V=1, Q[1]=[2, 3], Q[2]=[], Q[3]=[]] and tree#2 given as [V=1, Q[1]=[3, 2], Q[2]=[], Q[3]=[]], they will be considered different because Q[1] in the first tree is not equal to Q[1] in the second tree.

For any vertex i, Sereja calls number of vertices adjacent to it as E[i].

Given an array C of N elements, Let f(C) be the number of different trees (in Sereja's representation) such that there exists a permutation P[1], P[2], ... , P[N] so that E[P[1]]=C[1], E[P[2]]= C[2], ... , E[P[N]]=C[N].

Sereja gives you the array C. You have to compute the number f(C) modulo 1000000007 (109+7).
## Input
The first line of input contains the integer N. Next line contains N integers C[1], C[2], ..., C[N].
## Output
Output answer in single line.
## Constraints

    1 ≤ N ≤ 80
    0 ≤ C[i] ≤ 80

## Example

#### Input:
    4
    1 1 2 2

#### Output:
    72

#### Input:
  5
  3 1 1 1 2

#### Output:
    960

#### Input:
    3
    2 2 2

#### Output:
    0
