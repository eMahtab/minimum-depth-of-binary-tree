# Minimum Depth of Binary Tree
## https://leetcode.com/problems/minimum-depth-of-binary-tree/
Given a binary tree, find its minimum depth.

**The minimum depth is the number of nodes along the shortest path from the root node down to the nearest leaf node.**

**Note: A leaf is a node with no children.**
```
Example: Given binary tree [3,9,20,null,null,15,7],

    3
   / \
  9  20
    /  \
   15   7
return its minimum depth = 2.
```

## Implementation :

```java
 public int minDepth(TreeNode root) {
    if (root == null){
       return 0;
    }
    Queue<TreeNode> queue = new LinkedList<>();
    queue.add(root);
    int depth = 1;
    while (!queue.isEmpty()){
        int size = queue.size(); // number of nodes in that level
        for (int i = 0; i < size; i++){
            TreeNode node = queue.poll();
            if (node.left == null && node.right == null){
                return depth;
            }
            if (node.left!=null){
                queue.add(node.left);
            }
            if (node.right!=null){
                queue.add(node.right);
            }
        }
        depth ++;
    }  
  return depth;
}
```


