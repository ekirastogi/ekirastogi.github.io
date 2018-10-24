<h4>List Node</h4>
```java
package com.ekiras.ds.base;

public class ListNode {

    public int data;
    public ListNode next;

    public ListNode() {
    }

    public ListNode(int data) {
        this.data = data;
    }

    @Override
    public String toString() {
        return "ListNode{" +
                "data=" + data +
                '}';
    }
}

```