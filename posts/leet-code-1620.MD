---
title: "#1620 [最小的k个数]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","排序"]
draft: false
---

## 题目

````
输入整数数组 arr ，找出其中最小的 k 个数。例如，输入4、5、1、6、2、7、3、8这8个数字，则最小的4个数字是1、2、3、4。
````

## **示例**

````
输入：arr = [3,2,1], k = 2
输出：[1,2] 或者 [2,1]
````

## **限制**

````
0 <= k <= arr.length <= 10000
0 <= arr[i] <= 10000
````

## 思路

````
冒泡排序 或 选择排序 或 其他排序方式 k轮
````

## 实现

````go
func getLeastNumbers(arr []int, k int) []int {
    if arr == nil || len(arr) == 1{
        return arr
    }
    
    for i := 0; i < k; i++ {
        min := i
        for j := i+1; j < len(arr); j++ {
            if arr[min] > arr[j] {
                min = j
            }
        }
        if min != i {
            arr[i],arr[min] = arr[min],arr[i]
        }
    }
    return arr[:k]

}
````

