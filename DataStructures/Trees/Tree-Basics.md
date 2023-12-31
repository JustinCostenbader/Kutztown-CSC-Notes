# Trees
- Lists, stacks, and queues are **linear**
  - Items are one after another
- Trees are **nonlinear, hierarchical**
  - Item can have more than one immediate successor
 
## Unrooted tree vs rooted tree
<p>
An unrooted tree is an acyclic graph (without cycle).
<br>
Label one node as the root ➡️ rooted tree.
</p>

## Terminology
- Parent, child, sibling, ancestor, descendant
- Root, leaf, internal node
- Subtree

## General Tree and Binary Tree
- General tree
  - No limit on the number of children
 
```mermaid
graph TD;
A --> B
A --> F
A --> J
B --> C
B --> D
B --> E
F --> G
F --> H
J --> K
J --> L
J --> M
J --> N
M --> P
M --> Q
```
- Binary tree
  - at most two children
  - left child and right child

```mermaid
graph TD;
Jose --> Deepak
Jose --> Qiang
Deepak --> Anton
Deepak --> Elisa
Qiang --> Mia
Qiang --> Zoe
```

## Expression Tree
Binary trees that represent algebraic expressions
<br>
<br>
**a - b**
```mermaid
graph TD;
- --> a
- --> b
```
**a - b / c**
```mermaid
graph TD;
- --> a
- --> /
/ --> b
/ --> c
```
**(a-b) x c**
```mermaid
graph TD;
x --> -
x --> c
- --> a
- --> b
```

## Height of a Tree
- The number of nodes on the longest path from root to a leaf
- Maximum Height
  - The maximum possible height of a binary tree with n nodes is n
- Ex: Binary trees with the same nodes but different heights

![height](treeheight.png)


## Full Binary Trees
A full binary tree has all possible nodes at all levels

## Complete Binary Trees
A complete binary tree is full up to height h-1, with height h filled in from left to right.

## ADT Binary Tree
- Operations of ADT binary tree
  - Add, remove
  - Set, retrieve data
  - Test for empty
  - Traversal operations that visit every node

## Traversal of a Binary Tree
- Options for when to visit the root
  - Preorder: before it traverses both subtrees
  - Inorder: after it traverses left subtree, before it traverses right subtree
  - Postorder: after it traverses both subtrees
- Time complexity: O(n)
  
```mermaid
graph TD;
60 --> 20
60 --> 70
20 --> 10
20 --> 40
40 --> 30
40 --> 50
```
Preorder: 60, 20, 10, 40, 30, 50, 70
<br>
Inorder: 10, 20, 30, 40, 50, 60, 70
<br>
Postorder: 10, 30, 50, 40, 20, 70, 60

## Binary Search Tree (BST)
- A binary tree with the additional condition: The value in each tree node is
  - greater than all values in left subtree
  - less than all values in right subtree
