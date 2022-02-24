# Tree
**Timeline (Feb. 24 - )**
1. How to traverse the tree? There are two general strategies to traverse a tree:
  * **Depth First Search (DFS)**
    * In this strategy, we adopt the **depth** as the priority, so that one would start from a root and reach all the way down to certain leaf, and then back to root to reach another branch. The DFS strategy can further be distinguished as **preorder**, **inorder**, and **postorder** depending on the relative order among the root node, left node and right node.
  * **Breadth First Search (BFS)**
    * We scan through the tree level by level, following the order of height, from top to bottom. The nodes on higher level would be visited before the ones with lower levels.
    
    <p align="center">
        <img src="../imgs/tree_traversal.png" width="43%"/>
    </p>

2. [Master Theorem](../resources/master_theorem.pdf) for calculating the time complexity for recursion problems.
