# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)

##  Trees Terminology
+ Node - A Tree node is a component which may contain it’s own values, and references to other nodes
+ Root - The root is the node at the beginning of the tree
+ K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2
+ Left - A reference to one child node, in a binary tree
+ Right - A reference to the other child node, in a binary tree
+ Edge - The edge in a tree is the link between a parent and child node
+ Leaf - A leaf is a node that does not have any children
+ Height - The height of a tree is the number of edges from the root to the furthest leaf
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)

### Traversals
1- Depth First (Pre-order)

    Pre-order: root >> left >> right
    In-order: left >> root >> right
    Post-order: left >> right >> root
The most common way to traverse through a tree is to use recursion. With these traversals, we rely on the call stack to navigate back up the tree when we have reached the end of a sub-path.
2- Breadth First
Traditionally, breadth first traversal uses a queue (instead of the call stack via recursion) to traverse the width/breadth of the tree. 