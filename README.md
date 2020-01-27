# Minimum Depth of Binary Tree
## https://leetcode.com/problems/minimum-depth-of-binary-tree/

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
        for (int i = 0; i< size; i++){
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


