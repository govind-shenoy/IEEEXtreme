# Segment Tree
The segment tree is a data structure that is capable of processing different queries on the array in an efficient way.

A segment tree is usually created with the following routine.

createTree(left, right):
    currentNode = new node()
    currentNode->left = left
    currentNode->right = right
    currentNode->tag = 0
    if (left < right):
        middle = (left + right) / 2
        currentNode->leftSon = createTree(left, middle)
        currentNode->rightSon = createTree(middle + 1, right)
    return currentNode

The routine is called as:

    root = init(1, N)

Consider the following segment tree operations:

changeSegtree(currentNode, left, right):
   currentNode->tag = 1

   if (left == currentNode->left) and (right == currentNode->right)
       return

   newRight = min(right, currentNode->leftSon->right)
   if (left <= newRight):
       changeSegtree(currentNode->leftSon, left, newRight)

   newLeft = max(left, currentNode->rightSon->left)
   if (newLeft <= right):
       changeSegtree(currentNode->rightSon, newLeft, right)

                
change(left, right):
    changeSegtree(root, left, right)

Finally, an in-order traversal of the tree can be done with the following routine:

traverse(currentNode):
    if (currentNode->leftSon != NULL)
        traverse(currentNode->leftSon)
    print currentNode->tag
    if (currentNode->rightSon != NULL)
        traverse(currentNode->rightSon)


traverse(root)

You are given the value of N, denoting the length of the array on which the segment tree is built on (i.e. the second parameter to the init routine). You are also given M integers T1, T2, ..., TM. Here, M is the number of nodes in the segment tree and you'll have calculate it by yourself.

Your task is to find the minimum number of non-overlapping segments, so that after calling the change routine for each of these segments successively, on a newly created segment tree, the traverse routine will output T1, T2, ..., TM, or state that such a set of segments doesn't exist.

Two segments (l1,r1) and (l2,r2) are considered overlapping if there is some i such that l1 ≤ i ≤ r1 and l2 ≤ i ≤ r2.
## Input

The first line of the input contains an integer T denoting the number of test cases. The description of T test cases follows.

The first line of each test case contains a single integer N denoting the length of segment tree range.

The second line contains M space-separated integers T1, T2, ..., TM denoting what the tags of the segment tree's nodes should be, in in-order traversal. Here, M is the number of nodes in the segment tree.
## Output

For each test case, output a single line containing the minimum number of segments to modify. In case it's impossible to achieve the given configuration of tags, output -1.
## Constraints

    1 ≤ T ≤ 5 × 104
    1 ≤ N ≤ 105
    1 ≤ Sum of N ≤ 5 × 105

## Example

#### Input:
    2
    2
    1 1 1
    2
    1 0 1

#### Output:
    2
    -1

## Explanation

*Example case 1*. We can call change(1, 1) and change(2, 2).

*Example case 2*. There is no set of segments that would give the tree with such configuration of tags.
