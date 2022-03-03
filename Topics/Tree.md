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

3. A [node](https://en.wikipedia.org/wiki/Node_(computer_science)) is a structure which may contain a value or condition, or represent a separate data structure (which could be a tree of its own). Each node in a tree has zero or more **child nodes**, which are below it in the tree (by convention, trees are drawn growing downwards). A node that has a child is called the child's **parent node** (or superior). A node has at most one parent, but possibly many ancestor nodes, such as the parent's parent. Child nodes with the same parent are **sibling nodes**.
    * An **internal node** (also known as an **inner node**, **inode** for short, or **branch node**) is any node of a tree that has child nodes. Similarly, an **external node** (also known as an **outer node**, **leaf node**, or **terminal node**) is any node that does not have child nodes.
    * The **depth** of a node is the length of the path to its root (i.e., its root path). This is commonly needed in the manipulation of the various self-balancing trees, [AVL Trees](https://en.wikipedia.org/wiki/AVL_tree) in particular. 
      * The root node has depth 0. 
    * The **height** of a node is the length of the longest downward path to a leaf from that node, or equivalently, the depth of its deepest node. The height of the root is the height of the tree. 
      * Leaf nodes have height 0.
    * A tree with only a single node (hence both a root and leaf) has depth and height zero. Conventionally, an empty tree (tree with no nodes, if such are allowed) has height and depth −1.

4. Some problems I didn't come up with a good idea when I first try to solve them. Maybe worth revisiting:
  * **Easy**: [L1022](https://leetcode.com/problems/sum-of-root-to-leaf-binary-numbers/), [L235](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/) (In BST, the lowest common ancestor (LCA) of given input `p` and `q` is the split node which has the property: `p.val <= node.val <= q.val` or `q.val <= node.val <= p.val`)
  * **Medium**: [L236](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/solution/)
