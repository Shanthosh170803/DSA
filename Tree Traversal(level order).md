### Tree Traversal(level order)
Binary Tree Level Order Traversal
Given the root of a binary tree, return the level order traversal of its nodes' values. (i.e., from left to right, level by level).

### Example 1:
Input: root = [3,9,20,null,null,15,7]
Output: [[3],[9,20],[15,7]]

### Example 2:
Input: root = [1]
Output: [[1]]

### Example 3:
Input: root = []
Output: []
``` java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 * int val;
 * TreeNode left;
 * TreeNode right;
 * TreeNode() {}
 * TreeNode(int val) { this.val = val; }
 * TreeNode(int val, TreeNode left, TreeNode right) {
 * this.val = val;
 * this.left = left;
 * this.right = right;
 * }
 * }
 */
class Solution {
    List<List<Integer>> arrlist = new ArrayList<>();
    Queue<TreeNode> que = new LinkedList<>();

    public List<List<Integer>> levelOrder(TreeNode root) {
        if (root != null) {
            que.add(root);
            while (!que.isEmpty()) {
                int size = que.size();
                ArrayList<Integer> list = new ArrayList<>();
                for (int i = 0; i < size; i++) {

                    TreeNode node = que.poll();
                    if (node.left != null) {
                        que.add(node.left);
                    }
                    if (node.right != null) {
                        que.add(node.right);
                    }
                    list.add(node.val);
                }
                arrlist.add(list);
            }
            return arrlist;
        }
        return arrlist;
    }
}
```
