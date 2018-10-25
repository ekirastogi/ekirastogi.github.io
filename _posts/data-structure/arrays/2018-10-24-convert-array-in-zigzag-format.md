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

## Algorithm

## Program
```java
package com.ekiras.ds.arrays;

public class ConvertToZigZag {

    public static void main(String[] args) {
        int arr[] = new int[]{4, 3, 7, 8, 6, 2, 1};
        zigzag(arr);
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + "  ");
        }
    }

    public static void zigzag(int arr[]) {
        boolean odd = true;
        for (int i = 0; i < arr.length - 1; i++) {
            if (odd && (arr[i] > arr[i + 1])) {
                swap(arr, i, i + 1);
            } else if (!odd && (arr[i] < arr[i + 1])) {
                swap(arr, i, i + 1);
            }
            odd = !odd;
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