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
      * The empty node (None) has depth -1.
      * The root node has depth 0. 
    * The **height** of a node is the length of the longest downward path to a leaf from that node, or equivalently, the depth of its deepest node. The height of the root is the height of the tree. 
      * The empty node (None) has height -1.
      * Leaf nodes have height 0.
      * For every node, `height = 1 + max(left_tree_height, right_tree_height)`
    * The **diameter** of a tree is the length of the longest path between any two nodes in a tree. 
      * [L543](https://leetcode.com/problems/diameter-of-binary-tree/): For every node, `diameter = left_tree_height + right_tree_height + 2`.
 
4. Tree iterative traversal summary:
  * Binary Tree Traversals:
    <p align="center">
        <img src="../imgs/tree_traversal_summary.png" width="43%"/>
    </p>
    
    * Preorder traversal:

     ```python
     class Solution:
         def preorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
             st, res = [], []
        
             while st or root:
                 if root:
                     res.append(root.val)
                     st.append(root)
                     root = root.left
                 else:
                     node = st.pop()
                     root = node.right
             return res
     ```
       or 
     ```python
     class Solution:
         def preorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
             st, res = [root], []
        
             while st:
                 node = st.pop()
                 
                 if not root:
                     continue
                 else:
                     res.append(node.val)
                     st.append(node.right)
                     st.append(node.left)
             return res
      ```
       
       
     * Inorder traversal:

      ```python
      class Solution:
          def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
              st, res = [], []
        
              while st or root:
                  if root:
                      st.append(root)
                      root = root.left
                  else:
                      node = st.pop()
                      res.append(node.val)
                      root = node.right
                
              return res
      ```
     * Postorder traversal:

      ```python
      class Solution:
          def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
              st, res = [root], []
        
              while st:
                  node = st.pop()
            
                  if not node:
                      continue
                  else:
                      res.append(node.val)
                      st.append(node.left)
                      st.append(node.right)
                
              return res[::-1]
       ```

5. Some problems I didn't come up with a good idea when I first try to solve them. Maybe worth revisiting:
  * **Easy**: [L1022](https://leetcode.com/problems/sum-of-root-to-leaf-binary-numbers/), [L235](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/) (In BST, the lowest common ancestor (LCA) of given input `p` and `q` is the split node which has the property: `p.val <= node.val <= q.val` or `q.val <= node.val <= p.val`). [L108](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/), [L993](https://leetcode.com/problems/cousins-in-binary-tree/), [L543](https://leetcode.com/problems/diameter-of-binary-tree/), [L703](https://leetcode.com/problems/kth-largest-element-in-a-stream/), [L101](https://leetcode.com/problems/symmetric-tree/), [L501](https://leetcode.com/problems/find-mode-in-binary-search-tree/)
  * **Medium**: [L236](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/solution/)
