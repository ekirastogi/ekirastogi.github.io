<h4>Tree Node</h4>

Following is the Treenode class that represent the Node in a Tree 
 
```java
package com.ekiras.ds.base;

public class TreeNode {

    public int data;
    public TreeNode left;
    public TreeNode right;

    public TreeNode(int data) {
        this.data=data;
    }

    @Override
    public String toString() {
        return "TreeNode{" +
                "data=" + data +
                ", left=" + left +
                ", right=" + right +
                '}';
    }
}

```