---
title: "#1595 [数组中重复的数字]"
date: 2020-06-7T12:28:04+08:00
tags : ["leet-code","算法","数组"]
draft: false
---

## 题目

````
找出数组中重复的数字。


在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。
````

## **示例**

````
输入：
[2, 3, 1, 0, 2, 5, 3]
输出：2 或 3 
````

## **限制**

````
2 <= n <= 100000
````

## 思路

````
遍历数组到map中
插入之后在查询其数量
如果数量 > 1 就返回
````

## 实现

````go
func findRepeatNumber(nums []int) int {
    numMap := make(map[int]int,len(nums))
    for _,num := range nums {
        numMap[num]++
        if numMap[num] > 1 {
            return num
        }
    }
    return -1
}
````
