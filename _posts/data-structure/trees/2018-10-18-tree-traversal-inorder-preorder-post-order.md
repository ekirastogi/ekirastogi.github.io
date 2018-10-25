---
layout: post
title: Tree Traversal
categories: [data-structure, trees]
tags: [Trees, DataStructures, Traversal]
labels: [Trees, DataStructures, Traversal]
---

## Tree Traversal
A Tree can be traversed in the following standard ways
1. Pre Order 
2. In Order
3. Post Order

{% capture code%} {% include _treenode.md%} {% endcapture %}
{{code}}

### InOrder Traversal
Inorder traversal means that for every node,
1. First the left sub-tree of the node is traversed
2. then the root node is traversed
3. and at last the right node/ right sub-tree

```
                1
               / \
              2   3
            /  \   \
           4    5   6
```
For inorder traversal, we need to traverse the left sub tree first, so node `1`'s left sub-tree is traversed before node `1` itself. Node `2` is left of `1` and
similarly for node `2`, node `4` is the left node. So first node in traversal will be `4` then `2` and then node `5`. Now we have traversed the left sub tree
of the root node `1`, now we will print `1` and then traverse right sub tree of root node `1`.  

So the final output will be as follows  
```
4 2 5 1 3 6 
```

#### Program
```java
package com.ekiras.ds.trees.traversal;

import com.ekiras.ds.base.TreeNode;

public class InOrderTreeTraversal {

    public static void main(String[] args) {
        TreeNode node = new TreeNode(1);
        node.left = new TreeNode(2);
        node.left.left = new TreeNode(4);
        node.left.right = new TreeNode(5);
        node.right = new TreeNode(3);
        node.right.right = new TreeNode(6);

        inOrder(node);
    }

    private static void inOrder(TreeNode node)
    {
        if(node==null)
            return;
        System.out.print(node.data+" ");
        inOrder(node.left);
        inOrder(node.right);
    }
}
```

### PreOrder Traversal
PreOrder traversal means that for every node,
1. First the node itself is traversed
2. then the left sub-tree is traversed
3. and at last the right sub-tree is traversed

```
                1
               / \
              2   3
            /  \   \
           4    5   6
```
For the above tree, root node 1 is traversed first, then we go to the left child of the root node that is `2` then to the left node of `2` that is `4`.
Since `4` has no child nodes, we go back to node `2` and traverse its right node that is `5`. Now all the left nodes of root node have been traversed,
so we will now traverse right sub-tree of `1`. So the traversal of above tree will give the following output
```
1 2 4 5 3 6
```
#### Program
```java
package com.ekiras.ds.trees.traversal;

import com.ekiras.ds.base.TreeNode;

public class PreOrderTreeTraversal {

    public static void main(String[] args) {
        TreeNode node = new TreeNode(1);
        node.left = new TreeNode(2);
        node.left.left = new TreeNode(4);
        node.left.right = new TreeNode(5);
        node.right = new TreeNode(3);
        node.right.right = new TreeNode(6);

        preOrder(node);
    }

    private static void preOrder(TreeNode node)
    {
        if(node==null)
            return;
        preOrder(node.left);
        System.out.print(node.data+" ");
        preOrder(node.right);
    }

}
```

### PostOrder Traversal
PostOrder traversal means that for every node,
1. First the left sub-tree of the node is traversed
2. then the right sub-tree of the root is traversed
3. and at last the root node is traversed.

```
                1
               / \
              2   3
            /  \   \
           4    5   6
```
For the above tree, first the left sub tree of root node `1` is traversed, so we visit node `2`, then we visit left sub tree
of node `2` that is `4`. Since node `4` has no child nodes we print `4`. Now right sub-tree of node `2` is traversed that is 
`5`. After both left and right sub tree of node `2` is traversed we print node `2`. Now we traverse right sub tree of
node `1`, that is node `3`. Node `3` has no left child but has a right child so node `6` will be printed first and then
node `3` and finally node `1`. 
```
4 5 2 6 3 1 
```
#### Program
```java
package com.ekiras.ds.trees.traversal;

import com.ekiras.ds.base.TreeNode;

public class PostOrderTreeTraversal {

    public static void main(String[] args) {
        TreeNode node = new TreeNode(1);
        node.left = new TreeNode(2);
        node.left.left = new TreeNode(4);
        node.left.right = new TreeNode(5);
        node.right = new TreeNode(3);
        node.right.right = new TreeNode(6);

        postOrder(node);
    }

    private static void postOrder(TreeNode node)
    {
        if(node==null)
            return;
        postOrder(node.left);
        postOrder(node.right);
        System.out.print(node.data+" ");
    }
}
```