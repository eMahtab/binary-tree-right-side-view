# Binary Tree Right Side View
## https://leetcode.com/problems/binary-tree-right-side-view

Given a binary tree, imagine yourself standing on the right side of it, return the values of the nodes you can see ordered from top to bottom.

```
Example:
Given the below tree, right side view of the tree will be : [1, 3, 4, 6]
Explanation:

   1            <---
 /   \
2     3         <---
 \     \
  5     4       <---
 / 
6               <---
```

## Implementation :

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public List<Integer> rightSideView(TreeNode root) {
        List<Integer> list = new ArrayList<>();
        if(root == null)
            return list;
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        while(!queue.isEmpty()){
            int size = queue.size();
            for(int i = 0; i < size; i++){
                TreeNode current = queue.poll();
                if(i == size - 1)
                    list.add(current.val);
                if(current.left != null)
                    queue.offer(current.left);
                if(current.right != null)
                    queue.offer(current.right);
            }
        }
       return list; 
    }
}
```

# References :
https://www.youtube.com/watch?v=jCqIr_tBLKs
