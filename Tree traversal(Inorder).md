### Tree traversal(Inorder)
 Binary Tree Inorder Traversal
 Given the root of a binary tree, return the inorder traversal of its nodes' values.

### Example 1:
Input: root = [1,null,2,3]
Output: [1,3,2]

### Example 2:
Input: root = []
Output: []

### Example 3:
Input: root = [1]
Output: [1]

### Code(Java - withour driver code) 
``` java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    LinkedList<Integer> list=new LinkedList<>();
    public List<Integer> inorderTraversal(TreeNode root) {

        if(root==null){
            return list;
        }
        inorderTraversal(root.left);
        list.add(root.val);
        inorderTraversal(root.right);
        return list;
    }
}
```
