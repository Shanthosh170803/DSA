### Tree Traversal(Pre order)
Binary Tree Preorder Traversal
Given the root of a binary tree, return the preorder traversal of its nodes' values.

### Example 1:
Input: root = [1,null,2,3]
Output: [1,2,3]

### Example 2:
Input: root = []
Output: []

### Example 3:
Input: root = [1]
Output: [1]

### Code(Java-without DriverCode)
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
    public List<Integer> preorderTraversal(TreeNode root) {
        if(root==null){
            return list;
        }
        list.add(root.val);
        preorderTraversal(root.left);
        preorderTraversal(root.right);
        return list;
        
    }
}
```
