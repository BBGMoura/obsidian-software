## Recursion (DFS)
``` java
public int maxDepthRecursive(TreeNode root) {  
    if(root == null) {  
        return 0;  
    }  
    //find depth of left and right subtrees  
    int leftDepth = maxDepthRecursive(root.left);  
    int rightDepth = maxDepthRecursive(root.right);  
  
    // return larger  
    return Math.max(leftDepth, rightDepth) + 1;  
}
```

## Level Order Traversal (BFS)
``` Java
public int maxDepth(TreeNode root) {  
    if (root == null) return 0;  
  
    // initialise a queue to traverse the tree level by level  
    final Queue<TreeNode> queue = new LinkedList<>();  
    queue.add(root);  
  
    int height = 0;  
  
    // loop until queue is empty  
    while (!queue.isEmpty()) {  
        int size = queue.size();  
  
        // traverse all noses at current level  
        for (int i = 0; i < size; i++) {  
            TreeNode temp = queue.poll();  
  
            if (temp.left != null) queue.add(temp.left);  
            if (temp.right != null) queue.add(temp.right);  
        }  
        // increment height after traversing each level  
        height++;  
    }  
    return height;  
}
```