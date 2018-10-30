---
layout: post
title: Covert an array to Zig Zag pattern
categories:
 - data-structures
 - arrays
tags:
 - Arrays
 - Data Structures 
---

## Question 
Convert a given array into zig-zag pattern, where each even indexed number is greater than both the odd
indexed numbers.   
e.g given array is {1,2,3,4,5} so the output of the array should be {1,3,2,5,4}  
 

## Algorithm
To covert an array in zig-zag form following steps are required.
1. Traverse array from `0` to `n-1`  
2. For each element in array check  
    a. If index is even it should be smaller than the next element in array.  
    b. If index is odd it should be greater than the next element in array.

## Program
```java
package com.ekiras.ds.arrays;

public class ConvertToZigZag {

    public static void zigzag(int arr[]) {
        if(arr==null)
            return;
        for (int i = 0; i < arr.length - 1; i++) {
            boolean isEven = i%2==0;
            if (isEven && (arr[i] > arr[i + 1])) {
                swap(arr, i, i + 1);
            } else if (!isEven && (arr[i] < arr[i + 1])) {
                swap(arr, i, i + 1);
            }
        }
    }

    private static void swap(int arr[], int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
}
```

## Test Cases
```java
package com.ekiras.ds.arrays;

import org.junit.Assert;
import org.junit.Test;

public class ConvertToZigZagTest {

    @Test
    public void zigzag_arrayIsEmpty() {
        int arr[] = new int[]{};
        ConvertToZigZag.zigzag(arr);
        Assert.assertEquals(0, arr.length);
    }

    @Test
    public void zigzag_test1() {
        int arr[] = new int[]{4, 3, 7, 8, 6, 2, 1};
        ConvertToZigZag.zigzag(arr);
        Assert.assertEquals(7, arr.length);
        Assert.assertEquals(3, arr[0]);
        Assert.assertEquals(7, arr[1]);
        Assert.assertEquals(4, arr[2]);
        Assert.assertEquals(8, arr[3]);
        Assert.assertEquals(2, arr[4]);
        Assert.assertEquals(6, arr[5]);
        Assert.assertEquals(1, arr[6]);
    }

    @Test
    public void zigzag_test2() {
        int arr[] = new int[]{1,2,3,4,5};
        ConvertToZigZag.zigzag(arr);
        Assert.assertEquals(5, arr.length);
        Assert.assertEquals(1, arr[0]);
        Assert.assertEquals(3, arr[1]);
        Assert.assertEquals(2, arr[2]);
        Assert.assertEquals(5, arr[3]);
        Assert.assertEquals(4, arr[4]);
    }
}
```