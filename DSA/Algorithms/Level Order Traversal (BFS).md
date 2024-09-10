Traverse through all the nodes of a lower level before moving on to any of the nodes of the higher level.

This can be done in two ways:
- naïve way (finding height of tree then traversing each level and printing the nodes of that level)
- using a queue

## Queue

``` java
static int levelOrder(Node root)
    {
        Queue<Node> queue = new LinkedList<Node>();
        queue.add(root);

		int height = 0;
        
        while (!queue.isEmpty()) {
            // poll() dequeues/removes the present head.  
            Node curr = queue.poll();
            System.out.print(curr.data + " ");

            // Enqueue left child
            if (curr.left != null) {
                queue.add(curr.left);
            }

            // Enqueue right child
            if (curr.right != null) {
                queue.add(curr.right);
            }
            height++;
        }
    }
// output : 1 2 3 4 5
```