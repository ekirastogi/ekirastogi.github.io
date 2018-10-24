---
layout: post
title: Finding the middle element of a List.
categories: [data-structure, lists]
tags: 
 - Lists
 - DataStructures
 - Traversal
 - Searching
---

# Find the Middle Element of a List

## Question

## Algorithm
1. If list is `null` return -1
2. If list has only 1 node, then return that
3. Assign another variable to point to same node, example `i`      
  a. Iterate the list till both next and next to next node of `i` is not null.   
  b. While iterating, assign `node` to `node.next` and `i` to `i.next.next`.  

## Program
```java
package com.ekiras.ds.lists;

import com.ekiras.ds.base.ListNode;

public class MiddleElement {

    public static void main(String[] args) {
        ListNode list = new ListNode(1);
        list.next = new ListNode(2);
        list.next.next = new ListNode(3);
        list.next.next.next = new ListNode(4);
        list.next.next.next.next = new ListNode(5);
        list.next.next.next.next.next = new ListNode(6);
    }

    public static int middleElement(ListNode node) {
        if (node == null)
            return -1;

        ListNode i = node;

        while (!(i.next == null || i.next.next == null)) {
            node = node.next;
            i = i.next.next;
        }
        return node.data;
    }

}

```
## Test Cases  
```java
package com.ekiras.ds.lists;

import com.ekiras.ds.base.ListNode;
import org.junit.Assert;
import org.junit.Test;

import static org.junit.Assert.*;

public class MiddleElementTest {

    @Test
    public void middleElement_whenNullIsPassed() {
        Assert.assertEquals(-1,MiddleElement.middleElement(null));

    }

    @Test
    public void middleElement_whenListWithOneNodeIsPassed() {
        ListNode list = new ListNode(1);
        Assert.assertEquals(1,MiddleElement.middleElement(list));

    }

    @Test
    public void middleElement_whenOddNumberOfElementsPassed() {
        ListNode list = new ListNode(1);
        list.next = new ListNode(2);
        list.next.next = new ListNode(3);
        list.next.next.next = new ListNode(4);
        list.next.next.next.next = new ListNode(5);
        assertEquals(3, MiddleElement.middleElement(list));
    }

    @Test
    public void middleElement_whenEvenNumberOfElementsPassed() {
        ListNode list = new ListNode(1);
        list.next = new ListNode(2);
        list.next.next = new ListNode(3);
        list.next.next.next = new ListNode(4);
        list.next.next.next.next = new ListNode(5);
        list.next.next.next.next = new ListNode(6);
        assertEquals(3, MiddleElement.middleElement(list));
    }
}
```