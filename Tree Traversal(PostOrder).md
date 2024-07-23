### Tree Traversal(PostOrder)
Binary Tree Postorder Traversal

Given the root of a binary tree, return the postorder traversal of its nodes' values.

### Example 1:
Input: root = [1,null,2,3]
Output: [3,2,1]

### Example 2:
Input: root = []
Output: []

### Example 3:
Input: root = [1]
Output: [1]
### Code(Java without Driver Code)
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
    public List<Integer> postorderTraversal(TreeNode root) {
        if(root==null){
            return list;
        }
        postorderTraversal(root.left);
        postorderTraversal(root.right);
        list.add(root.val);
        return list;
    }
}
```
