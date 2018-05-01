# Leetcode: Binary Tree Pruning     :BLOG:Medium:


---

Binary Tree Pruning  

---

Similar Problems:  
-   Tag: [#binarytree](https://code.dennyzhang.com/tag/binarytree)

---

We are given the head node root of a binary tree, where additionally every node's value is either a 0 or a 1.  

Return the same tree where every subtree (of the given tree) not containing a 1 has been removed.  

(Recall that the subtree of a node X is X, plus every node that is a descendant of X.)  

Example 1:  

    Input: [1,null,0,0,1]
    Output: [1,null,0,null,1]
     
    Explanation: 
    Only the red nodes satisfy the property "every subtree not containing a 1".
    The diagram on the right represents the answer.

![img](//raw.githubusercontent.com/DennyZhang/images/master/code/binarytree_prune1.png)  

Example 2:  

    Input: [1,0,1,0,0,0,1]
    Output: [1,null,1,null,1]

![img](//raw.githubusercontent.com/DennyZhang/images/master/code/binarytree_prune2.png)  

Example 3:  

    Input: [1,1,0,1,1,0,1,0]
    Output: [1,1,0,1,1,null,1]

![img](//raw.githubusercontent.com/DennyZhang/images/master/code/binarytree_prune3.png)  

Note:  

-   The binary tree will have at most 100 nodes.
-   The value of each node will only be 0 or 1.

Github: [challenges-leetcode-interesting](https://github.com/DennyZhang/challenges-leetcode-interesting/tree/master/binary-tree-pruning)  

Credits To: [leetcode.com](https://leetcode.com/problems/binary-tree-pruning/description/)  

Leave me comments, if you have better ways to solve.  

    ## Blog link: https://code.dennyzhang.com/binary-tree-pruning
    ## Basic Ideas: post-order
    ##
    ## Complexity: Time O(n), Space O(1)
    ##
    # Definition for a binary tree node.
    # class TreeNode:
    #     def __init__(self, x):
    #         self.val = x
    #         self.left = None
    #         self.right = None
    
    class Solution:
        def pruneTree(self, root):
            """
            :type root: TreeNode
            :rtype: TreeNode
            """
            if root is None: return None
            root.left = self.pruneTree(root.left)
            root.right = self.pruneTree(root.right)
            if root.val == 0 and not root.left and not root.right:
                return None
            else:
                return root

    // Blog link: https://code.dennyzhang.com/binary-tree-pruning
    // Basic Ideas: post-order
    /**
     * Definition for a binary tree node.
     * type TreeNode struct {
     *     Val int
     *     Left *TreeNode
     *     Right *TreeNode
     * }
     */
    func pruneTree(root *TreeNode) *TreeNode {
    
    }