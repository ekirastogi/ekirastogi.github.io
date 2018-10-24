---
layout: post
title: Tree Traversal
categories: [data-structure, trees]
tags: [Trees, DataStructures, Traversal]
labels: [Trees, DataStructures, Traversal]
---

# Tree Traversal
A Tree can be traversed in the following standard ways
1. In Order 
2. Pre Order
3. Post Order

{% capture code%} {% include _treenode.md%} {% endcapture %}
{{code}}

## InOrder Traversal

```java
package com.ekiras.ds.trees.traversal;

import com.ekiras.ds.base.TreeNode;

public class InOrderTreeTraversal {

    public static void main(String[] args) {
        //         1
        //        / \
        //       2   3
        //     /  \   \
        //    4    5   6
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

## PreOrder Traversal
```java
package com.ekiras.ds.trees.traversal;

import com.ekiras.ds.base.TreeNode;

public class PreOrderTreeTraversal {

    public static void main(String[] args) {
        //         1
        //        / \
        //       2   3
        //     /  \   \
        //    4    5   6
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

## PostOrder Traversal
```java
package com.ekiras.ds.trees.traversal;

import com.ekiras.ds.base.TreeNode;

public class PostOrderTreeTraversal {

    public static void main(String[] args) {
        //         1
        //        / \
        //       2   3
        //     /  \   \
        //    4    5   6
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
        postOrder(node.right);
        postOrder(node.left);
        System.out.print(node.data+" ");
    }
}
```